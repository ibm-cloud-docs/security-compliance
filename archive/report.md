---

copyright:
  years: 2020
lastupdated: "2020-08-19"

keywords: compliance posture, security posture, audit evidence, security assessment, evaluation results, scan results, history, risk, controls, attributes, services, resources, noncompliant, compliant, csv file, evidence, dashboard 

subcollection: security-compliance

---

{:codeblock: .codeblock}
{:screen: .screen}
{:download: .download}
{:external: target="_blank" .external}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}
{:gif: data-image-type='gif'}
{:term: .term}
{:important: .important}
{:note: .note}
{:pre: .pre}
{:tip: .tip}
{:preview: .preview}
{:deprecated: .deprecated}
{:shortdesc: .shortdesc}
{:support: data-reuse='support'}
{:script: data-hd-video='script'}
{:table: .aria-labeledby="caption"}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:help: data-hd-content-type='help'}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tsSymptoms: .tsSymptoms}
{:beta: .beta}


# Downloading a report
{: #downloading-reports}

With the {{site.data.keyword.compliance_full}}, your results are kept for 7 days. In preparation for an audit or to maintain a longer history, you might want to download your results. You can choose to use the console or the API to download a report that contains the detailed evidence that you might need to prove compliance. 
{: shortdesc}

## Understanding the report
{: #understand-report}

When you download a report, you can see detailed results for the information that is detailed in the following table.

| Result | Description |
|--------|-------|---------|
| `id` | The ID of the profile, control, or statement. |
| `title` | The name of the profile, control, or statement. |
| `label` | The labels that are assigned to the control. |
| `category_id` | The ID of a control category. |
| `category_title` | The name of the control category. |
| `assessment` | The time of the last scan. |
| `status` | The status of compliance at the time of the last scan. |
| `results.total` | The total number of results. |
| `results.passes` | The number of results that are found to be compliant. |
| `results.warnings` | The number of results that returned a warning. |
| `results.failures` | The number of results that are found to be noncompliant. |
| `results.errors` | The number of results that returned an error. |
| `statements.total` | The total number of results for rules or implementations. |
| `statements.passes` | The total number of rules or implementations that are found to be compliant. |
| `statements.warnings` | The total number of rules or implementations that returned an warning. |
| `statements.failures` | The total number of rules or implementations that are found to be noncompliant. |
| `statements.errors` | The total number of rules or implementations that returned an error. |
| `controls.total` | The total number of results for controls. |
| `controls.passes` | The total number of controls that are found to be compliant. |
| `controls.warnings` | The total number of controls that returned an error. |
| `controls.failures` | The total number of controls that are found to be noncompliant. |
| `controls.errors` | The total number of controls that returned an error. |
| `profiles.total` | The total number of results for profiles. |
| `profiles.passes` | The total number of profiles that are found to be compliant. |
| `profiles.warnings` | The total number of profiles that returned an error. |
| `profiles.failures` | The total number of profiles that are found to be noncompliant. |
| `profiles.errors` | The total number of profiles that returned an error. |



## Downloading a report with the console
{: #download-console}

If you prefer to use a graphical interface, you can easily download your results in a few steps.


1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) > **Compliance and Security > Compliance posture** to access the {{site.data.keyword.compliance_short}}.

2. Using the information in investigating findings, navigate to the level of information that you want to see in your report. On that page, click **Download report**.

3. Choose whether you want only the summary of the information or if you'd like to see all of the evaluation results including audit evidence. If you're preparing for an external audit, select **Detailed report**.

4. Choose whether you want to download your report as a CSV file or as a YAML file. A YAML file can help you to process your data while a CSV can be imported into a spreadsheet for calculations and graphing.

5. Click **Download report**. The file downloads to your local system.

Now that you have your report, you can review the high-level summary of your compliance status with your relevant stakeholders.


