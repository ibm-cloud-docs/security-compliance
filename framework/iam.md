---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: "IAM access for {{site.data.keyword.compliance_short}}, permissions for {{site.data.keyword.compliance_short}}, identity and access management for {{site.data.keyword.compliance_short}}, roles for {{site.data.keyword.compliance_short}}, actions for {{site.data.keyword.compliance_short}}, assigning access for {{site.data.keyword.compliance_short}}"

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Managing IAM access for {{site.data.keyword.compliance_short}}
{: #access-management}

As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}

Access to the {{site.data.keyword.compliance_full}} is controlled by {{site.data.keyword.iamshort}} (IAM). Every user that accesses the {{site.data.keyword.compliance_short}} in your account must be assigned an access policy, with a defined IAM role. The policy determines which actions that a user can perform within the context of the {{site.data.keyword.compliance_short}}.

Policies enable access to be granted at different levels. Some options include the following actions:

* Access to manage profiles and controls
* Access to view security and compliance posture and results
* Access to manage event notifications


## Roles and permissions
{: #iam-roles}

After you define the level of access that a user might need, you can assign them an access role. To understand which role should be assigned, review the following table to see which {{site.data.keyword.compliance_short}} actions can be completed by each role.

Last year, {{site.data.keyword.compliance_short}} transitioned from a global service to a regional service. As part of completing that migration, new IAM actions for {{site.data.keyword.compliance_short}} that are mapped to *Service roles* will be available on 7 June 2024. For more information about what this change means for you, see the [release notes](/docs/security-compliance?topic=security-compliance-release-notes).
{: important}


| Existing action    | Description | Existing minimum required role | New minimum required role |
|:-------------------|:------------|:-------------------------------|:--------------------------|
| `compliance.admin.settings-read`   | View {{site.data.keyword.compliance_short}} settings for your account. | Viewer  | Reader |
| `compliance.admin.settings-update` | Update {{site.data.keyword.compliance_short}} settings for your account. | Administrator | Manager |
| `compliance.admin.test-event-send` | Send a test event to a connected {{site.data.keyword.en_short}} service instance. | Administrator | Manager |
| `compliance.configuration-governance.rules-create` | Create a rule. | Editor | Writer |
| `compliance.configuration-governance.rules-read` | View a rule. | Viewer | Reader |
| `compliance.configuration-governance.rules-update` | Update a rule. | Editor | Writer |
| `compliance.configuration-governance.rules-delete` | Delete a rule. | Editor | Writer |
| `compliance.posture-management.attachments-create` | Create an attachment. | Editor[^attach-1] | Writer[^attach-5] |
| `compliance.posture-management.attachments-read` | View the available attachments in your account. | Viewer[^attach-2] | Reader[^attach-6] |
| `compliance.posture-management.attachments-update` | Update an attachment. | Editor[^attach-3] | Writer[^attach-7] |
| `compliance.posture-management.attachments-upgrade` | Upgrade your attachment to use the latest version of a profile. | Editor | Writer |
| `compliance.posture-management.attachments-delete` | Delete an attachment. | Editor[^attach-4] | Writer[^attach-8] |
| `compliance.posture-management.control-libraries-create` | Create a control library. | Editor | Writer |
| `compliance.posture-management.control-libraries-read` | View the available control libraries in your account. | Viewer | Reader |
| `compliance.posture-management.control-libraries-update` | Update a control library. | Editor | Writer |
| `compliance.posture-management.control-libraries-delete` | Delete a control library. | Editor | Writer |
| `compliance.posture-management.controls-create` | Add a control to a profile. | Editor | Writer |
| `compliance.posture-management.controls-read` | View the controls that you can add to a profile. | Viewer | Reader |
| `compliance.posture-management.controls-update` | Update an existing control. | Editor | Writer |
| `compliance.posture-management.controls-delete` | Delete a control. | Editor | Writer |
| `compliance.posture-management.dashboard-view` | Access the {{site.data.keyword.compliance_short}} dashboard to view results. | Viewer | Reader |
| `compliance.posture-management.integrations-create` | Create an integration in {{site.data.keyword.compliance_short}}. | Operator | Writer |
| `compliance.posture-management.integrations-read` | View an integration in {{site.data.keyword.compliance_short}}. | Viewer | Reader |
| `compliance.posture-management.integrations-update` | Update an integration in {{site.data.keyword.compliance_short}}. | Operator | Writer |
| `compliance.posture-management.integrations-delete` | Delete an integration in {{site.data.keyword.compliance_short}}. | Editor | Writer |
| `compliance.posture-management.profiles-compare` | Compare two versions of the same profile to see how they differ. | Editor | Writer |
| `compliance.posture-management.profiles-create` | Create a profile. | Editor | Writer |
| `compliance.posture-management.profiles-read` | View profiles. | Viewer | Reader |
| `compliance.posture-management.profiles-update` | Update a profile. | Editor | Writer |
| `compliance.posture-management.profiles-delete` | Delete a profile. | Editor | Writer |
| `compliance.posture-management.reports-create` | Read results and reports. | Operator | Reader |
| `compliance.posture-management.scans-create` | Create a scan. | Administrator | Manager |
| `compliance.posture-management.scopes-create` | Create a scope. | Editor | Writer |
| `compliance.posture-management.scopes-read` | View scopes. | Viewer | Reader |
| `compliance.posture-management.scopes-update` | Edit a scope. | Editor | Writer |
| `compliance.posture-management.scopes-delete` | Delete a scope. | Editor | Writer |
| `compliance.posture-management.subscopes-create` | Create a subscope. | Editor | Writer |
| `compliance.posture-management.subscopes-read` | View subscopes. | Viewer | Reader |
| `compliance.posture-management.subscopes-update` | Edit a subscope. | Editor | Writer |
| `compliance.posture-management.subscopes-delete` | Delete a subscope. | Editor | Writer |
| `compliance.targets.create` | Create a target. | Editor | Writer |
| `compliance.targets.read` | View targets. | Viewer | Reader |
| `compliance.targets.update` | Update a target. | Editor | Writer |
| `compliance.targets.delete` | Delete a target. | Editor | Writer |
{: caption="IAM user roles and actions" caption-side="top"}

[^attach-1]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.

[^attach-2]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.

[^attach-3]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.

[^attach-4]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.

[^attach-5]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.

[^attach-6]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.

[^attach-7]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.

[^attach-8]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.



## Required roles and permissions for enterprises
{: #roles-enterprises}

If you are working within an enterprise account and want to configure scans for {{site.data.keyword.compliance_short}}, you must have additional permissions for the enterprise service. You can choose to provide Administrator access or create a custom role with the following actions. For help creating a role, see [Assigning access](/docs/security-compliance?topic=security-compliance-assign-roles).

* `enterprise.enterprise.attach-config-rules`
* `enterprise.enterprise.detach-config-rules`
* `enterprise.enterprise.update-config-rules`
* `enterprise.account-group.attach-config-rules`
* `enterprise.account-group.detach-config-rules`
* `enterprise.account-group.update-config-rules`
* `enterprise.account.attach-config-rules`
* `enterprise.account.detach-config-rules`
* `enterprise.account.update-config-rules`
* `enterprise.account.retrieve`
* `enterprise.account-group.retrieve`
* `enterprise.enterprise.retrieve`
* `global-search-tagging.resource.read`
