---

copyright:
  years: 2020, 2023
lastupdated: "2023-10-10"

keywords: custom profiles, user-defined, controls, goals, security, compliance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Setting up data storage and processing for {[scc]}
{: #storage}

When you work with {[scc-full]}, you must configure how you want your data to be handled. For more detailed information about the types of data that can be used with the service, see [Understanding data encryption]({[link]}-mng-data).
{: shortdesc}

## Before you begin
{: #before-storage}

Before you get started, be sure that you have the required level of access to update the settings for {[scc]}. To manage settings, you need the [**Editor** platform role or higher]({[link]}-access-management). 

## Bucket requirements
{: #scc-bucket}

The bucket that you use to store your results does not require any particular settings or naming format. However, it is recommended that you use a bucket on the Standard plan and Smart tier.

All the traffic between {[scc]} and {[cos]} is done over a private network. The retrieval of data for display purposes in the console does not cost you anything. However, if you choose to download the data directly from {[cos]} after it is stored, you do incur a data transfer cost. See [{[cos]} pricing](/docs/cloud-object-storage/iam?topic=cloud-object-storage-billing) for more information.


## Configuring storage
{: #cos-storage}
{: ui}

Before you can start evaluating your resources for compliance, you must configure a {[cos]} bucket where the service can forward your results data for long-term storage.

The processing of your data is configured in your instance's location. For example, if you provision a {[scc]} instance in the `us-south` region, your data is processed there.
{: note}


To connect your {[cos]} bucket, you can use the {[scc]} UI.

2. In the {[cloud]} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {[scc]}.
2. In the navigation, click **Settings**.
3. On the **Storage** tile, click **Connect**.
4. If a service-to-service policy is not already enabled, use the in-context settings to create one. If you already have a policy in place, this screen does not show and you can skip to the next step.
5. Select an instance of {[cos]}.
6. From the table, select the bucket that you want to use.
7. Click **Connect**.

If you disconnect your instance of {[cos]} or select a new bucket, {[scc]} is not able to read any of your existing results data. An evaluation can't complete without a connected {[cos]} bucket.
{: important}


## Configuring storage with the API
{: #cos-storage-api}
{: api}

Before you can start evaluating your resources for compliance, you must configure a {[cos]} bucket where the service can forward your results data for long-term storage.

The processing of your data is configured in your instance's location. For example, if you provision a {[scc]} instance in the `us-south` region, your data is processed there.
{: note}

To configure the settings of your {[cos]} bucket, you can use the {[scc]} API.

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


```node
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


If you disconnect your instance of {[cos]} or select a new bucket, {[scc]} is not able to read any of your existing results data. An evaluation can't complete without a connected {[cos]} bucket.
{: important}


A successful response returns the {[en]} and {[cos]} settings, along with other metadata. For more information about the required and optional request parameters, check out the [API docs](/apidocs/security-compliance#update-settings).

