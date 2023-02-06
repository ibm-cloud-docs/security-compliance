---

copyright:
  years: 2020, 2023
lastupdated: "2023-02-06"

keywords: getting started with the security and compliance center, get started, security, compliance

subcollection: security-compliance

content-type: tutorial
services: security-compliance, cos
completion-time: 5m

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

# Getting started with {{site.data.keyword.compliance_short}}
{: #getting-started}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, cos"}
{: toc-completion-time="5m"}

For highly regulated industries, such as financial services, achieving continuous compliance within a cloud environment is an important first step toward protecting customer and application data. Historically, that process was difficult and manual, which placed your organization at risk. But, with {{site.data.keyword.compliance_full}}, you can integrate daily, automatic compliance checks into your development lifecycle to help minimize that risk.
{: shortdesc}

Trying to evaluate an environment other than {{site.data.keyword.cloud_notm}}? Get started with [collector-based evaluations](/docs/security-compliance?topic=security-compliance-collector). 
{: note}


## Before you begin
{: #before-gs}

Before you get started, be sure that you have resources in your account to evaluate. You must also have a bucket in the Cloud Object Storage service that can be used to store your results data.

Running an evaluation does not ensure regulatory compliance. An evaluation provides a point in time statement of your current posture for a specific resource. It is your responsibility to review and interpret the results to ensure that your organization is adhering to the controls that are required for your industry. 
{: important}


## Assign access
{: #gs-access}
{: step}

If you are working in a larger organization, you might need to start by assigning access to those on your team who will be managing compliance. 

1. [Create an access group](/docs/account?topic=account-groups#create_ag) and add your compliance focals.
2. In the Console, go to **Manage > Access (IAM) > Access groups** and click select the group that you want to assign access to. A new page opens with the details of the group.
3. Click **Access > Assign access**.
4. Assign the following permissions by selecting a service and reviewing the available roles and actions that are available for each option.

| Service | Minimum required permissions |
|---------|----------------------|
| {{site.data.keyword.compliance_short}} | Administrator |
| Cloud Object Storage | Reader |
| Event Notifications | Reader |
| Enterprise | Administrator or custom role |
{: caption="Table. Minimum required permissions" caption-side="top"}

If you are working within an enterprise account and do not want to assign administrator access to your compliance focals, you can create [a custom role](/docs/security-compliance?topic=security-compliance-assign-roles).
{: note}


## Configure storage
{: #gs-storage}
{: step}

Before you can start evaluating your resources for compliance, you must configure a Cloud Object Storage bucket where the service can forward your results data for long-term storage. For more information about bucket requirements, see [Storing and processing data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-storage).

To connect your Cloud Object Storage bucket, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the navigation, click **Settings**.
2. On the **Storage** tile, click **Connect**.
3. Ensure that your service-to-service policy between Cloud Object Storage and {{site.data.keyword.compliance_short}} is configured. If your policy is already in place, this screen is not shown, and you can skip to the next step. 
4. Select an instance of Cloud Object Storage.
5. From the table, select the bucket that you want to use.
6. Click **Connect**.

## Create an attachment
{: #gs-attachment}
{: step}

An attachment is how you target a specific grouping of your resources to evaluate against a specific profile.

1. In the navigation, click **Dashboard**.
2. Click **Get started**.
3. Select the **Profile** that you want to use to evaluate compliance.
4. Target the specific resources to scan by selecting a **Scope**. 
5. Optionally, you can exclude accounts or resource groups from your scope that you don't want to evaluate.
5. Click **Next**.
6. Provide the specific values that you want to use when the parameters are evaluated. 

   The values that you provide are evaluated only for this attachment. Changing the values in this flow does not override the default value that is set in the control library.

7. Click **Next**.
8. Review your choices and click **Create**.


When you create your attachment, a scan is scheduled. When the scan completes your results are available on the **Dashboard** in the {{site.data.keyword.compliance_short}} UI.

## Next steps
{: #gs-next}

While you wait for your scan to complete, learn more about [the way the service works](/docs/security-compliance?topic=security-compliance-posture-management) or try [creating your own rule](/docs/security-compliance?topic=security-compliance-rules-define).


