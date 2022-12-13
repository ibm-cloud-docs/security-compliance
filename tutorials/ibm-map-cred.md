---

copyright:
  years: 2020, 2022
lastupdated: "2022-12-13"

keywords: ibm credentials, scc, security and compliance for ibm, compliance scan, {{site.data.keyword.cloud_notm}} resources

subcollection: security-compliance

content-type: tutorial
services: security-compliance, iam
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

# Part 3: Map additional credentials
{: #ibm-credential-map}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance"}
{: toc-completion-time="20m"}

This tutorial is part 3 of a 4-part tutorial series that guides you through configuring the {{site.data.keyword.compliance_short}} to scan your {{site.data.keyword.cloud_notm}} resources for compliance.

Some services require additional mapping in order for the collector to understand where to retrieve the data. Before you can map additional credentials, you must create a scope and run an initital discovery.

![The image shows the flow of user actions for this tutorial series](../images/credentials-tutorial.svg){: caption="Figure 1. Tutorial parts" caption-side="bottom"}



## Before you begin
{: #before-ibm-map}

To complete this tutorial, you must complete [part 2](/docs/security-compliance?topic=security-compliance-ibm-discover) first. 


## Configure {{site.data.keyword.openshiftshort}} permissions
{: #ibm-os}
{: step}

To enable scanning of your clusters, you must configure the OSCO integration, map additional information, and then configure your cluster through the CLI.

![This image is a visual representation of how to apply your credentials to specific resources in the GUI. The information that is shown in the image is detailed in the surrounding text.](../images/cluster-credential-map.svg){: caption="Figure 1. Mapping credentials through the UI" caption-side="bottom"}

When you configure your scope, you must **Enable integrated profiles** in order for the OSCO integration to work.
{: note}

1. Configure the OSCO integration.

   1. In the service navigation, click **Integrations**.
   2. In the **{{site.data.keyword.openshiftshort}} Compliance Operator** tile, click **Connect**. A side panel opens.
   3. Select a profile that you want to scan your clusters against.
   4. Click **Connect**. The connection is added to your list of integrations.

2. Map the credential.

   1. In [**Manage Posture > Configure > Scopes**](/security-compliance/scopes), select the scope that you want to map credentials for.
   2. In the **Credentials** section of the navigation, click **Add**. A side panel opens. 
   3. Select the credential that you assigned permissions to at the beginning of this tutorial.
   4. In the **Resource** field, provide your cluster ID in the format: `ROKS=cluster_id`.
   5. Click **Add**.

3. In your terminal, log into {{site.data.keyword.cloud_notm}} and configure your cluster by using the API key that you created at the beginning of this tutorial.

   1. Log in to the {{site.data.keyword.cloud_notm}} CLI by running the following command and then completing the prompts. If you have a federated ID, append the `--sso` option to the end of the command.

      ```sh
      ibmcloud login
      ```
      {: codeblock}

   2. Set the context for your cluster.

      ```sh
      ibmcloud os cluster config --cluster <CLUSTER_NAME_OR_ID>
      ```
      {: codeblock}
   
4. Repeat these steps as necessary until you have added all the clusters that you want to scan.


## Configure {{site.data.keyword.containershort}} permissions
{: #ibm-ks}
{: step}

To enable scanning of your clusters, you must map additional information and configure your cluster through the CLI.

1. Map the credential.

   1. In [**Manage Posture > Configure > Scopes**](/security-compliance/scopes), select the scope that you want to map credentials for.
   2. In the **Credentials** section of the navigation, click **Add**. A side appears. 
   3. Select the credential that you assigned permissions to at the beginning of this tutorial.
   4. In the **Resource** field, provide your cluster ID in the format: `cluster=cluster_id`.
   5. Click **Add**.

2. In your terminal, log into {{site.data.keyword.cloud_notm}} and configure your cluster by using the API key that you created at the beginning of this tutorial.

   1. Log in to the {{site.data.keyword.cloud_notm}} CLI by running the following command and then completing the prompts. If you have a federated ID, append the `--sso` option to the end of the command.

      ```sh
      ibmcloud login
      ```
      {: codeblock}

   2. Set the context for your cluster.

      ```sh
      ibmcloud ks cluster config --cluster <CLUSTER_NAME_OR_ID>
      ```
      {: codeblock}
   
3. Repeat these steps as necessary until you have added all the clusters that you want to scan.


## Configure Activity Tracker permissions
{: #ibm-at}
{: step}

If you enable a control that measures a specific number of days, it is monitored by using Activity Tracker. To ensure that the controls can be evaluated, you must create a new credential specific to Activity Tracker and then map the credentials to your scope.

1. Create a credential of type **Username / Password**.

   1. In the navigation, click [**Security and Compliance > Manage Posture > Configure > Credentials**](/security-compliance/credentials). Then, click **Create**.
   2. Give your credential a meaningful name and description.
   3. Select **Discovery/Collection** and click **Next**.
   4. Select **Username / Password**.
   5. For **Username** enter the Activity Tracker GUID for the instance that you want to use.
   6. For **Password** enter the service key.
   7. Click **Create**.

2. Map the credential.

   1. In the **Manage posture** section of the navigation, click [**Configure > Scopes**](/security-compliance/scopes).
   2. Select the scope that you want to map credentials for.
   3. In the **Credentials** section of the navigation, click **Add**. A side panel opens. 
   4. Select the credential that you created in step 1.
   5. In the **Resource** field, provide your Activity Tracker GUID in the format: `AT=resource_guid`.
   6. Click **Add**.

## Configure Virtual Private Cloud permissions
{: #ibm-vpc}
{: step}

To scan your Virtual Private Cloud's you must provide the name of the private cloud that you want to evaluate.

1. In [**Manage Posture > Configure > Scopes**](/security-compliance/scopes), select the scope that you want to map credentials for.
2. In the **Credentials** section of the navigation, click **Add**. A side panel opens. 
3. Select the credential that you assigned permissions to at the beginning of this tutorial.
4. In the **Resource** field, provide the name of your VPC in the format: `VPC=vpc-name`.
5. Click **Add**.



## Next steps
{: #next-3}

Next, you're ready to [complete part 4](/docs/security-compliance?topic=security-compliance-ibm-scan) by scanning all of your resources and viewing your results. 

