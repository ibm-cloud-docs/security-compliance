---

copyright:
  years: 2020, 2023
lastupdated: "2023-05-30"

keywords: security and compliance, secure development, security strategy

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Migrating to the updated architecture
{: #migrate}

Starting 8 July 2023 {{site.data.keyword.compliance_full}} will be a provision-able, regional service offering in the {{site.data.keyword.cloud_notm}} catalog. With this change, you will have full control over the region that is used when {{site.data.keyword.compliance_short}} processes your data. To process data in different regions, you can provision multiple instances of the service in a single account. As part of these changes, the collector-based architecture was deprecated and support will be removed. If you are currently working with the collector-based architecture, this topic can help you understand the differences in functionality and what your migration to the new architecture might look like. 

## What does the migration look like?
{: #migrate-how}

Because the foundational structure of the service changed, there is not a one-to-one correlation between the first version of the service and the second. At any time, you can start creating attachments and moving your scans to the new architecture. To avoid disruption in your compliance scan, it is recommended that you make this change prior to when the regional instances are launched and support for the first architecture is removed.

## What are the important dates?
{: #migrate-dates}

As you prepare for this change, please keep the following dates in mind:

	* 8 June 2023: The location setting in {{site.data.keyword.compliance_short}} will be frozen until the upgrade is complete. The location that is specified in the service is the region in which your new instance will be created. Additional instances can be created starting in July.
	* 1 July 2023: The collector-based architecture will be removed from {{site.data.keyword.compliance_short}}.
	* 9 July 2023: A regional instance of {{site.data.keyword.compliance_short}} will be available in your account based on your set location and the global instance will be removed. Additionally, the changes to IAM and context-based restrictions take effect.

You might see two instances of {{site.data.keyword.compliance_short}} through the Billing page during the migration period although you can’t see two instances in your account. This is due to the way that the migration is being conducted. You are only billed through one. When the migration is complete, the global instance will be removed from your account.
{: tip}

## How does the functionality differ between the architectures?
{: #arch-function}

Check out the following table to see the main differences between the architecture that are already available. V1 of the service will not be migrated into the regional service offering and will become unsupported on 1 July 2023.

## How does the functionality differ between flows?
{: #functionality}
{: support}

Depending on the evaluation flow that you're working in, your experience with the service differs. Review the following table to see how the functionality that is offered in each flow differs. As more functionality is released in the new architecture, this table will be updated.

|            | Version 1 architecture | Version 2 architecture |
|------------|-----------|-----------------|
| Availability | Amazon Web Services, Google Cloud Platform, Microsoft Azure, and On-premises | {{site.data.keyword.cloud_notm}}  \n Note: To evaluate a multi-cloud flow, get started with Workload Protection. |
| Integrations | Tanium and OSCO | {{site.data.keyword.cloud_notm}} Workload Protection  |
| Enterprise account support | Set up required | Available by default |
| Results storage | IBM-owned | Customer-owned |
| Control parameters | Customizable by account | Customizable by attachment |
| Custom assessments | Not available | Simple declarative rules can be written |
| Versioning | Not available | Supported for controls and profiles |
| Search | Searchable by control name | Ability to search and filter controls and results by component, scope, category, and status |
| Scan export | PDF and CSV | CSV |
| Profiles | 44 predefined profiles | 3 predefined profiles:  \n {{site.data.keyword.cloud_notm}} Security Best Practices  \n {{site.data.keyword.cloud_notm}} for Financial Services  \n CIS IBM Foundations Benchmark |
| Inventory | Available | Not available |
{: row-headers}
{: caption="Table 2. Functionality comparison" caption-side="top"}

Components such as credentials, goals, profiles, collectors, scopes, and scans will not be migrated to the new architecture.
{: note}
