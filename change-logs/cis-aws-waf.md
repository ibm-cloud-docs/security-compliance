---

copyright:
  years: 2020, 2025
lastupdated: "2025-04-21"

keywords: "release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements"

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: AWS Well-Architected Framework
{: #aws-waf-benchmark}

In this change log, you can learn about the latest changes, improvements, and updates for the AWS Well-Architected Framework profile. The change log lists changes that were made, ordered by the version number.


To work with this profile, you must connect an instance of [Workload Protection](/docs/security-compliance?topic=security-compliance-setup-workload-protection).
{: note}


## Profile versioning
{: #aws-waf-versioning}

When specifications or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new version is released. To take advantage of the changes in a new version, update your attachments to use the newest profile version.

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Be sure to validate the available controls to determine where you might need to supplement your workloads with other security measures.
{: important}


### Version summary
{: #aws-waf-versions}

The following table details the release dates and status of each profile version.

New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
{: important}

| Version number | Release date | Status |
|:---------------|:-------------|:-------|
| Version 1.2.0 | `2023-12-06` | Active |
| Version 1.1.0 | `2023-11-21` | Active |
| Version 1.0.0 | `2023-09-23` | Active |
{: caption="Table. Active versions of the AWS Well-Architected Framework" caption-side="top"}

## Version 1.2.0
{: #aws-waf-v120}

Now available
:   As of 6 December 2023, few component-id assesments in the AWS Well-Architected Framework profile have changed. The component-id of following assements from `container-eks` to `aws-resource`.

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
{: #aws-waf-v110}

Now available
:   As of 21 November 2023, the control hierarchy in the AWS Well-Architected Framework profile has changed. Assessments have been remapped so that a single assessment is mapped to a single specification. No new assessments were added.


## Version 1.0.0
{: #aws-waf-v100}

Now available
:   Released today, 23 September 2023, the AWS Well-Architected Framework helps you understand the pros and cons of deons you make while building systems on AWS. This profile is evaluated by using `wp-rule` assessments. These are assessments that are defined by the Workload Protection service and imported into {{site.data.keyword.compliance_short}}.
