---

copyright:
  years: 2020, 2023
lastupdated: "2023-03-29"

keywords: collector install, vpc collector, monitor resources, security, compliance, cluster collector, Kubernetes, Red Hat {{site.data.keyword.openshiftshort}}

subcollection: security-compliance

content-type: tutorial
services: security-compliance, vpc
completion-time: 10m

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

# Install a customer-managed collector on a {{site.data.keyword.containershort}} cluster
{: #collector-iks}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, vpc"}
{: toc-completion-time="10m"}

In this tutorial, you learn how to use {{site.data.keyword.compliance_full}} to automate the compliance checks that your organization must complete.
{: shortdesc}



To scan and validate your resource configurations, a [collector](/docs/security-compliance?topic=security-compliance-collector) is used. Collectors act as an intermediary between your resources and the {{site.data.keyword.compliance_short}}, where the gathering and validation of your configurations is done. In this scenario, you are a developer who wants to validate your {{site.data.keyword.cloud_notm}} resources against defined best practices. Due to the security requirements of your organization, you are required to install the collector on infrastructure that is owned by your organization, so you decide to use an [{{site.data.keyword.cloud_notm}} {{site.data.keyword.containershort}}](/docs/containers?topic=containers-getting-started) or [{{site.data.keyword.openshiftshort}}](/docs/openshift?topic=openshift-getting-started) cluster. 

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

1. Go to the [**Manage posture > Configure > Collectors** tab](/security-compliance/collectors) and click **Create**.
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
    * If you are using a {{site.data.keyword.containershort}} cluster, run the following command.

        ```sh
        ibmcloud ks cluster config --cluster <CLUSTER_NAME_OR_ID>
        ```
        {: codeblock}

    * Run the following command if you are deploying your collector on an {{site.data.keyword.openshiftshort}} cluster to deploy your collector.

        ```sh
        ibmcloud oc cluster config --cluster <CLUSTER_NAME_OR_ID>
        ```
        {: codeblock}

4. Deploy your collector.

    * If you are deploying your collector on a {{site.data.keyword.containershort}} cluster, run the following command. 

        ```sh
        kubectl apply -f <deployment-testdocumentation>.yaml
        ```
        {: codeblock}

    * Run the following command if you are using an {{site.data.keyword.openshiftshort}} cluster.

        ```sh
        OC apply -f <deployment-testdocumentation>.yaml
        ```
        {: codeblock}

5. On the **Collectors** page of the {{site.data.keyword.compliance_short}} UI, click **Approval required** to approve the collector for use. Wait a few minutes and refresh the page. The collector status updates to **Active**.


## Next steps
{: #ibm-customer-collector-next}

When a scan completes, you can view the results as an overview in your dashboard, or in more detail by resource or by control. In all three options, you are presented with a compliance score so that you can view your compliance posture at a glance. To learn more about your score, see [Understanding your compliance score](/docs/security-compliance?topic=security-compliance-view-posture).


