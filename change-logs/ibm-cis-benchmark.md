---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: "release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements"

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: CIS IBM Cloud Foundations Benchmark profile
{: #cis-benchmark-profile}

As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}

In this change log, you can learn about the latest changes, improvements, and updates for the CIS IBM Foundations Benchmark profile. The change log lists changes that were made, ordered by the version number.


## Profile versioning
{: #cis-profile-versioning}

When specifications or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new version is released. To take advantage of the changes in a new version, update your attachments to use the newest profile version.

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Be sure to validate the available controls to determine where you might need to supplement your workloads with other security measures.
{: important}

### Version summary
{: #cis-active-versions}

The following table details the release dates and status of each profile version.

New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
{: important}

| Version number | Release date | Status |
|:---------------|:-------------|:-------|
| Version 1.1.0 | `2024-06-25` | Active |
| Version 1.0.0 | `2023-05-17` | Active |
{: caption="Table. Active versions of the CIS IBM Cloud Foundations Benchmark profile" caption-side="top"}


## Version 1.1.0
{: #cis-v110}

The following rules were updated in the CIS IBM Cloud Foundations Benchmark profile as of 25 June 2024.

| Rule ID | Rule description| Control IDs | Update |
|:--------|:----------------|:--------------------|:-------|
| `rule-5b72d8d6-d4a2-4e3f-802a-a610b0b42ca8`	| Check whether no owner account API key exists |	`1.5` |	The rule was added. |
| `rule-ea9f2766-787f-44a4-b359-c0234313b587`	| Check whether IAM users contact email is valid |	`1.10` |	The rule was added. |
| `rule-359bbe77-7889-48f5-9191-5a6347e87765`	| Check whether IAM users contact phone number is valid |	`1.11` |	The rule was added. |
| `rule-7c86bb59-d677-422d-875c-0259053fad20`	| Check whether Cloud Object Storage is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |	`2.1.1.2` |	The rule was removed. |
| `rule-c97259ee-336d-4c5f-b436-1868107a9558`	| Check whether Cloud Object Storage is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |	`2.1.1.3` |	The rule was removed. |
| `rule-5da7c258-d143-4b23-9259-77ac01cfe312`	| Check whether Cloud Object Storage is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK) |	`2.1.1.1` |	The rule was added. |
| `rule-773385ab-4654-4088-883d-fe9d58bc4ecb`	| Check whether Block Storage for VPC is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |	`2.2.1.2` |	The rule was removed. |
| `rule-8ffe83cb-0ba1-47d6-a1e0-53e9932a5691`	| Check whether Block Storage for VPC is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |	`2.2.1.3` |	The rule was removed. |
| `rule-871594ca-0a70-492b-8a42-6f9474445f01`	| Check whether Databases for Elasticsearch is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |	`4.1` |	The rule was removed. |
| `rule-7f7ca588-9412-40a9-9bd8-0e5d19141e98`	| Check whether Databases for MongoDB is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |	`4.1` |	The rule was removed. |
| `rule-041ff30b-7167-4411-985d-5ad32ab6f850`	| Check whether Databases for PostgreSQL is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |	`4.1` |	The rule was removed. |
| `rule-e3cad136-17a8-4227-b8af-0be609da1da0`	| Check whether Databases for Redis is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |	`4.1` |	The rule was removed. |
| `rule-3c8c8ca6-986b-4d9e-867a-833b4f64c28d`	| Check whether Databases for MongoDB is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK) |	`4.1` |	The rule was added. |
| `rule-6d64d49d-5f45-4799-87c4-3947befb6801`	| Check whether Databases for MySql is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK) |	`4.1` |	The rule was added. |
| `rule-645f27e2-f905-4532-9965-547d71320676`	| Check whether Databases for PostgreSQL is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK) |	`4.1` |	The rule was added. |
| `rule-264930c6-642f-4a3b-a87a-61e938542bce`	| Check whether Databases for Elasticsearch is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK) |	`4.1` |	The rule was added. |
| `rule-d74b5d62-f5b7-4e75-97c3-8adb0aa34e2b`	| Check whether Databases for Redis is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK) |	`4.1` |	The rule was added. |
| `rule-8516ccd9-b184-4bbf-a139-ff69e8897118`	| Check whether Databases for MySql is accessible only through TLS 1.2 or higher |	`4.2` |	The rule was added. |
| `rule-ac6c79bd-603d-4161-a568-07854dc6c1ba`	| Check whether Databases for MySql is accessible only through private endpoints |	`4.3` |	The rule was added. |
| `rule-c821b867-7f04-4fbe-af6a-7be406b1e148`	| Check whether Databases for MySql is enabled with encryption |	`4.4` |	The rule was added. |
| `rule-8226d451-d6a7-46a7-8313-f8c091d6e33f`	| Check whether IBM Cloud Kubernetes Service Ingress has TLS 1.2 enabled for all inbound traffic |	`7.1.2` |	The rule was added. |
{: caption="Table. Summary of the changes for version 1.1.0 of the CIS IBM Cloud Foundations Benchmark profile" caption-side="top"}


## Version 1.0.0
{: #cis-v100}

Now available
:   Released in the new architecture today, 17 May 2023, the CIS IBM Cloud Foundations Benchmark profile is a collection of controls designed to validate the configuration of your {{site.data.keyword.cloud_notm}} resources in accordance with the CIS defined standards.
