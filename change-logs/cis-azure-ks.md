---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: "release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements"

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: CIS Azure Kubernetes Service (AKS) Benchmark
{: #cis-azure-ks-benchmark}

As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


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

New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
{: important}

| Version number | Release date | Status |
|:---------------|:-------------|:-------|
| Version 1.2.0 | `2023-12-06` | Active |
| Version 1.1.0 | `2023-11-07` | Active |
| Version 1.0.0 | `2023-07-14` | Active |
{: caption="Table. Active versions of the CIS Azure Kubernetes Service (AKS) Benchmark" caption-side="top"}

## Version 1.2.0
{: #cis-azure-ks-v120}

Now available
:   As of 6 December 2023, few component-id assesments in the AWS Well-Architected Framework profile have changed. The component-id of following assements from `container-aks` to `azure-resource`.

   - ACI - Untrusted Workloads
   - KMS - Enabled Secrets Encryption (AKS)
   - Logging - Enabled Cluster Logging (AKS)
   - Network - Disabled Endpoint Public Access in Existing Clusters (AKS)
   - Network - Enabled Endpoint Private Access in Existing Clusters (AKS)
   - Network - Private Nodes (AKS)
   - Network - Restricted Pod to Pod Traffic (AKS)
   - RBAC - Enabled Azure RBAC (AKS)
   - RBAC - Enabled with Azure AD


## Version 1.1.0
{: #cis-azure-ks-v110}

Now available
:   As of 7 November 2023, the control hierarchy in the CIS Azure Kubernetes Service (AKS) Benchmark profile has changed. Assessments have been remapped so that a single assessment is mapped to a single specification. No new assessments were added.


## Version 1.0.0
{: #cis-azure-ks-v100}

Now available
:   Released today, 14 July 2023, the CIS Azure Kubernetes Service (AKS) Benchmark is a collection of controls designed to validate the configuration of your Kubernetes Service clusters. This profile is evaluated by using `wp-rule` assessments. These are assessments that are defined by the Workload Protection service and imported into {{site.data.keyword.compliance_short}}.
