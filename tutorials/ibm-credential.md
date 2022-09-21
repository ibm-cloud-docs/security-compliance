---

copyright:
  years: 2020, 2022
lastupdated: "2022-09-08"

keywords: ibm credentials, scc, security and compliance for ibm, compliance scan, {{site.data.keyword.cloud_notm}} resources

subcollection: security-compliance

content-type: tutorial
services: security-compliance
completion-time: 20m

---

{:codeblock: .codeblock}
{:screen: .screen}
{:download: .download}
{:external: target="_blank" .external}
{:faq: data-hd-content-type='faq'}
{:gif: data-image-type='gif'}
{:important: .important}
{:note: .note}
{:pre: .pre}
{:tip: .tip}
{:preview: .preview}
{:deprecated: .deprecated}
{:beta: .beta}
{:term: .term}
{:shortdesc: .shortdesc}
{:script: data-hd-video='script'}
{:support: data-reuse='support'}
{:table: .aria-labeledby="caption"}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:help: data-hd-content-type='help'}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tsSymptoms: .tsSymptoms}
{:java: .ph data-hd-programlang='java'}
{:javascript: .ph data-hd-programlang='javascript'}
{:swift: .ph data-hd-programlang='swift'}
{:curl: .ph data-hd-programlang='curl'}
{:video: .video}
{:step: data-tutorial-type='step'}
{:tutorial: data-hd-content-type='tutorial'}
{:ui: .ph data-hd-interface='ui'}
{:cli: .ph data-hd-interface='cli'}
{:api: .ph data-hd-interface='api'}
{:release-note: data-hd-content-type='release-note'}

# Part 1: Manage permissions for {{site.data.keyword.cloud_notm}} credentials
{: #ibm-credential}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance"}
{: toc-completion-time="20m"}

This tutorial is part 1 of a 4-part tutorial series that guides you through configuring the {{site.data.keyword.compliance_short}} to scan your {{site.data.keyword.cloud_notm}} resources for compliance.

With the {{site.data.keyword.compliance_short}}, you can automatically evaluate your resource configurations for compliance every day, which can help to ensure the security of your organization. To scan your resources, you must first provide the {{site.data.keyword.compliance_short}} permission to view the configuration data of the resources that you want to scan.

![The image shows the flow of user actions for this tutorial series](../images/credentials-tutorial.svg){: caption="Figure 1. Tutorial parts" caption-side="bottom"}


## Before you begin
{: #before-ibm-credential}

To complete this tutorial, be sure that you have a Pay-As-You-Go or Subscription [{{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started) where you are the owner or have [full **Administrator** access](/docs/account?topic=account-assign-access-resources).

You must also have resources in your account that you are able to scan.

To learn more about how your credentials are stored, see Storing and encrypting data in the [{{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).
{: note}

## Create a service ID and assign IAM policies
{: #ibm-service-id-policies}
{: step}

The first step that the {{site.data.keyword.compliance_short}} takes in evaluating your resources for compliance is to gather configuration data. To gather the data, otherwise known as "collecting facts", a service ID API key is used by [a collector](/docs/security-compliance?topic=security-compliance-collector). The collector requires *Viewer* access to gather the configuration data for most services. In this step, you create a service ID and assign the permissions that most services require. 

1. Go to **Manage > Access (IAM) > Service IDs** and click **Create**.
2. Provide a **Name** and **Description**.
3. Click **Create**.
4. Click **Access policies > Assign access**. **Access policy** is automatically selected in the screen that loads.
5. Assign access to the {{site.data.keyword.compliance_short}} and Security and Compliance Integrations.
   1. From the table, select the **{{site.data.keyword.compliance_short}}** and click **Next**.
   2. Leave **All resources** and click **Next**.
   3. Select **Manager** and **Administrator**. Then, click **Review** to validate your choices.
   4. Click **Add**.
   5. Repeat step 5, but select Security and Compliance Integrations instead of {{site.data.keyword.compliance_short}}.
6. Assign access to all Identity and Access enabled services.
   1. From the table, select **Identity and Access enabled services** and click **Next**.
   2. Scope your access to the resources that you want to scan and then click **Next**.
   3. Select **Viewer** for **Resource group access** and click **Next**.
   4. In **Roles and actions**, select **Viewer**. Then, click **Review** to validate your choices.
   4. Click **Add**.
7. Assign access to all Account management services.
   1. From the table, select **Account Management services** and click **Next**.
   2. In **Roles and actions**, select **Viewer**. Then, click **Review** to validate your choices.
   3. Click **Add**.
8. Occasionally, services require additional permissions for the scan to complete. By using the following steps and table, assign the additional-required permissions. 

   1. From the following table, select a service and click **Next**.
   2. In the **Roles and actions** section, select the specified permissions that are required.
   3. Click **Add**. 
   
   | Service | Additional permission |
   |---------|---------------|
   | Activity Tracker Event Routing | Operator |
   | App ID | Reader |
   | Certificate Manager | Reader |
   | Cloud Catalog | Publisher |
   | Cloud Shell | Cloud Operator |
   | Cloud Object Storage | Reader and Writer |
   | Databases  \n * etcd  \n * ElasticSearch  \n * MongoDB  \n * PostgreSQL  \n * Redis| Operator |
   | Event streams | Reader |
   | Hyper Protect Crypto Services | Operator and Manager |
   | Key Protect | ReaderPlus, Manager and Editor |
   | Kubernetes Service | Reader |
   | OpenShift | Reader |
   | Satellite | Operator and Writer |
   | Secrets Manager | Reader |
   | Virtual Private Cloud  \n * Application Load Balancer  \n * Block Storage  \n * Block Storage Snapshots  \n * File Storage  \n * Security Groups | Reader |
   {: caption="Table 1. Additional required permissions" caption-side="top"}

9. Click **Assign**.


## Create a service ID API key
{: #ibm-create-key}
{: step}

To ensure that the {{site.data.keyword.compliance_short}} can access your resources, you provide an API key for the service ID that you assigned permissions to.

1. Go to **Manage > Access (IAM) > Service IDs** and select the service ID that you created in the previous step. 
2. Click **API keys**. Then, click **Create**.
3. Provide a name and detailed description. Then, click **Create**.
4. **Copy** and **Download** your API key. 

   To prevent your key from being deleted, you can [lock it](/docs/account?topic=account-serviceidapikeys#lockkey). But, you need to unlock it to create or update and policy that is associated with the key.
   {: tip}


## Create a user API key
{: #ibm-user-id}
{: step}

If you're working with Classic Infrastructure or the Continuous Delivery service, the provided credential must be a user API key. If only a service ID is provided, the scan will not complete.


1. Go to **Manage > Access (IAM) > Users** and select the user that you want to use.
1. Click **Access policies > Assign access**.
2. Assign access to Continuous Delivery.
   1. From the table, select Continuous Delivery and click **Next**.
   2. Select the resources that you want to scan and click **Next**.
   3. Select **Viewer**. Then, click **Review** to validate your choices.
   4. Click **Add**.
   5. Repeat step 2, but select **Classic Infratructure**.
3. Generate an API Key.
   1. In the user profile where you assigned access, click **API keys**. 
   2. Click **Create**.
   3. Provide a name and detailed description. Then, click **Create**.
   4. **Copy** and **Download** your API key. 



## Add your credentials to the {{site.data.keyword.compliance_short}}
{: #ibm-create-add-cred}
{: step}

1. In the navigation, click [**Security and Compliance > Manage Posture > Configure > Credentials**](/security-compliance/credentials). Then, click **Create**.
2. Give your credential a meaningful name and description.
3. Select **Discovery/Collection** and click **Next**.
4. Select **{{site.data.keyword.cloud_notm}}**.
5. Paste the API key that you created into the **IBM API key** field and then click **Create**. Your IAM key is added to a list of available credentials.
6. Repeat this process for the user API key.



## Next steps
{: #next-1}

Next, you're ready to discover the resources in your account that are available to evaluate in [part 2](/docs/security-compliance?topic=security-compliance-ibm-discover).

