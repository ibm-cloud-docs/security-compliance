---

copyright:
  years: 2021
lastupdated: "2021-03-01"

keywords: IAM access for {{site.data.keyword.compliance_short}}, permissions for {{site.data.keyword.compliance_short}}, identity and access management for {{site.data.keyword.compliance_short}}, roles for {{site.data.keyword.compliance_short}}, actions for {{site.data.keyword.compliance_short}}, assigning access for {{site.data.keyword.compliance_short}}

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


# Assigning access
{: #access-management}

Access to the {{site.data.keyword.compliance_full}} is controlled by {{site.data.keyword.iamshort}} (IAM). Every user that accesses the {{site.data.keyword.compliance_short}} in your account must be assigned an access policy with a defined platform IAM role. The policy determines which actions a user can perform within the context of the {{site.data.keyword.compliance_short}}.

Policies enable access to be granted at different levels. Some of the options include the following actions:

* Access to manage profiles and controls
* Access to view security and compliance posture and results
* Access to manage rules for governing the use of resources

## Assigning roles in the console
{: #assign-roles}

As an account owner, you are automatically assigned Administrator platform access to the {{site.data.keyword.compliance_short}} so that you can further assign roles and customize access policies for others.

To assign access, you can use the **Access (IAM)** section of the console.

1. [Create an access group](/docs/account?topic=account-groups#create_ag) for the type of users that you want to give access to and add those users to the group. For example, you might have a team of compliance specialists that need the same level of access.
2. After you create a group and add users, go to the **Manage > Access (IAM) > Access Groups** page of the console.
3. Select a table row, and click the **Actions** icon ![Actions icon](../icons/actions-icon-vertical.svg) to open a list of options for that access group.
4. From the options menu, click **Assign access**.
4. Select **Account management**.
5. From the list of services, select **{{site.data.keyword.compliance_short}}**.
6. Enter the compliance component that you want to assign access to.
    1. To assign access for using profiles to [monitor accounts for compliance](#compliance-roles), enter _posture-management_.
    2. To assign access for using rules to [govern the use of resources](#governance-roles), enter _configuration-governance_.
7. Choose a combination of [platform access roles](#iam-roles) to assign to the user.
8. Click **Add**.
9. Review your selections and click **Assign**.

## Roles and permissions
{: #iam-roles}

After you define the level of access that a user might need, you can assign them a platform access role. Review the following tables that outline which roles are required to perform actions within the {{site.data.keyword.compliance_short}}.

### Roles for monitoring accounts for compliance
{: #compliance-roles}

The following tables list the platform access roles that are required to manage collectors, credentials, scopes, validations, and profiles in your accounts.

| Action                                                | Description                                                  | Role                                    |
| :---------------------------------------------------- | :----------------------------------------------------------- | :-------------------------------------- |
| `compliance.posture-management.credentials-read`      | View credentials.                                            | Viewer, Operator, Editor, Administrator |
| `compliance.posture-management.credentials-create`    | Create a credential.                                         | Editor, Administrator                   |
| `compliance.posture-management.credentials-update`    | Update an existing credential.                               | Editor, Administrator                   |
| `compliance.posture-management.credentials-delete`    | Delete a credential.                                         | Editor, Administrator                   |
| `compliance.posture-management.credentialsmap-read`   | View mappings between credentials and scopes.                | Viewer, Operator, Editor, Administrator |
| `compliance.posture-management.credentialsmap-create` | Map credentials to a scope.                                  | Editor, Administrator                   |
| `compliance.posture-management.credentialsmap-update` | Update an existing mapping between a credential and a scope. | Editor, Administrator                   |
| `compliance.posture-management.credentialsmap-delete` | Delete a mapping.                                            | Editor, Administrator                   |
{: caption="Table 1. IAM user roles and actions" caption-side="top"}
{: #credentials-access}
{: tab-title="Credentials"}
{: tab-group="compliance"}
{: class="simple-tab-table"}

| Action                                            | Description                   | Role                                    |
| :------------------------------------------------ | :---------------------------- | :-------------------------------------- |
| `compliance.posture-management.collectors-read`   | View collectors.              | Viewer, Operator, Editor, Administrator |
| `compliance.posture-management.collectors-create` | Create a collector.           | Editor, Administrator                   |
| `compliance.posture-management.collectors-update` | Update an existing collector. | Editor, Administrator                   |
| `compliance.posture-management.collectors-delete` | Delete a collector.           | Editor, Administrator                   |
{: caption="Table 2. IAM user roles and actions" caption-side="top"}
{: #collectors-access}
{: tab-title="Collectors"}
{: tab-group="compliance"}
{: class="simple-tab-table"}

| Action                                        | Description               | Role                                    |
| :-------------------------------------------- | :------------------------ | :-------------------------------------- |
| `compliance.posture-management.scopes-read`   | View scopes.              | Viewer, Operator, Editor, Administrator |
| `compliance.posture-management.scopes-create` | Create a scope.           | Editor, Administrator                   |
| `compliance.posture-management.scopes-update` | Update an existing scope. | Editor, Administrator                   |
| `compliance.posture-management.scopes-delete` | Delete a scope.           | Editor, Administrator                   |
{: caption="Table 3. IAM user roles and actions" caption-side="top"}
{: #scopes-access}
{: tab-title="Scopes"}
{: tab-group="compliance"}
{: class="simple-tab-table"}

| Action                                             | Description                         | Role                                    |
| :------------------------------------------------- | :---------------------------------- | :-------------------------------------- |
| `compliance.posture-management.validations-read`   | View validation scans.              | Viewer, Operator, Editor, Administrator |
| `compliance.posture-management.validations-create` | Run a validation scan.              | Editor, Administrator                   |
| `compliance.posture-management.validations-update` | Update an existing validation scan. | Editor, Administrator                   |
| `compliance.posture-management.validations-delete` | Delete a validation scan.           | Editor, Administrator                   |
{: caption="Table 4. IAM user roles and actions" caption-side="top"}
{: #validations-access}
{: tab-title="Validations"}
{: tab-group="compliance"}
{: class="simple-tab-table"}

| Action                                        | Description                                          | Role                                    |
| :-------------------------------------------- | :--------------------------------------------------- | :-------------------------------------- |
| `compliance.posture-management.values-read`   | View the parameters that are associated with a goal. | Viewer, Operator, Editor, Administrator |
| `compliance.posture-management.values-create` | Add parameters to an existing goal.                  | Editor, Administrator                   |
| `compliance.posture-management.values-update` | Update the parameters of an existing goal.           | Editor, Administrator                   |
| `compliance.posture-management.values-delete` | Delete a parameter.                                  | Editor, Administrator                   |
{: caption="Table 5. IAM user roles and actions" caption-side="top"}
{: #goals-access}
{: tab-title="Goals"}
{: tab-group="compliance"}
{: class="simple-tab-table"}

| Action                                          | Description                                                | Role                                    |
| :---------------------------------------------- | :--------------------------------------------------------- | :-------------------------------------- |
| `compliance.posture-management.controls-read`   | View the available controls that you can add to a profile. | Viewer, Operator, Editor, Administrator |
| `compliance.posture-management.controls-create` | Add a control to a profile.                                | Editor, Administrator                   |
| `compliance.posture-management.controls-update` | Update an existing control.                                | Editor, Administrator                   |
| `compliance.posture-management.controls-delete` | Delete a control.                                          | Editor, Administrator                   |
{: caption="Table 6. IAM user roles and actions" caption-side="top"}
{: #controls-access}
{: tab-title="Controls"}
{: tab-group="compliance"}
{: class="simple-tab-table"}

| Action                                          | Description                 | Role                                    |
| :---------------------------------------------- | :-------------------------- | :-------------------------------------- |
| `compliance.posture-management.profiles-read`   | View profiles.              | Viewer, Operator, Editor, Administrator |
| `compliance.posture-management.profiles-create` | Create a profile.           | Editor, Administrator                   |
| `compliance.posture-management.profiles-update` | Update an existing profile. | Editor, Administrator                   |
| `compliance.posture-management.profiles-delete` | Delete a profile.           | Editor, Administrator                   |
{: caption="Table 7. IAM user roles and actions" caption-side="top"}
{: #profiles-access}
{: tab-title="Profiles"}
{: tab-group="compliance"}
{: class="simple-tab-table"}

| Action                                      | Description             | Role                                    |
| :------------------------------------------ | :---------------------- | :-------------------------------------- |
| `compliance.posture-management.tags-read`   | View tags.              | Viewer, Operator, Editor, Administrator |
| `compliance.posture-management.tags-create` | Create a tag.           | Editor, Administrator                   |
| `compliance.posture-management.tags-update` | Update an existing tag. | Editor, Administrator                   |
| `compliance.posture-management.tags-delete` | Delete a tag.           | Editor, Administrator                   |
{: caption="Table 8. IAM user roles and actions" caption-side="top"}
{: #tags-access}
{: tab-title="Tags"}
{: tab-group="compliance"}
{: class="simple-tab-table"}

| Action                                      | Description      | Role                                    |
| :------------------------------------------ | :--------------- | :-------------------------------------- |
| `compliance.posture-management.events-view` | View audit logs. | Viewer, Operator, Editor, Administrator |
{: caption="Table 9. IAM user roles and actions" caption-side="top"}
{: #audit-log-access}
{: tab-title="Audit logs"}
{: tab-group="compliance"}
{: class="simple-tab-table"}

### Roles for governing the use of resources
{: #governance-roles}

The following tables list the platform access roles that are required to manage configuration rules in your accounts.

| Action                                                   | Description                                         | Role                                    |
| :------------------------------------------------------- | :-------------------------------------------------- | :-------------------------------------- |
| `compliance.configuration-governance.rules-read`         | View rules.                                         | Viewer, Operator, Editor, Administrator |
| `compliance.configuration-governance.rules-create`       | Create a rule.                                      | Editor, Administrator                   |
| `compliance.configuration-governance.rules-update`       | Update an existing rule.                            | Editor, Administrator[^scopes-1]        |
| `compliance.configuration-governance.rules-delete`       | Delete a rule.                                      | Editor, Administrator[^scopes-2]        |
{: caption="Table 10. IAM user roles and actions" caption-side="top"}
{: #rules-access}
{: tab-title="Rules"}
{: tab-group="config"}
{: class="simple-tab-table"}

| Action                                                   | Description                                         | Role                                    |
| :------------------------------------------------------- | :-------------------------------------------------- | :-------------------------------------- |
| `compliance.configuration-governance.attachments-read`   | View the attachments that are available for a rule. | Viewer, Operator, Editor, Administrator |
| `compliance.configuration-governance.attachments-create` | Create an attachment between a rule and a scope.    | Editor, Administrator[^scopes-3]        |
| `compliance.configuration-governance.attachments-update` | Update an existing attachment.                      | Editor, Administrator[^scopes-4]        |
| `compliance.configuration-governance.attachments-delete` | Delete an attachment.                               | Editor, Administrator[^scopes-5]        |
{: caption="Table 11. IAM user roles and actions" caption-side="top"}
{: #attachments-access}
{: tab-title="Attachments"}
{: tab-group="config"}
{: class="simple-tab-table"}

| Action                                                   | Description                                         | Role                                    |
| :------------------------------------------------------- | :-------------------------------------------------- | :-------------------------------------- |
| `compliance.configuration-governance.results-read`   | View config rule results. | Viewer, Operator, Editor, Administrator |
{: caption="Table 11. IAM user roles and actions" caption-side="top"}
{: #results-access}
{: tab-title="Results"}
{: tab-group="config"}
{: class="simple-tab-table"}

[^scopes-1]: If the rule is attached to a scope, you must also have Administrator access to the scope.

[^scopes-2]: If the rule is attached to a scope, you must also have Administrator access to the scope.

[^scopes-3]: You must also have Administrator access to the scope.

[^scopes-4]: You must also have Administrator access to the scope.

[^scopes-5]: You must also have Administrator access to the scope.


For more information about assigning user roles in the console, see [Managing access to resources](/docs/account?topic=account-assign-access-resources).
{: tip}








