---

copyright:
  years: 2020, 2024
lastupdated: "2024-02-26"

keywords: release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: {{site.data.keyword.cloud_notm}} Security Best Practices
{: #ibm-sec-best-practices-change-log}

The {{site.data.keyword.cloud_notm}} Security Best Practices library is a collection of controls and goals that meet {{site.data.keyword.cloud_notm}} and industry best practices. The library is consistently updated and can change at any time, which can cause your compliance score to change without any update to your configuration. A new version is released when new controls or specifications are edited or removed from the library in a way that is not compatible with the current version.

As of 12 September 2023, this profile is deprecated. Switch to another profile to ensure continued support. [Learn more.](/docs/security-compliance?topic=security-compliance-release-notes#security-compliance-sep1223)
{: deprecated}

## Profile versioning
{: #fs-profile-versioning}

A new minor version is released when goals or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version. To take advantage of the changes in a new version, update your scans to use the newest profile version. 

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Users can validate the available goals and determine where a need to supplement their workloads with other security measures exists.
{: important}


### Version summary
{: #bp-active-versions}

The following table details the release dates and status of each profile version.

New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
{: important}

| Version number | Release date | Status |
|:---------------|:-------------|:-------|
| Version 1.2.0 | `2023-06-20` | Active |
| Version 1.1.0 | `2023-04-17` | Active |
| Version 1.0.0 | `2022-12-14` | Active |
{: caption="Table. Active versions of the {{site.data.keyword.cloud_notm}} Security Best Practices profile" caption-side="top"}

## Version 1.2.0
{: #sec-best-v1.2.0}

The following changes were made to the {{site.data.keyword.cloud_notm}} Security Best Practices library and profile.

| Rule | Associated controls | Update |
|:-----|:--------------------|:-------|
| Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to SSH port | `4.43` | The rule was removed. |	
| Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to RDP port | `4.44` | The rule was removed. |	
| Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to SSH port | `4.4` | The rule was removed. |	
| Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to RDP port | `4.5` | The rule was removed. |	
| IBMid does not allow changed or reset passwords to be the same as any of the 24 previously used passwords | `1.62` | The rule was removed. |
{: caption="Table. Rule updates for the {{site.data.keyword.cloud_notm}} Security Best Practices profile version 1.2.0" caption-side="top"}


## Version 1.1.0
{: #sec-best-v1.1.0}

The following changes have been made to the {{site.data.keyword.cloud_notm}} Security Best Practices library and profile.

### 17 April 2023
{: #v1.1.0-17-april}


The following controls and rules were updated in the {{site.data.keyword.cloud_notm}} Security Best Practices library and profile as of 17 April 2023.

| Control ID | Original control text| Updated control text | 
|:--------------|:--------------|:--------------|
| 6.1 | Ensure Toolchain scans during continuous integration the source code to identify vulnerabilities | Ensure DevSecOps Toolchain scans source code and their dependencies to identify vulnerabilities |
| 6.2 | Ensure Toolchain has unit tests that are continuously run to validate source code changes | Ensure DevSecOps Toolchain passes unit tests to validate all code changes |
| 6.3 | Ensure Toolchain has Code Risk Analyzer configured that collects a bill of materials for pipeline run | Ensure DevSecOps Toolchain collects software bills of materials (SBOM) to provide transparency in build artifacts |
| 6.4 | Ensure Toolchain is configured with image signing | Ensure DevSecOps Toolchain signs build artifacts to attest their provenance |
| 6.5 | Ensure Toolchain source code meets Center for Internet Security Docker benchmarks	|	Ensure DevSecOps Toolchain validates code against Center for Internet Security (CIS) Docker benchmarks to ensure container runtimes are configured securely |
| 6.6 | Ensure Toolchain has branch protection rules enabled | Ensure DevSecOps Toolchain verifies source code branch protection rules to enforce security policies | 
| 6.7 | Ensure Toolchain has secret detection scans enabled for source code	|	Ensure DevSecOps Toolchain source code contains no secrets |
| 6.8 | Ensure Toolchain production change request exists and is approved	| Ensure DevSecOps Toolchain deployment has approved change documentation including security impact analysis |
| 6.9 | Ensure Toolchain Container Registry Vulnerability Advisor scans images for OS vulnerability detection | Ensure DevSecOps Toolchain scans build artifacts to identify vulnerabilities |
| 6.12 | Ensure Toolchain acceptance tests exist and have passed | Ensure DevSecOps Toolchain passes acceptance tests to validate every deployment |
| 6.16 | Ensure that only the tool integrations within the toolchain are included in the allow list parameter array | Ensure Toolchain is configured only with the allowed integration tools |
| 6.17 | Ensure a Toolchain static scan exists and has passed | Ensure DevSecOps Toolchain passes static code scan to identify vulnerabilities in source code |
| 6.18 | Ensure a Toolchain dynamic scan exists and has passed | Ensure DevSecOps Toolchain passes dynamic code scan to identify vulnerabilities in deployed artifacts |
{: caption="Table. Understanding control and rule updates" caption-side="top"}
{: #scc-bp-1}
{: tab-title="Control"}
{: tab-group="v1.1"}
{: class="simple-tab-table"}

| Control ID | Original rule text| Updated rule text | 
|:--------------|:--------------|:--------------|
| 6.1 | Check whether the toolchain scans during continuous integration the source code to identify vulnerabilities | Check whether DevSecOps Toolchain scans source code and their dependencies to identify vulnerabilities |
| 6.2 | Check whether Toolchain has unit tests that are continuously run to validate source code changes | Check whether DevSecOps Toolchain passes unit tests to validate all code changes |
| 6.3 | Check whether Toolchain has Code Risk Analyzer configured that collects a bill of materials for pipeline run | Check whether DevSecOps Toolchain collects software bills of materials (SBOM) to provide transparency in build artifacts |
| 6.4 | Check whether Toolchain is configured with image signing | Check whether DevSecOps Toolchain signs build artifacts to attest their provenance |
| 6.5 | Check whether Toolchain source code meets Center for Internet Security Docker benchmarks |	Check whether DevSecOps Toolchain validates code against Center for Internet Security (CIS) Docker benchmarks to ensure container runtimes are configured securely |
| 6.6 | Check whether Toolchain has branch protection rules enabled	|	Check whether DevSecOps Toolchain verifies source code branch protection rules to enforce security policies |
| 6.7 | Check whether Toolchain has secret detection scans enabled for source code | Check whether DevSecOps Toolchain source code contains no secrets |
| 6.8 | Check whether Toolchain production change request exists and is approved | Check whether DevSecOps Toolchain deployment has approved change documentation including security impact analysis |
| 6.9 | Check whether the Toolchain Container Registry Vulnerability Advisor scans images for OS vulnerability detection | Check whether DevSecOps Toolchain scans build artifacts to identify vulnerabilities |
| 6.12 | Check whether Toolchain acceptance tests exist and have passed | Check whether DevSecOps Toolchain passes acceptance tests to validate every deployment |
| 6.16 | Checks whether only the tool integrations within the toolchain are included in the allow list parameter array	 | Check whether Toolchain is configured only with the allowed integration tools |
| 6.17 | Check whether a Toolchain static scan exists and has passed	| Check whether DevSecOps Toolchain passes static code scan to identify vulnerabilities in source code |
| 6.18 | Check whether a Toolchain dynamic scan exists and has passed | Check whether DevSecOps Toolchain passes dynamic code scan to identify vulnerabilities in deployed artifacts |
{: caption="Table. Understanding control and rule updates" caption-side="top"}
{: #scc-bp-2}
{: tab-title="Rule"}
{: tab-group="v1.1"}
{: class="simple-tab-table"}


### 13 March 2023
{: #v1.1.0-13-march}

The following new controls have been added to the {{site.data.keyword.cloud_notm}} Security Best Practices library and profile as of 17 March 2023. 

| Control ID | Control Description |
|:-----------|:--------------------|
| 6.1 | Ensure Toolchain scans during continuous integration the source code to identify vulnerabilities |
| 6.2 | Ensure Toolchain has unit tests that are continuously run to validate source code changes |
| 6.3 | Ensure Toolchain has Code Risk Analyzer configured that collects a bill of materials for pipeline run  |
| 6.4 | Ensure Toolchain is configured with image signing |
| 6.5 | Ensure Toolchain source code meets Center for Internet Security Docker benchmarks |
| 6.6 | Ensure Toolchain has branch protection rules enabled |
| 6.7 | Ensure Toolchain has secret detection scans enabled for source code |
| 6.8 | Ensure Toolchain production change request exists and is approved |
| 6.9 | Ensure Toolchain Container Registry Vulnerability Advisor scans images for OS vulnerability detection |
| 6.12 | Ensure Toolchain acceptance tests exist and have passed |
| 6.16 | Ensure that only the tool integrations within the toolchain are included in the allow list parameter array |
| 6.17 | Ensure a Toolchain static scan exists and has passed |
| 6.18 | Ensure a Toolchain dynamic scan exists and has passed |
{: caption="Table. Summary of {{site.data.keyword.cloud_notm}} Security Best Practices profile changes for Version 1.1.0" caption-side="top"}

The Toolchain controls that are listed in the table are configured to check DevSecOps Continuous Delivery (CD) and DevSecOps Continuous Compliance (CC) toolchains only, except for control 6.16, which is relevant to all toolchains. If you run an evaluation on a DevSecOps Continuous Integration (CI) toolchain, or on any other toolchain that is not a DevSecOps toolchain, the result is returned as *Unable to perform*.
{: note}

## Version 1.0.0
{: #sec-best-v1.0.0}

The format of the {{site.data.keyword.cloud_notm}} Security Best Practices profile was updated with the following changes. Review your configuration closely to ensure that the profile still meets your needs.
- The profile is not available on the **Profiles** page of the **Manage** section of the updated infrastructure.
- The format changed from being goal-based to assessment-based.

