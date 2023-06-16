---

copyright:
  years: 2020, 2023
lastupdated: "2023-06-16"

keywords: custom profiles, user-defined, controls, goals, security, compliance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Running an evaluation for {{site.data.keyword.cloud_notm}}
{: #scan-resources}

With {{site.data.keyword.compliance_full}}, you can evaluate your resources on a recurring schedule or you can initiate a scan at any time.
{: shortdesc}



If you want to evaluate an environment other than {{site.data.keyword.cloud_notm}}, you must use the collector-based architecture. To get started, see [Managing collectors](/docs/security-compliance?topic=security-compliance-collector).
{: note}



To evaluate your resources, you create an attachment. An attachment is the association between the set of resources that you want to evaluate and a profile that contains the specific controls that you want to evaluate.

![A diagram that shows the relationship between a control, profile, and scope.](images/term-flow.svg){: caption="Figure 1. Understanding entities in {{site.data.keyword.compliance_short}}" caption-side="bottom"}


## Before you begin
{: #before-evaluation}

Before you get started, be sure that you have the required level of access to create an attachment. To create an attachment, you need the **Editor** platform role or higher. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).

You must have also connected a Cloud Object Storage bucket in which to store your results. To connect your bucket, you must have a service-to-service policy in place that enables communication between {{site.data.keyword.compliance_short}} and Cloud Object Storage.


## Scheduling a recurring scan
{: #scan-schedule-ui}
{: ui}

To start scanning your resource, you create an attachment. To create an attachment, you can use the {{site.data.keyword.compliance_short}} UI to complete the following steps.





## Running a scan on demand
{: #scan-ondemand-ui}
{: ui}

If your attachment exists but you don't want to wait for the next scan to see your posture, you can initiate an on demand scan.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Profile**.
3. Click the **Overflow** menu in the row of the profile that you want to evaluate and select **Run scan**.
3. Click **Run scan**.

After your scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard.

