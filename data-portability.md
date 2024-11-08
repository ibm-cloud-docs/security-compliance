---

copyright:
  years: 2020, 2024
lastupdated: "2024-11-08"

keywords: {{site.data.keyword.compliance_short}}, data portability

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Understanding data portability for {{site.data.keyword.compliance_short}}
{: #data-portability}

Data portability involves a set of tools and procedures that enable customers to export the digital artifacts they need to implement similar workload and data processing on different service providers or on-premises software. It includes procedures for copying and storing the service customer content, including the related configuration that is used by the service to store and process the data, on the customer's own location.
{: shortdesc}

## Responsibilities
{: #data-portability-responsibilities}

{{site.data.keyword.cloud_notm}} services provide interfaces and instructions to guide the customer to copy and store the service customer content, including the related configuration, on their own selected location.

The customer is responsible for the use of the exported data and configuration for data portability to other infrastructures, which includes:

* The planning and execution for setting up alternative infrastructure on different cloud providers or on-premises software that provide similar capabilities to the {{site.data.keyword.IBM_notm}} services.
* The planning and execution for the porting of the required application code on the alternative infrastructure, including the adaptation of customer's application code, deployment automation, and so on.
* The conversion of the exported data and configuration to the format that's required by the alternative infrastructure and adapted applications.

For more information about your responsibilities, see [Shared responsibilities for {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-responsibilities).

## Data export procedures
{: #data-portability-procedures}

{{site.data.keyword.compliance_short}} provides mechanisms to export settings and configurations that are used to process the customer's content.

Use the [list attachments](/apidocs/security-compliance#list-attachments-account) API endpoint to export configuration details. This API provides a structured way to retrieve and export all relevant attachment configurations associated with an instance.

## Exported data formats
{: #data-portability-data-formats}

{{site.data.keyword.compliance_short}} supports the following data format and schema of the exported data and configuration:
* Format: JSON
* Schema: [List attachments API response](/apidocs/security-compliance#list-attachments-account-response)

## Data ownership
{: #data-portability-ownership}

All exported data is classified as customer content. Apply the full customer ownership and licensing rights, as stated in the [IBM Cloud Service Agreement](https://www.ibm.com/terms/?id=Z126-6304_WS).
