---

copyright:
  years: 2020, 2023
lastupdated: "2023-11-08"

keywords: release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: CIS Azure Kubernetes Service (AKS) Benchmark
{: #cis-azure-ks-benchmark}

In this change log, you can learn about the latest changes, improvements, and updates for the CIS Azure Kubernetes Service (AKS) Benchmark profile. The change log lists changes that were made, ordered by the version number.


To work with this profile, you must connect an instance of [Workload Protection](/docs/security-compliance?topic=security-compliance-setup-workload-protection).
{: note}


## Profile versioning
{: #cis-azure-ks-versioning}

When specifications or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new version is released. To take advantage of the changes in a new version, update your attachments to use the newest profile version.

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Be sure to validate the available controls to determine where you might need to supplement your workloads with other security measures.
{: important}


### Version summary
{: #cis-azure-ks-versions}

The following table details the release dates and status of each profile version.



| Version number | Release date | Status |
|:---------------|:-------------|:-------|
| Version 1.1.0 | `2023-11-07` | Active |
| Version 1.0.0 | `2023-07-14` | Active |
{: caption="Table. Active versions of the CIS Azure Kubernetes Service (AKS) Benchmark" caption-side="top"}

## Version 1.1.0
{: #cis-azure-ks-v110}

Now available
:   As of 7 November 2023, the control hierarchy in the CIS Amazon Web Services Foundations Benchmark profile has changed. Assessments have been remapped so that a single assessment is mapped to a single specification. No new assessments were added.


## Version 1.0.0
{: #cis-azure-ks-v100}

Now available
:   Released today, 14 July 2023, the CIS Azure Kubernetes Service (AKS) Benchmark is a collection of controls designed to validate the configuration of your Kubernetes Service clusters. This profile is evaluated by using `wp-rule` assessments. These are assessments that are defined by the Workload Protection service and imported into {{site.data.keyword.compliance_short}}.
