---

copyright:
  years: 2020, 2023
lastupdated: "2023-09-27"

keywords: cloud object storage, unable to store, failed to store

subcollection: security-compliance

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why am I unable to complete a scan?
{: #cos-unable-store}
{: troubleshoot} 
{: support}

You attempted to run a scan, but it failed during the storage process.
{: tsSymptoms}

Scan results are stored within your Cloud Object Storage bucket and it failed during the storage process. There are a few reasons that this might happen:
{: tsCauses}

* You might not have granted the correct authorization to allow {{site.data.keyword.compliance_short}} to access to your Cloud Object Storage service.
* The Cloud Object Storage bucket that you attempted to use may not be configured properly.
* You might not be authorized to use that Cloud Object Storage bucket.
* You might have reached the maximum storage capacity for your Cloud Object Storage plan.
* Your Cloud Object Storage plan may have expired.

To resolve the issue:
{: tsResolve}

In order to view your IBM Cloud accounts current Cloud Object Storage configuration please visit your accounts [resource list](https://cloud.ibm.com/resources) and open the dropdown menu for **Storage** and select your instance.

* Verify you have configured a service-to-service authorization by navigating to **[Manage > IAM > Authorizations](https://cloud.ibm.com/iam/authorizations)**. If your Cloud Object Storage service authorization is not listed, click **Create** and grant `Writer` service access between **{{site.data.keyword.compliance_short}}** and **Cloud Object Storage**.
* Verify that you have correctly configured your Cloud Object Storage bucket by selecting your Cloud Object Storage instance and confirming your bucket is setup properly.
* Verify your authorization to the Cloud Object Storage bucket by selecting the buckets **Permissions** tab and validating your access.
* Verify that you have not exceeded the maximum amount of storage you are allotted within your Cloud Object Storage instance. More information about your current storage usage can be found under the **Instance usage** tab. More information on setting a storage [quota](https://cloud.ibm.com/docs/cloud-object-storage?topic=cloud-object-storage-quota) on your bucket.
* Verify that if you are a Lite plan customer that your service has not been deactivated. Lite plan services are deleted after 30 days of inactivity. More information about your current plan can be found under the **Plan** tab.