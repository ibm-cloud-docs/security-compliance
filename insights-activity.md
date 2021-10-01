---

copyright:
  years: 2017, 2021
lastupdated: "2021-09-27"

keywords: Centralized security, security management, alerts, security risk, insights, threat detection

subcollection: security-compliance

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


# Enabling Activity Insights
{: #setup-activity}

With Security Insights, formerly known as {{site.data.keyword.security-advisor_long}}, you can continuously analyze your activity logs with predefined rule packages that can help you to identify unauthorized or suspicious behavior in your {{site.data.keyword.cloud_notm}} resources or applications. The predefined rule packages are based on security monitoring best practices for specific {{site.data.keyword.cloud_notm}} services.
{: shortdesc}

Activity Insights is available for {{site.data.keyword.containershort}} clusters on classic infrastructure only.
{: important}


## Before you begin
{: #activity-prereq}

Before you get started, be sure that you have the required level of access to view and manage Activity Insights. To manage Activity Insights, you must have the [**Writer** service role or higher for {{site.data.keyword.security-advisor_short}}](/docs/security-compliance?topic=security-compliance-access-management). 

You must also have the following prerequisites:

- A standard Kubernetes cluster version v1.10.11 or higher
- The [`yq` CLI](https://mikefarah.gitbook.io/yq/){: external}
- Updated cURL binary
   For CentOS and Red Hat, you can update by running `yum update -y nss curl libcurl`
- The [{{site.data.keyword.cloud_notm}} CLI and required plug-ins](/docs/cli/reference/ibmcloud?topic=cli-install-ibmcloud-cli)
- The [Kubernetes CLI](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: external} v1.10.11 or higher
- The [Kubernetes Helm (package manager)](/docs/containers?topic=containers-helm) v2.9.0 or higher.

If you are working on Windows 10, activate [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10){: external}
{: note}

## Connecting to Cloud Object Storage
{: #activity-store-data}

Before you can analyze your user and application activity, {{site.data.keyword.security-advisor_short}} must have access to your activity flow logs that are stored in Cloud Object Storage. To create the connection between the services, you must store the logs in a Cloud Object Storage bucket and then grant the service access to the bucket.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance**.
2. On the **Gain insight > Configure > Built-in Insights** page, click **Connect**.
3. Select a resource group, an instance of Cloud Object Storage, and a bucket.
4. Optionally, provide a description.
5. Click **Connect bucket**.
6. Create a *reader* [service-to-service authorization policy](https://{DomainName}/iam/authorizations) between Cloud Object Storage and {{site.data.keyword.security-advisor_short}}.


## Collecting activity flow logs
{: #collect-activity-logs}

To collect the activity flow logs from your {{site.data.keyword.cloud_notm}} account and store them in Cloud Object Storage, you must install an agent on your Kubernetes Service cluster.

1. Clone the [Activity Insights repository](https://github.com/ibm-cloud-security/security-advisor-activity-insights){: external} to your local system.

   ```sh
   git clone https://github.com/ibm-cloud-security/security-advisor-activity-insights.git
   ```
   {: codeblock}

2. Change into the `security-advisor-activity-insights` folder.
3. Change into the directory for the version of the chart that you're using. Currently, version `v3.0` is supported.
4. Extract the `.tar` file by running the following command.

   ```sh
   tar -xvf security-advisor-activity-insights.tar
   ```
   {: codeblock}

5. Change into `security-advisor-activity-insights` folder.
6. Log in to the {{site.data.keyword.cloud_notm}} CLI. Follow the prompts in the CLI to finish logging in.

   ```sh
   ibmcloud login -a cloud.ibm.com -r <region>
   ```
   {: codeblock}

   | Region | Endpoint |
   | --------- | ----------- |
   | United Kingdom | `eu-gb` |
   | US South | `us-south` |
   {: caption="Table 1. {{site.data.keyword.cloud_notm}} Endpoints by region" caption-side="top"}

7. Set the context for your cluster.

   ```sh
   ibmcloud ks cluster config --cluster <cluster_name_or_ID>
   ```
   {: codeblock}

8. Run the following command to install the agent. The command validates the naming convention of your bucket, creates Kubernetes secrets, updates the value with your cluster GUID, and deploys Activity Insights.

   ```sh
   ./activity-insight-install.sh -c <cos_region> -k <cos_api_key> -b <cos_bucket> -a <at_region> -s <at_service_api_key> -m <default_memory_request> -l <memory_limit> -n <namespace>
   ```
   {: codeblock}

   If you encounter an error, try running `helm init --upgrade`.
   {: tip}

   | Variable | Description |
   | --------- | ----------- |
   | cos_region | The region where your COS instance is deployed. Options include: `us-south` and `eu-gb`. |
   | cos_api_key | The [API key](/docs/cloud-object-storage/iam?topic=cloud-object-storage-service-credentials) that you created to access your COS instance and bucket. The key must have the platform role `writer`. |
   | cos_bucket | The name of the bucket that you created in Cloud Object Storage to use with Activity Insights. |
   | at_region | The region of the [{{site.data.keyword.at_short}}](/docs/activity-tracker?topic=activity-tracker-regions) instance. Example: `us-south`. |
   | at_service_api_key | Is an IAM service API key for your {{site.data.keyword.at_short}} instance. |
   | default_memory_request | The default memory that is requested when the pod is created during installation. If not provided, the default is `256Mi`. |
   | memory_limit | The maximum amount of memory that is provided to the pod by the cluster. If not provided, the default is `512Mi`. |
   | namespace | The Kubernetes namespace to install activity-insights-chart. Default: `security-advisor-activity-insights`. |
   {: caption="Table 2. Install command components explained" caption-side="top"}
  


## Enabling analysis
{: #enable-analysis-activity}

Now that you've installed the collector agent and verified that your flow logs are being stored in your Cloud Object Storage bucket, you can enable Activity Insights to start analyzing them.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance > Integrations > Built-in insights**.
2. Toggle Activity Insights to **On**.

As results come in, you can see any flagged issues on the **Insights** or **Detailed findings** pages of the UI.



## Uninstalling Activity Insights
{: #activity-delete}

If you no longer need to use Activity Insights, you can delete the agent and other service components from your cluster.

1. Delete the service components by using Helm. Be sure to use the `-tls` flag if you have TLS enabled.

   If you installed version 2 of the chart, use the following command to delete the components.

      ```sh
      helm del --purge activity-insights [--tls]
      ```
      {: codeblock}

   If you installed version 3 of the chart, use the following command to delete the components.

      ```sh
      helm uninstall activity-insights --namespace <namespace>
      ```
      {: codeblock}

2. To clean up your cluster, run the following command.

   ```sh
   kubectl delete ns <namespace>
   ```
   {: codeblock}

