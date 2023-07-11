---

copyright:
  years: 2020, 2023
lastupdated: "2023-07-11"

keywords: release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: {{site.data.keyword.cloud_notm}} Kubernetes Service
{: #iks-profile}

In this change log, you can learn about the latest changes, improvements, and updates for the {{site.data.keyword.cloud_notm}} Kubernetes Service profile. The change log lists changes that were made, ordered by the version number.


To work with this profile, you must connect an instance of [Workload Protection](/docs/security-compliance?topic=security-compliance=setup-workload-protection).
{: note}


## Profile versioning
{: #iks-profile-versioning}

When specifications or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new version is released. To take advantage of the changes in a new version, update your attachments to use the newest profile version. 

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Be sure to validate the available controls to determine where you might need to supplement your workloads with other security measures.
{: important}


### Active versions
{: #iks-active-versions}

The following table shows the service behavior changes for each version date. Switching to a later version date activates all changes that are introduced in earlier versions.

| Version number | Release date |
|:---------------|:-------------|
| Version 1.0.0 | `2023-07-12` |
{: caption="Table. Active versions of the {{site.data.keyword.cloud_notm}} Kubernetes Service profile" caption-side="top"}


## Version 1.0.0
{: #iks-v100}

Now available
:   Released today, 12 July 2023, the {{site.data.keyword.cloud_notm}} Kubernetes Service profile is a collection of controls designed to validate the configuration of your Kubernetes Service clusters. This profile introduces the concept of `wp-rule` assessments. These are assessments that are defined by the Workload Protection service and imported into {{site.data.keyword.compliance_short}}.

