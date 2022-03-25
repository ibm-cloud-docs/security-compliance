---

copyright:
  years: 2020, 2022
lastupdated: "2022-03-25"

keywords: Satellite, Scan resources, ROKS, OpenShift Compliance

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

# Scan {{site.data.keyword.cloud_notm}} resources that run on {{site.data.keyword.satelliteshort}}
{: #scan-sat-compliance}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, satellite"}
{: toc-completion-time="30m"}

In this tutorial, you learn how to use {{site.data.keyword.compliance_full}} to automate the compliance checks that your organization must complete for {{site.data.keyword.openshiftshort}} clusters that run in {[sat-long]} locations.
{: shortdesc}

SG: Would be nice if we could provide a scenario / use case / technical information here.
{: important}


## Before you begin
{: #scan-sat-before}

To complete this tutorial, be sure that you have the following requirements:

* A Pay-As-You-Go or Subscription [{{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started) where you are the owner or have [full **Administrator** access](/docs/account?topic=account-assign-access-resources).
* A {{site.data.keyword.satelliteshort}} location in which {{site.data.keyword.openshiftshort}} clusters are already deployed. If you need help setting up your location, check out [Getting started with {{site.data.keyword.satelliteshort}}](/docs/satellite?topic=satellite-getting-started).


## Set up the {{site.data.keyword.compliance_short}}
{: #scan-sat-service-setup}
{: step}

To validate your resources, a collector is used to gather the configuration information of your resources. To collect the information, the collector must have the required permissions to access the resources. For more information about the security of your credentials, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).

### Create a collector
{: #create-collector-sat}

SG: Insert image

1. In the {{site.data.keyword.compliance_short}}, go to [**Manage Posture > Configure > Collectors**](/security-compliance/collectors){: external}, and click **Create**.
2. Give your collector a name and description.
3. Click **Next**.

   If you have a passphrase enabled, you must enter it in the **Existing passphrase** field before you can move forward. Be sure to enter the passphrase exactly.

4. Determine whether you would like to manage your collector or if you want to allow IBM to manage it on your behalf.
5. Select the type of image that you want to use.
6. Select whether to use a **Private** or **Public** endpoint and then click **Create**.

   If you use a Private endpoint, you must also configure a Satellite Link in order for the collector to access your data.
   {: note}

   SG: Need more information here about why and how to configure the link.
   {: important}

### Give permission
{: #credential-sat}

Add a [credential](/iam/serviceids/){: external} that has *Read* access to the resources that you want to scan.

   1. In the {{site.data.keyword.compliance_short}}, go to [**Manage posture > Configure > Credentials**](/security-compliance/credentials){: external} and click **Create**.
   2. Give your credential a meaningful name.
   3. Select **Discovery / fact collection** as the purpose of the credential and click **Next**.
   4. Select **{{site.data.keyword.cloud_notm}}** as the type of credential.
   5. Paste the API key that you created in the previous step and click **Create**.


## Target and discover your resources
{: #scan-sat-scan}
{: step}

Target the resources that you want to validate by creating a scope and scheduling a scan. To create a scope, select an environment, select your collector, and select the credentials that are required to access your targeted resources. Then, you can schedule a scan to discover and validate your resource configurations.

1. In the {{site.data.keyword.compliance_short}}, go to [**Manage Posture > Configure > Scopes**](/security-compliance/scopes){: external}, click **Create**.
2. Give your scope a name and description and click **Next**.
3. From the **Evironment** drop-down, select **{{site.data.keyword.cloud_notm}}**.
4. From the **Credentials** drop-down, select a credential that you previously added to the service and click **Next**.
5. From the table, select the [collector](/docs/security-compliance?topic=security-compliance-collector) or collectors that you want to use to gather configuration data and click **Next**.
6. Create an attachment between your scope and profile by scheduling a scan. 

   1. Give your scan a name and description.
   2. Select a **Scan type**.
   3. From the **Profile** drop-down, select the profile that you want to use to evaluate your configuration.
   4. **Enable** the profiles that are associated with the [OSCO integration](/security-compliance/integrations){: external}.
   5. By default, the scan starts when your scope is created and continues to run once per day. If you need the scan to be run more or less often, you can change the **Frequency**.
   6. Click **Next**.

7. Review your selections and click **Create**. 


## Map your cluster to your credentials
{: #scan-sat-service-map}
{: step}

When you add a credential to the service, the collector uses it to gather configuration data for all of the resources that the credential has permission to access. For [some resources](/docs/security-compliance?topic=security-compliance-credential-mapping), like a cluster, you must create a mapping that tells the collector where to apply the credential and look for the information.


![This image is a visual representation of how to apply your credentials to specific resources in the GUI. The information that is shown in the image is detailed in the surrounding text.](../images/cluster-credential-map.svg){: caption="Figure 1. Mapping credentials through the UI" caption-side="bottom"}


1. In the {{site.data.keyword.compliance_short}}, go to [**Manage Posture > Configure > Scopes**](/security-compliance/scopes){: external} and select the scope that you previously created. A **Settings** page opens. In the **Credentials** section of the page, click **Add**.
2. In the side panel, select the **Credential** that you previously added.
3. Provide the cluster ID `cluster=cluster_id` for the {{site.data.keyword.openshiftshort}} cluster that you want to scan.
4. Optionally, you can also provide a **Namespace** and **Storage class**. Then, click **Add**.


## View results
{: #scan-sat-service-setup}
{: step}

After the scan is finished running, you can return to the UI to view your results.

![This image is a visual representation of how to apply your credentials to specific resources in the GUI. The information that is shown in the image is detailed in the surrounding text.](../images/scan-results-ui.svg){: caption="Figure 2. Viewing your validation results in the UI" caption-side="bottom"}


