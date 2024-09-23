---

copyright:
  years: 2020, 2024
lastupdated: "2024-09-23"

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

Before you get started, be sure that you have the required level of access to update the settings for {{site.data.keyword.compliance_short}}. To manage settings, you need the [**Manager** service role or higher](/docs/security-compliance?topic=security-compliance-access-management). 

## Bucket requirements
{: #scc-bucket}

The bucket that you use to store your results does not require any particular settings or naming format. However, it is recommended that you use a bucket on the Standard plan and Smart tier.

All the traffic between {{site.data.keyword.compliance_short}} and Cloud Object Storage is done over a private network. The retrieval of data for display purposes in the console does not cost you anything. However, if you choose to download the data directly from Cloud Object Storage after it is stored, you do incur a data transfer cost. See [Cloud Object Storage pricing](/docs/cloud-object-storage?topic=cloud-object-storage-billing) for more information.


## Configuring storage
{: #cos-storage}
{: ui}

Before you can start evaluating your resources for compliance, you must configure a Cloud Object Storage bucket where the service can forward your results data for long-term storage.

The processing of your data is configured in your instance's location. For example, if you provision a {{site.data.keyword.compliance_short}} instance in the `us-south` region, your data is processed there.
{: note}

To connect your Cloud Object Storage bucket, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, go to the **Resource list** page and select your instance of {{site.data.keyword.compliance_short}}.
2. In your instance of {{site.data.keyword.compliance_short}}, go to the **Settings** page.
3. On the **Storage** tile, click **Connect**.
4. If a service-to-service policy is not enabled between Cloud Object Storage and {{site.data.keyword.compliance_short}}, a notification will display. You must enable a policy before you can continue. If a policy has already been enabled, you will not see the notification and can skip to step 5. To enable a policy, use the following steps.
	1. Click **Authorize**.
	2. The **Target Service** is already selected for Cloud Object Storage.
	3. The **Writer** role that is required is selected by default.
	4. Click **Review**. Then, click **Assign**.
5. Select an instance of Cloud Object Storage and the bucket that you want to use.
6. Click **Connect**.

If you disconnect your instance of Cloud Object Storage or select a new bucket, {{site.data.keyword.compliance_short}} is not able to read any of your existing results data. An evaluation can't complete without a connected Cloud Object Storage bucket.
{: important}


## Configuring storage with the API
{: #cos-storage-api}
{: api}

Before you can start evaluating your resources for compliance, you must configure a Cloud Object Storage bucket where the service can forward your results data for long-term storage.

The processing of your data is configured in your instance's location. For example, if you provision a {{site.data.keyword.compliance_short}} instance in the `us-south` region, your data is processed there.
{: note}

To configure the settings of your Cloud Object Storage bucket, you can use the {{site.data.keyword.compliance_short}} API.

```bash
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
{: pre}
{: curl}



```go
eventNotificationsModel := &securityandcompliancecenterapiv3.EventNotifications{
  InstanceCrn: &eventNotificationsCrnForUpdateSettingsLink,
  SourceDescription: core.StringPtr("This source is used for integration with IBM Cloud Security and Compliance Center."),
  SourceName: core.StringPtr("compliance"),
}

objectStorageModel := &securityandcompliancecenterapiv3.ObjectStorage{
  InstanceCrn: &objectStorageCrnForUpdateSettingsLink,
  Bucket: &objectStorageBucketForUpdateSettingsLink,
  BucketLocation: &objectStorageLocationForUpdateSettingsLink,
}

updateSettingsOptions := securityAndComplianceCenterApiService.NewUpdateSettingsOptions()
updateSettingsOptions.SetEventNotifications(eventNotificationsModel)
updateSettingsOptions.SetObjectStorage(objectStorageModel)
updateSettingsOptions.SetXCorrelationID("1a2b3c4d-5e6f-4a7b-8c9d-e0f1a2b3c4d5")

settings, response, err := securityAndComplianceCenterApiService.UpdateSettings(updateSettingsOptions)
if err != nil {
  panic(err)
}
b, _ := json.MarshalIndent(settings, "", "  ")
fmt.Println(string(b))
```
{: codeblock}
{: go}


```java
EventNotifications eventNotificationsModel = new EventNotifications.Builder()
  .instanceCrn(eventNotificationsCrnForUpdateSettingsLink)
  .sourceDescription("This source is used for integration with IBM Cloud Security and Compliance Center.")
  .sourceName("compliance")
  .build();
ObjectStorage objectStorageModel = new ObjectStorage.Builder()
  .instanceCrn(objectStorageCrnForUpdateSettingsLink)
  .bucket(objectStorageBucketForUpdateSettingsLink)
  .bucketLocation(objectStorageLocationForUpdateSettingsLink)
  .build();
UpdateSettingsOptions updateSettingsOptions = new UpdateSettingsOptions.Builder()
  .eventNotifications(eventNotificationsModel)
  .objectStorage(objectStorageModel)
  .xCorrelationId(xCorrelationIdLink)
  .build();

Response<Settings> response = securityAndComplianceCenterApiService.updateSettings(updateSettingsOptions).execute();
Settings settings = response.getResult();

System.out.println(settings);
```
{: codeblock}
{: java}


```bash
// Request models needed by this operation.

// EventNotifications
const eventNotificationsModel = {
  instance_crn: eventNotificationsCrnForUpdateSettingsLink,
  source_description: 'This source is used for integration with IBM Cloud Security and Compliance Center.',
  source_name: 'compliance',
};

// ObjectStorage
const objectStorageModel = {
  instance_crn: objectStorageCrnForUpdateSettingsLink,
  bucket: objectStorageBucketForUpdateSettingsLink,
  bucket_location: objectStorageLocationForUpdateSettingsLink,
};

const params = {
  eventNotifications: eventNotificationsModel,
  objectStorage: objectStorageModel,
  xCorrelationId: '1a2b3c4d-5e6f-4a7b-8c9d-e0f1a2b3c4d5',
};

let res;
try {
  res = await securityAndComplianceCenterApiService.updateSettings(params);
  console.log(JSON.stringify(res.result, null, 2));
} catch (err) {
  console.warn(err);
}
```
{: codeblock}
{: node}


```python
event_notifications_model = {
  'instance_crn': event_notifications_crn_for_update_settings_link,
  'source_description': 'This source is used for integration with IBM Cloud Security and Compliance Center.',
  'source_name': 'compliance',
}

object_storage_model = {
  'instance_crn': object_storage_crn_for_update_settings_link,
  'bucket': object_storage_bucket_for_update_settings_link,
  'bucket_location': object_storage_location_for_update_settings_link,
}

response = security_and_compliance_center_api_service.update_settings(
  event_notifications=event_notifications_model,
  object_storage=object_storage_model,
  x_correlation_id='1a2b3c4d-5e6f-4a7b-8c9d-e0f1a2b3c4d5',
)
settings = response.get_result()

print(json.dumps(settings, indent=2))
```
{: codeblock}
{: python}


If you disconnect your instance of Cloud Object Storage or select a new bucket, {{site.data.keyword.compliance_short}} is not able to read any of your existing results data. An evaluation can't complete without a connected Cloud Object Storage bucket.
{: important}


A successful response returns the {{site.data.keyword.en_short}} and Cloud Object Storage settings, along with other metadata. For more information about the required and optional request parameters, check out the [API docs](/apidocs/security-compliance#update-settings).


## Configuring storage with the CLI
{: #cos-storage-cli}
{: cli}

Before you can start evaluating your resources for compliance, you must configure a Cloud Object Storage bucket where the service can forward your results data for long-term storage.

To connect your Cloud Object Storage bucket, you can use the {{site.data.keyword.compliance_short}} CLI. For more information, see the [CLI reference](/docs/security-compliance?topic=security-compliance-security-compliance-cli&interface=ui#security-compliance-cli-settings-update-command).

```sh
ibmcloud security-compliance setting update
--event-notifications='{
  "instance_crn": "crn:v1:staging:public:event-notifications:us-south:a/ff88f007f9ff4622aac4fbc0eda36255:7199ae60-a214-4dd8-9bf7-ce571de49d01::",
  "updated_on": "2019-01-01T12:00:00.000Z",
  "source_id": "crn:v1:staging:public:event-notifications:us-south:a/ff88f007f9ff4622aac4fbc0eda36255:b8b07245-0bbe-4478-b11c-0dce523105fd::",
  "source_description": "This source is used for integration with IBM Cloud Security and Compliance Center.",
  "source_name": "compliance"
  }'
--object-storage='{
  "instance_crn": "crn:v1:staging:public:cloud-object-storage:global:a/ff88f007f9ff4622aac4fbc0eda36255:7199ae60-a214-4dd8-9bf7-ce571de49d01::",
  "bucket": "px-scan-results",
  "bucket_location": "us-south",
  "bucket_endpoint": "exampleString",
  "updated_on": "2019-01-01T12:00:00.000Z"
  }'
--x-correlation-id=1a2b3c4d-5e6f-4a7b-8c9d-e0f1a2b3c4d5
--x-request-id=exampleString
```
{: pre}


If you disconnect your instance of Cloud Object Storage or select a new bucket, {{site.data.keyword.compliance_short}} is not able to read any of your existing results data. An evaluation can't complete without a connected Cloud Object Storage bucket.
{: important}
