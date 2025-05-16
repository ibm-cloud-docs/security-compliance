---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: scope, subscope, view results access, 

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Targeting resources to evaluate
{: #scopes}


As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


To run an evaluation by using {{site.data.keyword.compliance_full}}, you must target the specific resources that you want to scan by creating a scope. To learn more about subscopes and how they work, see [How does {{site.data.keyword.compliance_short}} work](/docs/security-compliance?topic=security-compliance-posture-management).
{: shortdesc}

## Before you begin
{: #before-scopes}

Before you get started, be sure that you have the following prerequisites.

* The required level of access to create and manage scopes. To manage scopes, you must have [the **Writer** service role or higher](/docs/security-compliance?topic=security-compliance-access-management).


## Creating a scope for {{site.data.keyword.cloud_notm}} resources
{: #create-scope-ibm}
{: ui}

You can create a scope by using the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, go to the **Resource list** page and select your instance of {{site.data.keyword.compliance_short}}.
2. In your instance of {{site.data.keyword.compliance_short}}, go to the **Scopes** page and click **Create**.
3. Provide a name and a description of your scope. Then, click **Next**.
4. Define your scope.

   1. Select a **{{site.data.keyword.cloud_notm}}** as your environment.
   2. Select the types of resources that you want to evaluate. Options include {{site.data.keyword.cloud_notm}} native services, and Kubernetes clusters or VMware workloads that run on {{site.data.keyword.cloud_notm}}.

      To evaluate Kubernetes clusters or VMware workloads that run on {{site.data.keyword.cloud_notm}}, an extra configuration is required. If you select either option, you must connect either the Workload Protection or Caveonix Cloud Platform integrations.
      {: note}
   
   3. Select the resources that you want to evaluate.
   4. Exclude any resources that you don't want to evaluate from your scope. For example, any accounts that are used only for testing.
   5. Click **Next**.

5. Review your selections and click **Create**.

Next, you might want to [segment your scope](/docs/security-compliance?topic=security-compliance-subscopes) so that only certain members of your team are able to see the results for specific resources. Alternatively, you can start evaluating your resources by [creating an attachment](/docs/security-compliance?topic=security-compliance-attachments).

### Including resources from another account
{: #cross-account-target}

To scan resources in another {{site.data.keyword.cloud_notm}}, you can use the {{site.data.keyword.compliance_short}} UI to add a target before creating your scope.

1. Create a [trusted profile](/docs/account?topic=account-create-trusted-profile) that provides the following access.

   | Service | Role | 
   |:--------|:-----|
   | All Account Management services | `Viewer`   \n `Service Configuration Reader`|
   | Kubernetes Service | `Reader`   \n `Viewer`   \n `Administrator`   \n `Service Configuration Reader` |
   | All Identity and Access enabled services | `Reader`   \n `Viewer`   \n `Service Configuration Reader` |
   {: caption="Required permissions for your trusted profile" caption-side="top"}
   
   The Kubernetes Service access policy is required to run the Red Hat OpenShift Compliance Operator (OSCO) scan when an attachment is created.
   {: note}

2. Add a target account.

   1. From the {{site.data.keyword.compliance_short}} navigation, click **Settings**.
   2. In the **Targets** section, click **Add**.
   3. Specify a unique name for your target account.
   4. Specify the ID of the account.
   5. Specify the ID of the trusted profile that you created in step 1.
   6. Click **Add**.

When you create a scope, the account that you added as a target is shown as an option.

### Including SaaS services in your scope
{: #saas-scope}

Some resources require more access in order for {{site.data.keyword.compliance_short}} to view all of the configurations associated with it. To evaluate SaaS services, you must add the account in which they reside as a target account. Then, provide an IAM API key that has the required permissions for {{site.data.keyword.compliance_short}} to be able to perform the evaluation.

Currently, only Watson Machine Learning services require these steps. Additionally, the [AI Security Guardrails 2.0](/docs/security-compliance?topic=security-compliance-ai-security-change-log&interface=ui) profile is the only profile that's configured for SaaS products.
{: important}

1. If you don't already have one, create an instance of [{{site.data.keyword.secrets-manager_short}}](/docs/secrets-manager?topic=secrets-manager-create-instance).

2. In the IAM UI, make the following configurations.

   1. Go to **Manage** > **Access (IAM)** > **Service IDs** and create a [service ID](/docs/account?topic=account-serviceids&interface=ui#create_serviceid) with the **Viewer** Role on your SaaS service.
   2. From the service ID, create an [API key](/docs/account?topic=account-serviceidapikeys&interface=ui#create_service_key).
   3. Go to **Manage** > **Access (IAM)** > **Authorizations** and create an authorization between {{site.data.keyword.compliance_short}} and {{site.data.keyword.secrets-manager_short}} with the following values.

      * **Source**: The account ID of the account that contains the {{site.data.keyword.compliance_short}} instance that you want to use to evaluate.
      * **Service**: {{site.data.keyword.compliance_short}}.
      * **Resources**: The API key that you created in Step 2.
      * **Target**: {{site.data.keyword.secrets-manager_short}}.
      * **Resources**: The instance ID.
      * **Role**: *SecretsReader*.

   4. Create a [trusted profile](/docs/account?topic=account-create-trusted-profile) that provides the following access.

      | Service | Role | 
      |:--------|:-----|
      | All Account Management services | `Viewer`   \n `Service Configuration Reader`|
      | Kubernetes Service | `Reader`   \n `Viewer`   \n `Administrator`   \n `Service Configuration Reader` |
      | All Identity and Access enabled services | `Reader`   \n `Viewer`   \n `Service Configuration Reader` |
      {: caption="Required permissions for your trusted profile" caption-side="top"}

3. In your instance of {{site.data.keyword.secrets-manager_short}}, create an [arbitrary](/docs/secrets-manager?topic=secrets-manager-arbitrary-secrets) or [IAM credentials](/docs/secrets-manager?topic=secrets-manager-iam-credentials) secret to store the API key that you previously created. 

   If you are using an arbitrary secret, save the API key as the secret value. If you choose to use an IAM credentials secret, use the service ID that is associated with the API key that you created.

   The secret must remain unlocked for {{site.data.keyword.compliance_short}} to be able to access and read it.
   {: important}

4. Create a Target.

   1. From the {{site.data.keyword.compliance_short}} navigation, click **Settings**.
   2. In the **Targets** section, click **Add**.
   3. Specify a unique name for your target account.
   4. Specify the ID of the account.
   5. Specify the ID of the trusted profile that you created in step 1.
   6. Click **Add**.

4. Assign credentials for your target account.

   1. In the **Settings > Targets** section, expand the row of your target account. 
   2. Click **Assign credentials**.
   3. On the **Select credentials** tab, make the following selections. Then, click **Next**.

      1. Select the instance of {{site.data.keyword.secrets-manager_short}} that you want to work with.
      2. Select the secret group that the secret is part of.
      3. Select the type of secret that you created.
      4. Select your secret.

      Alternatively, you can use the **Locate by CRN** tab to find your secret.
      {: tip}

   4. Select the services that you want to evaluate and click **Add** icon (**+**) to add them. Then, click **Assign**.

By completing these steps, you've added the required credentials and your SaaS services will be an option when you [create a scope](/docs/security-compliance?topic=security-compliance-scopes). To start evaluating your resources, you must [create an attachment](/docs/security-compliance?topic=security-compliance-attachments) after creating your scope.



## Creating a scope for resources that do not run on {{site.data.keyword.cloud_notm}}
{: #create-scope-other-provider}
{: ui}

You can create a scope that contains resouces in other environments by using the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, go to the **Resource list** page and select your instance of {{site.data.keyword.compliance_short}}.
2. In your instance of {{site.data.keyword.compliance_short}}, go to the **Scopes** page and click **Create**.
3. Provide a name and a description of your scope. Then, click **Next**.

   Be sure to be as specific as possible so that other members of your team are able to quickly find the scan results.
   {: tip}

4. Define your scope.

   1. Select either **Amazon Web Services** or **Microsoft Azure** as your environment.
   2. Connect the **Workload Protect** integration.
   3. Select the resources that you want to evaluate by providing the **Locations**, **Accounts**, **Organizations**, and any **Labels**.
   4. Optionally, provide the information that is required to evaluate Kubernetes clusters that run on your selected environment.

5. Review your selections and click **Create**.

Next, [create an attachment](/docs/security-compliance?topic=security-compliance-attachments) to start evaluating your resources. 
