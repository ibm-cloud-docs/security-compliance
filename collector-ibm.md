---

copyright:
  years: 2021
lastupdated: "2021-07-29"

keywords: collector, security and compliance, security, compliance, install, resource monitoring, configuration monitoring, security, approve collector, register collector, use credentials, ibm managed collector, ibm managed

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


# Configuring managed collectors
{: #ibm-collector}

For the {{site.data.keyword.compliance_full}} to gather and validate information about your resource configurations, you must create a collector. An IBM managed collector is created on IBM owned infrastructure and is maintained by the {{site.data.keyword.compliance_short}}. To learn more about how collectors work, how your data is handled, and your responsibilities, see [What is a collector?](/docs/security-compliance?topic=security-compliance-collector).
{: shortdesc}


## Before you begin
{: #before-collector-ibm}

Before you begin, be sure that you're using a Pay-As-You-Go or Subscription [{{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started) where you are the owner or have [full **Administrator** access](/docs/account?topic=account-assign-access-resources). To create a collector, you must also have the **Administrator** role access to the {{site.data.keyword.compliance_short}}. Be sure that you also have access to the [credentials](/docs/security-compliance?topic=security-compliance-credentials) that your collector needs to gather your resource configurations.

A managed collector can support up to 400 resources per customer. If your organization has more resources, you can always [manually create and install a collector](/docs/security-compliance?topic=security-compliance-collector-manual).
{: note}


## Creating a managed collector with the console
{: #create-managed-collector-ui}
{: ui}

You can use the {{site.data.keyword.compliance_short}} UI to create a collector by completing the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Manage posture > Configure > Settings > Collectors**.
3. Click **Create**.
4. Give your collector a name and description.

  It is helpful to ensure that the name is unique across your organization so that its intended purpose is clear to other members of your team.

5. If you have a passphrase enabled, the **Existing passphrase** field displays. Enter your passphrase. If you do not have a passphrase enabled, the field will not display.
6. Click **Next**.
7. In the **Managed by** field, select **IBM**.
8. By default, the **Private** endpoint type is selected.

  A collector requires constant communication with the service to validate your current posture. By default, a private endpoint is used for communication in all IBM managed collectors.

9. Click **Create**. When the collector is created successfully, the status updates to **Installing**.

When your collector is ready, the status updates to **Active**.

