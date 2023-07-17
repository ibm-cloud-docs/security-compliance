---

copyright:
  years: 2020, 2023
lastupdated: "2023-07-17"

keywords: custom profiles, user-defined, controls, goals, security, compliance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Running an evaluation for {{site.data.keyword.cloud_notm}}
{: #scan-resources}

With {{site.data.keyword.compliance_full}}, you can evaluate your resources on a recurring schedule or you can initiate a scan at any time.
{: shortdesc}

To evaluate your resources, you create an attachment. An attachment is the association between the set of resources that you want to evaluate and a profile that contains the specific controls that you want to evaluate.

![A diagram that shows the relationship between a control, profile, and scope.](images/term-flow.svg){: caption="Figure 1. Understanding entities in {{site.data.keyword.compliance_short}}" caption-side="bottom"}


## Before you begin
{: #before-evaluation}

Before you get started, be sure that you have the required level of access to create an attachment. To create an attachment, you need the **Editor** platform role or higher. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).

You must also connect a Cloud Object Storage bucket in which to store your results. To connect your bucket, you must have a service-to-service policy in place that enables communication between {{site.data.keyword.compliance_short}} and Cloud Object Storage.


## Scheduling a recurring scan
{: #scan-schedule-ui}
{: ui}

To start scanning your resource, you create an attachment. To create an attachment, you can use the {{site.data.keyword.compliance_short}} UI to complete the following steps.

1. In the {{site.data.keyword.compliance_short}} UI, navigate to the **Attachments** page and click **Create**. A flat list of all of the attachments in your account is displayed.

	Alternatively, you can create an attachment through the **Profiles** page. On the **Attachments** tab of the profile details page, click **Create** and then continue with step 2.
	{: tip}

2. Provide a name and description for your attachment. Be sure to be as descriptive as possible so that it's easy for other members of your team to understand what is being evaluated. Then, click **Next**.
3. Select the **Profile** and **Profile version** that you want to use for your evaluation.

	Predefined profiles are available, but you can create a custom profile that uses only the controls that you want. In other words, create a custom profile if you don’t want to use all the controls in the predefined profile. For multi-cloud support, be sure to select a profile that includes the `wp-rule`, which is Azure Kubernetes Service (AKS), Amazon Web Service (AWS), or Amazon Elastic Kubernetes Service (EKS),
   {: tip}

4. Customize the underlying evaluations in your scan by editing the default parameters to match your specific use case.
5. Target the resources you want to evaluate by defining a scope. If you are working with {{site.data.keyword.cloud_notm}} resources, you can also specify resources that you want to exlude from your scope. If you are working with resources from other environments, you must [connect an instance of the {{site.data.keyword.sysdigsecure_short}} service](/docs/security-compliance?topic=security-compliance-setup-workload-protection) and provide the reqested information to move forward.
6. Click **Next**.
7. Select the frequency at which you want to evaluate your attachment.
	
	Options include every day, every 7 days, and every 30 days. Additionally, you can now pause your scans if you need to.

8. Optional: Configure notifications.
	1. If you want to receive notifications, toggle **Notify me** to **On**.
	2. By default, when notifications are enabled, you are alerted when 15% or more of your controls fail in a single scan. You can change this by adjusting the **Threshold** percentage. 
	
		For example, if you have a profile with 100 controls and you want to be notified if 5 of them fail, you would select 5% as your threshold.
	
	3. Select specific controls that you want to be notified about.

		If there are high priority controls that pertain specifically to your job role, you might want to be notified every time that they fail. You can identify up to 15 controls per scan that you can receive individual notifications for. These notifications are sent regardless of whether the threshold that was identified in the previous step was met.

		1. Click **Select control**.
		2. Select the controls that you want to be notified about by checking the box next to the control.
		3. Click **Ok**.
9. Review your choices and click **Create**.

When you create your attachment, a scan is scheduled. When the scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard.







## Running a scan on demand
{: #scan-ondemand-ui}
{: ui}

If your attachment exists, but you don't want to wait for the next scan to see your posture, you can initiate an on-demand scan.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Profile**.
3. Click the **Overflow** menu in the row of the profile that you want to evaluate and select **Run scan**.
3. Click **Run scan**.

After your scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard.

