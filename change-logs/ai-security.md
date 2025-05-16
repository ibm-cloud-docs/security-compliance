---
copyright:
  years: "2025"
lastupdated: "2025-05-16"

keywords: "release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements, ai security"

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: AI Security Guardrails 2.0
{: #ai-security-change-log}


As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}

In this change log, you can learn about the latest changes, improvements, and updates for the Service Organization Control (AI Security Guardrails 2.0) profile. The change log lists changes that were made, ordered by the version number.

The AI Security Guardrails 2.0 provides a list of controls for the full stack including AI Applications, Models, Data, and infrastructure layers, which are required to handle AI and Generative AI (GenAI) workloads. These controls include AI specific elaborations across control categories like AI governance, AI app protection, AI model lifecycle, data classification, and infrastructure security and operational resiliency.

## Profile versioning
{: #ai-security-versioning}

When specifications or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new version is released. To take advantage of the changes in a new version, update your attachments to use the newest profile version.

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Be sure to validate the available controls to determine where you might need to supplement your workloads with other security measures.
{: important}


### Version summary
{: #ai-security-versions}

The following table details the release dates and status of each profile version.

New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
{: important}

| Version number | Release date | Status |
|:---------------|:-------------|:-------|
| Version 1.1.0 | `2024-09-10` | Active |
| Version 1.0.0 | `2024-07-09` | Active |
{: caption="Table. Active versions of the AI Security Guardrails 2.0 profile" caption-side="top"}



## Version 1.1.0
{: #ai-sec-v110}

The following rules were updated in the AI Security Guardrails 2.0 profile as of 10 September 2024.

| Rule ID | Rule description| Associated controls | Update |
|:--------|:----------------|:--------------------|:-------|
| `rule-8cbd597c-7471-42bd-9c88-36b2696456e9`	| Check whether Cloud Object Storage network access is restricted to a specific IP range |	`Mod 4.1` |	The rule was removed. |
| `rule-3027fd86-72c5-4c81-8ccd-ff556a922ec1`	| Check whether Cloud Object Storage network access is restricted to a specific IP range |	`Mod 4.1` |	The rule was added. |
| `rule-92c541f6-5c40-47e1-935d-228ec688dc1c`	| Check whether account has at least one VPN or Direct Link configured	| `Mod 4.1`	| The rule was removed. |
| `rule-a3b44c6a-1911-4d88-beea-58e56522a7ef` | Check whether account has at least # instances of VPN or Direct Link configured | `Mod 4.1` | The rule was added. |
| `rule-c0f15737-b451-44d0-a0b6-649013a155bc`	| Check whether there are at least # instances of Direct Link in an account |	`ISR 1.3`	| The rule was removed. |
{: caption="Table. Summary of the changes for version 1.1.0 of the AI Security Guardrails 2.0 profile" caption-side="top"}


## Version 1.0.0
{: #ai-security-version1}

Now available
:   As of 9 July 2024, the AI Security Guardrails 2.0 profile is a collection of controls that is designed to validate the configuration of your resources.
