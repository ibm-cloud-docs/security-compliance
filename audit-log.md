---

copyright:
  years: 2020
lastupdated: "2020-08-31"

keywords: audit log, compliance, user activity, read-only events

subcollection: security-compliance

---

{:codeblock: .codeblock}
{:screen: .screen}
{:download: .download}
{:external: target="_blank" .external}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}
{:gif: data-image-type='gif'}
{:term: .term}
{:important: .important}
{:note: .note}
{:pre: .pre}
{:tip: .tip}
{:preview: .preview}
{:deprecated: .deprecated}
{:shortdesc: .shortdesc}
{:support: data-reuse='support'}
{:script: data-hd-video='script'}
{:table: .aria-labeledby="caption"}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:help: data-hd-content-type='help'}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tsSymptoms: .tsSymptoms}
{:beta: .beta}


# Auditing compliance activity
{: #audit-log}

You can audit the activity that takes place in the **Automate security and compliance** section of the {{site.data.keyword.compliance_full}}.
{: shortdesc}

Auditing actions that are associated with [config rules](/docs/security-compliance?topic=security-compliance-rules) is not currently available.
{: note}

## Before you begin
{: #before-auditing}

Before you get started, be sure that you have the required level of access to view and manage your audit log. To view audit logging, you need the viewer platform role or higher for the {{site.data.keyword.compliance_short}}. To turn off read events, you need the editor platform role or higher. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).



## Viewing logs
{: #view-audit-logs}

You can view the user actions that are associated with the security and compliance monitoring section of the {{site.data.keyword.compliance_short}} by using the UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Assess > Audit log** to view a list of events. 
3. Optional: Filter your list of logs by clicking the **Filter** icon and choosing from the following available options:

  * Start and end date
  * Start and end time
  * Source
  * Completed by
  * Event type
  * Event ID
  * Description
  * Status

4. Optional: Click **Download report** to keep a history of your audit log.



## Hiding read-only events
{: #hide-read-only}

By default, audit logs are enabled for every action that is taken in the {{site.data.keyword.compliance_short}}. If you want to see the activity where a user changed something only, you can hide read-only events. A read-only event is when a user looks at a page of the service but doesn't change anything on the page. 

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Settings > Settings**.
3. In the **Audit log settings** section, select **No**.
4. Click **Save**.

