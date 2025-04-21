---
copyright:
  years: "2025"
lastupdated: "2025-04-21"

keywords: "release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements, Information Technology Security Guidance, "

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Information Technology Security Guidance (ITSG)
{: #itsg-change-log}

In this change log, you can learn about the latest changes, improvements, and updates for the Service Organization Control (Information Technology Security Guidance) profile. The change log lists changes that were made, ordered by the version number.

An ITSG compliance profile is a collection of pre-selected security controls from the Information Technology Security Guidance (ITSG) 33 catalog that are tailored to a specific business environment. The ITSG 33 is a document published by the Canadian Centre for Cybersecurity (CCCS) that covers IT security risk management.

## Profile versioning
{: #itsg-iec-versioning}

When specifications or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new version is released. To take advantage of the changes in a new version, update your attachments to use the newest profile version.

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Be sure to validate the available controls to determine where you might need to supplement your workloads with other security measures.
{: important}


### Version summary
{: #itsg-versions}

The following table details the release dates and status of each profile version.

New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
{: important}

| Version number | Release date | Status |
|:---------------|:-------------|:-------|
| Version 1.1.0 | `2025-04-03` | Active |
| Version 1.0.0 | `2024-10-29` | Active |
{: caption="Active versions of the Information Technology Security Guidance (ITSG) profile" caption-side="top"}



## Version 1.1.0
{: #itsg-iec-version110}

The following rules were updated in the {{site.data.keyword.cloud_notm}} for Information Technology Security Guidance (ITSG) as of 31 March 2025.

| Rule ID | Rule description| Associated controls | Update |
|:--------|:----------------|:--------------------|:-------|
| `rule-3d16d1a3-1b73-47d1-b862-407e8c0a4039`	| Check whether Activity Tracker is provisioned in allowed region |	`SI-12(0)` | The rule is removed. |
| `rule-2aa7888e-ed67-40f3-9bff-8a70fddb4671`	| Check whether IBM Log Analysis can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not |	`AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(4)(a)`, `SC-7(5)(0)`, `SC-7(a)`, and `SC-7(b)` | The rule is removed. |
| `rule-14808a2d-ab9b-4333-8275-f12559620cbb`	| Check whether there are no wild cards and wide flows in the private and public endpoints allow list for IBM Log Analysis (Context-based restrictions or service) |	`AC-4(0)`, `CM-7(a)`, `CM-7(b)`, `SC-7(4)(a)`, `SC-7(5)(0)`, `SC-7(a)`, and `SC-7(b)` | The rule is removed. |
{: caption="Table. Summary of the changes for version 1.1.0 of the {{site.data.keyword.cloud_notm}} Framework for Financial Services (Moderate)" caption-side="top"}


## Version 1.0.0
{: #itsg-iec-version1}

Now available
:   As of 29 October 2024, the Information Technology Security Guidance (ITSG) profile is available.
