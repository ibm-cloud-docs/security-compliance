---

copyright:
  years: 2021
lastupdated: "2021-03-02"

keywords: activity tracker for _servicename_, LogDNA for _servicename_, _servicename_ events, _servicename_ security, audit logs for _servicename_, viewing _servicename_ events, _servicename_ events

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

## Before you begin
{: #before-auditing}

Before you get started, be sure that you have the required level of access to view and manage your audit log. To view audit logging, you need the viewer platform role or higher for the {{site.data.keyword.compliance_short}}. To turn off read events, you need the editor platform role or higher. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).



# Auditing events for {{site.data.keyword.compliance_short}}
{: #at_events}

As a security officer, auditor, or manager, you can use the Activity Tracker service to track how users and applications interact with the {{site.data.keyword.compliance_short}} service in {{site.data.keyword.cloud_notm}}.
{: shortdesc}

{{site.data.keyword.at_full_notm}} records user-initiated activities that change the state of a service in {{site.data.keyword.cloud_notm}}. You can use this service to investigate abnormal activity and critical actions and to comply with regulatory audit requirements. In addition, you can be alerted about actions as they happen. The events that are collected comply with the Cloud Auditing Data Federation (CADF) standard. For more information, see the [getting started tutorial for {{site.data.keyword.at_full_notm}}](/docs/Activity-Tracker-with-LogDNA?topic=Activity-Tracker-with-LogDNA-getting-started#getting-started).


## Events for Posture Management
{: #at_actions_posture}

The following events are triggered by the Posture Management component of the {{site.data.keyword.compliance_short}}.

| Action                                                | Description                                                  |
| :---------------------------------------------------- | :----------------------------------------------------------- |
| `compliance.posture-management.credentials-read`      | View credentials.                                            |
| `compliance.posture-management.credentials-create`    | Create a credential.                                         |
| `compliance.posture-management.credentials-update`    | Update an existing credential.                               |
| `compliance.posture-management.credentials-delete`    | Delete a credential.                                         |
| `compliance.posture-management.credentialsmap-read`   | View mappings between credentials and scopes.                |
| `compliance.posture-management.credentialsmap-create` | Map credentials to a scope.                                  |
| `compliance.posture-management.credentialsmap-update` | Update an existing mapping between a credential and a scope. |
| `compliance.posture-management.credentialsmap-delete` | Delete a mapping.                                            |
{: caption="Table 1. List of events that apply to the Posture Management component" caption-side="top"}
{: #credentials-events}
{: tab-title="Credentials"}
{: tab-group="posture"}
{: class="simple-tab-table"}

| Action                                            | Description                   |
| :------------------------------------------------ | :---------------------------- |
| `compliance.posture-management.collectors-read`   | View collectors.              |
| `compliance.posture-management.collectors-create` | Create a collector.           |
| `compliance.posture-management.collectors-update` | Update an existing collector. |
| `compliance.posture-management.collectors-delete` | Delete a collector.           |
{: caption="Table 1. List of events that apply to the Posture Management component" caption-side="top"}
{: #collectors-events}
{: tab-title="Collectors"}
{: tab-group="posture"}
{: class="simple-tab-table"}

| Action                                        | Description               |
| :-------------------------------------------- | :------------------------ |
| `compliance.posture-management.scopes-read`   | View scopes.              |
| `compliance.posture-management.scopes-create` | Create a scope.           |
| `compliance.posture-management.scopes-update` | Update an existing scope. |
| `compliance.posture-management.scopes-delete` | Delete a scope.           |
{: caption="Table 1. List of events that apply to the Posture Management component" caption-side="top"}
{: #scopes-events}
{: tab-title="Scopes"}
{: tab-group="posture"}
{: class="simple-tab-table"}

| Action                                             | Description                         |
| :------------------------------------------------- | :---------------------------------- |
| `compliance.posture-management.validations-read`   | View validation scans.              |
| `compliance.posture-management.validations-create` | Run a validation scan.              |
| `compliance.posture-management.validations-update` | Update an existing validation scan. |
| `compliance.posture-management.validations-delete` | Delete a validation scan.           |
{: caption="Table 1. List of events that apply to the Posture Management component" caption-side="top"}
{: #validations-events}
{: tab-title="Scans"}
{: tab-group="posture"}
{: class="simple-tab-table"}

| Action                                        | Description                                          |
| :-------------------------------------------- | :--------------------------------------------------- |
| `compliance.posture-management.values-read`   | View the parameters that are associated with a goal. |
| `compliance.posture-management.values-create` | Add parameters to an existing goal.                  |
| `compliance.posture-management.values-update` | Update the parameters of an existing goal.           |
| `compliance.posture-management.values-delete` | Delete a parameter.                                  |
{: caption="Table 1. List of events that apply to the Posture Management component" caption-side="top"}
{: #goals-events}
{: tab-title="Goals"}
{: tab-group="posture"}
{: class="simple-tab-table"}

| Action                                          | Description                                                |
| :---------------------------------------------- | :--------------------------------------------------------- |
| `compliance.posture-management.controls-read`   | View the available controls that you can add to a profile. |
| `compliance.posture-management.controls-create` | Add a control to a profile.                                |
| `compliance.posture-management.controls-update` | Update an existing control.                                |
| `compliance.posture-management.controls-delete` | Delete a control.                                          |
{: caption="Table 1. List of events that apply to the Posture Management component" caption-side="top"}
{: #controls-events}
{: tab-title="Controls"}
{: tab-group="posture"}
{: class="simple-tab-table"}

| Action                                          | Description                 |
| :---------------------------------------------- | :-------------------------- |
| `compliance.posture-management.profiles-read`   | View profiles.              |
| `compliance.posture-management.profiles-create` | Create a profile.           |
| `compliance.posture-management.profiles-update` | Update an existing profile. |
| `compliance.posture-management.profiles-delete` | Delete a profile.           |
{: caption="Table 1. List of events that apply to the Posture Management component" caption-side="top"}
{: #profiles-events}
{: tab-title="Profiles"}
{: tab-group="posture"}
{: class="simple-tab-table"}

| Action                                      | Description             |
| :------------------------------------------ | :---------------------- |
| `compliance.posture-management.tags-read`   | View tags.              |
| `compliance.posture-management.tags-create` | Create a tag.           |
| `compliance.posture-management.tags-update` | Update an existing tag. |
| `compliance.posture-management.tags-delete` | Delete a tag.           |
{: caption="Table 1. List of events that apply to the Posture Management component" caption-side="top"}
{: #tags-events}
{: tab-title="Tags"}
{: tab-group="posture"}
{: class="simple-tab-table"}



## Events for Configuration Governance
{: #at_actions_governance}

The following events are triggered by the Configuration Governance component of the {{site.data.keyword.compliance_short}}.

| Action                                                   | Description                                         |
| :------------------------------------------------------- | :-------------------------------------------------- |
| `compliance.configuration-governance.rules-read`         | View rules.                                         |
| `compliance.configuration-governance.rules-create`       | Create a rule.                                      |
| `compliance.configuration-governance.rules-update`       | Update an existing rule.                            |
| `compliance.configuration-governance.rules-delete`       | Delete a rule.                                      |
{: caption="Table 2. List of events that apply to Configuration Governance" caption-side="top"}
{: #rules-access}
{: tab-title="Rules"}
{: tab-group="config"}
{: class="simple-tab-table"}

| Action                                                   | Description                                         |
| :------------------------------------------------------- | :-------------------------------------------------- |
| `compliance.configuration-governance.attachments-read`   | View the attachments that are available for a rule. |
| `compliance.configuration-governance.attachments-create` | Create an attachment between a rule and a scope.    |
| `compliance.configuration-governance.attachments-update` | Update an existing attachment.                      |
| `compliance.configuration-governance.attachments-delete` | Delete an attachment.                               |
{: caption="Table 2. List of events that apply to Configuration Governance" caption-side="top"}
{: #attachments-access}
{: tab-title="Attachments"}
{: tab-group="config"}
{: class="simple-tab-table"}

| Action                                                   | Description                                         |
| :------------------------------------------------------- | :-------------------------------------------------- |
| `compliance.configuration-governance.results-read`   | View config rule results. |
{: caption="Table 2. List of events that apply to Configuration Governance" caption-side="top"}
{: #results-access}
{: tab-title="Results"}
{: tab-group="config"}
{: class="simple-tab-table"}



## Viewing events
{: #at_ui}

Events that are generated by an instance of the {{site.data.keyword.compliance_short}} are automatically forwarded to the {{site.data.keyword.at_full_notm}} service instance that is available in the same location.

{{site.data.keyword.at_full_notm}} can have only one instance per location. To view events, you must access the web UI of the {{site.data.keyword.at_full_notm}} service in the same location where your service instance is available. For more information, see [Launching the web UI through the IBM Cloud UI](/docs/Activity-Tracker-with-LogDNA?topic=Activity-Tracker-with-LogDNA-launch#launch_cloud_ui).








