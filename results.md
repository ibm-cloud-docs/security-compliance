---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: custom profiles, user-defined, controls, goals, security, compliance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Viewing results
{: #results}

As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


With {{site.data.keyword.compliance_full}}, you can view the results of a compliance evaluation in the dashboard or by using the API.
{: shortdesc}

If you have access to a subscope but not the overarching scope, you will only see the results for the resources that you have [access to view](/docs/security-compliance?topic=security-compliance-assign-roles).
{: tip}

If you have access to a subscope but not the overarching scope, you can see the results for the resources that you have [access to view](/docs/security-compliance?topic=security-compliance-assign-roles).
{: tip}

## Before you begin
{: #before-results}

Before you get started, be sure that you have the following prerequisites.
   * To view results for a subscope, you must have the [**Reader** service role or higher](/docs/security-compliance?topic=security-compliance-access-management) to {{site.data.keyword.compliance_short}} and for the resource that is being evaluated.
   * If you are evaluating resources that require more credentials, you must also have access to those credentials.


## Understanding the dashboard
{: #understand-dashboard}

As you evaluate your resources, the results are returned via the service UI in graphical and detailed formats.

![A visual representation of the service dashboard. The concepts are fully explained in the surrounding text.](images/dashboard.svg){: caption="Example dashboard" caption-side="bottom"}

When you visit the dashboard, there are three graphical representations of data that have been aggregated from your scans. You see the:

Success rate
:   The rate at which your configurations pass the evaluation that is conducted. **Note:** The number of evaluations that are conducted does not always match the number of billable evaluations, as there is no charge for assessments that are evaluated as unable to perform. Be sure to look for the billable evaluations in each scan result if you need to estimate your cost.

Total controls
:   The total number of controls that have been evaluated in the past 30 days.

Total evaluations
:   The total number of evaluations that have been run in the past 30 days. An evaluation is the check of one resource against one assessment.

## Understanding statuses
{: #status}

When you view results in {{site.data.keyword.compliance_short}}, each evaluation produces a result of `pass`, `fail`, `unable to perform`, or `user_evaluation_required`. Check out the following table to learn more about what each result means.

| Result | Description |
|:-------|:------------|
| Pass | Your resource was compliant with the defined standard. |
| Fail | Your resource was not compliant with the defined standard. |
| Unable to perform | The assessment could not be performed. Potential reasons include the resource not existing in your account, a misconfiguration, or an error on behalf of {{site.data.keyword.compliance_short}}. |
| User evaluation required | The assessment has not yet been automated. To validate that you are meeting the standard, you must check your resource manually. |
{: caption="Understanding result statuses}

## Viewing results with the UI
{: #view-detailed-results}
{: ui}

To view the information of a scan, you can use the {{site.data.keyword.compliance_short}} UI.

If you edit your scope after it is already part of an attachment, any following scan results are listed as a new entry in the detailed results for your attachment. This means that you might see two entries with the same name.

1. In the {{site.data.keyword.cloud_notm}} console, go to the **Resource list** page and select your instance of {{site.data.keyword.compliance_short}}.
2. In your instance of {{site.data.keyword.compliance_short}}, go to the **Dashboard**.
3. In the **Detailed results** section, find the row for the specific **Scope** and **Profile** combination that you want to view results for and click **View** in the **Results** column.

A page opens with an **Overview** of your results. To further investigate, you can view the results by **Control** or by **Resource**. Check out the following table to see what information is available in each tab.

| | Description |
|:---|:---------|
| Overview | On the overview tab, you are provided with a graphical representation of your compliance for your selected scan.   \n ![A visual representation of detailed results that are returned when an evaluation is run.](images/results-overview-tab.svg){: caption="Example overview tab results" caption-side="bottom"}  \n   \n **Success rate**: The rate at which your configurations pass the evaluation that is conducted.  \n   \n **Total controls**: The total number of controls that were evaluated during this scan.  \n   \n **Drift**: The difference in results for your selected evaluation timeframe. |
| Controls | On the **Controls** tab, you are provided with an overview of the controls that were evaluated. The controls and their compliance status are listed for the time that the scan was done. You can also view annotations from this screen.  \n Click **View history** to see your audit history. |
| Resources | On the **Resources** tab, you are provided with the results for each specific resource that was evaluated.  \n ![A visual representation of detailed results that are returned when an evaluation is run.](images/results-resources-tab.svg){: caption="Example results tab results" caption-side="bottom"}</br></br>In the **JSON** tab, you can see the assessment definition. <ul><li>In the **Parameters** tab, you can see the parameters that are relevant to that resource. </li><li>In the **Noncompliant properties** tab, you are able to view which properties are noncompliant to begin remediating any issues that are found.</li><li> In the **Controls** tab, you are able to view which controls that the assessment is associated with.</li></li>In the **Additional details** tab, you can view the additional information that a specific provider might send with the evaluation results. This information might include, additional information, relevant links, or evidence.</li></ul> |
{: caption="Understanding detailed results" caption-side="top"}
{: row-headers}

## Viewing results with the API
{: #view-detailed-results-api}
{: api}

To get a report summary, you can use the {{site.data.keyword.compliance_short}} API.

```bash
curl -X GET
  --location --header "Authorization: Bearer {iam_token}"
  --header "Accept: application/json"
"https://us-south.compliance.cloud.ibm.com/instances/{instance_id}/v3/reports/{report_id}/summary"
```
{: pre}
{: curl}


```go
(securityAndComplianceCenterApi *SecurityAndComplianceCenterApiV3) GetReportSummary(getReportSummaryOptions *GetReportSummaryOptions) (result *ReportSummary, response *core.DetailedResponse, err error)
```
{: codeblock}
{: go}

```java
GetReportSummaryOptions getReportSummaryOptions = new GetReportSummaryOptions.Builder()
  .reportId(reportIdForReportLink)
  .build();

Response<ReportSummary> response = securityAndComplianceCenterApiService.getReportSummary(getReportSummaryOptions).execute();
ReportSummary reportSummary = response.getResult();

System.out.println(reportSummary);
```
{: codeblock}
{: java}

```bash
const params = {
  reportId: reportIdForReportLink,
};

let res;
try {
  res = await securityAndComplianceCenterApiService.getReportSummary(params);
  console.log(JSON.stringify(res.result, null, 2));
} catch (err) {
  console.warn(err);
}
```
{: codeblock}
{: node}

```python
response = security_and_compliance_center_api_service.get_report_summary(
  report_id=report_id_for_report_link,
)
report_summary = response.get_result()

print(json.dumps(report_summary, indent=2))
```
{: codeblock}
{: python}


A successful response returns the detailed report from your scan, along with other metadata. For more information about the required and optional request parameters, check out the [API docs](/apidocs/security-compliance#get-report-summary).



## Viewing results with the CLI
{: #view-detailed-results-cli}
{: cli}

To get a report summary, you can use the {{site.data.keyword.compliance_short}} CLI. For more information, see the [CLI reference](/docs/security-compliance?topic=security-compliance-security-compliance-cli&interface=cli#security-compliance-cli-reports-get-summary-command).

```sh
ibmcloud security-compliance report summary
--report-id=exampleString
--x-correlation-id=exampleString
--x-request-id=exampleString
```
{: pre}

## Viewing results with Terraform
{: #view-detailed-results-terraform}
{: terraform}

To get a report summary, you can use Terraform. 

```terraform
data "ibm_scc_report_summary" "scc_report_summary" {
	report_id = "report_id"
}
```
{: pre}

## Compliance
{: #understanding-comp}

For more information, check out the {{site.data.keyword.compliance_short}} [Terraform reference](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/scc_rule){: external}.

![A visual representation of the service dashboard. The concepts are fully explained in the surrounding text.](images/Compliance.jpg){: caption="Example dashboard" caption-side="bottom"}

The dashboard displays:

- **Evaluated controls and resources**:   The total number of controls and resources that are evaluated in the past 30 days.
- **Evaluation pass rate**: The rate at which your configurations pass the evaluation that is conducted. 

## Downloading a report
{: #download-report}
{: ui}

    The number of evaluations that are conducted does not always match the number of billable evaluations, as there is no charge for assessments that are evaluated as unable to perform. Be sure to look for the billable evaluations in each scan result if you need to estimate your cost.
    {: note}

If you need to keep your results for long periods of time, or provide information to key stakeholders, you can download a report.
- **Tickets**: The total number of evaluations that are run in the past 30 days. An evaluation is the check of one resource against one assessment.

1. In the {{site.data.keyword.cloud_notm}} console, go to the **Resource list** page and select your instance of {{site.data.keyword.compliance_short}}.
2. In your instance of {{site.data.keyword.compliance_short}}, go to the **Dashboard**.
3. Find the row for the specific **Scope** and **Profile** combination that you want to view results for and click the **Results** link. A page with the details of the latest evaluation opens.
4. Click **Download report**.

A CSV with your evaluation results is downloaded to your local system.
