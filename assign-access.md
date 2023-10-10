---

copyright:
  years: 2020, 2023
lastupdated: "2023-10-10"

keywords: IAM access for {[scc]}, permissions for {[scc]}, identity and access management for {[scc]}, roles for {[scc]}, actions for {[scc]}, assigning access for {[scc]}

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Assigning access to {[scc]}
{: #assign-roles}

As an account owner, you are automatically assigned Administrator platform access to {[scc]} so that you can further assign roles and customize access policies for others.

## Assigning access for an account
{: #assign-access-scc}

1. [Create an access group](/docs/account?topic=account-groups#create_ag) for the type of users that you want to give access to and add those users to the group. For example, you might have a team of compliance specialists that all need the same level of access.
2. After you create a group and add users, go to the **Manage > Access (IAM) > Access Groups** page of the console.
3. Select the name of the group that you want to assign access to.
4. Click **Access > Assign access**.
5. Assign the following permissions by selecting a service and reviewing the available roles and actions that are available for each option.
   
	| Service | Minimum required permissions |
	|---------|----------------------|
	| {[scc]} | Administrator |
	| Cloud Object Storage | Reader |
	| Event Notifications | Reader |
	{: caption="Table. Minimum required permissions" caption-side="top"}

	To review the full list of which permissions are required for each action and assign more granular access to {[scc]}, see [IAM actions for {[scc]}]({[link]}-access-management).
	{: note}

6. Click **Add**.
7. Review your selections and click **Assign**.



## Assigning access for an Enterprise
{: #assign-access-enterprise}

If you are working in an enterprise account, you must also assign permissions for the enterprise service. 

You can assign *Administrator* access for the service, or you can create a custom role. When you assign permissions for an enterprise, you can give access to the full enterprise or specific accounts or account groups. To learn more about recommendations for enterprises, see [Best practices for enterprises]({[link]}-best-practices#bp-enterprise).
{: tip}

1. In the Console, go to **Manage > Access (IAM) > Roles** and click **Create**.
2. Give your role a name, programmatic ID, and description. For example, *Compliance focals*, *ComplianceFocals*, and *Permissions required for compliance focals to work with {[scc]}*.
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


## Assigning access to Satellite
{: #assign-access-sat}

To evaluate the resources that run on Satellite, you must create a service-to-service authorization between {[scc]} and Satellite. To create a new authorization through the IAM UI, you can use the following steps.

1. In the {[cloud]} console, go to **Manage > Access (IAM) > Authorizations**.
2. Click **Create**.
3. Select **{[scc]}** from the **Source service** drop-down.
4. Leave **All resources** selected.
5. Select **Satellite** from the **Target service** drop-down.
6. Leave **All resources** selected.
7. Check **Viewer** to provide the required access.
8. Click **Authorize**.

