---

copyright:
  years: 2023
lastupdated: "2023-11-01"

keywords: best practices, security and compliance, governance, profile, predefined profiles, profile versioning, benchmark, controls, goals, security, compliance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Profile versioning 
{: #profile-versioning}

You can control {{site.data.keyword.compliance_full}} profiles by maintaining only defined versions of a profile. Based on a specified expiration date, you can automatically deprecate or delete a specific version of the profile. 
{: shortdesc}

When a new profile version is released, if you use a previous version of the profile, you are notified that you must upgrade your attachments to use the new profile version. When the deprecated version of the profile expires, support for it is removed, evaluations of any attachments that use this profile are stopped, and the attachments are scheduled for deletion.

You can still view the results for your attachment through the Security and Compliance dashboard, or by pulling them from from your Cloud Object Storage bucket. But, you cannot see your attachment in the list of attachments in the UI.

## Upgrading attachments for new profile versions
{: #upgrade-profile-versions}

1. In the Security and Compliance Center UI, navigate to the **Profiles** page.
2. On the **Attachments** tab of the profile details page, click **Upgrade** to upgrade your attachment to use the new profile version. This operation cannot be undone.

	


