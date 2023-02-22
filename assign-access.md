---

copyright:
  years: 2020, 2023
lastupdated: "2023-02-17"

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
{:release-note: data-hd-content-type='release-note'}


# Assigning access to {{site.data.keyword.compliance_short}}
{: #assign-roles}

As an account owner, you are automatically assigned Administrator platform access to the {{site.data.keyword.compliance_short}} so that you can further assign roles and customize access policies for others.


1. [Create an access group](/docs/account?topic=account-groups#create_ag) for the type of users that you want to give access to and add those users to the group. For example, you might have a team of compliance specialists that all need the same level of access.
2. After you create a group and add users, go to the **Manage > Access (IAM) > Access groups** page of the console.
3. Select the name of the group that you want to assign access to.
4. Click **Access > Assign access**.
5. Assign the following permissions by selecting a service and reviewing the available roles and actions that are available for each option.
   
	| Service | Minimum required permissions |
	|---------|----------------------|
	| {{site.data.keyword.compliance_short}} | Administrator |
	| Cloud Object Storage | Reader |
	| Event Notifications | Reader |
	{: caption="Table. Minimum required permissions" caption-side="top"}

	To review the full list of which permissions are required for each action and assign more granular access to {{site.data.keyword.compliance_short}}, see [IAM actions for {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-access-management).
	{: note}

6. Click **Add**.
7. Review your selections and click **Assign**.
8. Enterprises: If you are working in an enterprise account, you must also assign permissions for the enterprise service. 

	You can assign *Administrator* access for the service, or you can create a custom role. When you assign permissions for an enterprise you can give access to the full enterprise or specific accounts or account groups. To learn more about recommendations for enterprises, see [Best practices for enterprises](/docs/security-compliance?topic=security-compliance-best-practices#bp-enterprise).

	1. In the Console, go to **Manage > Access (IAM) > Roles** and click **Create**.
	2. Give your role a name, programatic ID, and description. For example, *Compliance focals*, *ComplianceFocals*, and *Permissions required for compliance focals to work with {{site.data.keyword.compliance_short}}*.
	3. From the **Service** drop-down, select **Enterprise**, and then add the following actions.
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
	4. Review your selections to ensure you've added the correct permissions and click **Create**.



If you are working with the collector-based architecture, you must assign additional access for your credentials. For more information, see [Assigning the required permissions](/docs/security-compliance?topic=security-compliance-permissions).
{: note}


