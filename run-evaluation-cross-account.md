---

copyright:
  years: 2020, 2024
lastupdated: "2024-08-20"

keywords: custom profiles, user-defined, controls, goals, security, compliance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Scanning resources across accounts
{: #scan-resources-cross-account}

With {{site.data.keyword.compliance_full}}, you can scan resources in other {{site.data.keyword.cloud_notm}} accounts that are either part of an enterprise or outside of an enterprise. You can enable scanning across other accounts by adding these {{site.data.keyword.cloud_notm}} accounts to your attachment as target accounts.
{: shortdesc}

You can take advantage of an automation script that can help you to automatically register to scan resources across accounts. For more information, check out the [script in GitHub](https://github.com/IBM/security-compliance-automation){: external}.
{: tip}


If you want to scan your Watson Machine Learning resources with {{site.data.keyword.compliance_short}}, see [Scanning Watson Machine Learning resources](/docs/security-compliance?topic=security-compliance-scan-watson-machine-learning) for more information. 


## Before you begin
{: #before-evaluation-cross-account}

Before you get started, make sure that you [create a trusted profile](/docs/account?topic=account-create-trusted-profile&interface) with the following access policies set for the target account, and assign the specified roles.

* All Account Management services (`Viewer`, `Service Configuration Reader`)
* Kubernetes Service (`Reader`, `Viewer`, `Administrator`, `Service Configuration Reader`)

   This access policy is required to run the Red Hat OpenShift Compliance Operator (OSCO) scan when an attachment is created.
   {: important}

* All Identity and Access enabled services (`Reader`, `Viewer`, `Service Configuration Reader`)

The trusted profile must also contain the {{site.data.keyword.compliance_short}} instance Cloud Resource Name (CRN) for the monitoring account in the {{site.data.keyword.cloud_notm}} services. You can find the CRN in the **Settings** > **Service instance** section of the {{site.data.keyword.compliance_short}} UI.

When you are enabling scanning of resources across accounts, if you add your main account as a target, you must use trusted profiles to run the scans. If you change the trusted profile, the scan results are impacted. To change the trusted profile and avoid issues with your scan results, you must delete the target and all the attachments that are on the account first. Then, you can create a new target with the updated trusted profile. 
{: note}


## Adding target accounts for scanning
{: #add-target-account}

To enable scanning of resources across accounts, add a target account to your attachment.

1. In the {{site.data.keyword.compliance_short}} navigation, click **Settings**.
2. In the **Targets** section, click **Add**.
3. Specify a unique name for your target account.
4. Specify the ID of the target account to add.
5. Specify the ID of the trusted profile for scanning across accounts.
6. Click **Add** to add the target account to your attachment.

## Removing target accounts from scanning
{: #remove-target-account}

Before you remove a target account from your scans, make sure that you remove that account from any of your attachments that are configured to scan resources in it. 
{: important}

1. In the {{site.data.keyword.compliance_short}} navigation, click **Settings**.
2. In the **Targets** section, find the account that you want to remove. Then, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) and select **Remove**.
3. Click **Remove** to confirm that you want to remove this target account from scanning across accounts.

## Scheduling a recurring scan for resources across accounts
{: #schedule-cross-account-scan}

To schedule a recurring scan for resources across accounts, [create an attachment](/docs/security-compliance?topic=security-compliance-scan-resources&interface=ui#scan-schedule-ui). When you create an attachment for a profile with the {{site.data.keyword.cloud_notm}} environment, you can view the accounts that are registered in the **Settings** page. Then, you can select from these accounts to use as your scope. If you select multiple accounts, each account is created as a separate scope within the attachment. You cannot select or exclude resource groups for scanning across accounts.

When the scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard. If your results are not updated, review the [troubleshooting guide](/docs/security-compliance?topic=security-compliance-ts-cache).
