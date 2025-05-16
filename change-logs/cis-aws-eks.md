---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: "release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements"

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: CIS Amazon Elastic Kubernetes Service (EKS) Benchmark
{: #cis-amazon-eks-benchmark}

As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the replacement service {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}

In this change log, you can learn about the latest changes, improvements, and updates for the CIS Amazon Elastic Kubernetes Service (EKS) Benchmark profile. The change log lists changes that were made, ordered by the version number.


To work with this profile, you must connect an instance of [Workload Protection](/docs/security-compliance?topic=security-compliance-setup-workload-protection).
{: note}


## Profile versioning
{: #cis-amazon-eks-versioning}

When specifications or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new version is released. To take advantage of the changes in a new version, update your attachments to use the newest profile version.

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Be sure to validate the available controls to determine where you might need to supplement your workloads with other security measures.
{: important}


### Version summary
{: #cis-amazon-eks-versions}

The following table details the release dates and status of each profile version.

New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
{: important}

| Version number | Release date | Status |
|:---------------|:-------------|:-------|
| Version 1.2.0 | `2023-12-06` | Active |
| Version 1.1.0 | `2023-11-07` | Active |
| Version 1.0.0 | `2023-07-14` | Active |
{: caption="Table. Active versions of the CIS Amazon Elastic Kubernetes Service (EKS) Benchmark" caption-side="top"}


## Version 1.2.0
{: #cis-amazon-eks-v120}

Now available
 As of 6 December 2023, few component-id assesments in the CIS Amazon Elastic Kubernetes Service (EKS) Benchmarkprofile have changed.
 The component-id of following assements from `container-eks` to `aws-resource`.

   * ECR - Enabled Vulnerability Scanning
   * Fargate - Untrusted Workloads
   * KMS - Enabled Secrets Encryption (EKS)
   * Logging - Enabled Cluster Logging (EKS)
   * Network - Disabled Endpoint Public Access in Existing Clusters (EKS)
   * Network - Enabled Endpoint Private Access in Existing Clusters (EKS)
   * Network - Private Nodes (EKS)
   * Network - TLS Encryption to HTTPS Load Balancers (EKS)
   * RBAC - Enabled with AWS IAM Authenticator for Kubernetes



## Version 1.1.0
{: #cis-amazon-eks-v110}

Now available
:   As of 7 November 2023, the control hierarchy in the CIS Amazon Elastic Kubernetes Service (EKS) Benchmark profile has changed. Assessments have been remapped so that a single assessment is mapped to a single specification. No new assessments were added.


## Version 1.0.0
{: #cis-amazon-eks-v100}

Now available
:   Released today, 14 July 2023, the CIS Amazon Elastic Kubernetes Service (EKS) Benchmark is a collection of controls designed to validate the configuration of your Kubernetes Service clusters. This profile is evaluated by using `wp-rule` assessments. These are assessments that are defined by the Workload Protection service and imported into {{site.data.keyword.compliance_short}}.
