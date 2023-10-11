---

copyright:
  years: 2020, 2023
lastupdated: "2023-10-11"

keywords: release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: IBM Cloud Red Hat OpenShift Kubernetes OCP4 profile
{: #openshift-profile}

In this change log, you can learn about the latest changes, improvements, and updates for the Red Hat OpenShift Kubernetes OCP4 profile. The change log lists changes that were made, ordered by the version number.



## Profile versioning
{: #os-profile-versioning}

When specifications or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new version is released. To take advantage of the changes in a new version, update your attachments to use the newest profile version. 

This profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Be sure to validate the available controls to determine where you might need to supplement your workloads with other security measures.
{: important}


### Version summary
{: #os-active-versions}

The following table details the release dates and status of each profile version.



| Version number | Release date | Status |
|:---------------|:-------------|:-------|
| Version 1.2.0  | `2023-10-10` | Active |
| Version 1.1.0  | `2023-09-23` | Active |
| Version 1.0.0  | `2023-06-07` | Active |
{: caption="Table. Active versions of the Red Hat OpenShift Kubernetes OCP4 profile" caption-side="top"}

## Version 1.2.0
{: #os-v120}

As of today, 10 October 2023, controls have been removed from the Red Hat OpenShift Kubernetes OCP4 profile.

| Parent control | Removed sub controls |
|:---------------|:---------------------|
| Control 1: Control plane requirements | `1.1`, `1.2`, `1.3`, and `1.4` |
| Control 2: etcd | All controls |
| Control 3: Control plane configuration | `3.1`, and `3.2` |
| Control 4: Worker node | `4.2.1`, `4.2.2`, `4.2.3`, `4.2.4`, `4.2.5`, `4.2.7`, `4.2.9`, `4.2.10`, `4.2.11`, `4.2.12`, and `4.2.13`,   |
| Control 5: Policies | All controls in `5.1`, `5.2`, and `5.3` |
{: caption="Table. Changes now available in version 1.2.0 of the Red Hat OpenShift Kubernetes OCP4 profile" caption-side="top"}


## Version 1.1.0
{: #os-v110}

As of today, 23 September 2023, new controls have been added to the Red Hat OpenShift Kubernetes OCP4 profile.


## Version 1.0.0
{: #os-v100}

Now available
:   Released today, 6 June 2023, the Red Hat OpenShift Kubernetes OCP4 profile is a collection of controls designed to validate the configuration of your {{site.data.keyword.cloud_notm}} Red Hat OpenShift clusters.

