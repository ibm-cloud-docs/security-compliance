---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: "release notes for {{site.data.keyword.compliance_short}}, what's new, enhancements, fixes, improvements"

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: {{site.data.keyword.cloud_notm}} Framework for Financial Services profile
{: #fs-change-log}

As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


In this change log, you can learn about the latest changes, improvements, and updates for the {{site.data.keyword.cloud_notm}} Framework for Financial Services profile. The change log lists changes that were made, ordered by the version number.

## Profile versioning
{: #fs-profile-versioning}

When goals or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new minor version is released. To take advantage of the changes in a new version, update your scans to use the newest profile version.

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Users can validate the available goals and determine where a need to supplement their workloads with other security measures exists.
{: important}


### Version summary
{: #fs-versions}

The following table details the release dates and status of each profile version.

New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
{: important}

| Version number | Release date | Status |
|:---------------|:-------------|:-------|
| Version 1.7.0 | `2024-08-27` | Active |
| Version 1.6.0 | `2024-03-12` | Active |
| Version 1.5.0 | `2023-09-23` | Active |
| Version 1.4.0 | `2023-08-09` | Active |
| Version 1.3.0 | `2023-06-20` | Active |
| Version 1.2.0 | `2023-04-20` | Active |
| Version 1.1.0 | `2023-03-02` | Active |
| Version 1.0.0 | `2022-12-14` | Active |
{: caption="Table. Active versions of the {{site.data.keyword.cloud_notm}} Framework for Financial Services profile" caption-side="top"}


## Version 1.7.0
{: #fs-cloud-v170}

The following rules were updated in the {{site.data.keyword.cloud_notm}} Framework for Financial Services library and profile as of 27 August 2024.

| Rule ID | Rule description| Associated controls | Update |
|:--------|:----------------|:--------------------|:-------|
| `rule-1d0a1c93-b89f-432e-af25-758ae517a7ba`	| Check whether App Configuration can be accessed only through a private endpoint (Context-based restrictions or service) |	`AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` |	The rule was removed. |
| `rule-b5675539-fb0a-4464-93a3-f9c3ab1da0f8` |	Check whether App Configuration can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs |	`AC-4 CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was	added. |
| `rule-9b2822ec-cde3-4367-b3b7-3aabceb7ce13`	| Check whether Auto scale for VPC can be accessed only through a private endpoint (Context-based restrictions or service) |	`AC-4 CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` |	The rule was removed. |
| `rule-7cbf96ea-a032-4bc0-aae7-21d088965ef4` |	Check whether Auto scale for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4 CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)`	| The rule was added. |
| `rule-30e49535-38d9-4969-8f78-56cf8be67557`	| Check whether Backup for VPC can be accessed only through a private endpoint (Context-based restrictions or service) |	`AC-4 CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was	removed. |
| `rule-6b80be89-7c9f-472f-9ad2-363086fbcc86` |	Check whether Backup for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs |	`AC-4 CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was	added. |
| `rule-1399da2c-af02-47a3-bec1-0baa48297619` |	Check whether Bare Metal Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service) |	`AC-4 CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was	removed. |
| `rule-a6843b59-7e8b-4e5f-8f45-fe98a28269e2`	| Check whether Bare Metal Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs |	`AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-23aca5fe-3659-4b4d-a965-daad23ce2a01`| Check whether Block Storage for VPC can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-3d843573-0a71-44cc-926a-330fbcf80ec6`	| Check whether Block Storage for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs |	`AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-bf187b2f-0d3b-48f2-a5a7-cab0c0788c43`	| Check whether Block Storage Snapshots for VPC can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and SC-7(5)	| The rule was removed |
| `rule-af1c19bb-a40e-4798-92ad-57d4e9d540ba`	| Check whether Block Storage Snapshots for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| AC-4, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)` and `SC-7(5)` | The rule was	added. |
| `rule-8f3a6416-3621-4666-a2a7-271704432552` |	Check whether Client VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was	removed. |
| `rule-9d0ae8c0-7332-4b65-858c-56fe9875789f`	| Check whether Client VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, `SC-7(5)` | The rule was	added. |
| `rule-9eb7b514-5c27-43ba-83fc-26d75e0bf695`	| Check whether Cloud Object Storage can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | THe rule was	removed. |
| `rule-61878b48-e181-455d-aed3-5730b6e27890`	| Check whether Cloud Object Storage can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs |	`AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, `SC-7(5)` | The rule was added. |
| `rule-e9bae442-b92e-414d-88a9-d107511f554c`	| Check whether Code Engine can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-15e9118b-2fd4-46a7-a454-7af07b2b342c`	| Check whether Code Engine can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)`	| The rule was added. |
| `rule-87b52247-ec12-4e84-b328-d00491301e16`	| Check whether Container Registry can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was	removed. |
| `rule-94ca1725-f251-4cee-8c4c-280e141f194a`	| Check whether Container Registry can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)`| The rule was added. |
| `rule-4aebb5fe-61df-458c-b534-60fd644ae542`	| Check whether Dedicated Host for VPC can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, `SC-7(5)` | The rule was removed. |
| `rule-c5642f67-fb2c-4fe1-aed1-585d9215808f`	| Check whether Dedicated Host for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was	added. |
| `rule-94048ffe-f910-4ff2-881f-50df9005c0a2`	| Check whether Direct Link can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, `SC-7(5)`	| The rule was removed. |
| `rule-65627941-63ee-4f52-9248-3b5a09163965`	| Check whether Direct Link can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, `SC-7(5)` | The rule was added. |
| `rule-6252793f-9da5-4a04-9f9d-279b6e2c6907`	| Check whether DNS Services can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-dce07761-8ffd-4beb-a7cc-d38a17fffd4e`	| Check whether DNS Services can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was	added. |
| `rule-c9dfee2f-6283-43ce-9337-4eaacaa3313c`	| Check whether Event Notifications can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-0ffd34a1-3ca7-4d53-adbe-40f3980694e6`	| Check whether Event Notifications can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-762180a3-95e1-462b-a7ca-7995ca0dfb7c`	| Check whether Event Streams can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-23850407-cbf6-42cf-8985-f90b2c966d04`	| Check whether Event Streams can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` |	 The rule was added. |
| `rule-a4841766-a395-41be-8a64-b51e85168fab`	| Check whether Flow Logs for VPC can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-5593b5b5-dd27-45c9-b088-b40e447af5ef`	| Check whether Flow Logs for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-315c8bb3-3eb8-4186-85bc-e66d68ba9dd0`	| Check whether Hyper Protect Crypto Services can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)` and `SC-7(5)` | The rule was removed. |
| `rule-00882b45-ee37-4dc1-b948-afa618755fbd` |	Check whether Hyper Protect Crypto Services can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-0051b1c6-bee9-4e04-87e2-300e2c145104`	| Check whether IAM access groups can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-a534cbfa-1d2b-4b10-b405-7d6a0a969944`	| Check whether IAM access groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-e9a2d69f-757d-4371-8508-419fc13550f1`	| Check whether IAM access management can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)` and `SC-7(5)` | The rule was	removed. |
| `rule-8e7fd3c6-01aa-47b8-9898-ba34ebc27015`	| Check whether IAM access management can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)` and `SC-7(5)` | The rule was added. |
| `rule-0cddf009-8620-47e2-add9-e7609d82a221`	| Check whether IAM identities can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-56c515ef-4d2b-42e2-aa62-df4b37eab801`	| Check whether Kubernetes Service can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-4554e868-eb89-4b18-8692-564da18e0c2d`	| Check whether Kubernetes Service can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-b5a6bedd-16b0-4a21-bb01-04d70d48a752`	| Check whether Load Balancer for VPC can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-10b28c5d-27aa-4d03-b863-2e770090df74`	| Check whether Load Balancer for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-3d59273d-8ed1-4767-8112-c3f95ce09c3e`	| Check whether Schematics can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-553bdee0-a3c4-4ff9-a2f2-7903cc98ca2f`	| Check whether Schematics can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-c26980c7-5fae-47b7-ad2a-e96e87cf28fc`	| Check whether Secrets Manager can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-21fd1a1e-7909-48a4-949a-ada1785a34cf`	| Check whether Secrets Manager can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-d6b8cc81-b78b-49a5-87a3-34c71a198a71`	| Check whether Security and Compliance Center can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-5c9aed4a-af5e-47e0-8a86-cac8199aa90d`	| Check whether Security and Compliance Center can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-ff00ff6c-61d2-4a94-8de8-b150b4d35aab`	| Check whether there are no wild cards in the private endpoint allow list for IAM identities (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
|	`rule-b426a552-33c4-4b8d-8e71-659e06a45024`	| Check whether Transit Gateway can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-ca36ff5d-003b-4b21-b584-061a2ac5268a`	| Check whether Transit Gateway can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-7601aadc-cce6-4929-b3d2-26c4ba7e05ad`	| Check whether User Management can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-e54063a9-379f-4cdf-a00c-2fd02c8d9eda`	| Check whether User Management can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-9d963fd1-c56c-45ad-976e-96a45899b576`	| Check whether Virtual Private Cloud can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-29286737-f65b-41fb-8ba7-30e81f0f9dd8`	| Check whether Virtual Private Cloud can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-45e6a74e-74d4-495d-88da-f0cda147d8b4`	| Check whether Virtual Private Endpoints for VPC can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-fce897fe-d572-4412-9c74-828bfab0c26a`	| Check whether Virtual Private Endpoints for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-4a8fce3e-5bf4-4b57-8df7-c9f2f374abf3`	| Check whether Virtual Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-b6b7e67f-e7c2-4435-a883-80ab3d835d0e`	| Check whether Virtual Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-a3ee571a-b0fe-408f-9c8b-064e44fe99d5`	| Check whether VPC floating IPs can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-4736fc5d-63e2-4673-92e5-4c1f381645f5`	| Check whether VPC floating IPs can be accessed only through a private endpoint (Context-based restrictions or service) and allowed Ips | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` |  The rule was added. |
| `rule-72f16940-fa5b-4719-a7e8-35a1cc721a6a`	| Check whether VPC images can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-ed883cda-bdd3-48fd-972b-bf98b085423b`	| Check whether VPC images can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-eaff5bf5-7754-4218-8cb7-ae87ec8fdc7f`	| Check whether VPC network access control lists can be accessed only through a private endpoint (Context-based restrictions or service) |	`AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-9a64c779-5744-4bcc-a5ac-e4ad04b0f59c`	| Check whether VPC network access control lists can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-113e00c2-0503-4a09-8e6c-893ad51b6643`	| Check whether VPC placement groups can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-fdabbd31-1b00-4a84-aca2-6c57e8404b9e`	| Check whether VPC placement groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-3ead3fb3-9156-4d93-971c-7b782ceb00ae`	| Check whether VPC public gateways can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` |  The rule was	removed. |
| `rule-7758e8eb-c4d8-42a8-869f-30e3c189f6fa`	| Check whether VPC public gateways can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-02ad5735-93ba-4229-9d10-70dd48d0f96c`| Check whether VPC security groups can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-2b0fc034-063b-47a7-86e9-5a96c8ca9f23`	| Check whether VPC security groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-235d040e-ae2b-4832-9c28-b79cc2d6be6c`	| Check whether VPC SSH keys can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-b96fdad1-c2d5-4399-861f-49adecfd3485`	| Check whether VPC SSH keys can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-f33e4a5e-3297-4ec1-91b6-5f902fe87e75`	| Check whether VPC subnets can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-8b014ee6-2fcf-4e78-9412-d290251ff2a1`	| Check whether VPC subnets can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-2a1b103a-4ef3-416e-822a-abf556f8dbae`	| Check whether VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` |  The rule was removed. |
| `rule-a4cc268c-9c97-4dbb-b02f-bf74d5a5aa93`	| Check whether VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-3898fc92-305f-41c2-9464-c26ca71d639e`	| Check whether VPN for VPC has an **establish mode** configuration that is different from **peer_only** | `SC-13` | The rule was	added. |
| `rule-8226d451-d6a7-46a7-8313-f8c091d6e33f`	| Check whether IBM Cloud Kubernetes Service Ingress has TLS 1.2 enabled for all inbound traffic | `SC-11SC-13`, `SC-23`, `CM-7(b)`, `SC-7(4)(C)`, `SC-8` `SC-8(1)`	|  The rule was added. |
{: caption="Table. Summary of the changes for version 1.7.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}


## Version 1.6.0
{: #fs-cloud-v160}

The following rules were updated in the {{site.data.keyword.cloud_notm}} Framework for Financial Services library and profile as of 12 March 2024.

| Rule ID | Rule description| Associated controls | Update |
|:--------|:----------------|:--------------------|:-------|
| `rule-613c6100-b99c-4adc-8978-fab5e30523aa`	| Check whether Event Notifications is configured to work with Security and Compliance Center |	`SI-2 (a)` and `SI-5 (a)` |	The rule was added. |
| `rule-3826cfe4-c2bd-4c61-b462-acc46c6a251e`	| Check whether DevSecOps Toolchain verifies all changes to source code have been manually reviewed |	`CM-2(1)(a)`, `CM-2(1)(b)`, `CM-2(1)(c)`, `CM-3(2)(0)`, `CM-3(b)`, `CM-3(d)`, `CM-3(f)`, `CM-3(g)`, `CM-4(0)`, `CM-4(1)(0)`, `CM-5(0)`, `CM-6(1)(0)`, `CM-6(c)`, `CM-6(d)`, `CM-7(1)(a)`, `CM-9(a)`, `CM-9(b)`, `CM-9(c)`, `CM-9(d)`, `SA-10(a)`, `SA-10(b)`, `SA-10(c)`, `SA-10(d)`, `SA-10(e)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-4(3)(0)`, `SA-8(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(d)`, and `SI-7(0)`	| The rule was added. |
| `rule-59261292-1723-4234-9fa9-48df0088cde1`	| Check whether DevSecOps Toolchain validates signature provenance of each deployed artifact| `CM-3(2)(0)`, `CM-4(0)`, `SA-10(1)(0)`, `SA-10(b)`, `SA-10(c)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(d)`, and `SI-7(0)`	| The rule was added. |
| `rule-153b7f10-d8a8-43a2-8696-731de7790f06`	| Check whether virtual servers for VPC is provisioned from customer-defined list of images |	`CM-8(3)(a)` | The rule was removed. |
| `rule-709caded-75d6-4481-b9cd-de20851a9b19`	| Check whether virtual servers for VPC is provisioned from customer-defined list of images |	`CM-8(3)(a)`| The rule was added. |
|	`rule-ea8660d1-c322-4adb-8dc2-e0b77b6dc9fb`	| Check whether a security group other than the default for Virtual Private Cloud is attached to all endpoints	| `AC-4(0)`, `SC-7(a)`, `SC-7(b)`, `SC-7(c)`, and `SC-7(5)(0)`	| The rule was removed. |
| `rule-a1fff3f6-6428-4ad4-9be2-2171ce09fb8f` |	Check whether a security group other than the default for Virtual Private Cloud is attached to all endpoints	| `AC-4(0)`, `SC-7(a)`, `SC-7(b)`, `SC-7(c)`, and `SC-7(5)(0)`|	The rule was added. |
|	`rule-ac203dbc-ff0d-49f7-bf11-c08af429cb86`	| Check whether Cloud Object Storage network access is restricted to a specific IP range |	`AC-4(0)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`	| The rule was removed. |
| `rule-3027fd86-72c5-4c81-8ccd-ff556a922ec1`	| Check whether Cloud Object Storage network access is restricted to a specific IP range |	`AC-4(0)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`	| The rule was added. |
| `rule-3617cc3c-f6a5-44a5-806b-e929bbd664ba`	| Check whether OpenShift version is up-to-date |	`CM-8(3)(a)` and `SI-2(2)(0)`	| The rule was removed. |
| `rule-de84afba-b83a-41d6-8c80-d0b6acafe039`	| Check whether OpenShift version is up-to-date |	`CM-8(3)(a)` and `SI-2(2)(0)`	| The rule was added. |
|	`rule-79ed2fa6-e8b3-4fc4-8ea1-36055d527cd9`	| Check whether Event Streams is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK) | `SC-13`, `SC-28(0)`, and `SC-28(1)(0)`	| The rule was removed. |
| `rule-b9fec237-3867-4679-9f98-c1a3c8f2d249`	| Check whether Event Streams is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |	`SC-13`, `SC-28(0)`, and `SC-28(1)(0)`	| The rule was added. |
| `rule-255105cf-70f0-4494-a8c9-466ca6e558fb`	| Check whether Hyper Protect DBaaS for MongoDB is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |	`SC-13(0)`, `SC-28(0)`, and `SC-28(1)(0)`	| The rule was removed. |
|	`rule-9328227a-2750-4b5a-919f-a6342f1ed97d`	| Check whether Hyper Protect DBaaS for PostgreSQL is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |	`SC-13(0)`, `SC-28(0)`, and `SC-28(1)(0)`	| The rule was removed. |
|	`rule-184933d2-6819-4c07-ae05-3e46f1888e88`	| Check whether an OpenShift cluster has worker nodes across multiple zones |	`CP-7(a)`, `CP-7(b)`, `CP-7(c)`, `CP-7(1)(0)`, `CP-10(0)`, and `SC-6(0)` |	The rule was removed. |
| `rule-88f25dca-0e62-43c1-939e-f6637d23847f`	| Check whether a Red Hat OpenShift cluster has at least # worker nodes across multiple zones	| `CP-7(a)`, `CP-7(b)`, `CP-7(c)`, `CP-7(1)(0)`, `CP-10(0)`, and `SC-6(0)`	| The rule was added. |
{: caption="Table. Summary of the changes for version 1.6.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}

## Version 1.5.0
{: #fs-cloud-v150}

The following rules were updated in the {{site.data.keyword.cloud_notm}} Framework for Financial Services library and profile as of 23 September 2023.

The name of the profile has been changed from {{site.data.keyword.cloud_notm}} for Financial Services to {{site.data.keyword.cloud_notm}} Framework for Financial Services as part of this release.
{: tip}

| Rule ID | Rule description| Associated controls | Update |
|:--------|:----------------|:--------------------|:-------|
| `rule-17b54156-373a-48f9-b340-a7e47acd87b6` | Check whether Virtual Servers for VPC instance doesn't have a floating IP | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was removed. |
| `rule-7cf9deab-b418-4374-9e10-a13d217166bb` | Check whether virtual servers for VPC instance doesn't have a floating IP | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-c2dd768e-9a49-4d6d-8ac5-8fcfb233a7b0` | Check whether Virtual Private Cloud (VPC) has no subnet with public gateway attached | `AC-4(0)`, `SC-7(a)`, `SC-7(4)(a)(a)`, `SC-7(5)(0)`, and `SC-7(10)(0)` | The rule was removed. |
| `rule-c92a1ac3-6f9a-4fb1-9cb8-57d312679020` | Check whether Virtual Private Cloud (VPC) has no subnet with public gateway attached | `AC-4(0)`, `SC-7(a)`, `SC-7(4)(a)(a)`, `SC-7(5)(0)`, and `SC-7(10)(0)` | The rule was added. |
| `rule-de84afba-b83a-41d6-8c80-d0b6acafe039` | Check whether OpenShift version is up-to-date | `CM-8(3)(a)`, and `SI-2(2)(0)` | The rule was removed. |
| `rule-3617cc3c-f6a5-44a5-806b-e929bbd664ba` | Check whether OpenShift version is up-to-date | `CM-8(3)(a)`, and `SI-2(2)(0)` | The rule was added. |
| `rule-8cbd597c-7471-42bd-9c88-36b2696456e9` | Check whether Cloud Object Storage network access is restricted to a specific IP range | `AC-4(0)`,`SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)` | The rule was removed. |
| `rule-ac203dbc-ff0d-49f7-bf11-c08af429cb86` | Check whether Cloud Object Storage network access is restricted to a specific IP range | `AC-4(0)`,`SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)` | The rule was added. |
| `rule-0c2d0cef-a217-4eb0-a4ca-813fb2a08a31` | Check whether Event Notifications can be accessed only through a private endpoint |`AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was removed. |
| `rule-c9dfee2f-6283-43ce-9337-4eaacaa3313c` | Check whether Event Notifications can be accessed only through a private endpoint |`AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-f45487db-513e-4c49-b227-9101fdaf9259` | Check whether Secrets Manager can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was removed. |
| `rule-c26980c7-5fae-47b7-ad2a-e96e87cf28fc` |Check whether Secrets Manager can be accessed only through a private endpoint |`AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-dd1600d2-2e69-4ada-bca5-9e70b76ccd21` | Check whether App ID avoid password reuse policy is enabled | `CM-7(a)` | The rule was removed. |
| `rule-315c8bb3-3eb8-4186-85bc-e66d68ba9dd0` | Check whether Hyper Protect Crypto Services can be accessed only through a private endpoint | `IA-7(0)` | The rule was removed. |
| `rule-24508beb-c00a-4c6b-bd04-d38dd8cb7d71` | Check whether App ID user data is encrypted | `SC-13(0)`, `SC-28(0)`, and `SC-28(1)(0)` | The rule was removed. |
| `rule-b44ca99d-23fd-49cd-851a-b393f42dc8ba` | Check whether Container Registry image pushes, and pulls take place only over private endpoints | `CM-7(a)`, and `CM-7(b)` | The rule was added. |
| `rule-bf455a75-0ab7-406f-8321-b8bd10d01c50` | Check that there is an Activity Tracker event route defined in each region to collect location-based events | `AC-2(g)`, `AC-2(4)(0)`, `AC-2(7)(b)`, `AC-6(9)(0)`, `AU-2(a)`, `AU-2(d)`, `AU-3(0)`, `AU-8(a)`, `AU-8(b)`, `AU-8(1)(a)`, `AU-8(1)(b)`, `AU-12(a)`, `AU-12(b)`, `AU-12(c)`, `CA-7(d)`, `SI-4(a)`, `SI-4(b)`, and `SI-4(c)` | The rule was added. |
{: caption="Table. Summary of the changes for version 1.5.0 of the {{site.data.keyword.cloud_notm}} Framework for Financial Services profile" caption-side="top"}



## Version 1.4.0
{: #fs-cloud-v140}

The following rules were updated in the {{site.data.keyword.cloud_notm}} for Financial Services library and profile as of 9 August 2023.

|Rule ID | Rule Description | Associated controls | Update|
|:-------|:-----------------|:--------------------|:------|
| `rule-200dc6e7-96f1-49a9-9999-7e4645dc7ea6` | Check whether Application Load Balancer for VPC has public access disabled | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was removed. |
| `rule-ce6dff83-7280-4d25-a032-e5ff893e2fce` | Check whether Application Load Balancer for VPC has public access disabled | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-11425765-ea68-47e7-b4e0-c443ec0cbd19` | Check whether Event Streams network access is restricted to a specific IP range | `AC-4(0)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was removed. |
| `rule-3b2768e5-d783-4b0c-a47f-81479af34689` | Check whether Event Streams is accessible only by using private endpoints | `AC-4(0)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was removed. |
| `rule-762180a3-95e1-462b-a7ca-7995ca0dfb7c` | Check whether Event Streams can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-f6197ee2-31bf-4d73-aacd-316c41a48df3` | Check whether Cloud Object Storage is accessible only by using private endpoints | `AC-4(0)`| The rule was removed. |
| `rule-9eb7b514-5c27-43ba-83fc-26d75e0bf695` | Check whether Cloud Object Storage can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-c7e66875-56c6-4150-a7c9-879ff5c23c17` | Check whether Hyper Protect Crypto Services is accessible only through private endpoints | `IA-7(0)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was removed. |
| `rule-315c8bb3-3eb8-4186-85bc-e66d68ba9dd0` | Check whether Hyper Protect Crypto Services can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `IA-7(0)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-1d0a1c93-b89f-432e-af25-758ae517a7ba` | Check whether App Configuration can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-87b52247-ec12-4e84-b328-d00491301e16` | Check whether Container Registry can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-56c515ef-4d2b-42e2-aa62-df4b37eab801` | Check whether Kubernetes Service can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-94048ffe-f910-4ff2-881f-50df9005c0a2` | Check whether Direct Link can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-0c2d0cef-a217-4eb0-a4ca-813fb2a08a31` | Check whether Event Notifications can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-0051b1c6-bee9-4e04-87e2-300e2c145104` | Check whether IAM access groups can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-0cddf009-8620-47e2-add9-e7609d82a221` | Check whether IAM identities can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-e9a2d69f-757d-4371-8508-419fc13550f1` | Check whether IAM access management services can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-d6b8cc81-b78b-49a5-87a3-34c71a198a71` | Check whether Security and Compliance Center can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-e9bae442-b92e-414d-88a9-d107511f554c` | Check whether Code Engine can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-6252793f-9da5-4a04-9f9d-279b6e2c6907` | Check whether DNS Services can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-3d59273d-8ed1-4767-8112-c3f95ce09c3e` | Check whether Schematics can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-f45487db-513e-4c49-b227-9101fdaf9259` | Check whether Secrets Manager can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-b426a552-33c4-4b8d-8e71-659e06a45024` | Check whether Transit Gateway can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-7601aadc-cce6-4929-b3d2-26c4ba7e05ad` | Check whether User Management can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-9b2822ec-cde3-4367-b3b7-3aabceb7ce13` | Check whether Auto Scale for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-1399da2c-af02-47a3-bec1-0baa48297619` | Check whether Bare Metal Servers for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-23aca5fe-3659-4b4d-a965-daad23ce2a01` | Check whether Block Storage for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-bf187b2f-0d3b-48f2-a5a7-cab0c0788c43` | Check whether Block Storage Snapshots for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-8f3a6416-3621-4666-a2a7-271704432552` | Check whether Client VPN for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-4aebb5fe-61df-458c-b534-60fd644ae542` | Check whether Dedicated Host for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-a3ee571a-b0fe-408f-9c8b-064e44fe99d5` | Check whether VPC floating IPs can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-a4841766-a395-41be-8a64-b51e85168fab` | Check whether Flow Logs for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-30e49535-38d9-4969-8f78-56cf8be67557` | Check whether Backup for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-72f16940-fa5b-4719-a7e8-35a1cc721a6a` | Check whether VPC images can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-113e00c2-0503-4a09-8e6c-893ad51b6643` | Check whether VPC placement groups can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-b5a6bedd-16b0-4a21-bb01-04d70d48a752` | Check whether Load Balancer for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-eaff5bf5-7754-4218-8cb7-ae87ec8fdc7f` | Check whether VPC network access control lists can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-3ead3fb3-9156-4d93-971c-7b782ceb00ae` | Check whether VPC public gateways can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-02ad5735-93ba-4229-9d10-70dd48d0f96c` | Check whether VPC security groups can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-235d040e-ae2b-4832-9c28-b79cc2d6be6c` | Check whether VPC SSH keys can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-f33e4a5e-3297-4ec1-91b6-5f902fe87e75` | Check whether VPC subnets can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-9d963fd1-c56c-45ad-976e-96a45899b576` | Check whether Virtual Private Cloud can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-45e6a74e-74d4-495d-88da-f0cda147d8b4` | Check whether Virtual Private Endpoints for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-4a8fce3e-5bf4-4b57-8df7-c9f2f374abf3` | Check whether Virtual Servers for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-2a1b103a-4ef3-416e-822a-abf556f8dbae` | Check whether VPN for VPC can be accessed only through a private endpoint | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-7f249933-a745-462c-aa6b-fcde8fbba826` | Check whether there are no wild cards in the private endpoint allow list for Event Streams | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-78c2061b-b8fd-43ca-862f-582ab911c800` | Check whether there are no wild cards in the private endpoint allow list for Cloud Object Storage | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-94242843-07b4-496b-ac86-540aed2f74da` | Check whether there are no wild cards in the private endpoint allow list for Kubernetes Service | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-7ce216fc-90ee-4f61-8f3b-70d00321fe97` | Check whether there are no wild cards in the private endpoint allow list for Hyper Protect Crypto Services | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-466f9d3c-6e3c-4e2a-aa53-d6120018da83` | Check whether there are no wild cards in the private endpoint allow list for App Configuration| `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-08a4e6b2-45f7-456e-a9a9-0010ed2f72a3` | Check whether there are no wild cards in the private endpoint allow list for Container Registry| `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-c0d4d0e2-f014-46fa-9be1-8c03e59b443b` | Check whether there are no wild cards in the private endpoint allow list for Direct Link | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-9090851b-2577-4b2d-b790-d7c97a75681e` | Check whether there are no wild cards in the private endpoint allow list for Event Notifications | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-f88e215f-bb33-4bd8-bd1c-d8a065e9aa70` | Check whether there are no wild cards in the private endpoint allow list for IAM access groups | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-ff00ff6c-61d2-4a94-8de8-b150b4d35aab` | Check whether there are no wild cards in the private endpoint allow list for IAM identities | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-7e7c09f6-fc69-4a9c-9282-5d04c4eef96b` | Check whether there are no wild cards in the private endpoint allow list for IAM access management | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-554328f0-188f-4d1c-a088-f20f77248a32` | Check whether there are no wild cards in the private endpoint allow list for Security and Compliance Center | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-7937a8fd-a7ba-4c03-89ad-09726eb30c59` | Check whether there are no wild cards in the private endpoint allow list for Code Engine | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-bd17ba0b-d749-445f-9f8e-d0aa076bf575` | Check whether there are no wild cards in the private endpoint allow list for DNS Services | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-e1a1fc17-59dc-4e1e-b303-6b5442048f31` | Check whether there are no wild cards in the private endpoint allow list for Schematics | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-a805aeea-8037-4a99-be6e-4537089922a7` | Check whether there are no wild cards in the private endpoint allow list for Secrets Manager | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-83a7de4c-f63c-488b-b4ba-80bf8141cadd` | Check whether there are no wild cards in the private endpoint allow list for Transit Gateway | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-d1a21d53-67fe-4018-a670-f7a5840210ba` | Check whether there are no wild cards in the private endpoint allow list for User Management | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-d271f870-ceee-4c7b-80cd-afa656d91345` | Check whether there are no wild cards in the private endpoint allow list for Auto Scale for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-0f5956af-a27b-41b4-a0ba-2a5f7c241361` | Check whether there are no wild cards in the private endpoint allow list for Bare Metal Servers for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-7566b2cb-eb91-43b3-a661-154cf08664dc` | Check whether there are no wild cards in the private endpoint allow list for Block Storage for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-9d6236c6-6549-4722-b8ed-ef3f998396b2` | Check whether there are no wild cards in the private endpoint allow list for Block Storage Snapshots for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-38ed88e7-45b5-4c40-919a-5556796cf50e` | Check whether there are no wild cards in the private endpoint allow list for Client VPN for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-466c09e7-f7d5-47e5-a4b1-d89d0cb7b847` | Check whether there are no wild cards in the private endpoint allow list for Dedicated Host for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-af947fb3-f91d-4019-949e-ee25a3a441a7` | Check whether there are no wild cards in the private endpoint allow list for VPC floating IPs | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-e3981f0e-89f1-44c2-bf3c-05c280f3c93c` | Check whether there are no wild cards in the private endpoint allow list for Flow Logs for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-8c0d2fba-9f40-41ca-aad2-d65df81d4390` | Check whether there are no wild cards in the private endpoint allow list for Backup for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-18717f44-e8ed-4224-9e28-e8a0a2181766` | Check whether there are no wild cards in the private endpoint allow list for VPC images | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-e32c033a-0d2b-4477-8129-01ec758281e3` | Check whether there are no wild cards in the private endpoint allow list for VPC placement groups | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-6fd901b9-879a-4894-bda5-ed40fbe99730` | Check whether there are no wild cards in the private endpoint allow list for Load Balancer for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-eeba25ca-0084-4b84-9979-ef8477942df7` | Check whether there are no wild cards in the private endpoint allow list for VPC network access control lists | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-134ad94f-186c-410f-a97b-4d739627b881` | Check whether there are no wild cards in the private endpoint allow list for VPC public gateways | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-628cf4f7-1b07-472b-8162-ea95b9335397` | Check whether there are no wild cards in the private endpoint allow list for VPC security groups | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-97595caa-f691-41f3-991f-b06222b9ff8d` | Check whether there are no wild cards in the private endpoint allow list for SSH keys | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-2c129d6e-61b4-43cb-8dc0-81cb553afec3` | Check whether there are no wild cards in the private endpoint allow list for VPC subnets | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-cbfa30f4-f766-468d-a539-b83e3ce8901e` | Check whether there are no wild cards in the private endpoint allow list for Virtual Private Cloud | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-052e91d0-75be-46a8-9b95-dc6e72c78580` | Check whether there are no wild cards in the private endpoint allow list for Virtual Private Endpoints for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-454c9e3f-1441-4214-acb8-0c74980a1d75` | Check whether there are no wild cards in the private endpoint allow list for Virtual Servers for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
| `rule-821f0dd8-8516-45e0-bdde-17c726573d44` | Check whether there are no wild cards in the private endpoint allow list for VPN for VPC | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)` | The rule was added. |
{: caption="Table. Summary of the changes for version 1.4.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}


## Version 1.3.0
{: #fs-cloud-v130}

The following rules were updated in the {{site.data.keyword.cloud_notm}} for Financial Services library and profile as of 19 June 2023.

| Rule | Associated controls | Update |
|:-----|:--------------------|:-------|
| Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to RDP port | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)(0)`| The rule was removed. |
| Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to SSH port | `AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`| The rule was removed. |
| Check whether a security group other than the default for Virtual Private Cloud is attached to all endpoints | `SC-7(b)`, and `SC-7(c)`| The rule was added. |
| Check whether OpenShift version is up-to-date | `CP-7(a)`| The rule was removed. |
| Check whether permissions for API key creation are limited and configured in IAM settings for the account owner | `SC-12(0)`| The rule was removed. |
| Check that Hyper Protect Crypto Services has failover units in at least 2 different regions that are Financial Services Validated | `SI-12(0)`| The rule was removed. |
| Check whether App ID customer-provided email service is used | `CM-6(a)` | The rule was removed. |
| Check whether Container Registry image pushes and pulls take place only over private endpoints | `SA-3(a)` and `SA-3(d)`| The rule was removed. |
| Check whether App ID email verification is enabled for Cloud Directory users | `CM-6(a)`| The rule was removed. |
| Check whether Container Registry Vulnerability Advisor scans for critical or high vulnerabilities in the system at least every # day(s) | `CM-3(2)(0)`, `CM-4(0)`, `CM-4(1)(0)`, `CM-7(1)(a)`, `RA-5(c)`, `RA-5(d)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SA-10(e)`, `SA-15(a)`, `SI-2(b)`, `SI-2(c)` and `SI-2(d)`| The rule was added. |
| Check whether Cloud Object Storage bucket resiliency is set to cross region |`CP-6(1)(0)`, `CP-10(0)`, `CP-7(a)`, `CP-7(b)`, `CP-7(c)`, `CP-7(1)(0)`, `CP-9(b)`, `CP-9(d)`, and `SC-6(0)`  \n  \n  `CP-6(a)`, `CP-6(b)` `CP-10(0)`| The rule was added.  \n  \n  The rule was updated. |
| Check whether any Cloud Object Storage buckets used by Activity Tracker Event Routing are configured as cross-region | `AU-9(2)(0)`, `CP-6(a)`, `CP6(b)`, `CP-6(1)(0)`, `CP-7(a)`, `CP-7(b)`, `CP-7(c)`, `CP-7(1)(0)`, `CP-9(b)`, `CP-9(d)`, `CP-10(0)`, and `SC-6(0)`| The rule was removed. |
| Check whether any Cloud Object Storage buckets used by Activity Tracker Event Routing resiliency are set to cross region | `AU-9(2)(0)`, `CP-6(a)`, CP6(b), `CP-6(1)(0)`, `CP-7(a)`, `CP-7(b)`, `CP-7(c)`, `CP-7(1)(0)`, `CP-9(b)`, `CP-9(d)`, and `CP-10(0)`,| The rule was added. |
| Check whether Event Notifications are configured for Secrets manager | `SI-2(a)`, and `SI-5(a)`| The rule was added. |
| Check whether Event Notifications are configured for each of the supported Services | `SI-2(a)` and `SI-5(a)`| The rule was removed. |
| Check whether App ID email verification is enabled for Cloud Directory users | `IA-5(a)`| The rule was added. |
{: caption="Table. Summary of the changes for version 1.3.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}



## Version 1.2.0
{: #fs-cloud-v120}

The following rules were updated in the {{site.data.keyword.cloud_notm}} for Financial Services library and profile as of 20 April 2023.

| Rule | Associated controls | Update |
|:----|:---------|:---------|
| Check whether DevSecOps Toolchain scans source code and their dependencies to identify vulnerabilities | `CM-10(1)(0)`, `CM-3(2)(0)`, `CM-4(0)`, `CM-4(1)(0)`, `CM-7(1)(a)`, `RA-5(1)(0)`, `RA-5(2)(0)`, `RA-5(3)(0)`, `RA-5(a)`, `RA-5(b)`, `RA-5(c)`, `RA-5(d)`, `SA-10(e)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(b)`, `SI-2(c)`, and `SI-2(d)` | Rule was added |
| Check whether DevSecOps Toolchain passes unit tests to validate all code changes | `CM-3(2)(0)`, `SA-15(a)`, `SA-8(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(b)`, and `SI-2(d)` | Rule was added |
| Check whether DevSecOps Toolchain collects software bills of materials (SBOM) to provide transparency in build artifacts| `CM-2(0)`, `CM-2(1)(a)`, `CM-2(1)(b)`, `CM-2(1)(c)`, `CM-2(2)(0)`, `CM-2(3)(0)`, `CM-3(2)(0)`, `CM-3(e)`, `CM-3(f)`, `CM-8(1)(0)`, `CM-8(2)(0)`, `CM-8(a)`, `CM-8(b)`, `SA-10(a)`, `SA-10(b)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(d)`, and `SI-7(0)` | Rule was added |
| Check whether DevSecOps Toolchain signs build artifacts to attest their provenance | `CM-3(2)(0)`, `SA-10(1)(0)`, `SA-10(b)`, `SA-10(c)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(d)`, and `SI-7(0)` | Rule was added |
| Check whether DevSecOps Toolchain validates code against Center for Internet Security (CIS) Docker benchmarks to ensure container runtimes are configured securely | `CM-3(2)(0)`, `CM-4(0)`, `CM-4(1)(0)`, `CM-6(1)(0)`, `CM-6(a)`, `CM-6(b)`, `CM-6(c)`, `CM-6(d)`, `CM-7(1)(a)`, `CM-7(b)`, `RA-5(1)(0)`, `RA-5(2)(0)`, `RA-5(3)(0)`, `RA-5(a)`, `RA-5(b)`, `RA-5(c)`, `RA-5(d)`, `SA-10(e)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(b)`, `SI-2(c)` and `SI-2(d)` | Rule was added |
| Check whether DevSecOps Toolchain verifies source code branch protection rules to enforce security policies | `CM-3(2)(0)`, `CM-4(0)`, `CM-5(0)`, `CM-9(a)`, `CM-9(d)`, `SA-10(b)`, `SA-10(e)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(b)`, `SI-2(d)`, and `SI-7(0)` | Rule was added |
| Check whether DevSecOps Toolchain source code contains no secrets | `CM-3(2)(0)`, `CM-4(0)`, `CM-4(1)(0)`, `CM-7(1)(a)`, `CM-9(d)`, `RA-5(1)(0)`, `RA-5(2)(0)`, `RA-5(3)(0)`, `RA-5(a)`, `RA-5(b)`, `RA-5(c)`, `RA-5(d)`, `SA-10(e)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(b)`, `SI-2(c)`, and `SI-2(d)` | Rule was added |
| Check whether DevSecOps Toolchain deployment has approved change documentation including security impact analysis | `CM-2(0)`, `CM-2(1)(a)`, `CM-2(1)(b)`, `CM-2(1)(c)`, `CM-2(2)(0)`, `CM-2(3)(0)`, `CM-3(2)(0)`, `CM-3(a)`, `CM-3(b)`, `CM-3(c)`, `CM-3(d)`, `CM-3(e)`, `CM-3(f)`, `CM-3(g)`, `CM-4(0)`, `CM-6(1)(0)`, `CM-6(c)`, `CM-6(d)`, `CM-8(1)(0)`, `CM-8(2)(0)`, `CM-8(a)`, `CM-8(b)`, `CM-9(a)`, `CM-9(b)`, `CM-9(c)`, `SA-10(a)`, `SA-10(b)`, `SA-10(c)`, `SA-10(d)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(b)`, `SI-2(c)`, `SI-2(d)`, and `SI-7(0)` | Rule was added |
| Check whether DevSecOps Toolchain scans build artifacts to identify vulnerabilities | `CM-3(2)(0)`, `CM-4(0)`, `CM-4(1)(0)`,   `CM-7(1)(a)`, `RA-5(1)(0)`, `RA-5(2)(0)`, `RA-5(3)(0)`, `RA-5(a)`, `RA-5(b)`, `RA-5(c)`, `RA-5(d)`, `SA-10(e)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(b)`, `SI-2(c)`, and `SI-2(d)` | Rule was added |
| Check whether DevSecOps Toolchain passes acceptance tests to validate every deployment | `CM-3(2)(0)`, `CM-4(1)(0)`, `CM-9(a)`, `RA-5(c)`, `RA-5(d)`, `SA-15(a)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(b)`, and `SI-2(d)` | Rule was added |
| Check whether Toolchain is configured only with the allowed integration tools | `CM-3(2)(0)` and `SA-8(0)` | Rule was added |
| Check whether DevSecOps Toolchain passes static code scan to identify vulnerabilities in source code | `CM-3(2)(0)`, `CM-4(0)`, `CM-4(1)(0)`, `CM-7(1)(a)`, `CM-7(b)`, `RA-5(1)(0)`, `RA-5(2)(0)`, `RA-5(3)(0)`, `RA-5(a)`, `RA-5(b)`, `RA-5(c)`, `RA-5(d)`, `SA-10(e)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SI-10(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(b)`, `SI-2(c)`, and `SI-2(d)` | Rule was added |
| Check whether DevSecOps Toolchain passes dynamic code scan to identify vulnerabilities in deployed artifacts | `CM-3(2)(0)`, `CM-4(0)`, `CM-4(1)(0)`, `CM-7(1)(a)`, `CM-7(b)`, `RA-5(1)(0)`, `RA-5(2)(0)`, `RA-5(3)(0)`, `RA-5(a)`, `RA-5(b)`, `RA-5(c)`, `RA-5(d)`, `SA-10(e)`, `SA-15(a)`, `SA-3(a)`, `SA-3(d)`, `SA-8(0)`, `SI-10(0)`, `SI-2(2)(0)`, `SI-2(a)`, `SI-2(b)`, `SI-2(c)`, and `SI-2(d)` | Rule was added |
| Check whether Secrets Manager arbitrary secrets are rotated at least every # days | `IA-5(g)` | Rule was added |
| Check whether Secrets Manager user credentials are rotated at least every # days | `IA-5(g)` | Rule was added |
| Check whether Container Registry Vulnerability Advisor scans for critical or high vulnerabilities in the system at least every # day(s) | `RA-5(b)` and `RA-5(3)(0)` | Rule was added |
| Check whether a security group other than the default for Virtual Private Cloud is attached to all endpoints | `CM-1` | Rule was removed |
| Check whether Container Registry Vulnerability Advisor scans for critical or high vulnerabilities in the system at least every # day(s) | `CM-8(3)(a)` | Rule was removed |
{: caption="Table. Summary of the changes for version 1.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}


## Version 1.1.0
{: #fs-cloud-v110}

Version 1.1.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile has been updated to include all 565 controls that have been identified as required to ensure that you are compliant with the {{site.data.keyword.cloud_notm}} Framework for Financial Services reference architecture. As part of that update we've introduced the concept of "Manual assessments". When results are returned, you will see a new status: `user_evaluation_required` - this indicates that the control must be evaluated manually by your organization as the control check is either not yet or cannot be automated.

Additionally, the phrasing of 42 controls was updated for grammar purposes. For example, controls that use the Activity Tracker Event Tracking service were updated to include the correct capitalization.


## Version 1.0.0
{: #fs-cloud-v100}

The format of the {{site.data.keyword.cloud_notm}} for Financial Services profile has been updated with the following changes. Review your configuration closely to ensure that the profile still meets your needs.
- The profile is available only on the **Profiles** page of the **Manage** section of the updated infrastructure.
- The format changed from being goal-based to assessment-based.

Starting with version 1.0.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile, all new versions of the profile that become available will be compatible only with the updated service architecture. To upgrade your profile version, you must move to the new evaluation format. For more information, see [Getting started](/docs/security-compliance?topic=security-compliance-getting-started).
{: important}
