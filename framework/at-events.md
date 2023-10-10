---
copyright:
  years: 2020, 2023
lastupdated: "2023-10-10"

keywords: Activity Tracker for {[scc]}, LogDNA for {[scc]}, {[scc]} events, {[scc]} security, audit logs for {[scc]}, viewing {[scc]} events, {[scc]} events

subcollection: security-compliance
---

{{site.data.keyword.attribute-definition-list}}

# Auditing events for {[scc]}
{: #at_events}

As a security officer, auditor, or manager, you can use the {[at]} service to track how users and applications interact with the {[scc]} service in {[cloud]}.
{: shortdesc}

{[at]} records user-initiated activities that change the state of a service in {[cloud]}. You can use this service to investigate abnormal activity and critical actions and to comply with regulatory audit requirements. In addition, you can be alerted about actions as they happen. The events that are collected comply with the Cloud Auditing Data Federation (CADF) standard. For more information, see the [getting started tutorial for {[at]}](/docs/activity-tracker?topic=activity-tracker-getting-started#getting-started).

You must use a paid plan for the {[at]} service to see events for the {[scc]}.
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
| `compliance.posture-management-profiles-attachments-parameters.list` | View the parameters that are associated with a profile attachment. |
| `compliance.posture-management-profiles-attachments-parameters.create` | Set a parameter variable for an attachment. |
| `compliance.posture-management-profiles-attachments-parameters.read` | View the parameter details. |
| `compliance.posture-management-profiles-attachments-parameters.update` | Update a parameter value for an attachment. |
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
| `compliance.posture-management.integrations-create` | Create an instance of a provider. |
| `compliance.posture-management.integrations-read` | List all providers. |
| `compliance.posture-management.integrations-update` | Remove a provider. |
| `compliance.posture-management.integrations-delete` | Update an instance of a specific provider. |
| `compliance.configuration-governance-rules.list` | View the available rules in {[scc]}. |
| `compliance.configuration-governance-rules.create` | Create a new rule. |
| `compliance.configuration-governance-rules.read` | View the details of a rule. |
| `compliance.configuration-governance-rules.update` | Update a rule. |
| `compliance.configuration-governance-rules.delete` | Delete a rule. |
| `compliance.admin-settings.list` | View {[scc]} settings for your account. |
| `compliance.admin-settings.update` | Update {[scc]} settings for your account. |
| `compliance.admin-test-event.send` | Send a test event to a connected {[en]} service instance. |
{: caption="Table 1. List of events that apply to {[scc]}" caption-side="top"}

