---
copyright:
  years: "2025"
lastupdated: "2025-05-09"

keywords: "release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements, ai security"

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: {{site.data.keyword.cloud_notm}} Framework for Financial Services (Moderate)
{: #moderate-fs-change-log}

In this change log, you can learn about the latest changes, improvements, and updates for the Service Organization Control (IBM Cloud Framework for Financial Services (Moderate)) profile. The change log lists changes that were made, ordered by the version number.

## Profile versioning
{: #moderate-fs-versioning}

When specifications or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new version is released. To take advantage of the changes in a new version, update your attachments to use the newest profile version.

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Be sure to validate the available controls to determine where you might need to supplement your workloads with other security measures.
{: important}


### Version summary
{: #moderate-fs-versions}

The following table details the release dates and status of each profile version.

New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
{: important}

| Version number | Release date | Status |
|:---------------|:-------------|:-------|
| Version 1.2.0 | `2025-04-03` | Active |
| Version 1.1.0 | `2024-08-27` | Active |
| Version 1.0.0 | `2024-06-06` | Active |
{: caption="Table. Active versions of the IBM Cloud Framework for Financial Services (Moderate) profile" caption-side="top"}


## Version 1.2.0
{: #moderate-fs-v120}

The following rules were updated in the {{site.data.keyword.cloud_notm}} for Financial Services library and profile as of 31 March 2025.

| Rule ID | Rule description| Associated controls | Update |
|:--------|:----------------|:--------------------|:-------|
| `rule-ed64fa73-81e5-4920-8519-acfad845dd6c`	| Check whether Identity and Access Management (IAM) is enabled with audit logging |	`AC-2(g)`, `AC-2(4)`, `AC-2(7)(b)`, `AC-6(9)`, `AU-2(a)`, `AU-2(d)`, `AU-3`, `AU-8(a)`, `AU-8(b)`, `AU-8(1)(a)`, `AU-8(1)(b)`, `AU-12(a)`, `AU-12(b)`, `AU-12©`, `CA-7(d)`, `SI-4(a)`, `SI-4(b)`, and `SI-4(c)` | The rule is removed. |
{: caption="Table. Summary of the changes for version 1.2.0 of the {{site.data.keyword.cloud_notm}} Framework for Financial Services (Moderate)" caption-side="top"}


## Version 1.1.0
{: #moderate-fs-v110}

The following rules were updated in the {{site.data.keyword.cloud_notm}} for Financial Services library and profile as of 27 August 2024.

| Rule ID | Rule description| Associated controls | Update |
|:--------|:----------------|:--------------------|:-------|
| `rule-1d0a1c93-b89f-432e-af25-758ae517a7ba`	| Check whether App Configuration can be accessed only through a private endpoint (Context-based restrictions or service) |	`AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-b5675539-fb0a-4464-93a3-f9c3ab1da0f8`	| Check whether App Configuration can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-9b2822ec-cde3-4367-b3b7-3aabceb7ce13` |	Check whether Auto scale for VPC can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was	removed. |
| `rule-7cbf96ea-a032-4bc0-aae7-21d088965ef4`	| Check whether Auto scale for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| rule-30e49535-38d9-4969-8f78-56cf8be67557	| Check whether Backup for VPC can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was	removed. |
| `rule-6b80be89-7c9f-472f-9ad2-363086fbcc86`	| Check whether Backup for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-1399da2c-af02-47a3-bec1-0baa48297619`	| Check whether Bare Metal Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-a6843b59-7e8b-4e5f-8f45-fe98a28269e2`	| Check whether Bare Metal Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-23aca5fe-3659-4b4d-a965-daad23ce2a01`	| Check whether Block Storage for VPC can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-3d843573-0a71-44cc-926a-330fbcf80ec6`	| Check whether Block Storage for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-bf187b2f-0d3b-48f2-a5a7-cab0c0788c43`	| Check whether Block Storage Snapshots for VPC can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-af1c19bb-a40e-4798-92ad-57d4e9d540ba`	| Check whether Block Storage Snapshots for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-8f3a6416-3621-4666-a2a7-271704432552`	| Check whether Client VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-9d0ae8c0-7332-4b65-858c-56fe9875789f`	| Check whether Client VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-9eb7b514-5c27-43ba-83fc-26d75e0bf695`	| Check whether Cloud Object Storage can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-61878b48-e181-455d-aed3-5730b6e27890`	| Check whether Cloud Object Storage can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-e9bae442-b92e-414d-88a9-d107511f554c`	| Check whether Code Engine can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-15e9118b-2fd4-46a7-a454-7af07b2b342c`	| Check whether Code Engine can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-87b52247-ec12-4e84-b328-d00491301e16`	| Check whether Container Registry can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was	removed. |
| `rule-94ca1725-f251-4cee-8c4c-280e141f194a`	| Check whether Container Registry can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-4aebb5fe-61df-458c-b534-60fd644ae542`	| Check whether Dedicated Host for VPC can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-c5642f67-fb2c-4fe1-aed1-585d9215808f`	| Check whether Dedicated Host for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-94048ffe-f910-4ff2-881f-50df9005c0a2`	| Check whether Direct Link can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-65627941-63ee-4f52-9248-3b5a09163965`	| Check whether Direct Link can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-6252793f-9da5-4a04-9f9d-279b6e2c6907`	| Check whether DNS Services can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-dce07761-8ffd-4beb-a7cc-d38a17fffd4e`	| Check whether DNS Services can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-c9dfee2f-6283-43ce-9337-4eaacaa3313c`	| Check whether Event Notifications can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-0ffd34a1-3ca7-4d53-adbe-40f3980694e6` |	Check whether Event Notifications can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| A`AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-762180a3-95e1-462b-a7ca-7995ca0dfb7c` |	Check whether Event Streams can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-23850407-cbf6-42cf-8985-f90b2c966d04`	| Check whether Event Streams can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-a4841766-a395-41be-8a64-b51e85168fab`	| Check whether Flow Logs for VPC can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-5593b5b5-dd27-45c9-b088-b40e447af5ef`	| Check whether Flow Logs for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-315c8bb3-3eb8-4186-85bc-e66d68ba9dd0`	| Check whether Hyper Protect Crypto Services can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-00882b45-ee37-4dc1-b948-afa618755fbd`	| Check whether Hyper Protect Crypto Services can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| A`AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-0051b1c6-bee9-4e04-87e2-300e2c145104`	| Check whether IAM access groups can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-a534cbfa-1d2b-4b10-b405-7d6a0a969944`	| Check whether IAM access groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-e9a2d69f-757d-4371-8508-419fc13550f1`	| Check whether IAM access management can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-8e7fd3c6-01aa-47b8-9898-ba34ebc27015`	| Check whether IAM access management can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-0cddf009-8620-47e2-add9-e7609d82a221`	| Check whether IAM identities can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-56c515ef-4d2b-42e2-aa62-df4b37eab801`	| Check whether Kubernetes Service can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-4554e868-eb89-4b18-8692-564da18e0c2d`	| Check whether Kubernetes Service can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-b5a6bedd-16b0-4a21-bb01-04d70d48a752`	| Check whether Load Balancer for VPC can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-10b28c5d-27aa-4d03-b863-2e770090df74`	| Check whether Load Balancer for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added.	|
| `rule-3d59273d-8ed1-4767-8112-c3f95ce09c3e`	| Check whether Schematics can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-553bdee0-a3c4-4ff9-a2f2-7903cc98ca2f`	| Check whether Schematics can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-c26980c7-5fae-47b7-ad2a-e96e87cf28fc`	| Check whether Secrets Manager can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-21fd1a1e-7909-48a4-949a-ada1785a34cf`	| Check whether Secrets Manager can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-d6b8cc81-b78b-49a5-87a3-34c71a198a71`	| Check whether Security and Compliance Center can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-5c9aed4a-af5e-47e0-8a86-cac8199aa90d`	| Check whether Security and Compliance Center can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-ff00ff6c-61d2-4a94-8de8-b150b4d35aab`	| Check whether there are no wild cards in the private endpoint allow list for IAM identities (Context-based restrictions or service) |	`AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-b426a552-33c4-4b8d-8e71-659e06a45024`	| Check whether Transit Gateway can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-ca36ff5d-003b-4b21-b584-061a2ac5268a`	| Check whether Transit Gateway can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-7601aadc-cce6-4929-b3d2-26c4ba7e05ad`	| Check whether User Management can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-e54063a9-379f-4cdf-a00c-2fd02c8d9eda`	| Check whether User Management can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-9d963fd1-c56c-45ad-976e-96a45899b576`	| Check whether Virtual Private Cloud can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-29286737-f65b-41fb-8ba7-30e81f0f9dd8`	| Check whether Virtual Private Cloud can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-45e6a74e-74d4-495d-88da-f0cda147d8b4`	| Check whether Virtual Private Endpoints for VPC can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-fce897fe-d572-4412-9c74-828bfab0c26a`	| Check whether Virtual Private Endpoints for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-4a8fce3e-5bf4-4b57-8df7-c9f2f374abf3`	| Check whether Virtual Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service)	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-b6b7e67f-e7c2-4435-a883-80ab3d835d0e`	| Check whether Virtual Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs	| `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-a3ee571a-b0fe-408f-9c8b-064e44fe99d5`	| Check whether VPC floating IPs can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-4736fc5d-63e2-4673-92e5-4c1f381645f5`	| Check whether VPC floating IPs can be accessed only through a private endpoint (Context-based restrictions or service) and allowed Ips | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-72f16940-fa5b-4719-a7e8-35a1cc721a6a`	| Check whether VPC images can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-ed883cda-bdd3-48fd-972b-bf98b085423b`	| Check whether VPC images can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-eaff5bf5-7754-4218-8cb7-ae87ec8fdc7f`	| Check whether VPC network access control lists can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-9a64c779-5744-4bcc-a5ac-e4ad04b0f59c` | Check whether VPC network access control lists can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-113e00c2-0503-4a09-8e6c-893ad51b6643`	| Check whether VPC placement groups can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-fdabbd31-1b00-4a84-aca2-6c57e8404b9e`	| Check whether VPC placement groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-3ead3fb3-9156-4d93-971c-7b782ceb00ae`	| Check whether VPC public gateways can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-7758e8eb-c4d8-42a8-869f-30e3c189f6fa`	| Check whether VPC public gateways can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-02ad5735-93ba-4229-9d10-70dd48d0f96c`	| Check whether VPC security groups can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-2b0fc034-063b-47a7-86e9-5a96c8ca9f23`	| Check whether VPC security groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-235d040e-ae2b-4832-9c28-b79cc2d6be6c`	| Check whether VPC SSH keys can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-b96fdad1-c2d5-4399-861f-49adecfd3485`	| Check whether VPC SSH keys can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-f33e4a5e-3297-4ec1-91b6-5f902fe87e75`	| Check whether VPC subnets can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-8b014ee6-2fcf-4e78-9412-d290251ff2a1`	| Check whether VPC subnets can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs |	`AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-2a1b103a-4ef3-416e-822a-abf556f8dbae`	| Check whether VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was removed. |
| `rule-a4cc268c-9c97-4dbb-b02f-bf74d5a5aa93`	| Check whether VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs | `AC-4`, `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)`, and `SC-7(5)` | The rule was added. |
| `rule-3898fc92-305f-41c2-9464-c26ca71d639e`	| Check whether VPN for VPC has an **establish mode** configuration that is different from **peer_only** | `SC-13` | The rule was added. |
| `rule-8226d451-d6a7-46a7-8313-f8c091d6e33f`	| Check whether IBM Cloud Kubernetes Service Ingress has TLS 1.2 enabled for all inbound traffic |	`SC-11SC-13`, `SC-23`, `CM-7(b)`, `SC-7(4)(C)`, `SC-8`, and `SC-8(1)` | The rule was added. |
{: caption="Table. Summary of the changes for version 1.1.0 of the {{site.data.keyword.cloud_notm}} Framework for Financial Services (Moderate)" caption-side="top"}


## Version 1.0.0
{: #moderate-fs-version1}

Now available
:   As of 6 June 2024, the IBM Cloud Framework for Financial Services (Moderate) profile is a collection of controls that is designed to validate the configuration of your resources.


The following changes were made.

- All the existing customer-managed encryption Keep Your Own Key (KYOK) rules were replaced with customer-managed encryption (Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)).

The following rules were added.

| Rule ID | Rule description| Associated controls | Update |
|:--------|:----------------|:--------------------|:-------|
| `rule-ed64fa73-81e5-4920-8519-acfad845dd6c` | Check whether Identity and Access Management (IAM) is enabled with audit logging | `AC-2(4)`, `AC-2(7)(b)`, `AC-2(g)`, `AC-6(9)`, `AU-12(a)`, `AU-12(b)`, `AU-12(c)`, `AU-2(a)`, `AU-2(d)`, `AU-3`, `AU-8(1)(a),` `AU-8(1)(b)`, `AU-8(a)`, `AU-8(b)`, `CA-7(d)`, `SI-4(a)`, `SI-4(b)`, and `SI-4(c)` | The rule was added. |
{: caption="Table. Summary of the changes for version 1.0.0 of the {{site.data.keyword.cloud_notm}} Framework for Financial Services (Moderate)" caption-side="top"}
