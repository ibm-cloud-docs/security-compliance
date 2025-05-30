---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: "IAM access for {{site.data.keyword.compliance_short}}, permissions for {{site.data.keyword.compliance_short}}, identity and access management for {{site.data.keyword.compliance_short}}, roles for {{site.data.keyword.compliance_short}}, actions for {{site.data.keyword.compliance_short}}, assigning access for {{site.data.keyword.compliance_short}}"

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Assigning access to {{site.data.keyword.compliance_short}}
{: #assign-roles}

As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


As an account owner, you are automatically assigned Administrator platform access to {{site.data.keyword.compliance_short}} so that you can further assign roles and customize access policies for others.

## Assigning access for an account
{: #assign-access-scc}

1. [Create an access group](/docs/account?topic=account-groups&interface=ui#create_ag) for the type of users that you want to give access to and add those users to the group. For example, you might have a team of compliance specialists that all need the same level of access.
2. After you create a group and add users, go to the **Manage > Access (IAM) > Access Groups** page of the console.
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



## Assigning access for an Enterprise
{: #assign-access-enterprise}

If you are working in an enterprise account, you must also assign permissions for the enterprise service.

You can assign *Administrator* access for the service, or you can create a custom role. When you assign permissions for an enterprise, you can give access to the full enterprise or specific accounts or account groups. To learn more about recommendations for enterprises, see [Best practices for enterprises](/docs/security-compliance?topic=security-compliance-best-practices#bp-enterprise).
{: tip}

1. In the console, go to **Manage > Access (IAM) > Roles** and click **Create**.
2. Give your role a name, programmatic ID, and description. For example, *Compliance focal*, *ComplianceFocal*, and *Permissions that are required for compliance focal to work with {{site.data.keyword.compliance_short}}*.
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
4. Review your selections to ensure that you added the correct permissions and click **Create**.
5. Assign that role to the user or group that needs access to {{site.data.keyword.compliance_short}}.


## Assigning access to a scope or subscope
{: #assign-access-scopes}

To allow for certain users of your account to view results without having access to the rest of your {{site.data.keyword.compliance_short}} instance, you must assign the following policies for the scope or subscope that you want to provide access to.

1. Get your scope or subscope ID from the {{site.data.keyword.compliance_short}} UI.
2. Navigate to the IAM UI.
	1. Click **Manage** > **Access (IAM)** > **Users**, and select the user that you want to provide access to.

	   Be sure to start from the **Access groups** tab if you're working with a group.
	   {: tip}

	2. Click **Access** > **Assign access**.

3. Give your user or access group permission to view {{site.data.keyword.compliance_short}} instances.

	1. Select **{{site.data.keyword.compliance_short}}** and then click **Next**.
	2. For resources, select **All** or provide the ID for a specific instance of the service.
	3. For permissions, select **InstanceViewer**.
	4. Click **Add**.

4. Give your user or access group permission to read results for a specific scope or subscope.

	1. Select **{{site.data.keyword.compliance_short}}**, and then click **Next**.
	2. Select **Specific resources**. Then, select either **Scope ID** or **Subscope ID**.
	3. Input the ID that you copied in step 1 as the **Value**. Then, click **Next**.
	4. For permissions, select **Reader**. Then, click **Next**.
	5. Click **Add**.

5. Review your selections in the side panel.
6. Click **Assign**.

## Assigning access to Satellite
{: #assign-access-sat}

To evaluate the resources that run on Satellite, you must create a service-to-service authorization between {{site.data.keyword.compliance_short}} and Satellite. To create a new authorization through the IAM UI, you can use the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, go to **Manage > Access (IAM) > Authorizations**.
2. Click **Create**.
3. Select **{{site.data.keyword.compliance_short}}** from the **Source service** drop-down.
4. Leave **All resources** selected.
5. Select **Satellite** from the **Target service** drop-down.
6. Leave **All resources** selected.
7. Check **Viewer** to provide the required access.
8. Click **Authorize**.
