---

copyright:
  years: 2020, 2023
lastupdated: "2023-07-08"

keywords: IAM access for {{site.data.keyword.compliance_short}}, permissions for {{site.data.keyword.compliance_short}}, identity and access management for {{site.data.keyword.compliance_short}}, roles for {{site.data.keyword.compliance_short}}, actions for {{site.data.keyword.compliance_short}}, assigning access for {{site.data.keyword.compliance_short}}

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Managing IAM access for {{site.data.keyword.compliance_short}}
{: #access-management}

Access to the {{site.data.keyword.compliance_full}} is controlled by {{site.data.keyword.iamshort}} (IAM). Every user that accesses the {{site.data.keyword.compliance_short}} in your account must be assigned an access policy, with a defined platform IAM role. The policy determines which actions that a user can perform within the context of the {{site.data.keyword.compliance_short}}.

Policies enable access to be granted at different levels. Some options include the following actions:

* Access to manage profiles and controls
* Access to view security and compliance posture and results
* Access to manage event notifications


## Roles and permissions
{: #iam-roles}

After you define the level of access that a user might need, you can assign them a platform access role. Review the following tables that outline which roles are required to perform actions within the {{site.data.keyword.compliance_short}}.

The following tables list the platform access roles that are required to manage collectors, credentials, scopes, validations, and profiles in your accounts.

| Action                          | Description                      | Minimum required role |
| :------------------------------ | :------------------------------- | :---------------- |
| `compliance.admin.settings-read`|	View {{site.data.keyword.compliance_short}} settings for your account.  | Viewer |
| `compliance.admin.settings-update` | Update {{site.data.keyword.compliance_short}} settings for your account. | Administrator |
| `compliance.admin.test-event-send` | Send a test event to a connected {{site.data.keyword.en_short}} service instance. | Administrator |
| `compliance.posture-management.attachments-create` | Create an attachment. | Editor[^attach-1] |
| `compliance.posture-management.attachments-delete` | Delete an attachment. | Editor[^attach-2] |
| `compliance.posture-management.attachments-read` | View the available attachments in your account. | Viewer[^attach-3] |
| `compliance.posture-management.attachments-update` | Update an attachment. | Editor[^attach-4] |
| `compliance.posture-management.control-libraries-create` | Create a control library. | Editor |
| `compliance.posture-management.control-libraries-delete` | Delete a control library. | Editor |
| `compliance.posture-management.control-libraries-read` | View the available control libraries in your account. | Viewer |
| `compliance.posture-management.control-libraries-update` | Update a control library. | Editor |
| `compliance.posture-management.control-library-create` | Create a control library. | Editor |
| `compliance.posture-management.control-library-delete` | Delete a control library. | Editor |
| `compliance.posture-management.control-library-read` | View the details of a control library.| Viewer |
| `compliance.posture-management.control-library-update` | Update a control library. | Editor |
| `compliance.posture-management.controls-create` | Add a control to a profile. | Editor |
| `compliance.posture-management.controls-delete` | Delete a control. | Editor |
| `compliance.posture-management.controls-read` | View the controls that you can add to a profile. | Viewer |
| `compliance.posture-management.controls-update` | Update an existing control. | Editor |
| `compliance.posture-management.dashboard-view` | View hybrid cloud results. | Viewer|
| `compliance.posture-management.integrations-create` | Create an integration in {{site.data.keyword.compliance_short}}. | Operator |
| `compliance.posture-management.integrations-delete` | Delete an integration in {{site.data.keyword.compliance_short}}. | Editor |
| `compliance.posture-management.integrations-read` | View an integration in {{site.data.keyword.compliance_short}}. | Viewer |
| `compliance.posture-management.integrations-update` | Update an integration in {{site.data.keyword.compliance_short}}. | Operator |
| `compliance.posture-management.profiles-create` | Create a profile. | Editor |
| `compliance.posture-management.profiles-delete` | Delete a profile. | Editor |
| `compliance.posture-management.profiles-read` | View profiles. | Viewer |
| `compliance.posture-management.profiles-update` | Update a profile. | Editor |
| `compliance.posture-management.reports-create` | Download a report. | Operator |
| `compliance.posture-management.reports-list` | View IBM Cloud results. | Operator |
| `compliance.posture-management.reports-read` | View IBM Cloud results. | Operator |
| `compliance.posture-management.scans-create` | Creat a scan. | Editor |
| `compliance.posture-management.scans-delete` | Delete a scan. | Editor |
| `compliance.posture-management.scans-read` | View scans. | Viewer |
| `compliance.posture-management.scans-update` | Update scans. | Editor |
| `compliance.posture-management.scopes-create` | Create a scope. | Editor |
| `compliance.posture-management.scopes-delete` | Delete a scope. | Editor |
| `compliance.posture-management.scopes-read` | View scopes. | Viewer |
| `compliance.posture-management.scopes-update` | Edit a scope. | Editor |
{: caption="Table 1. IAM user roles and actions" caption-side="top"}

[^attach-1]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.

[^attach-2]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.

[^attach-3]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.

[^attach-4]: To create an attachment within an enterprise, you must also have permissions for the enterprise. You can provide Administrator access to the entire enterprise or create a custom role using the actions found in the following section.


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

