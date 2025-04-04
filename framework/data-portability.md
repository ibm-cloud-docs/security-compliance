---

copyright:
  years: 2020, 2025
lastupdated: "2025-04-01"

keywords: Security and Compliance Center, data portability

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Understanding data portability for {{site.data.keyword.compliance_short}}
{: #data-portability}

Data portability involves a set of tools and procedures that enable you to export the digital artifacts you need to implement similar workload and data processing on different service providers or on-premises software. It includes procedures for copying and storing the service customer content, including the related configuration that is used by the service to store and process the data, in your location.
{: shortdesc}

## Responsibilities
{: #data-portability-responsibilities}

{{site.data.keyword.cloud_notm}} services provide interfaces and instructions that guide you through the process of copying and storing the service customer content, including the related configuration, in your selected location.

You are responsible for the use of the exported data and configuration for data portability to other infrastructures, which includes:

* The planning and execution for setting up alternative infrastructure on different cloud providers or on-premises software that provide similar capabilities to the {{site.data.keyword.IBM_notm}} services.
* The planning and execution for the porting of the required application code on the alternative infrastructure, including the adaptation of your application code, deployment automation, and so on.
* The conversion of the exported data and configuration to the format that's required by the alternative infrastructure and adapted applications.

For more information about your responsibilities, see [Shared responsibilities for {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-responsibilities).

## Data export procedures
{: #data-portability-procedures}

{{site.data.keyword.compliance_short}} provides mechanisms to export settings and configurations that are used to process your content. The [{{site.data.keyword.compliance_short}} API](/apidocs/security-compliance) documents the commands to interact with your data.

* [List attachments](/apidocs/security-compliance#list-instance-attachments) provides a structured way to retrieve and export all relevant attachment configurations associated with an instance.
* [List rules](/apidocs/security-compliance#list-rules) with the `type=user_defined` query parameter provides a structured way to retrieve and export all relevant custom rule configurations associated with an instance.
* [Settings](/apidocs/security-compliance#get-settings) provides a structured way to retrieve and export all relevant settings associated with an instance.

### Export result data
{: #data-portability-result-data}

Scan results are stored in the IBM Cloud Object Storage bucket you have configured in your instance settings. For detailed information about exporting your results, see [IBM Cloud Object Storage data export procedures](/cloud-object-storage?topic=cloud-object-storage-data-portability).

## Exported data formats
{: #data-portability-data-formats}

{{site.data.keyword.compliance_short}} supports the following data format and schema of the exported data and configurations.

Attachment configurations
* Format: JSON
* Schema: [List attachments API response](apidocs/security-compliance?code=go#list-instance-attachments)

Custom rule configurations
* Format: JSON
* Schema: [List rules API response](/apidocs/security-compliance?code=go#get-rule-response)

Settings
* Format: JSON
* Schema: [Settings API response](/apidocs/security-compliance?code=go#get-settings-response)

## Data ownership
{: #data-portability-ownership}

All exported data is classified as customer content. Apply the full customer ownership and licensing rights, as stated in the [{{site.data.keyword.cloud_notm}} Service Agreement](https://www.ibm.com/support/customer/csol/terms/?id=Z126-6304_WS&cc=us&lc=en).
