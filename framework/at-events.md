---
copyright:
  years: 2020, 2023
lastupdated: "2023-06-27"

keywords: Activity Tracker for {{site.data.keyword.compliance_short}}, LogDNA for {{site.data.keyword.compliance_short}}, {{site.data.keyword.compliance_short}} events, {{site.data.keyword.compliance_short}} security, audit logs for {{site.data.keyword.compliance_short}}, viewing {{site.data.keyword.compliance_short}} events, {{site.data.keyword.compliance_short}} events

subcollection: security-compliance
---

{{site.data.keyword.attribute-definition-list}}

# Auditing events for {{site.data.keyword.compliance_short}}
{: #at_events}

As a security officer, auditor, or manager, you can use the {{site.data.keyword.at_short}} service to track how users and applications interact with the {{site.data.keyword.compliance_short}} service in {{site.data.keyword.cloud_notm}}.
{: shortdesc}

{{site.data.keyword.at_short}} records user-initiated activities that change the state of a service in {{site.data.keyword.cloud_notm}}. You can use this service to investigate abnormal activity and critical actions and to comply with regulatory audit requirements. In addition, you can be alerted about actions as they happen. The events that are collected comply with the Cloud Auditing Data Federation (CADF) standard. For more information, see the [getting started tutorial for {{site.data.keyword.at_short}}](/docs/activity-tracker?topic=activity-tracker-getting-started#getting-started).

You must use a paid plan for the {{site.data.keyword.at_short}} service to see events for the {{site.data.keyword.compliance_short}}.
{: note}



| Action                                            | Description     |
| :-----------------------------------------------------|:----------------|
| `compliance.posture-management-profiles.list` | List the available profiles. |
| `compliance.posture-management-profiles.create` | Create a profile. |
| `compliance.posture-management-profiles.read` | View the details of a profile. |
| `compliance.posture-management-profiles.update` | Update a profile. |
| `compliance.posture-management-profiles.delete` | Delete a profile. |
| `compliance.posture-management-profiles-attachments.list` | View the attachments related to a specific profile. |
| `compliance.posture-management-profiles-attachments.create` | Create a new attachment. |
| `compliance.posture-management-profiles-attachments.read` | View the details of an attachment. |
| `compliance.posture-management-profiles-attachments.update` | Update an attachment. |
| `compliance.posture-management-profiles-attachments.delete` | Delete an attachment. |
| `compliance.posture-management-profiles-attachments-parameters.list` | View the parameters that are associated with a profile attachement. |
| `compliance.posture-management-profiles-attachments-parameters.create` | Set a parameter variable for an attachment. |
| `compliance.posture-management-profiles-attachments-parameters.read` | View the parameter details. |
| `compliance.posture-management-profiles-attachments-parameters.update` | Update a paramater value for an attachment. |
| `compliance.posture-management-control-libraries.list` | View the available control libraries in your account. |
| `compliance.posture-management-control-libraries.create` | Create a new control library. |
| `compliance.posture-management-control-libraries.read` | View the details of a control library. |
| `compliance.posture-management-control-libraries.update` | Update a control library. |
| `compliance.posture-management-control-libraries.delete` | Delete a control library. |
| `compliance.posture-management-scans.create` | Initiate a scan. |
| `compliance.posture-management-reports.list` | View all available results. |
| `compliance.posture-management-reports.create` | Generate a new report. |
| `compliance.posture-management-reports.read` | View detailed results. |
| `compliance.posture-management-reports.delete` | Delete results. |
| `compliance.configuration-governance-rules.list` | View the available rules in {{site.data.keyword.compliance_short}}. |
| `compliance.configuration-governance-rules.create` | Create a new rule. |
| `compliance.configuration-governance-rules.read` | View the details of a rule. |
| `compliance.configuration-governance-rules.update` | Update a rule. |
| `compliance.configuration-governance-rules.delete` | Delete a rule. |
| `compliance.admin-settings.list` | View {{site.data.keyword.compliance_short}} settings for your account. |
| `compliance.admin-settings.update` | Update {{site.data.keyword.compliance_short}} settings for your account. |
| `compliance.admin-test-event.send` | Send a test event to a connected {{site.data.keyword.en_short}} service instance. |
{: caption="Table 1. List of events that apply to {{site.data.keyword.compliance_short}}" caption-side="top"}


