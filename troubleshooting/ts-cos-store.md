---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: cloud object storage, unable to store, failed to store

subcollection: security-compliance

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why am I unable to complete a scan?
{: #cos-unable-store}
{: troubleshoot} 
{: support}


As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


You attempted to run a scan, but it failed during the storage process.
{: tsSymptoms}

Scan results are stored within your Cloud Object Storage bucket and it failed during the storage process. Few reasons for the failure include:
{: tsCauses}

* You might not have granted the correct authorization to allow {{site.data.keyword.compliance_short}} to access to your Cloud Object Storage service.
* The Cloud Object Storage bucket that you attempted to use may not be configured properly.
* You might not be authorized to use that Cloud Object Storage bucket.
* You might have reached the maximum storage capacity for your Cloud Object Storage plan.
* Your Cloud Object Storage plan may have expired.

To resolve the issue:
{: tsResolve}

In order to view your IBM Cloud accounts current Cloud Object Storage configuration, visit your accounts [resource list](https://cloud.ibm.com/resources) and open the dropdown menu for **Storage** and select your instance.

* Verify that you have configured a service-to-service authorization by navigating to **[Manage > IAM > Authorizations](https://cloud.ibm.com/iam/authorizations)**. If your Cloud Object Storage service authorization is not listed, click **Create** and grant `Writer` service access between **{{site.data.keyword.compliance_short}}** and **Cloud Object Storage**.
* Verify that you have correctly configured your Cloud Object Storage bucket by selecting your Cloud Object Storage instance and confirming your bucket is setup properly.
* Verify your authorization to the Cloud Object Storage bucket by selecting the buckets **Permissions** tab and validating your access.
* Verify that you have not exceeded the maximum amount of storage you are allotted within your Cloud Object Storage instance. More information about your current storage usage can be found under the **Instance usage** tab. More information on setting a storage [quota](https://cloud.ibm.com/docs/cloud-object-storage?topic=cloud-object-storage-quota) on your bucket.
* If you are a Lite plan customer, verify that your service is not deactivated. Lite plan services are deleted after 30 days of inactivity. More information about your current plan can be found under the **Plan** tab.
