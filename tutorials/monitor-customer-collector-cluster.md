---

copyright:
  years: 2021
lastupdated: "2021-12-16"

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


## Creating a collector
{: #ibm-customer-collector-cluster-create}
{: step}

A collector is a container image that you install on your Virtual Private Cloud. The collector image is responsible for gathering your configuration information and validating it.

1. Go to the **Manage posture > Configure > Collectors** tab and click **Create**.
2. Give your collector a meaningful name and description. For example, `ibm-cloud-collector`. 
3. Click **Next**.
4. Select **Customer** to install the collector on your organization's infrastructure.
5. **UBI** is selected as the default container **image type**.

   Universal Base Images (UBI) are OCI-compliant container-based operating system images. They cannot be used with Windows OS.

6. Alternatively, you can choose **Ubuntu**.

   Ubuntu images are disk-images that are designed to run on the Ubuntu OS. Ubuntu images are not compliant with the Federal Information Processing Standards (FIPS).

7. For **Endpoint type**, select **Public**.  To allow the collector to use a private IP that is accessible only through the IBM Cloud private network, choose **Private**. 
8. Click **Create**.


## Installing a collector
{: #customer-collector-install-cluster}
{: step}

Complete the following steps to install a collector on a cluster.

1. On the **Download collector** panel that appears after you create a collector, select **Download YAML file**, and then click **Download**. The registration key is included in the file.
2. Log in to the IBM Cloud CLI by running the following command and then following the prompts. If you have a federated ID, append the `--sso` option to the end of the command.
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

To run the scan, the collector must have *read* access to the resources that you want to scan. This access is granted through an {{site.data.keyword.cloud_notm}} API key. For more information about the security of your credentials, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).

1. Create an {{site.data.keyword.cloud_notm}} API key.

   1. Go to **Manage > Access (IAM) > API keys**.
   2. Click **Create an {{site.data.keyword.cloud_notm}} API key**.
   3. Give your API key a meaningful name and description. For example, `compliance-api-key` and this key is used by the collector to validate my resource configurations.
   4. Click **Create**.
   5. Click **Copy** or **Download** to save your key.

2. Add the API key to the {{site.data.keyword.compliance_short}} as a credential.

   1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and compliance** to return to the {{site.data.keyword.compliance_short}}.
   2. In the navigation, click **Manage posture > Configure > Credentials**.
   3. Click **Create**.
   4. Give your credential a meaningful name. For example, `ibm-cloud-compliance`.
   5. Select **Discovery / fact collection** as the purpose of the credential and then click **Next**.
   6. Select **{{site.data.keyword.cloud_notm}}** as the type of credential.
   7. Paste the API key that you created in the previous step and click **Create**.

## Target your resources
{: #ibm-customer-collector-scope}
{: step}

To target the resources that you want your collector to validate, you create a scope. To do so, you select an environment, a collector, and a set of credentials. The collector uses the credentials to gather information from the resources that are available in the environment that you selected. 


1. Go to the **Manage posture > Configure > Scopes** tab and click **Create**.
2. Give your scope a meaningful name. For example, `ibm-cloud-compliance`.
3. Click **Next**.
4. From the **Environment** dropdown, select **{{site.data.keyword.cloud_notm}}**.
5. From the **Credentials** dropdown, select the credential that you previously added. Then, click **Next**.
6. From the table, select the **Collector** that you previously installed. Then, click **Next**.
7. Review your choices and click **Create**.

After you create the scope, a discovery scan is run to inventory your available resources.


## Validate your configurations
{: #ibm-customer-collector-scan}
{: step}

When your resources and their configurations are discovered, you're ready to validate the configurations. To validate your configurations, you schedule a scan. To do so, you select the scope that you created and choose a profile to validate it against. A profile is a collection of compliance goals and best practices are predefined by {{site.data.keyword.cloud_notm}} or external regulators.


1. Go to the **Manage posture > Assess > Scans > Scheduled scans** tab and click **Schedule**.
2. Give your scan a meaningful name. For example, `ibm-cloud-scan-daily`.
3. For **Scan type**, select **Validation**.
4. From the **Scope** dropdown, select the scope that you previously created.
5. From the **Profile** dropdown, select the **{{site.data.keyword.cloud_notm}} Best Practices Controls 1.0**.
6. Click **Next**.
7. Select the frequency that you want your scan to run. It is automatically set to 1 day.
8. Specify when you want the scan end. The scan can run daily indefinitely, a specific number of times, or it can stop on a specific date.
9. Click **Create**.


## Next steps
{: #ibm-customer-collector-next}

When a scan completes, you can view the results as an overview in your dashboard, or in more detail by resource or by control. In all three options, you are presented with a compliance score so that you can view your compliance posture at a glance. To learn more about your score, see [Understanding your compliance score](/docs/security-compliance?topic=security-compliance-view-posture#understand-scores).




