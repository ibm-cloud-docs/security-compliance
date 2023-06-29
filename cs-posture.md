---

copyright:
  years: 2020, 2023
lastupdated: "2023-06-28"

keywords: compliance posture, security posture, audit evidence, security scan, evaluation results, scan results, scan results, compliance, score, compliance score

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Viewing results for hybrid cloud scans
{: #view-posture}

With {{site.data.keyword.compliance_full}}, you can see an overview and a detailed evaluation results in the console. 
{: shortdesc}


The collector-based architecture is deprecated. For more information, see the [release notes](/docs/security-compliance?topic=security-compliance-release-notes).
{: deprecated}


## Before you begin
{: #before-view-posture}

Before you get started, be sure that you have the required level of access to view results. To view results, you need the [**Viewer** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management). You must also have access to the credentials that are needed to access your resource configurations.



## Understanding the dashboard overview
{: #view-dashboard-overview}

In the {{site.data.keyword.compliance_short}} UI, you can see a graphical overview of your current posture.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access {{site.data.keyword.compliance_short}}.
2. Click **Hybrid cloud results > Current posture**. Check out the following table to see the information that is displayed in the dashboard.

   | Tile | Description |
   |:------------|:------------| 
   | Compliance score | Your compliance score is an analytical assessment of your organization's current posture. The {{site.data.keyword.compliance_short}} assigns each goal a severity level when it is created. The goals can be `Critical`, `High`, `Medium`, and `Low`. Critical goals have a much greater impact to your compliance and security scores than a low severity goal. To improve your score, address the security and compliance issues that are found. To make the biggest difference, start with the highest severity issues on your most significant resources.  \n ![A visual representation of validation results. The information in the diagram is detailed in the surrounding text.](images/scan-details.svg){: caption="Figure 1. Example compliance score breakdown" caption-side="bottom"}  \n Your compliance score is calculated by finding the weighted average of the goals that passed and failed determined by the severity of the goals. For example, if you have two goals and one is a high severity, the other is low. If the high severity goal passed but the low severity goal failed, your score would still be high. If the high severity goal failed but the low severity goal passed, your compliance score would be significantly impacted.|
   | Scans | A results summary of the most recent scan that was run. |
   | Collector status | The status of the collectors that exist in your account. |
   | Total validations | The total number of validations run for your account. The tile also contains information about how many are recurring and how many were run once as an on demand scan. |
   | Control validation results | An aggregated list of the results for all your resources, presented by day. |
   {: caption="Table 1. Understanding the dashboard" caption-side="top"}

You can update the time that information is displayed for by selecting **Today**, **Yesterday**, or the **Last 7**, **15**, or **30 days** from the dropdown.
{: tip}


## Viewing detailed results
{: #view-validations}

To view the most detailed information in a scan, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Hybrid cloud results > Detailed results**. A list of your scans that have results is shown.
3. In the **Results** table, click the **Name** of the scan. 

   A page opens with the detailed results of your scan. You can choose to view your results **By resource** or **By control**. Depending on your choice, your view options differ. Check out the following table to see your options.

   | View | Availability | Description |
   | --------- | ----------- | ----------- |
   | Chart | By control | A graphical display of the resource results, including your compliance score for that scan. |
   | List | By resource and control | A list of the individual resources that were scanned. The result is displayed in numerical order based on goal ID. |
   | Tree | By resource and control | A nested tree display of the resources that were scanned. The results are displayed in numerical order based on the goal ID. |
   | Drift | By control | A graphical display of the change in results between each scan that is run. |
   {: caption="Table 2. Understanding result display options" caption-side="top"}

4. Optional: Export the detailed results.

   | Report type | Description | File type |
   | --------- | ----------- | ----------- |
   | Detailed | All the control and resource information; organized by control. | Microsoft Excel (`.xlsx`) and PDF (`.pdf`) |
   | Delta | The change between two selected detail reports. | PDF (`.pdf`) |
   {: caption="Table 3. Understanding export options" caption-side="top"}


### Downloading a general report
{: #download-report}

If you need to keep your results for long periods of time, or provide information to key stakeholders, you can download a report that details your compliance score for selected scopes. For more information, see [Downloading a report](/docs/security-compliance?topic=security-compliance-view-posture#download-report).

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Hybrid cloud results > Detailed results**.
2. Click **Generate a report**.
3. Select the scans the scope that you want to download a report for.
4. Select the information that you want to include in your report.
5. Provide a start and end date for the evidence that you want included in your report.
6. Click **Generate report**. The file downloads to your local system.



## Viewing discovery and fact collection results
{: #view-discovery-collection}

To see the results of a discovery or fact collection scan, you can use the {{site.data.keyword.compliance_short}} UI. The scan results that are displayed by default are the most recent. To view historical results, use the timeline to select the specific scan that you want to view.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Scopes**. A list of the scopes that are associated with your account is shown.
3. In the **Scopes** table, click the **Name** of the scope that you want to view results for. A page opens with detailed information about the available resources in that scope and their configurations. 
4. Select **Fact collection** or **Discovery** from the drop-down to adjust the results that you see. Check out the following table to learn more about your options for viewing results.

   | View | Description |
   | --------- | ----------- |
   | List | A list of the individual resources that were scanned. The result is displayed in numerical order based on goal ID. |
   | Tree | A nested tree display of the resources that were scanned. The results is displayed in numerical order based on the goal ID. |
   | Topology | The topology of the resources that were scanned. |
   {: caption="Table 4. Understanding what each view provides" caption-side="top"}

5. Optional: **Download facts** to keep a snapshot of your resource configurations at that point in time.



