---

copyright:
  years: 2021
lastupdated: "2021-07-12"

keywords: remediation, aws, compliance, security, 

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


# Remediating issues
{: #remediation}

If you're working with an Amazon Web Services (AWS) or Azure account, you can use the {{site.data.keyword.compliance_full}} to remediate issues that are found.
{: shortdesc}


## Before you begin
{: #before-remediation}

Before you get started, be sure that you have the following prerequisites.

- An [installed collector](/docs/security-compliance?topic=security-compliance-collector).
- A [scope](/docs/security-compliance?topic=security-compliance-scopes) that is targeted to AWS.
- [Scan results](/docs/security-compliance?topic=security-compliance-view-posture#view-validations).
- The required level of access to view and manage remediation. To manage remediation, you need the editor platform role or higher. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).


## Running remediation
{: #run-remediation} 

You can use the {{site.data.keyword.compliance_short}} UI to get the remediation scripts that you can run to fix issues as they're found.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Actions icon](../icons/actions-icon-vertical.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Assess > Remediation**. 
3. In the **Remediation** table, select the issue that you want to remediate.
4. If the screen shows **Pending input**, click the **User inputs** edit icon.
5. In the configuration inputs pane, enter the values for the fields that are displayed. Options vary depending on the issue that is flagged.
6. Click **Save**. 
   1. If automatic remediation is in place, the status is set to **Ready to fix** or **Processing**, which indicates that the job is waiting in the queue to run.
   2. If the screen shows **Pending approval**, the script is ready to be run. Click the **Run** icon. Remediation is initiated.



