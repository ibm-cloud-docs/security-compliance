---
copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: "Activity Tracking events for {{site.data.keyword.compliance_short}}, LogDNA for {{site.data.keyword.compliance_short}}, {{site.data.keyword.compliance_short}} events, {{site.data.keyword.compliance_short}} security, audit logs for {{site.data.keyword.compliance_short}}, viewing {{site.data.keyword.compliance_short}} events, {{site.data.keyword.compliance_short}} events"

subcollection: security-compliance
---

{{site.data.keyword.attribute-definition-list}}


# Activity tracking events for {{site.data.keyword.compliance_short}}
{: #at_events}



As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the replacement service {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}



{{site.data.keyword.cloud_notm}} services, such as {{site.data.keyword.compliance_full}}, generate activity tracking events.
{: shortdesc}

Activity tracking events report on activities that change the state of a service in {{site.data.keyword.cloud_notm}}. You can use the events to investigate abnormal activity and critical actions and to comply with regulatory audit requirements.

You can use {{site.data.keyword.atracker_full_notm}}, a platform service, to route auditing events in your account to destinations of your choice by configuring targets and routes that define where activity tracking events are sent. For more information, see [About {{site.data.keyword.atracker_full_notm}}](/docs/atracker?topic=atracker-about).

You can use {{site.data.keyword.logs_full_notm}} to visualize and alert on events that are generated in your account and routed by {{site.data.keyword.atracker_full_notm}} to an {{site.data.keyword.logs_full_notm}} instance.

## Locations where activity tracking events are generated
{: #at-locations}

{{site.data.keyword.compliance_short}} generates activity tracking events to {{site.data.keyword.logs_full_notm}} hosted event search in the regions that are indicated in the following table.


| Dallas (`us-south`) | Washington (`us-east`)  | Toronto (`ca-tor`) | Sao Paulo (`br-sao`) |
|---------------------|-------------------------|-------------------|----------------------|
| [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} | [No]{: tag-red} |
{: caption="Regions where activity tracking events are sent in Americas locations" caption-side="top"}
{: #atracker-table-11}
{: tab-title="Americas"}
{: tab-group="atracker"}
{: class="simple-tab-table"}
{: row-headers}

| Tokyo (`jp-tok`)    | Sydney (`au-syd`) |  Osaka (`jp-osa`) | Chennai (`in-che`) |
|---------------------|------------------|------------------|--------------------|
| [No]{: tag-red} | [No]{: tag-red} | [No]{: tag-red} | [No]{: tag-red} |
{: caption="Regions where activity tracking events are sent in Asia Pacific locations" caption-side="top"}
{: #atracker-table-12}
{: tab-title="Asia Pacific"}
{: tab-group="atracker"}
{: class="simple-tab-table"}
{: row-headers}

| Frankfurt (`eu-de`)  | London (`eu-gb`) | Madrid (`eu-es`) |
|---------------------------------------------------------------|---------------------|------------------|
| [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} |
{: caption="Regions where activity tracking events are sent in Europe locations" caption-side="top"}
{: #atracker-table-13}
{: tab-title="Europe"}
{: tab-group="atracker"}
{: class="simple-tab-table"}
{: row-headers}


## Locations where activity tracking events are sent by {{site.data.keyword.atracker_full_notm}}
{: #atracker-locations}

{{site.data.keyword.compliance_short}} sends activity tracking events by {{site.data.keyword.atracker_full_notm}} in the regions that are indicated in the following table.

| Dallas (`us-south`) | Washington (`us-east`)  | Toronto (`ca-tor`) | Sao Paulo (`br-sao`) |
|---------------------|-------------------------|-------------------|----------------------|
| [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} | [No]{: tag-red} |
{: caption="Regions where activity tracking events are sent in Americas locations" caption-side="top"}
{: #atracker-table-21}
{: tab-title="Americas"}
{: tab-group="atracker"}
{: class="simple-tab-table"}
{: row-headers}

| Tokyo (`jp-tok`)    | Sydney (`au-syd`) |  Osaka (`jp-osa`) | Chennai (`in-che`) |
|---------------------|------------------|------------------|--------------------|
| [No]{: tag-red} | [No]{: tag-red} | [No]{: tag-red} | [No]{: tag-red} |
{: caption="Regions where activity tracking events are sent in Asia Pacific locations" caption-side="top"}
{: #atracker-table-22}
{: tab-title="Asia Pacific"}
{: tab-group="atracker"}
{: class="simple-tab-table"}
{: row-headers}

| Frankfurt (`eu-de`)  | London (`eu-gb`) | Madrid (`eu-es`) |
|---------------------------------------------------------------|---------------------|------------------|
| [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} |
{: caption="Regions where activity tracking events are sent in Europe locations" caption-side="top"}
{: #atracker-table-23}
{: tab-title="Europe"}
{: tab-group="atracker"}
{: class="simple-tab-table"}
{: row-headers}

## Enabling activity tracking events for {{site.data.keyword.compliance_short}}
{: #at-enable}

You must use a paid plan for the {{site.data.keyword.atracker_full_notm}} service to see events for {{site.data.keyword.compliance_short}}.


## Viewing activity tracking events for {{site.data.keyword.compliance_short}}
{: #at-viewing}

You can use {{site.data.keyword.logs_full_notm}} to visualize and alert on events that are generated in your account and routed by {{site.data.keyword.atracker_full_notm}} to an {{site.data.keyword.logs_full_notm}} instance.


### Launching {{site.data.keyword.logs_full_notm}} from the Observability page
{: #log-launch-standalone}

For information on launching the {{site.data.keyword.logs_full_notm}} UI, see [Launching the UI in the {{site.data.keyword.logs_full_notm}} documentation](/docs/cloud-logs?topic=cloud-logs-instance-launch).


## List of events
{: #at_actions}

| Action                                            | Description     |
| :-----------------------------------------------------|:----------------|
| `compliance.posture-management-profiles.list` | An event is generated when a user lists all of the available profils.|
| `compliance.posture-management-profiles.create` | An event is generated when a user creates a profile. |
| `compliance.posture-management-profiles.read` | An event is generated when a user views the details of a profile. |
| `compliance.posture-management-profiles.update` | An event is generated when a user updates a profile. |
| `compliance.posture-management-profiles.delete` | An event is generated when a user deletes a profile. |
| `compliance.posture-management-profiles-attachments.list` | An event is generated when a user views the attachments related to a specific profile. |
| `compliance.posture-management-profiles-attachments.create` | An event is generated when a user creates a new attachment. |
| `compliance.posture-management-profiles-attachments.read` | An event is generated when a user views the details of an attachment. |
| `compliance.posture-management-profiles-attachments.update` | An event is generated when a user updates an attachment. |
| `compliance.posture-management-profiles-attachments.delete` | An event is generated when a user deletes an attachment. |
| `compliance.posture-management-profiles-attachments-parameters.list` | An event is generated when a user views the parameters that are associated with a profile attachment. |
| `compliance.posture-management-profiles-attachments-parameters.create` | An event is generated when a user sets a parameter variable for an attachment. |
| `compliance.posture-management-profiles-attachments-parameters.read` | An event is generated when a user views the parameter details. |
| `compliance.posture-management-profiles-attachments-parameters.update` | An event is generated when a user updates a parameter value for an attachment. |
| `compliance.posture-management-control-libraries.list` | An event is generated when a user views the available control libraries in your account. |
| `compliance.posture-management-control-libraries.create` | An event is generated when a user creates a new control library. |
| `compliance.posture-management-control-libraries.read` | An event is generated when a user views the details of a control library. |
| `compliance.posture-management-control-libraries.update` | An event is generated when a user updates a control library. |
| `compliance.posture-management-control-libraries.delete` | An event is generated when a user deletes a control library. |
| `compliance.posture-management-scans.create` | An event is generated when a user initiates a scan. |
| `compliance.posture-management-reports.list` | An event is generated when a user views all available results. |
| `compliance.posture-management-reports.create` | An event is generated when a user generates a new report. |
| `compliance.posture-management-reports.read` | An event is generated when a user views detailed results. |
| `compliance.posture-management-reports.delete` | An event is generated when a user deletes results. |
| `compliance.posture-management.integrations-create` | An event is generated when a user creates an instance of a provider. |
| `compliance.posture-management.integrations-read` | An event is generated when a user lists all providers. |
| `compliance.posture-management.integrations-update` | An event is generated when a user removes a provider. |
| `compliance.posture-management.integrations-delete` | An event is generated when a user updates an instance of a specific provider. |
| `compliance.configuration-governance-rules.list` | An event is generated when a user views the available rules in {{site.data.keyword.compliance_short}}. |
| `compliance.configuration-governance-rules.create` | An event is generated when a user creates a new rule. |
| `compliance.configuration-governance-rules.read` | An event is generated when a user views the details of a rule. |
| `compliance.configuration-governance-rules.update` | An event is generated when a user updates a rule. |
| `compliance.configuration-governance-rules.delete` | An event is generated when a user deletes a rule. |
| `compliance.admin-settings.list` | An event is generated when a user views {{site.data.keyword.compliance_short}} settings for your account. |
| `compliance.admin-settings.update` | An event is generated when a user updates {{site.data.keyword.compliance_short}} settings for your account. |
| `compliance.admin-test-event.send` | An event is generated when a user sends a test event to a connected {{site.data.keyword.en_short}} service instance. |
{: caption="List of events that apply to {{site.data.keyword.compliance_short}}" caption-side="top"}
