---

copyright:
  years: "2024"
lastupdated: "2024-07-10"

keywords: watson machine learning, ai profiles, ai, artificial intelligence, cross-account scanning, secrets-manager, credentials

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Scanning Watson Machine Learning resources
{: #scan-watson-machine-learning} 

You can scan your Watson Machine Learning resources against the [AI Security Guardrails 2.0](/docs/security-compliance?topic=security-compliance-ai-security-change-log&interface=ui) profile by using {{site.data.keyword.compliance_short}}.
{: shortdesc} 

To scan Watson Machine Learning resources in an account with {{site.data.keyword.compliance_short}}, you must use an IAM API key that you store in {{site.data.keyword.secrets-manager_short}} as an IAM credentials or arbitrary secret. After you create a target, as a credential to the target, you must add the API key of an IAM service ID that is part of the IBM watsonx project.

## Before you begin 
{: #scan-watson-machine-learning-prerequisites} 

Before you can scan Watson Machine Learning resources, you must connect your instances of {{site.data.keyword.compliance_short}} and {{site.data.keyword.secrets-manager_short}}. Complete the following tasks before you begin. 

- Create a [service ID](/docs/account?topic=account-serviceids&interface=ui#create_serviceid) with `Viewer` role to access your Watson Machine Learning service. Go to **Manage** > **Access (IAM)** > **Service ID**.

- Create an [API key](/docs/account?topic=account-serviceidapikeys&interface=ui#create_service_key) from that service ID to access the account that contains your Watson Machine Learning service. Go to **Manage** > **Access (IAM)** > **API keys**.

- Create an instance of [{{site.data.keyword.secrets-manager_short}}](/docs/secrets-manager?topic=secrets-manager-create-instance), if you don't have an existing one. 

- In that {{site.data.keyword.secrets-manager_short}} instance, create an [arbitrary](/docs/secrets-manager?topic=secrets-manager-arbitrary-secrets) or [IAM credentials](/docs/secrets-manager?topic=secrets-manager-iam-credentials) secret to store the API key that you want to use to access the account that contains your Watson Machine Learning service. Copy the secret CRN to use later in the process.
  - If you want to use an arbitrary secret, save the API key as the secret value. 
  - If you choose to use an IAM credentials secret, use the service ID that is associated with the API key you created.

  If the IAM credentials secret that you want to use is locked, {{site.data.keyword.compliance_short}} can't access or read it. To regenerate your IAM credentials, you can remove all the locks that are associated with your secret, and try again. To delete locks, navigate to the {{site.data.keyword.secrets-manager_short}} dashboard and go to **Secrets** > **secret name** > **Locks** > **Delete**. For more information, see [Why can't I read a locked IAM credentials secret?](/docs/secrets-manager?topic=secrets-manager-locked-iam-credentials)
  {: note}

- [Create an authorization](/docs/account?topic=account-serviceauth&interface=ui) between the {{site.data.keyword.compliance_short}} instance and the {{site.data.keyword.secrets-manager_short}} instance.
  1. Go to **Manage** > **Access (IAM)** > **Authorizations**.
  2. Create an authorization with the following values. 
    1. In the **Source** section, add the account ID of the account that contains the {{site.data.keyword.compliance_short}} instance as the **Source account**. 
    2. Select {{site.data.keyword.compliance_short}} as the **Service**. 
    3. In the **Resources** field, add the service instance ID. 
    4. In the **Target** section, select {{site.data.keyword.secrets-manager_short}} as the **Service**. 
    5. Add the instance ID in the **Resources** field.
    6. Assign `SecretsReader` as the **Role**. 

- To scan your main account, you can [create a trusted profile](/docs/account?topic=account-create-trusted-profile&interface) with the following access policies and assign the specified roles.

  * All Account Management services (`Viewer`, `Service Configuration Reader`)
  * Kubernetes Service (`Reader`, `Viewer`, `Administrator`, `Service Configuration Reader`)

    This access policy is required to run the Red Hat OpenShift Compliance Operator (OSCO) scan when an attachment is created.
    {: important}

  * All Identity and Access enabled services (`Reader`, `Viewer`, `Service Configuration Reader`)


When you are enabling scanning of resources across accounts, if you add your main account as a target, you must use trusted profiles to run the scans. If you change the trusted profile, the scan results are impacted. To change the trusted profile and avoid issues with your scan results, you must delete the target and all the attachments that are on the account first. Then, you can create a new target with the updated trusted profile. 
{: note}


## Assigning credentials to scan Watson Machine Learning
{: #scan-targets-credentials-create} 

Complete the following steps to set up cross-account scanning of Watson Machine Learning resources.

1. Navigate to your {{site.data.keyword.compliance_short}} instance. 
2. Go to **Settings**.
3. In the **Targets** section, click **Add**.
4. In the **Add target** page, enter the **Name**, **Account ID**, and **Trusted profile ID** of your target account.
5. Click **Add**.
6. In the **What's next** section, click **Assign credentials** to assign credentials that you want to use when you're scanning the Watson Machine Learning resources that are in the target account. 
7. In the **Select credential** tab, you can assign the secret (IAM credentials or arbitrary) that contains the API key that provides access to your Watson Machine Learning instance. You can select **Locate by CRN** to enter the CRN of the secret that you want to use directly. 
8. In the **Locate by instance** tab, click the dropdowns and select the **Secrets Manager instance**, **Secret group**, and **Secret type**. 
9. Select the secret that contains the API key, then click **Next**.
10. Click the add icon to select the Watson Machine Learning instances in your target account that you want to access with this credential. You can assign this credential to all or specific instances of a service. 
11. Click **Assign**. 


## Next steps
{: scan-watson-attachment}

After you assign the credentials, you can start create an attachment against the AI Security Guardrails 2.0 profile to [schedule a recurring scan](/docs/security-compliance?topic=security-compliance-scan-resources&interface=ui#scan-schedule-ui) of your Watson Machine Learning resources. 
