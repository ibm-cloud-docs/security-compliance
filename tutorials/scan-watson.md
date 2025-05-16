---

copyright:
  years: "2025"
lastupdated: "2025-05-16"

keywords: watson machine learning, ai profiles, ai, artificial intelligence, scanning, secrets-manager, credentials

subcollection: security-compliance

content-type: tutorial
services: security-compliance, secrets-manager, account
completion-time: 20m

---

{{site.data.keyword.attribute-definition-list}}


# Evaluate your Watson Machine Learning resources for security and compliance
{: #scan-watson}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, secrets-manager, account"}
{: toc-completion-time="30m"}


As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}

As the focal in charge of setting up the compliance posture in an environment that contains your SaaS services, such as Watson Machine Learning, you can use {{site.data.keyword.compliance_full}}. This tutorial walks you through scanning your Watson Machine Learning resources against the [AI Security Guardrails 2.0](/docs/security-compliance?topic=security-compliance-ai-security-change-log&interface=ui) profile.
{: shortdesc} 

To scan the Watson Machine Learning resources in your account, you use an IAM API key that you store in {{site.data.keyword.secrets-manager_short}} as an IAM credentials or arbitrary secret. After you create a target, you can then add the API key of an IAM service ID that is part of the IBM watsonx project.

## Before you begin 
{: #scan-watson-machine-learning-prerequisites} 

Before you get started, complete the following tasks.

- Make sure that you can create IAM credentials for your organization.
- Create an instance of [{{site.data.keyword.secrets-manager_short}}](/docs/secrets-manager?topic=secrets-manager-create-instance), if you don't have an existing one. 

## Configure the required access permissions for {{site.data.keyword.compliance_short}}
{: #watson-required-access}
{: step}

Before you can scan your watson resources, you must set up the required access permissions.

### Create service credentials
{: #watson-iam-serviceid-apikey}

First, create a service ID and API key that you can later store in your {{site.data.keyword.secrets-manager_short}} instance.

- Create a [service ID](/docs/account?topic=account-serviceids&interface=ui#create_serviceid) with `Viewer` role to access your Watson Machine Learning service. Go to **Manage** > **Access (IAM)** > **Service ID**.

- Create an [API key](/docs/account?topic=account-serviceidapikeys&interface=ui#create_service_key) from that service ID to access the account that contains your Watson Machine Learning service. Go to **Manage** > **Access (IAM)** > **API keys**.

### Authorize {{site.data.keyword.secrets-manager_short}} to connect to {{site.data.keyword.compliance_short}}
{: #watson-secrets-manager-authorization}

Before you can scan your Watson Machine Learning resources, connect your instance of {{site.data.keyword.compliance_short}} and {{site.data.keyword.secrets-manager_short}}. 

[Create an authorization](/docs/account?topic=account-serviceauth&interface=ui) between your {{site.data.keyword.compliance_short}} instance and your {{site.data.keyword.secrets-manager_short}} instance.

   1. Go to **Manage** > **Access (IAM)** > **Authorizations**.
   2. Create an authorization with the following values. 
      1. In the **Source** section, add the account ID of the account that contains the {{site.data.keyword.compliance_short}} instance as the **Source account**. 
      2. Select {{site.data.keyword.compliance_short}} as the **Service**. 
      3. In the **Resources** field, add the service instance ID. 
      4. In the **Target** section, select {{site.data.keyword.secrets-manager_short}} as the **Service**. 
      5. Add the instance ID in the **Resources** field.
      6. Assign `SecretsReader` as the **Role**. 

### Create a trusted profile
{: #watson-trusted-profile}

To scan your account, [create a trusted profile](/docs/account?topic=account-create-trusted-profile&interface) with the following access policies and assign the specified roles.

   * All Account Management services (`Viewer`, `Service Configuration Reader`)
   * Kubernetes Service (`Reader`, `Viewer`, `Administrator`, `Service Configuration Reader`)
   * All Identity and Access enabled services (`Reader`, `Viewer`, `Service Configuration Reader`)

## Store your service credentials in {{site.data.keyword.secrets-manager_short}}
{: #watson-credentials-secrets-manager}
{: step}

Next, it's time to store the API key in Secrets Manager so that {{site.data.keyword.compliance_short}} can access it to scan your Watson Machine Learning resources.

In your instance of Secrets Manager, create an [arbitrary](/docs/secrets-manager?topic=secrets-manager-arbitrary-secrets) or [IAM credentials](/docs/secrets-manager?topic=secrets-manager-iam-credentials) secret to store the API key that you previously created.

If you are using an arbitrary secret, save the API key as the secret value. If you choose to use an IAM credentials secret, use the service ID that is associated with the API key that you created.

The secret must remain unlocked for Security and Compliance Center to be able to access and read it.
{: important}


## Create a target
{: #scan-target-create} 
{: step}

Now that your {{site.data.keyword.compliance_short}} and {{site.data.keyword.secrets-manager_short}} instances are connected, you can target the trusted profile that you created.

1. Navigate to your {{site.data.keyword.compliance_short}} instance. 
2. Go to **Settings**.
3. In the **Targets** section, click **Add**.
4. In the **Add target** page, enter the **Name**, **Account ID**, and **Trusted profile ID** of your target account.
5. Click **Add**.

## Assign credentials to scan Watson Machine Learning
{: #scan-targets-credentials-create} 
{: step}

After you create a target, you can assign the API key to the Watson Machine Learning resources that you want to scan. 

1. In the **What's next** section, click **Assign credentials** to assign credentials that you want to use when you're scanning your Watson Machine Learning resources.
2. In the **Select credential** tab, you can assign the secret that contains the API key. 
3. Select the **Secrets Manager instance**, **Secret group**, and **Secret type**. 
4. Select the secret that contains the API key, then click **Next**.
5. Click **Add** icon (+) to select the Watson Machine Learning instances in your target account that you want to access with this credential. You can assign this credential to all or specific instances of the service. 
6. Click **Assign**. 

Alternatively, you can select **Locate by CRN** to enter the CRN of the secret that you want to use directly. 
{: tip}

## Create a scope
{: #watson-create-scope}
{: step} 

A scope is the grouping of resources that you want to evaluate. For help with creating a scope, see [Targeting your resources](/docs/security-compliance?topic=security-compliance-scopes).

## Scan your resources
{: #watson-resources-scan}
{: step} 

After you assign the credentials, you're free to start scanning your Watson Machine Learning resources. Complete the following steps to do so.

1. In the **Profiles** section of the console, select **AI Security Guardrails 2.0**. A details page opens.
2. In the **Attachments** tab, click **Create**.
2. Target your resources by selecting a **Scope**. Optionally, you can choose to exclude portions of your selected scope to ensure that they are not included in your scan.
3. Click **Next**.
4. Unless your profile contains additional controls, you can skip the **Parameters** tab by clicking **Next**.
5. Toggle **Enable scan** to **On** to ensure that the scan runs.
6. Select the frequency at which you want to evaluate your resource. Options include **Every day**, **Every 7 days**, and **Every 30 days**.
7. Optionally, you can enable notifications.
8. Click **Next**. Review your selections and click **Create**.

## Next steps
{: scan-watson-attachment-next}

Now that you finished evaluating your Watson Machine Learning resources against the AI Security Guardrails 2.0 profile, you can [view detailed results in the dashboard](/docs/security-compliance?topic=security-compliance-results&interface=ui#view-detailed-results) and download a report. 
