---

copyright:
  years: 2020, 2023
lastupdated: "2023-07-28"

keywords: custom profiles, user-defined, controls, goals, security, compliance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Setting up data storage and processing for {{site.data.keyword.compliance_short}}
{: #storage}

When you work with {{site.data.keyword.compliance_full}}, you must configure how you want your data to be handled. For more detailed information about the types of data that can be used with the service, see [Understanding data encryption](/docs/security-compliance?topic=security-compliance-mng-data).
{: shortdesc}

## Before you begin
{: #before-storage}

Before you get started, be sure that you have the required level of access to update the settings for {{site.data.keyword.compliance_short}}. To manage settings, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).

## Bucket requirements
{: #scc-bucket}

The bucket that you use to store your results does not require any particular settings or naming format. But, it is recommended that you use a bucket on the Standard plan and Smart tier.

All the traffic between {{site.data.keyword.compliance_short}} and Cloud Object Storage is done over a private network. The retrieval of data for display purposes in the console does not cost you anything. However, if you choose to download the data directly from Cloud Object Storage after it is stored, you do incur a data transfer cost. See [Cloud Object Storage pricing](/docs/cloud-object-storage/iam?topic=cloud-object-storage-billing) for more information.


## Configuring storage
{: #cos-storage}
{: ui}

Before you can start evaluating your resources for compliance, you must configure a Cloud Object Storage bucket where the service can forward your results data for long-term storage.

The processing of your data is configured in your instance's location. For example, if you provision a {{site.data.keyword.compliance_short}} instance in the `us-south` region, your data is processed there.
{: note}


To connect your Cloud Object Storage bucket, you can use the {{site.data.keyword.compliance_short}} UI.

2. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Settings**.
3. On the **Storage** tile, click **Connect**.
4. If a service-to-service policy is not already enabled, use the in-context settings to create one. If you already have a policy in place, this screen does not show and you can skip to the next step.
5. Select an instance of Cloud Object Storage.
6. From the table, select the bucket that you want to use.
7. Click **Connect**.

If you disconnect your instance of Cloud Object Storage or select a new bucket, {{site.data.keyword.compliance_short}} is not able to read any of your existing results data. An evaluation can't complete without a connected Cloud Object Storage bucket.
{: important}


## Configuring storage with the API
{: #cos-storage-api}
{: api}

Before you can start evaluating your resources for compliance, you must configure a Cloud Object Storage bucket where the service can forward your results data for long-term storage.

The processing of your data is configured in your instance's location. For example, if you provision a {{site.data.keyword.compliance_short}} instance in the `us-south` region, your data is processed there.
{: note}

To configure the settings of your Cloud Object Storage bucket, you can use the {{site.data.keyword.compliance_short}} API.

```sh
curl -X PATCH 
   --location --header "Authorization: Bearer {iam_token}" 
   --header "Accept: application/json" 
   --header "Content-Type: application/json-patch+json" 
   --data '{ 
               "event_notifications": { 
                  "instance_crn": "crn:v1:staging:public:event-notifications:us-south:a/130003ea8bfa43c5aacea07a86da3000:1c858449-3537-45b8-9d39-2707115b4cc7::" 
                  }, 
               "object_storage": { 
                  "instance_crn": "crn:v1:staging:public:cloud-object-storage:global:a/130003ea8bfa43c5aacea07a86da3000:1c858449-3537-45b8-9d39-2707115b4cc7::", 
                  "bucket": "scc-bucket" 
               } 
            }' 
   "https://us-south.compliance.cloud.ibm.com/instances/{instance_id}/v3/settings"
```
{: codeblock}


If you disconnect your instance of Cloud Object Storage or select a new bucket, {{site.data.keyword.compliance_short}} is not able to read any of your existing results data. An evaluation can't complete without a connected Cloud Object Storage bucket.
{: important}


A successful response returns the {{site.data.keyword.en_short}} and Cloud Object Storage settings, along with other metadata. For more information about the required and optional request parameters, check out the [API docs](/apidocs/security-compliance#update-settings).

