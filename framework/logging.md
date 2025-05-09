---
copyright:
  years: 2020, 2025
lastupdated: "2025-05-09"

keywords: "LogDNA for {{site.data.keyword.compliance_short}}, {{site.data.keyword.compliance_short}} logging, {{site.data.keyword.compliance_short}} external logs"

subcollection: security-compliance
---

{{site.data.keyword.attribute-definition-list}}


# Logging for {{site.data.keyword.compliance_short}}
{: #logging}

{{site.data.keyword.cloud_notm}} services, such as {{site.data.keyword.compliance_short}}, generate platform logs that you can use to investigate abnormal activity and critical actions in your account, and troubleshoot problems.
{: shortdesc}

You can use {{site.data.keyword.logs_routing_full_notm}}, a platform service, to route platform logs in your account to a destination of your choice by configuring a tenant that defines where platform logs are sent. For more information, see [About Logs Routing](/docs/logs-router?topic=logs-router-about).

You can use {{site.data.keyword.logs_full_notm}} to visualize and alert on platform logs that are generated in your account and routed by {{site.data.keyword.logs_routing_full_notm}} to an {{site.data.keyword.logs_full_notm}} instance.

## Locations where logs are sent by {{site.data.keyword.logs_routing_full_notm}}
{: #lr-locations}

{{site.data.keyword.compliance_short}} sends logs by {{site.data.keyword.logs_routing_full_notm}} in the regions that are indicated in the following table.

| Dallas (`us-south`) | Washington (`us-east`)  | Toronto (`ca-tor`) | Sao Paulo (`br-sao`) |
|---------------------|-------------------------|-------------------|----------------------|
| [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} | [No]{: tag-red} |
{: caption="Regions where platform logs are sent in Americas locations" caption-side="top"}
{: #lr-table-1}
{: tab-title="Americas"}
{: tab-group="lr"}
{: class="simple-tab-table"}
{: row-headers}

| Tokyo (`jp-tok`)    | Sydney (`au-syd`) |  Osaka (`jp-osa`) | Chennai (`in-che`) |
|---------------------|------------------|------------------|--------------------|
| [No]{: tag-red} | [No]{: tag-red} | [No]{: tag-red} | [No]{: tag-red} |
{: caption="Regions where platform logs are sent in Asia Pacific locations" caption-side="top"}
{: #lr-table-2}
{: tab-title="Asia Pacific"}
{: tab-group="lr"}
{: class="simple-tab-table"}
{: row-headers}

| Frankfurt (`eu-de`)  | London (`eu-gb`) | Madrid (`eu-es`) |
|---------------------------------------------------------------|---------------------|------------------|
| [Yes]{: tag-green} | [No]{: tag-red} | [Yes]{: tag-green} |
{: caption="Regions where platform logs are sent in Europe locations" caption-side="top"}
{: #lr-table-3}
{: tab-title="Europe"}
{: tab-group="lr"}
{: class="simple-tab-table"}
{: row-headers}

## Platform logs that are generated
{: #log-platform}

The {{site.data.keyword.compliance_short}} service generates platform logs related to the following cases:

- When a scan begins or when a scan cannot be initiated
- Any errors related to provider integrations
- Report generation or if an error associated with a report is found
- When there is an error in storing reports


## Enabling logging
{: #log-enable}

Platform logs are logs that are exposed by logging-enabled services and the platform in {{site.data.keyword.cloud_notm}}. Platform logs are regional. You can monitor logs from enabled services on {{site.data.keyword.cloud_notm}} in the region where the service is available. While you can configure multiple {{site.data.keyword.cloud_notm}} Logs service in a location, only one instance of the logging service can be configured to receive logs from enabled services in that {{site.data.keyword.cloud_notm}} location.

To configure your {{site.data.keyword.cloud_notm}} instance, you must turn on the platform logs configuration setting. You must also have the platform role of editor or higher for the {{site.data.keyword.cloud_notm}} Log service in your account. For more information about platform logs, see [Configuring {{site.data.keyword.cloud_notm}} platform logs](/docs/logs-router?topic=logs-router-target-cloud-logs).



## Viewing logs
{: #log-viewing}

### Launching {{site.data.keyword.logs_full_notm}} from the Observability page
{: #logs-launch-standalone}

For more information about launching the {{site.data.keyword.logs_full_notm}} UI, see [Launching the UI in the {{site.data.keyword.logs_full_notm}} documentation.](/docs/cloud-logs?topic=cloud-logs-instance-launch)

## Fields by log type
{: #log-fields}

For information about fields included in every platform log, see [Fields for platform logs](/docs/logs-router?topic=logs-router-about-platform-logs#about-platform-logs-2)

| Field	 | Type	 | Description	|
|---------|--------|-------------|
| `logSourceCRN`	| Required | Defines the {{site.data.keyword.compliance_short}} instance where the log is published. |
| `resourceGroupId` | Required | Defines the resource group that is associated with the {{site.data.keyword.compliance_short}} instance. |
| `message`	 | Required | Description of the log that is generated. |
| `msgTimestamp`	| Required | UTC timestamp of the message. |
| `messageId`	 | Required | ID of the log that is generated. |
| `correlationId`	 | Required | Unique identifier used to correlate multiple log entries associated with a single API request. |
| `level`	 | Required | Type of log. Valid values are `info`, `warn`, `error`. |
| `requestId`	 | Optional | Identifier of the associated request. |
| `resolution`	| Optional | Guidance on how to proceed if you receive this log record. |
| `documentUrls`	| Optional | More information on how to proceed if you receive this log record. |
{: caption="Log record fields" caption-side="top"}


## Log messages
{: #log_messages}

The following table lists the message IDs that are generated by the {{site.data.keyword.compliance_short}} service:

| Message ID | Log type | Description | Additional fields | Resolution |
|------------|----------|-------------|-------------------|------------|
| `compliance.00001E` | ERROR | Provider integration missing. | `scanID`, `providerType` | Please create an integration between Workload Protection and Security and Compliance. |
| `compliance.00002E` | ERROR | Unable to retrieve results from the provider. | `scanID`, `providerType` | Please review the workload protection configuration. Additionally, please reach out to the Security and Compliance team and provide them with the correlationID. |
| `compliance.00003I` | INFO | Scheduled scan started. | `scanID`, `attachmentID`, `scanType` | N/A |
| `compliance.00004I` | INFO | On-demand scan started. | `scanID`, `attachmentID`, `scanType` | N/A |
| `compliance.00005E` | ERROR | One scan is already running for the attachment, hence could not initiate a new scan. | `attachmentID` | One scan is already in progress for this attachment, you can run only one scan per attachment at a time. Please wait until the current running scan to complete and then initiate a new scan. |
| `compliance.00006E` | ERROR | Cloud Object Storage configuration not valid. | `attachmentID`, `scanType` | Missing storage configuration. Before you can evaluate your resources you must connect a Cloud Object Storage bucket that can be used to store results. |
| `compliance.00007E` | ERROR | Billing plan validation failed. | `attachmentID`, `scanType` | Most likely your trial-period has ended, please check and upgrade your plan. To continue to work with the service. |
| `compliance.00008E` | ERROR | Scan failed. | `scanID` | Scan failed due to an unexpected error, please create support case with the necessary information like correlationId. |
| `compliance.00009E` | ERROR | Unable to store report in Cloud Object Storage bucket. | `scanID` | Validate the configuration of your Cloud Object Storage bucket associated with this Security and Compliance instance. |
{: caption="Message IDs" caption-side="top"}
