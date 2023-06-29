---

copyright:
  years: 2020, 2023
lastupdated: "2023-06-29"

keywords: security and compliance, secure development, security strategy

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Migrating to the updated architecture
{: #migrate}

Starting 9 July 2023 {{site.data.keyword.compliance_full}} will be a provision-able, regional service offering in the {{site.data.keyword.cloud_notm}} catalog. With this change, you will have full control over the region that is used when {{site.data.keyword.compliance_short}} processes your data. To process data in different regions, you can provision multiple instances of the service in a single account. As part of these changes, the collector-based architecture was deprecated and support will be removed. If you are currently working with the collector-based architecture, this topic can help you understand the differences in functionality and what your migration to the new architecture might look like. 

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


## What are the notable changes?
{: #migrate-change}

The following changes with platform integrations are expected as part of this transition:

* Any Identity and Access Management (IAM) access policies or context-based restrictions that are scoped to “All Account Management Services” will no longer apply to {{site.data.keyword.compliance_short}}. Users who have access to “All Identity and Access Enabled Services” will now have access to {{site.data.keyword.compliance_short}}.
* If users have access only to products added to a private catalog and not the full IBM Cloud catalog, then {{site.data.keyword.compliance_short}} must be added to their private catalog to enable them to create an instance.
* If users have a quota on the number of resources for their account that has already been met, instances of the service will not be able to be created.
* The events related to collector-based evaluations have also been removed. To continue to receive events for your evaluations you must [configure new topics in Event Notifications](/docs/security-compliance?topic=security-compliance-event-notifications). 

## How does the functionality differ between the architectures?
{: #arch-function}

Check out the following table to see the main differences between the architecture that are already available. V1 of the service will not be migrated into the regional service offering and will become unsupported on 1 July 2023.

|            | Version 1 architecture | Version 2 architecture |
|------------|-----------|-----------------|
| Availability | Amazon Web Services, Google Cloud Platform, Microsoft Azure, and On-premises | {{site.data.keyword.cloud_notm}}  \n Note: To evaluate a multi-cloud flow, get started with [Workload Protection](/docs/workload-protection). |
| Integrations | Tanium | {{site.data.keyword.cloud_notm}} Workload Protection and OSCO |
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

