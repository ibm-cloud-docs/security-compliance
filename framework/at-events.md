---
copyright:
  years: 2020, 2022
lastupdated: "2022-12-14"

keywords: Activity Tracker for {{site.data.keyword.compliance_short}}, LogDNA for {{site.data.keyword.compliance_short}}, {{site.data.keyword.compliance_short}} events, {{site.data.keyword.compliance_short}} security, audit logs for {{site.data.keyword.compliance_short}}, viewing {{site.data.keyword.compliance_short}} events, {{site.data.keyword.compliance_short}} events

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
| `compliance.posture-management-credentials.list`      | View credentials. |
| `compliance.posture-management-credentials.read`      | View the details for an added credential. |
| `compliance.posture-management-credentials.create`    | Create a credential. |
| `compliance.posture-management-credentials.update`    | Update an existing credential. |
| `compliance.posture-management-credentials.delete`    | Delete a credential. |
| `compliance.posture-management-credentialsmap.list`   | View the available mappings between credentials and scopes.|
| `compliance.posture-management-credentialsmap.read`   | View the details of a specific credential and scope mapping. |
| `compliance.posture-management-credentialsmap.create` | Map credentials to a scope. |
| `compliance.posture-management-credentialsmap.update` | Update an existing mapping between a credential and a scope. |
| `compliance.posture-management-credentialsmap.delete` | Delete a mapping. |
| `compliance.posture-management-collectors.list`   | View collectors.              |
| `compliance.posture-management-collectors.read`   | View the details of a specific collector.              |
| `compliance.posture-management-collectors.create` | Create a collector.           |
| `compliance.posture-management-collectors.update` | Update an existing collector. |
| `compliance.posture-management-collectors.delete` | Delete a collector.           |
| `compliance.posture-management-scopes.list`   | View all available scopes. |
| `compliance.posture-management-scopes.read`   | View scopes.               |
| `compliance.posture-management-scopes.create` | Create a scope.            |
| `compliance.posture-management-scopes.update` | Update an existing scope.  |
| `compliance.posture-management-scopes.delete` | Delete a scope.            |
| `compliance.posture-management-schedules.list`   | View a list of all scheduled scans. |
| `compliance.posture-management-schedules.read`   | View the details of a scan. |
| `compliance.posture-management-schedules.create` | Schedule a scan. |
| `compliance.posture-management-schedules.update` | Update an existing scan. |
| `compliance.posture-management-schedules.delete` | Stop a scan from running. |
| `compliance.posture-management-validations.list`   | View validation scans. |
| `compliance.posture-management-validations.read`   | View the results of a specific scan. |
| `compliance.posture-management-goals.list`   | List all the available goals. |
| `compliance.posture-management-goals.read`   | View the details of a specific goal. |
| `compliance.posture-management-values.list`   | List the parameters that can be set for a goal. |
| `compliance.posture-management-values.read`   | View the value for a goal parameter. |
| `compliance.posture-management-values.update` | Update the parameters of an existing goal.           |
| `compliance.posture-management-controls.list`   | View the available controls that are available in a profile. |
| `compliance.posture-management-profiles.list`   | View a list of available profiles. |
| `compliance.posture-management-profiles.read`   | View the details of a profile.              |
| `compliance.posture-management-profiles.create` | Create a profile.           |
| `compliance.posture-management-profiles.update` | Update an existing profile. |
| `compliance.posture-management-profiles.delete` | Delete a profile.           |
| `compliance.posture-management-tags.list`   | View tags.              |
| `compliance.posture-management-tags.create` | Create a tag.           |
| `compliance.posture-management-tags.update` | Update an existing tag. |
| `compliance.posture-management-tags.delete` | Delete a tag.           |
| `compliance.posture-management-inventory.list`   | View your available inventory across all your environments. |
| `compliance.posture-management-inventory.read`   | View the details of a specific environment's inventory. |
| `compliance.posture-management-inventory.create` | Discover your inventory. |
| `compliance.posture-management-inventory.update` | Update your inventory. |
| `compliance.posture-management-inventory.delete` | Delete an inventory.  |
| `compliance.posture-management-remediation.list`      | List a remediation. |
| `compliance.posture-management-remediation.update`    | Update a remediation. |
| `compliance.posture-management-remediation.remediate` | Trigger a remediation. |
| `compliance.posture-management-keys.read`   | View your customer managed encryption configuration. |
| `compliance.posture-management-keys-write`  | Enable customer managed encryption configuration. |
| `compliance.posture-management-keys.delete` | Disable customer managed encryption configuration. |
| `compliance.posture-management.integrations-read`        | View an integration in {{site.data.keyword.compliance_short}}.   |
| `compliance.posture-management.integrations-create`      | Create an integration in {{site.data.keyword.compliance_short}}. |
| `compliance.posture-management.integrations-update`      | Update an integration in {{site.data.keyword.compliance_short}}. |
| `compliance.posture-management.integrations-delete`      | Delete an integration in {{site.data.keyword.compliance_short}}. |
| `compliance.configuration-governance-rules.list`   | View rules. |
| `compliance.configuration-governance-rules.read`   | View the details of a rule. |
| `compliance.configuration-governance-rules.create` | Create a rule. |
| `compliance.configuration-governance-rules.update` | Update an existing rule. |
| `compliance.configuration-governance-rules.delete` | Delete a rule. |
| `compliance.configuration-governance-templates.list`   | View templates. |
| `compliance.configuration-governance-templates.read`   | View the details of a template. |
| `compliance.configuration-governance-templates.create` | Create a template. |
| `compliance.configuration-governance-templates.update` | Update an existing template. |
| `compliance.configuration-governance-templates.delete` | Delete a template. |
| `compliance.configuration-governance-attachments.list`   | View the attachments that are available for a rule or template. |
| `compliance.configuration-governance-attachments.read`   | View the details of an attachment. |
| `compliance.configuration-governance-attachments.create` | Create an attachment between a rule or template and a scope. |
| `compliance.configuration-governance-attachments.update` | Update an existing attachment. |
| `compliance.configuration-governance-attachments.delete` | Delete an attachment. |
| `compliance.configuration-governance-results.read`   | View config rule results. |
| `compliance.configuration-governance-resource.eval` | Describes the resource that is being evaluated. |
| `compliance.configuration-governance-rule.eval` | Describes the rule that is being evaluated. |
| `compliance.admin-settings.list`   | View {{site.data.keyword.compliance_short}} settings for your account. |
| `compliance.admin-settings.update` | Update {{site.data.keyword.compliance_short}} settings for your account. |
| `compliance.admin.test-event-send` | Send a test event to a connected {{site.data.keyword.en_short}} service instance. |
{: caption="Table 1. List of events that apply to {{site.data.keyword.compliance_short}}" caption-side="top"}


