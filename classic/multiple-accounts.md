---

copyright:
  years: 2021, 2022
lastupdated: "2022-10-03"

keywords: monitor compliance, enterprise compliance, scan multiple accounts

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
{:release-note: data-hd-content-type='release-note'}



# Scanning multiple accounts from a single account

If you manage multiple {{site.data.keyword.cloud_notm}} accounts, you can configure the {{site.data.keyword.compliance_short}} to scan all your resources across cloud from a single account. To configure your account, use the following steps as a guide.

Before you get started, be sure to decide on a naming convention that will be easily understood by others in your organization. For example, when you create a collector, you might name it Account 1 – collector.
{: tip}

1. Create API keys in each account for the resources that you want to monitor for compliance. To understand which permissions to assign, see [Understanding required permissions](/docs/security-compliance?topic=security-compliance-permissions) or try walking through the [Monitoring IBM Cloud resources](/docs/security-compliance?topic=security-compliance-ibm-credential) tutorial series.
   
   To ensure that only specific resources are scanned, you can apply different access roles to your IAM keys. For example, you can enable your key to scan only the "Production" resource group and not the "Development" resource group.
   {: note}

2. Add the API keys that you created to {{site.data.keyword.compliance_short}} as [credentials](/docs/security-compliance?topic=security-compliance-credentials).
3. Create a customer-managed collector for each account or specific scope that you want to evaluate. You can create as many collectors as you need, but each collector should be associated with only a single scope. For help with your collector, see [Installing and activating a collector on VPC](/docs/security-compliance?topic=security-compliance-collector-vpc) or [on {{site.data.keyword.containershort}}](/docs/security-compliance?topic=security-compliance-collector-iks).
4. In the account that you want to use to manage your compliance, [create a new scope](/docs/security-compliance?topic=security-compliance-scopes) for each account that you want to monitor. Be sure to select **Validation** as your scan type when you schedule your initial scan.
   
   If you plan to scan your {{site.data.keyword.openshiftshort}} or {{site.data.keyword.containershort}} clusters, you must [configure the integration](/docs/security-compliance?topic=security-compliance-setup-osco) and then enable integrated profiles during scope creation.
   {: note}

5. To view aggregated results for all of your resources, navigate to the **Dashboard** in the {{site.data.keyword.compliance_short}} UI. To view more detailed results, go to **Validation results** and select the specific scope that you want to review.

