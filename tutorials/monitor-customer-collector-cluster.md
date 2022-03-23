---

copyright:
  years: 2020, 2022
lastupdated: "2022-03-23"

keywords: collector install, vpc collector, monitor resources, security, compliance, cluster collector, Kubernetes, Red Hat OpenShift

subcollection: security-compliance

content-type: tutorial
services: security-compliance, vpc
completion-time: 15m

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

# Monitor {{site.data.keyword.cloud_notm}} resources with a customer-managed collector on a cluster
{: #ibm-customer-collector-cluster}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, vpc"}
{: toc-completion-time="15m"}

In this tutorial, you learn how to use {{site.data.keyword.compliance_full}} to automate the compliance checks that your organization must complete.
{: shortdesc}

To scan and validate your resource configurations, a [collector](/docs/security-compliance?topic=security-compliance-collector) is used. Collectors act as an intermediary between your resources and the {{site.data.keyword.compliance_short}}, where the gathering and validation of your configurations is done. In this scenario, you are a developer who wants to validate your {{site.data.keyword.cloud_notm}} resources against defined best practices. Due to the security requirements of your organization, you are required to install the collector on infrastructure that is owned by your organization. You decide to use an [{{site.data.keyword.cloud_notm}} {{site.data.keyword.containershort}}](/docs/containers?topic=containers-cs_cluster_tutorial) or [Red Hat OpenShift on {{site.data.keyword.cloud_notm}}](/docs/openshift?topic=openshift-openshift_tutorial) cluster. 

This tutorial must be completed within 24 hours or the collector registration key expires.
{: note}

## Before you begin
{: #ibm-customer-collector-cluster-before}

To complete this tutorial, be sure that you have the following requirements:

* A Pay-As-You-Go or Subscription [{{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started) where you are the owner or have [full **Administrator** access](/docs/account?topic=account-assign-access-resources)
* Docker
* Resources in your {{site.data.keyword.cloud_notm}} account


## Create a collector
{: #ibm-customer-collector-cluster-create}
{: step}

A collector is a container image that you install on your Virtual Private Cloud. The collector image is responsible for gathering your configuration information and validating it.

1. Go to the [**Manage posture > Configure > Collectors** tab](https://{DomainName}/security-compliance/collectors) and click **Create**.
2. Give your collector a meaningful name and description. For example, `ibm-cloud-collector`. 
3. Click **Next**.
4. Select **Customer** to install the collector on your organization's infrastructure.
5. **UBI** is selected as the default container **image type**.

   Universal Base Images (UBI) are OCI-compliant container-based operating system images. They cannot be used with Windows OS.

6. Alternatively, you can choose **Ubuntu**.

   Ubuntu images are disk-images that are designed to run on the Ubuntu OS. Ubuntu images are not compliant with the Federal Information Processing Standards (FIPS).

7. For **Endpoint type**, select **Public**.  To allow the collector to use a private IP that is accessible only through the IBM Cloud private network, choose **Private**. 
8. Click **Create**.


## Install a collector
{: #customer-collector-install-cluster}
{: step}

Complete the following steps to install a collector on a cluster.

1. On the **Download collector** panel that appears after you create a collector, select **Download YAML file**, and then click **Download**. The registration key is included in the file.
2. Log in to the {{site.data.keyword.cloud_notm}} CLI by running the following command and then following the prompts. If you have a federated ID, append the `--sso` option to the end of the command.
    ```sh
    ibmcloud login
    ```
    {: codeblock}

3. Set the context for your cluster.
    * If you are using a Kubernetes Service cluster, run the following command.

        ```sh
        ibmcloud ks cluster config --cluster <cluster_name_or_ID>
        ```
        {: codeblock}

    * Run the following command if you are deploying your collector on an OpenShift cluster to deploy your collector.

        ```sh
        ibmcloud oc cluster config --cluster <cluster_name_or_ID>
        ```
        {: codeblock}

4. Deploy your collector.

    * If you are deploying your collector on a Kubernetes Service cluster, run the following command. 

        ```sh
        kubectl apply -f <deployment-testdocumentation>.yaml
        ```
        {: codeblock}

    * Run the following command if you are using an OpenShift cluster.

        ```sh
        OC apply -f <deployment-testdocumentation>.yaml
        ```
        {: codeblock}

5. On the **Collectors** page of the {{site.data.keyword.compliance_short}} UI, click **Approval required** to approve the collector for use. Wait a few minutes and refresh the page. The collector status updates to **Active**.

## Grant your collector access to your resources
{: #ibm-customer-collector-access}
{: step}

To validate your resources, a collector must have *read* access to the resources that you want to scan. This access is granted through an {{site.data.keyword.cloud_notm}} API key. For more information about the security of your credentials, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).

1. Create an {{site.data.keyword.cloud_notm}} API key for a service ID.

   1. Go to [**Manage > Access (IAM) > Service IDs**](https://{DomainName}/iam/serviceids/). If you don't already have a service ID that you want to use, click **Create** and provide a name and description. Click **Create** again.
   2. Select the service ID that you want to use and click **API keys**.
   3. Click **Create** and give your API key a meaningful name and description. For example, `compliance-api-key` and this key is used by the collector to validate my resource configurations. Click **Create**.
   4. Click **Copy** or **Download** to save your key.

2. Add the API key to the {{site.data.keyword.compliance_short}} as a credential.

   1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and compliance** to return to the {{site.data.keyword.compliance_short}}.
   2. In the navigation, click [**Manage posture > Configure > Credentials**](https://{DomainName}/security-compliance/credentials).
   3. Click **Create**.
   4. Give your credential a meaningful name. For example, `ibm-cloud-compliance`.
   5. Select **Discovery / fact collection** as the purpose of the credential and then click **Next**.
   6. Select **{{site.data.keyword.cloud_notm}}** as the type of credential.
   7. Paste the API key that you created in the previous step and click **Create**.

## Target your resources and validate your configurations
{: #ibm-customer-collector-scope}
{: step}

Target the resources that you want to validate by creating a scope and scheduling a scan. To create a scope, select an environment, select your collector, and select the credentials that are required to access your targeted resources. Then, you can schedule a scan to discover and validate your resource configurations.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In **Manage Posture > Configure > Scopes**, click **Create**.
3. Give your scope a name and description and then click **Next**.

   Be sure to give a detailed name as you use this field later to configure scans and remediation.
4. Select an **Evironment** from the drop-down list.

   If you choose On-premises, you can select from multiple options to discover your resources. For example, you can [schedule a discovery scan](/docs/security-compliance?topic=security-compliance-schedule-scan), import resources from a file, or connect to a third party. Supported format for imported files is  `.json`. Max file size is 30 MB.
5. From the **Credentials** drop-down, select a credential that you previously added to the service and then click **Next**.

   If you have not yet added a credential, you can use the following steps to add one and then select it from the drop-down.

   1. Click **Create**. A side panel opens.
   2. Provide a name and description.
   3. Select a **Purpose** and then click **Next**.
   4. Select a **Credential type**.
   5. Provide the information that is requested. For more information about each type of secret, see [Understanding credentials](/docs/security-compliance?topic=security-compliance-permissions#understand-credentials).
   6. Click **Create**.
   7. Repeat step 5.

6. From the table, select the [collector](/docs/security-compliance?topic=security-compliance-collector) or collectors that you want to use to gather configuration data and then click **Next**.
8. Create an attachment between your scope and profile by scheduling a scan. 

   1. Give your scan a name and description.
   2. Select a **Scan type**.
   3. From the **Profile** drop-down, select the profile that you want to use to evaluate your configuration.
   4. **Enable** or **Disable** the profiles that are associated with your integrated resources. For more information about integrations see the [integrations tab of the UI](/security-compliance/integrations){: external}.
   4. If applicable: Select a remediation type.

      Only some environments are configured to provide automatic remediation. For more information, see [Remediating issues](/docs/security-compliance?topic=security-compliance-remediation).

   5. The scan will automatically occur when the scope is created. To schedule additional scans select the **Frequency** at which you want them to be run and the date when you want the scan to **End**.

9. Click **Next** and review your selections.
10. Click **Create**. 



## Next steps
{: #ibm-customer-collector-next}

When a scan completes, you can view the results as an overview in your dashboard, or in more detail by resource or by control. In all three options, you are presented with a compliance score so that you can view your compliance posture at a glance. To learn more about your score, see [Understanding your compliance score](/docs/security-compliance?topic=security-compliance-view-posture#understand-scores).




