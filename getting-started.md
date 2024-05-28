---

copyright:
  years: 2020, 2024
lastupdated: "2024-05-28"

keywords: getting started with the security and compliance center, get started, security, compliance

subcollection: security-compliance

content-type: tutorial
services: security-compliance, cloud-object-storage, event-notifications, iam
completion-time: 5m

---

{{site.data.keyword.attribute-definition-list}}

# Getting started with {{site.data.keyword.compliance_short}}
{: #getting-started}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, cloud-object-storage, event-notifications, iam"}
{: toc-completion-time="5m"}

For highly regulated industries, such as financial services, achieving continuous compliance within a cloud environment is an important first step toward protecting customer and application data. Historically, that process was difficult and manual, which placed your organization at risk. But, with {{site.data.keyword.compliance_full}}, you can integrate daily, automatic compliance checks into your development lifecycle to help minimize that risk.
{: shortdesc}


## Before you begin
{: #before-gs}

Before you get started, be sure that you have resources in your account to evaluate. You must also have a bucket in the Cloud Object Storage service that can be used to store your results data.

Running an evaluation does not ensure regulatory compliance. An evaluation provides a point in time statement of your current posture for a specific resource. It is your responsibility to review and interpret the results to ensure that your organization is adhering to the controls that are required for your industry. 
{: important}


## Create an instance
{: #gs-instance}
{: step}

To get started with {{site.data.keyword.compliance_short}}, you must first create an instance of the service.

1. Go to the [{{site.data.keyword.cloud_notm}} catalog](/catalog) and search for *[{{site.data.keyword.compliance_short}}](/catalog/services/security-and-compliance-center)*.
2. In the service details page, select a location. The selected location is where {{site.data.keyword.compliance_short}} will conduct the evaluation of your resources.
3. Select a pricing plan. Options include **Standard** or **Trial**.
4. Configure your resource by providing a name for the instance, specifying a resource group and adding any needed tags.
5. Acknowledge and agree to the terms and conditions.
6. Click **Create**.


## Assign access
{: #gs-access}
{: step}

After you have an instance of the service, the next step is to assign access to those on your team who manage compliance.  

1. [Create an access group](/docs/account?topic=account-groups&interface=ui#create_ag) and add your compliance focals.
2. In the Console, go to **Manage > Access (IAM) > Access groups** and click select the group that you want to assign access to. A new page opens with the details of the group.
3. Click **Access > Assign access**.
4. Assign the following permissions by selecting a service and reviewing the available roles and actions that are available for each option.

| Service | Minimum required permissions |
|---------|----------------------|
| {{site.data.keyword.compliance_short}} | Administrator |
| Cloud Object Storage | Reader |
| Event Notifications | Reader |
| Enterprise | Administrator or custom role |
{: caption="Table. Minimum required permissions" caption-side="top"}

If you are working within an enterprise account and do not want to assign administrator access to your compliance focals, you can create [a custom role](/docs/security-compliance?topic=security-compliance-assign-roles).
{: note}


## Configure storage
{: #gs-storage}
{: step}

Before you can start evaluating your resources for compliance, you must configure a Cloud Object Storage bucket where the service can forward your results data for long-term storage. For more information about bucket requirements, see [Storing and processing data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-storage).

To connect your Cloud Object Storage bucket, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.compliance_short}} navigation, click **Settings**.
2. On the **Storage** tile, click **Connect**.
3. Ensure that the service-to-service policy between Cloud Object Storage and {{site.data.keyword.compliance_short}} is configured. If a policy is already in place, this screen is not shown and you can skip to the next step. 
4. Select an instance of Cloud Object Storage.
5. From the table, select the bucket that you want to use.
6. Click **Connect**.


## Scan your resources
{: #gs-attachment}
{: step}

An attachment is how you target a specific grouping of your resources to evaluate against a specific profile. To start scanning your resources, create an attachment.

1. In the {{site.data.keyword.compliance_short}} UI, navigate to the **Attachments** page and click **Create**.

	Alternatively, you can create an attachment through the **Profiles** page. On the **Attachments** tab of the profile details page, click **Create** and then continue with step 2.
	{: tip}

2. Provide a name and description for your attachment. Be sure to be as descriptive as possible so that it's easy for other members of your team to understand what is being evaluated. Then, click **Next**.
3. Select the **Profile** and **Profile version** that you want to use for your evaluation.

	Predefined profiles are available, but you can create a custom profile that uses only the controls that you want. In other words, create a custom profile if you don’t want to use all the controls in the predefined profile. For multi-cloud support, be sure to select a profile that includes the `wp-rule`, which is Azure Kubernetes Service (AKS), Amazon Web Service (AWS), or Amazon Elastic Kubernetes Service (EKS),
   {: tip}
	
	New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
	{: important}

4. Customize the underlying evaluations in your scan by editing the default parameters to match your specific use case.
5. Target the resources that you want to evaluate by defining a scope within a single enterprise account. Or, define a scope across each of the target accounts in an {{site.data.keyword.cloud_notm}} environment that are outside of an enterprise. A flat list of the attachments in your account or across target accounts is displayed. For more information about evaluating resources in other accounts, see [Scanning resources across accounts](/docs/security-compliance?topic=security-compliance-scan-resources-cross-account).

   If you are working with {{site.data.keyword.cloud_notm}} resources, you can also specify resources that you want to exclude from your scope. If you are working with resources from other environments, you must [connect an instance of the {{site.data.keyword.sysdigsecure_short}} service](/docs/security-compliance?topic=security-compliance-setup-workload-protection) and provide the requested information to move forward.
6. Click **Next**.
7. Select the frequency at which you want to evaluate your attachment.
	
	Options include every day, every 7 days, and every 30 days. Additionally, you can now pause your scans if you need to.

8. Optional: Configure notifications.
   1. If you want to receive notifications, toggle **Notify me** to **On**.
   2. By default, when notifications are enabled, you are alerted when 15% or more of your controls fail in a single scan. You can change this by adjusting the **Threshold** percentage.

      For example, if you have a profile with 100 controls and you want to be notified if 5 of them fail, you would select 5% as your threshold.
	
   3. Select specific controls that you want to be notified about.

      If there are high priority controls that pertain specifically to your job role, you might want to be notified every time they fail. You can identify up to 15 controls per scan that you can receive individual notifications for. These notifications are sent regardless of whether the threshold identified in the previous step has been met.

      1. Click **Select control**.
      2. Select the controls that you want to be notified about by checking the box next to the control.
      3. Click **Ok**.
9. Review your choices and click **Create**.

When you create your attachment, a scan is scheduled. When the scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard.



## Next steps
{: #gs-next}

While you wait for your scan to complete, learn more about [the way the service works](/docs/security-compliance?topic=security-compliance-posture-management) or try [creating your own rule](/docs/security-compliance?topic=security-compliance-rules-define).


