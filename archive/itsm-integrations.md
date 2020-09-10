---

copyright:
  years: 2020
lastupdated: "2020-08-20"

keywords: governance, configuration, rules, enforce, resources, conditions, target, user-defined,

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


# Integrating ITSM
{: #itsm}

To help facilitate the remediation of findings, you can choose to connect your business's ServiceNow account with the {{site.data.keyword.compliance_full}}.
{: shortdesc}


## Connecting ServiceNow
{: #servicenow}

To facilitate remediation, you can create a connection between the service and your business' ServiceNow system.
{: shortdesc}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.

2. In the navigation, click **Settings > ITSM integrations**.

3. Enter your **ServiceNow URL**.

4. Enter your **Client ID** and **Client secret**. 

5. Enter the **Group SYS ID** and **User SYS ID**.

6. Enter your ServiceNow **User ID** and password.

7. Select the status that you want an existing ticket to have before a duplicate ticket is opened.

  If an issue is encountered while an existing ticket is already open, you can choose the status that you want the ticket to have before the issue creates a duplicate ticket. For example, say that the status of a ticket must be **Done** before a ticket is open. You run a validation scan every day and a container vulnerability is flagged on a Tuesday. The service does not continue to create a new ticket because there is already an open one. Now, say you fix the vulnerability and move the ticket to done on Thursday. But, on Friday the same issue is flagged during the validation scan, and a new ticket is opened.

8. Enter the number of days that you want to wait before a new ticket is created, if an existing ticket is already open.

  This setting overrides the setting in step 7. By having an override for the number of days, you're able to prevent critical issues from getting lost in a group of old tickets.

9. Click **Save**.




## Grouping ITSM tickets
{: #ticket-grouping}

You can decide whether you want to open tickets in ServiceNow per resource or per control. For example, if you have a password check to meet a control and validation fails on two separate resources. You can choose whether to open two tickets - one per resource, or open one ticket for the control that failed that details the information for both resources within it.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) > **Security and compliance** to access the {{site.data.keyword.compliance_short}}.

2. In the navigation, click **Settings > Settings**.

3. In the **ITSM settings** section, select **By resources** or **By controls** to determine the way that tickets that are created.

  If you select **By resource**, tickets are created per resource that fails. If you select **By controls**, tickets are created per control that fails.

4. Click **Update**.



