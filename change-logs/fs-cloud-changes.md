---

copyright:
  years: 2020, 2023
lastupdated: "2023-07-24"

keywords: release notes for {{site.data.keyword.compliance_short}}, what's new, enhancements, fixes, improvements

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: {{site.data.keyword.cloud_notm}} for Financial Services profile
{: #fs-change-log}

In this change log, you can learn about the latest changes, improvements, and updates for the {{site.data.keyword.cloud_notm}} for Financial Services profile. The change log lists changes that were made, ordered by the version number.

## Profile versioning
{: #fs-profile-versioning}

When goals or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new minor version is released. To take advantage of the changes in a new version, update your scans to use the newest profile version. 

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Users can validate the available goals and determine where a need to supplement their workloads with other security measures exists.
{: important}


### Active versions
{: #fs-active-versions}

The following table shows the service behavior changes for each version date. Switching to a later version date activates all changes that are introduced in earlier versions.

| Version number | Release date |
|:---------------|:-------------|
| Version 1.3.0 | `2023-06-20` |
| Version 1.2.0 | `2023-04-20` |
| Version 1.1.0 | `2023-03-02` |
| Version 1.0.0 | `2022-12-14` |
{: caption="Table. Active versions of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}



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

Version 1.1.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile has been updated to include all 565 controls that have been identified as required to ensure that you are compliant with the {{site.data.keyword.cloud_notm}} for Financial Services reference architecture. As part of that update we've introduced the concept of "Manual assessments". When results are returned, you will see a new status: `user_evaluation_required` - this indicates that the control must be evaluated manually by your organization as the control check is either not yet or cannot be automated.

Additionally, the phrasing of 42 controls was updated for grammar purposes. For example, controls that use the Activity Tracker Event Tracking service were updated to include the correct capitalization.


## Version 1.0.0
{: #fs-cloud-v100}

The format of the {{site.data.keyword.cloud_notm}} for Financial Services profile has been updated with the following changes. Review your configuration closely to ensure that the profile still meets your needs.
- The profile is available only on the **Profiles** page of the **Manage** section of the updated infrastructure.
- The format changed from being goal-based to assessment-based.

Starting with version 1.0.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile, all new versions of the profile that become available will be compatible only with the updated service architecture. To upgrade your profile version, you must move to the new evaluation format. For more information, see [Getting started](/docs/security-compliance?topic=security-compliance-getting-started).
{: important}
