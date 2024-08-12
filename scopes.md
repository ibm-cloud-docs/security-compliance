---

copyright:
  years: 2020, 2024
lastupdated: "2024-08-12"

keywords: scope, subscope, view results access, 

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Targeting resources to evaluate
{: #scopes}

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

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Scopes**, and click **Create**.
2. Provide a name and a description of your scope. Then, click **Next**.
3. Define your scope.

   1. Select a **{{site.data.keyword.cloud_notm}}** as your environment.
   2. Select the types of resources that you want to evaluate. Options include {{site.data.keyword.cloud_notm}} native services, and Kubernetes clusters or VMware workloads that run on {{site.data.keyword.cloud_notm}}.

      To evaluate Kubernetes clusters or VMware workloads that run on {{site.data.keyword.cloud_notm}}, an extra configuration is required. If you select either option, you must connect either the Workload Protection or Caveonix Cloud Platform integrations.
      {: note}
   
   3. Select the resources that you want to evaluate.
   4. Exclude any resources that you don't want to evaluate from your scope. For example, any accounts that are used only for testing.
   5. Click **Next**.

4. Review your selections and click **Create**.

Next, you might want to [segment your scope](/docs/security-compliance?topic=security-compliance-subscopes) so that only certain members of your team are able to see the results for specific resources. Alternatively, you can start evaluating your resources by [creating an attachment](/docs/security-compliance?topic=security-compliance-attachments).

### Including resources from another account
{: #cross-account-target}

To create a scope that contains resources from another account within {cloud}, you can use the {{site.data.keyword.compliance_short}} UI.

1. Create a [trusted profile](/docs/account?topic=account-create-trusted-profile) that provides the following access.

   | Service | Role | 
   |:--------|:-----|
   | All Account Management services | `Viewer`   \n `Service Configuration Reader`|
   | Kubernetes Service | `Reader`   \n `Viewer`   \n `Administrator`   \n `Service Configuration Reader` |
   | All Identity and Access enabled services | `Reader`   \n `Viewer`   \n `Service Configuration Reader` |
   {: caption="Table 1. Required permissions for your trusted profile" caption-side="top"}
   
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

Some resources require more access in order for {{site.data.keyword.compliance_short}} to view all of the configurations associated with it. To evaluate SaaS services, you must add the account in which it resides as a target account. Then, provide an IAM API key that has the required permissions for {{site.data.keyword.compliance_short}} to be able to perform the evaluation.

Currently, only Watson Machine Learning services require these steps. Additionally, the [AI Security Guardrails 2.0](/docs/security-compliance?topic=security-compliance-ai-security-change-log&interface=ui) profile is the only profile that is currently configured to evaluate SaaS products.
{: important}

1. Set up Secrets Manager.

   1. If you don't already have one, create an instance of [{{site.data.keyword.secrets-manager_short}}](/docs/secrets-manager?topic=secrets-manager-create-instance).
   2. Create a service ID that has the required permissions to view your resource.
   3. Create an API key. 

1. Create a [trusted profile](/docs/account?topic=account-create-trusted-profile) that provides the following access.

   | Service | Role | 
   |:--------|:-----|
   | All Account Management services | `Viewer`   \n `Service Configuration Reader`|
   | All Identity and Access enabled services | `Reader`   \n `Viewer`   \n `Service Configuration Reader` |
   {: caption="Table 1. Required permissions for your trusted profile" caption-side="top"}

2. Add a target account.

   1. From the {{site.data.keyword.compliance_short}} navigation, click **Settings**.
   2. In the **Targets** section, click **Add**.
   3. Specify a unique name for your target account.
   4. Specify the ID of the account.
   5. Specify the ID of the trusted profile that you created in step 1.
   6. Click **Add**.

3. Add an API 


## Creating a scope for resources that do not run on {{site.data.keyword.cloud_notm}}
{: #create-scope-other-provider}
{: ui}

You can create a scope by using the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Scopes**, and click **Create**.
2. Provide a name and a description of your scope. Then, click **Next**.

   Be sure to be as specific as possible so that other members of your team are able to quickly find the scan results.\
   {: tip}

3. Define your scope.

   1. Select either **Amazon Web Services** or **Microsoft Azure** as your environment.
   2. Connect the **Workload Protect** integration.
   3. Select the resources that you want to evaluate by providing the **Locations**, **Accounts**, **Organizations**, and any **Labels**.
   4. Optionally, provide the information that is required to evaluate Kubernetes clusters that run on your selected environment.

4. Review your selections and click **Create**.

Next, [create an attachment](/docs/security-compliance?topic=security-compliance-attachments) to start evaluating your resources. 

