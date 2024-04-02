---

copyright:
  years: "2023"
lastupdated: "2023-12-11"

subcollection: security-compliance

keywords: security compliance CLI, security and compliance center CLI command line , security compliance CLI terminal, security compliance CLI shell, security compliance cli plugin

---

{{site.data.keyword.attribute-definition-list}}


# Security and Compliance Center CLI Reference
{: #security-compliance-cli}

You can use the {{site.data.keyword.cloud_notm}} Security and Compliance Center command-line interface (CLI) to manage your instances. 
{: shortdesc}

Current version: **3.0.0**

## Prerequisites
{: #security-compliance-cli-prereq}

* Install the [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started).
* Install the Security and Compliance Center CLI by running the following command:

   ```sh
   ibmcloud plugin install security-compliance
   ```
   {: pre}


You're notified on the command line when updates to the {{site.data.keyword.cloud_notm}} CLI and plug-ins are available. Be sure to keep your CLI up to date so that you can use the latest commands. You can view the current version of all installed plug-ins by running `ibmcloud plugin list`.
{: tip}




## Globals
{: #globals}

### Options
{: #security-compliance-global-options}

`--region` (string)
:   &nbsp;

`--instance-id` (string)
:   The ID of the managing instance.

`--output` (string)
:   Choose an output format - can be `json`, `yaml`, or `table`. Defaults to `table`.

`-j`, `--jmes-query` (string)
:   Provide a JMESPath query to customize output.

`-q`, `--quiet`
:   Suppresses verbose messages.

#### Example
{: #security-compliance-global-options-example}

```sh
ibmcloud security-compliance
    --region=us-south.compliance \
    --instance-id=instance_id \
    --output=json \
    --jmes-query="[:10]" \
    --quiet
```
Note: This example only demonstrates the global options available to all sub-commands and is not a valid command itself.

## Provider types
{: #security-compliance-provider-types-cli}

Commands for Provider Type resources.

```sh
ibmcloud security-compliance provider-type --help
```


### `ibmcloud security-compliance provider-type list`
{: #security-compliance-cli-provider-types-list-command}

List all the registered provider types. For more information about connecting Workload Protection with the Security and Compliance Center, see [Connecting Workload Protection](/docs/security-compliance?topic=security-compliance-setup-workload-protection&interface=api#wp-register).

```sh
ibmcloud security-compliance provider-type list [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-provider-types-list-cli-options}

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-provider-types-list-examples}

```sh
ibmcloud security-compliance provider-type list \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance provider-type get`
{: #security-compliance-cli-provider-types-get-command}

Retrieve a provider type by specifying its ID. For more information about integrations, see [Connecting Workload Protection](/docs/security-compliance?topic=security-compliance-setup-workload-protection).

```sh
ibmcloud security-compliance provider-type get --provider-type-id PROVIDER-TYPE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-provider-types-get-cli-options}

`--provider-type-id` (string)
:   The provider type ID. Required.

    The maximum length is `36` characters. The minimum length is `32` characters. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-provider-types-get-examples}

```sh
ibmcloud security-compliance provider-type get \
    --provider-type-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance provider-type instances`
{: #security-compliance-cli-provider-type-instances-list-command}

Retrieve all instances of provider type. For more information about integrations, see [Connecting Workload Protection](/docs/security-compliance?topic=security-compliance-setup-workload-protection).

```sh
ibmcloud security-compliance provider-type instances --provider-type-id PROVIDER-TYPE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-provider-type-instances-list-cli-options}

`--provider-type-id` (string)
:   The provider type ID. Required.

    The maximum length is `36` characters. The minimum length is `32` characters. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-provider-type-instances-list-examples}

```sh
ibmcloud security-compliance provider-type instances \
    --provider-type-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance provider-type-instance create`
{: #security-compliance-cli-provider-types-create-command}

Create an instance of a provider type. For more information about integrations, see [Connecting Workload Protection](/docs/security-compliance?topic=security-compliance-setup-workload-protection).

```sh
ibmcloud security-compliance provider-type-instance create --provider-type-id PROVIDER-TYPE-ID [--name NAME] [--attributes ATTRIBUTES] [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-provider-types-create-cli-options}

`--provider-type-id` (string)
:   The provider type ID. Required.

    The maximum length is `36` characters. The minimum length is `32` characters. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--name` (string)
:   The provider type instance name.

    The maximum length is `64` characters. The minimum length is `1` character. The value must match regular expression `/[A-Za-z0-9]+/`.

`--attributes` (generic map)
:   The attributes for connecting to the provider type instance.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--attributes=@path/to/file.json`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-provider-types-create-examples}

```sh
ibmcloud security-compliance provider-type-instance create \
    --provider-type-id=exampleString \
    --name=workload-protection-instance-1 \
    --attributes='{"anyKey": "anyValue"}' \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance provider-type-instance delete`
{: #security-compliance-cli-provider-types-delete-command}

Remove a specific instance of a provider type.

```sh
ibmcloud security-compliance provider-type-instance delete --provider-type-id PROVIDER-TYPE-ID --provider-type-instance-id PROVIDER-TYPE-INSTANCE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-provider-types-delete-cli-options}

`--provider-type-id` (string)
:   The provider type ID. Required.

    The maximum length is `36` characters. The minimum length is `32` characters. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--provider-type-instance-id` (string)
:   The provider type instance ID. Required.

    The maximum length is `36` characters. The minimum length is `32` characters. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-provider-types-delete-examples}

```sh
ibmcloud security-compliance provider-type-instance delete \
    --provider-type-id=exampleString \
    --provider-type-instance-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance provider-type-instance get`
{: #security-compliance-cli-provider-type-instances-get-command}

Retrieve a provider type instance by specifying the provider type ID, and Security and Compliance Center instance ID. For more information about integrations, see [Connecting Workload Protection](/docs/security-compliance?topic=security-compliance-setup-workload-protection).

```sh
ibmcloud security-compliance provider-type-instance get --provider-type-id PROVIDER-TYPE-ID --provider-type-instance-id PROVIDER-TYPE-INSTANCE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-provider-type-instances-get-cli-options}

`--provider-type-id` (string)
:   The provider type ID. Required.

    The maximum length is `36` characters. The minimum length is `32` characters. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--provider-type-instance-id` (string)
:   The provider type instance ID. Required.

    The maximum length is `36` characters. The minimum length is `32` characters. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-provider-type-instances-get-examples}

```sh
ibmcloud security-compliance provider-type-instance get \
    --provider-type-id=exampleString \
    --provider-type-instance-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance provider-type-instance update`
{: #security-compliance-cli-provider-types-update-command}

Patch a specific instance of a provider type.

```sh
ibmcloud security-compliance provider-type-instance update --provider-type-id PROVIDER-TYPE-ID --provider-type-instance-id PROVIDER-TYPE-INSTANCE-ID [--name NAME] [--attributes ATTRIBUTES] [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-provider-types-update-cli-options}

`--provider-type-id` (string)
:   The provider type ID. Required.

    The maximum length is `36` characters. The minimum length is `32` characters. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--provider-type-instance-id` (string)
:   The provider type instance ID. Required.

    The maximum length is `36` characters. The minimum length is `32` characters. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--name` (string)
:   The provider type instance name.

    The maximum length is `64` characters. The minimum length is `1` character. The value must match regular expression `/[A-Za-z0-9]+/`.

`--attributes` (generic map)
:   The attributes for connecting to the provider type instance.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--attributes=@path/to/file.json`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-provider-types-update-examples}

```sh
ibmcloud security-compliance provider-type-instance update \
    --provider-type-id=exampleString \
    --provider-type-instance-id=exampleString \
    --name=workload-protection-instance-1 \
    --attributes='{"anyKey": "anyValue"}' \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance provider-type-instance list`
{: #security-compliance-cli-provider-types-list-all-command}

Get a list of instances for all provider types.

```sh
ibmcloud security-compliance provider-type-instance list [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-provider-types-list-all-cli-options}

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this headers is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-provider-types-list-all-examples}

```sh
ibmcloud security-compliance provider-type-instance list \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

## Settings
{: #security-compliance-settings-cli}

Commands for Setting resources.

```sh
ibmcloud security-compliance setting --help
```


### `ibmcloud security-compliance setting get`
{: #security-compliance-cli-settings-get-command}

Retrieve the settings of your service instance.

```sh
ibmcloud security-compliance setting get [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-settings-get-cli-options}

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request, and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request, and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-settings-get-examples}

```sh
ibmcloud security-compliance setting get \
    --x-correlation-id=1a2b3c4d-5e6f-4a7b-8c9d-e0f1a2b3c4d5 \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance setting update`
{: #security-compliance-cli-settings-update-command}

Update the settings of your service instance.

```sh
ibmcloud security-compliance setting update [--event-notifications EVENT-NOTIFICATIONS] [--object-storage OBJECT-STORAGE] [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-settings-update-cli-options}

`--event-notifications` ([`EventNotifications`](#cli-event-notifications-example-schema))
:   The Event Notifications settings. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--event-notifications=@path/to/file.json`.

`--object-storage` ([`ObjectStorage`](#cli-object-storage-example-schema))
:   The Cloud Object Storage settings. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--object-storage=@path/to/file.json`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request, and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request, and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--event-notifications-instance-crn` (string)
:   The Event Notifications instance CRN. This option provides a value for a sub-field of the JSON option 'event-notifications'. It is mutually exclusive with that option.

    The maximum length is `512` characters. The minimum length is `0` characters. The value must match regular expression `/^crn:v[0-9](:([A-Za-z0-9-._~!$&'()*+,;=@\/]|%[0-9A-Z]{2})*){8}|$/`.

`--event-notifications-updated-on` (strfmt.DateTime)
:   The date when the Event Notifications connection was updated. This option provides a value for a sub-field of the JSON option 'event-notifications'. It is mutually exclusive with that option.

`--event-notifications-source-id` (string)
:   The connected Security and Compliance Center instance CRN. This option provides a value for a sub-field of the JSON option 'event-notifications'. It is mutually exclusive with that option.

    The maximum length is `512` characters. The minimum length is `1` character. The value must match regular expression `/([A-Za-z0-9]+(:[A-Za-z0-9]+)+)/`.

`--event-notifications-source-description` (string)
:   The description of the source of the Event Notifications. This option provides a value for a sub-field of the JSON option 'event-notifications'. It is mutually exclusive with that option.

    The default value is `This source is used for integration with IBM Cloud Security and Compliance Center.`. The maximum length is `512` characters. The minimum length is `1` character.

`--event-notifications-source-name` (string)
:   The name of the source of the Event Notifications. This option provides a value for a sub-field of the JSON option 'event-notifications'. It is mutually exclusive with that option.

    The default value is `compliance`. The maximum length is `512` characters. The minimum length is `1` character.

`--object-storage-instance-crn` (string)
:   The connected Cloud Object Storage instance CRN. This option provides a value for a sub-field of the JSON option 'object-storage'. It is mutually exclusive with that option.

    The maximum length is `512` characters. The minimum length is `0` characters. The value must match regular expression `/^crn:v[0-9](:([A-Za-z0-9-._~!$&'()*+,;=@\/]|%[0-9A-Z]{2})*){8}|$/`.

`--object-storage-bucket` (string)
:   The connected Cloud Object Storage bucket name. This option provides a value for a sub-field of the JSON option 'object-storage'. It is mutually exclusive with that option.

    The maximum length is `64` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z]+|/`.

`--object-storage-bucket-location` (string)
:   The connected Cloud Object Storage bucket location. This option provides a value for a sub-field of the JSON option 'object-storage'. It is mutually exclusive with that option.

    The maximum length is `32` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z]+/`.

`--object-storage-bucket-endpoint` (string)
:   The connected Cloud Object Storage bucket endpoint. This option provides a value for a sub-field of the JSON option 'object-storage'. It is mutually exclusive with that option.

    The maximum length is `512` characters. The minimum length is `1` character. The value must match regular expression `/([A-Za-z0-9-]+)/`.

`--object-storage-updated-on` (strfmt.DateTime)
:   The date when the bucket connection was updated. This option provides a value for a sub-field of the JSON option 'object-storage'. It is mutually exclusive with that option.

#### Examples
{: #security-compliance-settings-update-examples}

```sh
ibmcloud security-compliance setting update \
    --event-notifications='{"instance_crn": "crn:v1:staging:public:event-notifications:us-south:a/ff88f007f9ff4622aac4fbc0eda36255:7199ae60-a214-4dd8-9bf7-ce571de49d01::", "updated_on": "2019-01-01T12:00:00.000Z", "source_id": "crn:v1:staging:public:event-notifications:us-south:a/ff88f007f9ff4622aac4fbc0eda36255:b8b07245-0bbe-4478-b11c-0dce523105fd::", "source_description": "This source is used for integration with IBM Cloud Security and Compliance Center.", "source_name": "compliance"}' \
    --object-storage='{"instance_crn": "crn:v1:staging:public:cloud-object-storage:global:a/ff88f007f9ff4622aac4fbc0eda36255:7199ae60-a214-4dd8-9bf7-ce571de49d01::", "bucket": "px-scan-results", "bucket_location": "us-south", "bucket_endpoint": "exampleString", "updated_on": "2019-01-01T12:00:00.000Z"}' \
    --x-correlation-id=1a2b3c4d-5e6f-4a7b-8c9d-e0f1a2b3c4d5 \
    --x-request-id=exampleString
```
{: pre}

Alternatively, granular options are available for for the sub-fields of JSON string options:
```sh
ibmcloud security-compliance setting update \
    --x-correlation-id=1a2b3c4d-5e6f-4a7b-8c9d-e0f1a2b3c4d5 \
    --x-request-id=exampleString \
    --event-notifications-instance-crn=crn:v1:staging:public:cloud-object-storage:global:a/ff88f007f9ff4622aac4fbc0eda36255:7199ae60-a214-4dd8-9bf7-ce571de49d01:: \
    --event-notifications-updated-on=2019-01-01T12:00:00.000Z \
    --event-notifications-source-id=crn:v1:staging:public:event-notifications:us-south:a/ff88f007f9ff4622aac4fbc0eda36255:b8b07245-0bbe-4478-b11c-0dce523105fd:: \
    --event-notifications-source-description='This source is used for integration with IBM Cloud Security and Compliance Center.' \
    --event-notifications-source-name=compliance \
    --object-storage-instance-crn=exampleString \
    --object-storage-bucket=exampleString \
    --object-storage-bucket-location=exampleString \
    --object-storage-bucket-endpoint=exampleString \
    --object-storage-updated-on=2019-01-01T12:00:00.000Z
```
{: pre}

### `ibmcloud security-compliance setting post-test-event`
{: #security-compliance-cli-settings-post-test-event-command}

Send a test event to your Event Notifications instance to ensure that the events that are generated  by Security and Compliance Center are being forwarded to Event Notifications. For more information, see [Enabling event notifications](/docs/security-compliance?topic=security-compliance-event-notifications#event-notifications-test-api).

```sh
ibmcloud security-compliance setting post-test-event [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-settings-post-test-event-cli-options}

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request, and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request, and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-settings-post-test-event-examples}

```sh
ibmcloud security-compliance setting post-test-event \
    --x-correlation-id=1a2b3c4d-5e6f-4a7b-8c9d-e0f1a2b3c4d5 \
    --x-request-id=exampleString
```
{: pre}

## Control libraries
{: #security-compliance-control-libraries-cli}

Commands for Control Library resources.

```sh
ibmcloud security-compliance control-library --help
```


### `ibmcloud security-compliance control-library list`
{: #security-compliance-cli-control-libraries-list-all-command}

Retrieve all of the control libraries that are available in your account, including predefined, and custom libraries.

With Security and Compliance Center, you can create a custom control library that is specific to your organization's needs.  You define the controls and specifications before you map previously created assessments. Each control has several specifications  and assessments that are mapped to it. A specification is a defined requirement that is specific to a component. An assessment, or several,  are mapped to each specification with a detailed evaluation that is done to check whether the specification is compliant. For more information, see [Creating custom libraries](/docs/security-compliance?topic=security-compliance-custom-library).
Note: If the `--all-pages` option is not set, the command will only retrieve a single page of the collection.

```sh
ibmcloud security-compliance control-library list [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID] [--limit LIMIT] [--control-library-type CONTROL-LIBRARY-TYPE] [--start START]
```


#### Command options
{: #security-compliance-control-libraries-list-all-cli-options}

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--limit` (int64)
:   The field that indicates how many resources to return, unless the response is the last page of resources.

    The default value is `50`. The maximum value is `100`. The minimum value is `0`.

`--control-library-type` (string)
:   The field that indicate how you want the resources to be filtered by.

    The maximum length is `10` characters. The minimum length is `6` characters. The value must match regular expression `/custom|predefined/`.

`--start` (string)
:   Determine what resource to start the page on or after.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/.*/`.

`--all-pages` (bool)
:   Invoke multiple requests to display all pages of the collection for control-libraries-list-all.

#### Example
{: #security-compliance-control-libraries-list-all-examples}

```sh
ibmcloud security-compliance control-library list \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --limit=50 \
    --control-library-type=custom \
    --start=exampleString
```
{: pre}

### `ibmcloud security-compliance control-library create`
{: #security-compliance-cli-control-libraries-create-command}

Create a custom control library that is specific to your organization's needs.

With Security and Compliance Center, you can create a custom control library that is specific to your organization's needs.  You define the controls and specifications before you map previously created assessments. Each control has several specifications  and assessments that are mapped to it. A specification is a defined requirement that is specific to a component. An assessment, or several,  are mapped to each specification with a detailed evaluation that is done to check whether the specification is compliant. For more information, see [Creating custom libraries](/docs/security-compliance?topic=security-compliance-custom-library).

```sh
ibmcloud security-compliance control-library create --control-library-name CONTROL-LIBRARY-NAME --control-library-description CONTROL-LIBRARY-DESCRIPTION --control-library-type CONTROL-LIBRARY-TYPE --controls CONTROLS [--version-group-label VERSION-GROUP-LABEL] [--control-library-version CONTROL-LIBRARY-VERSION] [--latest LATEST] [--controls-count CONTROLS-COUNT] [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-control-libraries-create-cli-options}

`--control-library-name` (string)
:   The control library name. Required.

    The maximum length is `64` characters. The minimum length is `2` characters. The value must match regular expression `/^[a-zA-Z0-9_\\s\\-]*$/`.

`--control-library-description` (string)
:   The control library description. Required.

    The maximum length is `256` characters. The minimum length is `2` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--control-library-type` (string)
:   The control library type. Required.

    Allowable values are: `predefined`, `custom`.

`--controls` ([`ControlsInControlLib[]`](#cli-controls-in-control-lib-example-schema))
:   The controls. Required.

    The maximum length is `1200` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--controls=@path/to/file.json`.

`--version-group-label` (string)
:   The version group label.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--control-library-version` (string)
:   The control library version.

    The maximum length is `64` characters. The minimum length is `5` characters. The value must match regular expression `/^[a-zA-Z0-9_\\-.]*$/`.

`--latest` (bool)
:   The latest control library version.

`--controls-count` (int64)
:   The number of controls.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-control-libraries-create-examples}

```sh
ibmcloud security-compliance control-library create \
    --control-library-name='IBM Cloud for Financial Services' \
    --control-library-description='IBM Cloud for Financial Services' \
    --control-library-type=custom \
    --controls='[{"control_name": "SC-7", "control_id": "1fa45e17-9322-4e6c-bbd6-1c51db08e790", "control_description": "Boundary Protection", "control_category": "System and Communications Protection", "control_parent": "exampleString", "control_tags": ["1fa45e17-9322-4e6c-bbd6-1c51db08e790"], "control_specifications": [{"control_specification_id": "5c7d6f88-a92f-4734-9b49-bd22b0900184", "responsibility": "user", "component_id": "iam-identity", "component_name": "exampleString", "environment": "ibm-cloud", "control_specification_description": "IBM cloud", "assessments_count": 38, "assessments": [{"assessment_id": "rule-a637949b-7e51-46c4-afd4-b96619001bf1", "assessment_method": "ibm-cloud-rule", "assessment_type": "automated", "assessment_description": "Check that there is an Activity Tracker event route defined to collect global events generated by IBM Cloud services", "parameter_count": 38, "parameters": [{"parameter_name": "session_invalidation_in_seconds", "parameter_display_name": "Sign out due to inactivity in seconds", "parameter_type": "numeric", "parameter_value": "public"}]}]}], "control_docs": {"control_docs_id": "sc-7", "control_docs_type": "ibm-cloud"}, "control_requirement": true, "status": "enabled"}]' \
    --version-group-label=33fc7b80-0fa5-4f16-bbba-1f293f660f0d \
    --control-library-version=1.0.0 \
    --latest=true \
    --controls-count=38 \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance control-library delete`
{: #security-compliance-cli-control-libraries-delete-command}

Delete a custom control library by providing the control library ID.  You can find this ID by looking in the Security and Compliance Center UI.

With Security and Compliance Center, you can manage a custom control library  that is specific to your organization's needs. Each control has several specifications  and assessments that are mapped to it.  For more information, see [Creating custom libraries](/docs/security-compliance?topic=security-compliance-custom-library).

```sh
ibmcloud security-compliance control-library delete --control-libraries-id CONTROL-LIBRARIES-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-control-libraries-delete-cli-options}

`--control-libraries-id` (string)
:   The control library ID. Required.

    The maximum length is `256` characters. The minimum length is `1` character. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-control-libraries-delete-examples}

```sh
ibmcloud security-compliance control-library delete \
    --control-libraries-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance control-library get`
{: #security-compliance-cli-control-libraries-get-command}

View the details of a control library by specifying its ID.

With Security and Compliance Center, you can create a custom control library that is specific to your organization's needs.  You define the controls and specifications before you map previously created assessments. Each control has several specifications  and assessments that are mapped to it. A specification is a defined requirement that is specific to a component. An assessment, or several,  are mapped to each specification with a detailed evaluation that is done to check whether the specification is compliant. For more information, see [Creating custom libraries](/docs/security-compliance?topic=security-compliance-custom-library).

```sh
ibmcloud security-compliance control-library get --control-libraries-id CONTROL-LIBRARIES-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-control-libraries-get-cli-options}

`--control-libraries-id` (string)
:   The control library ID. Required.

    The maximum length is `256` characters. The minimum length is `1` character. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-control-libraries-get-examples}

```sh
ibmcloud security-compliance control-library get \
    --control-libraries-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance control-library update`
{: #security-compliance-cli-control-libraries-update-command}

Update a custom control library by providing the control library ID. You can find this ID in the Security and Compliance Center UI.

With Security and Compliance Center, you can create and update a custom control library that is specific to your organization's needs.  You define the controls and specifications before you map previously created assessments. Each control has several specifications  and assessments that are mapped to it. For more information, see [Creating custom libraries](/docs/security-compliance?topic=security-compliance-custom-library).

```sh
ibmcloud security-compliance control-library update --control-libraries-id CONTROL-LIBRARIES-ID [--id ID] [--account-id ACCOUNT-ID] [--control-library-name CONTROL-LIBRARY-NAME] [--control-library-description CONTROL-LIBRARY-DESCRIPTION] [--control-library-type CONTROL-LIBRARY-TYPE] [--version-group-label VERSION-GROUP-LABEL] [--control-library-version CONTROL-LIBRARY-VERSION] [--created-on CREATED-ON] [--created-by CREATED-BY] [--updated-on UPDATED-ON] [--updated-by UPDATED-BY] [--latest LATEST] [--hierarchy-enabled HIERARCHY-ENABLED] [--controls-count CONTROLS-COUNT] [--control-parents-count CONTROL-PARENTS-COUNT] [--controls CONTROLS] [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-control-libraries-update-cli-options}

`--control-libraries-id` (string)
:   The control library ID. Required.

    The maximum length is `256` characters. The minimum length is `1` character. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--id` (string)
:   The control library ID.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[a-zA-Z0-9-]*$/`.

`--account-id` (string)
:   The account ID.

    The maximum length is `32` characters. The minimum length is `0` characters. The value must match regular expression `/^[a-zA-Z0-9-]*$/`.

`--control-library-name` (string)
:   The control library name.

    The maximum length is `64` characters. The minimum length is `2` characters. The value must match regular expression `/^[a-zA-Z0-9_\\s\\-]*$/`.

`--control-library-description` (string)
:   The control library description.

    The maximum length is `256` characters. The minimum length is `2` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--control-library-type` (string)
:   The control library type.

    Allowable values are: `predefined`, `custom`.

`--version-group-label` (string)
:   The version group label.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--control-library-version` (string)
:   The control library version.

    The maximum length is `64` characters. The minimum length is `5` characters. The value must match regular expression `/^[a-zA-Z0-9_\\-.]*$/`.

`--created-on` (strfmt.DateTime)
:   The date when the control library was created.

`--created-by` (string)
:   The user who created the control library.

    The maximum length is `255` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9-\\.:,_\\s]*$/`.

`--updated-on` (strfmt.DateTime)
:   The date when the control library was updated.

`--updated-by` (string)
:   The user who updated the control library.

    The maximum length is `255` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9-\\.:,_\\s]*$/`.

`--latest` (bool)
:   The latest version of the control library.

`--hierarchy-enabled` (bool)
:   The indication of whether hierarchy is enabled for the control library.

`--controls-count` (int64)
:   The number of controls.

`--control-parents-count` (int64)
:   The number of parent controls in the control library.

`--controls` ([`ControlsInControlLib[]`](#cli-controls-in-control-lib-example-schema))
:   The list of controls in a control library.

    The maximum length is `1200` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--controls=@path/to/file.json`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-control-libraries-update-examples}

```sh
ibmcloud security-compliance control-library update \
    --control-libraries-id=exampleString \
    --id=exampleString \
    --account-id=exampleString \
    --control-library-name='IBM Cloud for Financial Services' \
    --control-library-description='IBM Cloud for Financial Services' \
    --control-library-type=custom \
    --version-group-label=exampleString \
    --control-library-version=1.1.0 \
    --created-on=2019-01-01T12:00:00.000Z \
    --created-by=exampleString \
    --updated-on=2019-01-01T12:00:00.000Z \
    --updated-by=exampleString \
    --latest=true \
    --hierarchy-enabled=true \
    --controls-count=38 \
    --control-parents-count=38 \
    --controls='[{"control_name": "SC-7", "control_id": "1fa45e17-9322-4e6c-bbd6-1c51db08e790", "control_description": "Boundary Protection", "control_category": "System and Communications Protection", "control_parent": "exampleString", "control_tags": ["1fa45e17-9322-4e6c-bbd6-1c51db08e790"], "control_specifications": [{"control_specification_id": "5c7d6f88-a92f-4734-9b49-bd22b0900184", "responsibility": "user", "component_id": "iam-identity", "component_name": "exampleString", "environment": "ibm-cloud", "control_specification_description": "IBM cloud", "assessments_count": 38, "assessments": [{"assessment_id": "rule-a637949b-7e51-46c4-afd4-b96619001bf1", "assessment_method": "ibm-cloud-rule", "assessment_type": "automated", "assessment_description": "Check that there is an Activity Tracker event route defined to collect global events generated by IBM Cloud services", "parameter_count": 38, "parameters": [{"parameter_name": "session_invalidation_in_seconds", "parameter_display_name": "Sign out due to inactivity in seconds", "parameter_type": "numeric", "parameter_value": "public"}]}]}], "control_docs": {"control_docs_id": "sc-7", "control_docs_type": "ibm-cloud"}, "control_requirement": true, "status": "enabled"}]' \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

## Profiles
{: #security-compliance-profiles-cli}

Commands for Profile resources.

```sh
ibmcloud security-compliance profile --help
```


### `ibmcloud security-compliance profile attachments`
{: #security-compliance-cli-attachments-list-command}

View all of the attachments that are linked to a specific profile.  An attachment is the association between the set of resources that you want to evaluate  and a profile that contains the specific controls that you want to use. For more information, see [Running an evaluation for IBM Cloud](/docs/security-compliance?topic=security-compliance-scan-resources).
Note: If the `--all-pages` option is not set, the command will only retrieve a single page of the collection.

```sh
ibmcloud security-compliance profile attachments --profile-id PROFILE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID] [--limit LIMIT] [--start START]
```


#### Command options
{: #security-compliance-attachments-list-cli-options}

`--profile-id` (string)
:   The profile ID. Required.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--limit` (int64)
:   The indication of how many resources to return, unless the response is the last page of resources.

    The default value is `50`. The maximum value is `100`. The minimum value is `0`.

`--start` (string)
:   Determine what resource to start the page on or after.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/.*/`.

`--all-pages` (bool)
:   Invoke multiple requests to display all pages of the collection for attachments-list.

#### Example
{: #security-compliance-attachments-list-examples}

```sh
ibmcloud security-compliance profile attachments \
    --profile-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --limit=10 \
    --start=exampleString
```
{: pre}

### `ibmcloud security-compliance profile list`
{: #security-compliance-cli-profiles-list-all-command}

View all of the predefined and custom profiles that are available in your account.
Note: If the `--all-pages` option is not set, the command will only retrieve a single page of the collection.

```sh
ibmcloud security-compliance profile list [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID] [--limit LIMIT] [--profile-type PROFILE-TYPE] [--start START]
```


#### Command options
{: #security-compliance-profiles-list-all-cli-options}

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request, and repeated in a response header for the corresponding response. The same value is used for downstream requests, and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--limit` (int64)
:   The indication of how many resources to return, unless the response is the last page of resources.

    The default value is `50`. The maximum value is `100`. The minimum value is `0`.

`--profile-type` (string)
:   The field that indicate how you want the resources to be filtered by.

    The maximum length is `10` characters. The minimum length is `6` characters. The value must match regular expression `/custom|predefined/`.

`--start` (string)
:   Determine what resource to start the page on or after.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/.*/`.

`--all-pages` (bool)
:   Invoke multiple requests to display all pages of the collection for profiles-list-all.

#### Example
{: #security-compliance-profiles-list-all-examples}

```sh
ibmcloud security-compliance profile list \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --limit=10 \
    --profile-type=custom \
    --start=exampleString
```
{: pre}

### `ibmcloud security-compliance profile create`
{: #security-compliance-cli-profiles-create-command}

Create a custom profile that is specific to your usecase, by using an existing library as a starting point.  For more information, see [Building custom profiles](/docs/security-compliance?topic=security-compliance-build-custom-profiles&interface=api).

```sh
ibmcloud security-compliance profile create --profile-name PROFILE-NAME --profile-description PROFILE-DESCRIPTION --profile-type PROFILE-TYPE --controls CONTROLS --default-parameters DEFAULT-PARAMETERS [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-profiles-create-cli-options}

`--profile-name` (string)
:   The name of the profile. Required.

    The maximum length is `64` characters. The minimum length is `2` characters. The value must match regular expression `/^[a-zA-Z0-9_\\s\\-]*$/`.

`--profile-description` (string)
:   The description of the profile. Required.

    The maximum length is `256` characters. The minimum length is `2` characters. The value must match regular expression `/^[a-zA-Z0-9_,'"\\s\\-\\[\\]]+$/`.

`--profile-type` (string)
:   The profile type. Required.

    Allowable values are: `predefined`, `custom`.

`--controls` ([`ProfileControlsPrototype[]`](#cli-profile-controls-prototype-example-schema))
:   The controls that are in the profile. Required.

    The maximum length is `512` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--controls=@path/to/file.json`.

`--default-parameters` ([`DefaultParametersPrototype[]`](#cli-default-parameters-prototype-example-schema))
:   The default parameters of the profile. Required.

    The maximum length is `512` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--default-parameters=@path/to/file.json`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request, and repeated in a response header for the corresponding response. The same value is used for downstream requests, and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-profiles-create-examples}

```sh
ibmcloud security-compliance profile create \
    --profile-name=test_profile1 \
    --profile-description=test_description1 \
    --profile-type=custom \
    --controls='[{"control_library_id": "e98a56ff-dc24-41d4-9875-1e188e2da6cd", "control_id": "1fa45e17-9322-4e6c-bbd6-1c51db08e790"}]' \
    --default-parameters='[{"assessment_type": "Automated", "assessment_id": "rule-a637949b-7e51-46c4-afd4-b96619001bf1", "parameter_name": "session_invalidation_in_seconds", "parameter_default_value": "120", "parameter_display_name": "Sign out due to inactivity in seconds", "parameter_type": "numeric"}]' \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance profile delete`
{: #security-compliance-cli-profiles-delete-command}

Delete a custom profile by providing the profile ID.  You can find the ID in the Security and Compliance Center UI. For more information about managing your custom profiles, see [Building custom profiles](/docs/security-compliance?topic=security-compliance-build-custom-profiles&interface=api).

```sh
ibmcloud security-compliance profile delete --profile-id PROFILE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-profiles-delete-cli-options}

`--profile-id` (string)
:   The profile ID. Required.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-profiles-delete-examples}

```sh
ibmcloud security-compliance profile delete \
    --profile-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance profile get`
{: #security-compliance-cli-profiles-get-command}

View the details of a profile by providing the profile ID.  You can find the profile ID in the Security and Compliance Center UI. For more information, see [Building custom profiles](/docs/security-compliance?topic=security-compliance-build-custom-profiles&interface=api).

```sh
ibmcloud security-compliance profile get --profile-id PROFILE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-profiles-get-cli-options}

`--profile-id` (string)
:   The profile ID. Required.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-profiles-get-examples}

```sh
ibmcloud security-compliance profile get \
    --profile-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance profile update`
{: #security-compliance-cli-profiles-update-command}

Update the details of a custom profile. With Security and Compliance Center, you can manage  a profile that is specific to your usecase, by using an existing library as a starting point.  For more information, see [Building custom profiles](/docs/security-compliance?topic=security-compliance-build-custom-profiles&interface=api).

```sh
ibmcloud security-compliance profile update --profile-id PROFILE-ID --profile-name PROFILE-NAME --profile-description PROFILE-DESCRIPTION --profile-type PROFILE-TYPE --controls CONTROLS --default-parameters DEFAULT-PARAMETERS [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-profiles-update-cli-options}

`--profile-id` (string)
:   The profile ID. Required.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--profile-name` (string)
:   The name of the profile. Required.

    The maximum length is `64` characters. The minimum length is `2` characters. The value must match regular expression `/^[a-zA-Z0-9_\\s\\-]*$/`.

`--profile-description` (string)
:   The description of the profile. Required.

    The maximum length is `256` characters. The minimum length is `2` characters. The value must match regular expression `/^[a-zA-Z0-9_,'"\\s\\-\\[\\]]+$/`.

`--profile-type` (string)
:   The profile type. Required.

    Allowable values are: `predefined`, `custom`.

`--controls` ([`ProfileControlsPrototype[]`](#cli-profile-controls-prototype-example-schema))
:   The controls that are in the profile. Required.

    The maximum length is `512` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--controls=@path/to/file.json`.

`--default-parameters` ([`DefaultParametersPrototype[]`](#cli-default-parameters-prototype-example-schema))
:   The default parameters of the profile. Required.

    The maximum length is `512` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--default-parameters=@path/to/file.json`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-profiles-update-examples}

```sh
ibmcloud security-compliance profile update \
    --profile-id=exampleString \
    --profile-name=test_profile1 \
    --profile-description=test_description1 \
    --profile-type=custom \
    --controls='[{"control_library_id": "e98a56ff-dc24-41d4-9875-1e188e2da6cd", "control_id": "1fa45e17-9322-4e6c-bbd6-1c51db08e790"}]' \
    --default-parameters='[{"assessment_type": "Automated", "assessment_id": "rule-a637949b-7e51-46c4-afd4-b96619001bf1", "parameter_name": "session_invalidation_in_seconds", "parameter_default_value": "120", "parameter_display_name": "Sign out due to inactivity in seconds", "parameter_type": "numeric"}]' \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

## Rules
{: #security-compliance-rules-cli}

Commands for Rule resources.

```sh
ibmcloud security-compliance rule --help
```


### `ibmcloud security-compliance rule list`
{: #security-compliance-cli-rules-list-command}

Retrieve all the rules that you use to target the exact configuration properties  that you need to ensure are compliant. For more information, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

```sh
ibmcloud security-compliance rule list [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID] [--type TYPE] [--search SEARCH] [--service-name SERVICE-NAME]
```


#### Command options
{: #security-compliance-rules-list-cli-options}

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--type` (string)
:   The list of only user-defined, or system-defined rules.

    The maximum length is `14` characters. The minimum length is `12` characters. The value must match regular expression `/user_defined|system_defined/`.

`--search` (string)
:   The indication of whether to search for rules with a specific string string in the name, description, or labels.

    The maximum length is `256` characters. The minimum length is `0` characters. The value must match regular expression `/.*/`.

`--service-name` (string)
:   Searches for rules targeting corresponding service.

    The maximum length is `64` characters. The minimum length is `0` characters. The value must match regular expression `/.*/`.

#### Example
{: #security-compliance-rules-list-examples}

```sh
ibmcloud security-compliance rule list \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --type=system_defined \
    --search=exampleString \
    --service-name=exampleString
```
{: pre}

### `ibmcloud security-compliance rule create`
{: #security-compliance-cli-rules-create-command}

Create a custom rule to to target the exact configuration properties  that you need to evaluate your resources for compliance. For more information, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

```sh
ibmcloud security-compliance rule create --description DESCRIPTION [--target TARGET] [--required-config REQUIRED-CONFIG] [--type TYPE] [--version VERSION] [--import IMPORT] [--labels LABELS] [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-rules-create-cli-options}

`--description` (string)
:   The rule description. Required.

    The maximum length is `512` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--target` ([`Target`](#cli-target-example-schema))
:   The rule target. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--target=@path/to/file.json`.

`--required-config` ([`RequiredConfig`](#cli-required-config-example-schema))
:   The required configurations. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--required-config=@path/to/file.json`.

`--type` (string)
:   The rule type (user_defined or system_defined).

    Allowable values are: `user_defined`, `system_defined`. The maximum length is `14` characters. The minimum length is `12` characters. The value must match regular expression `/[A-Za-z]+_[A-Za-z]+/`.

`--version` (string)
:   The rule version number.

    The maximum length is `10` characters. The minimum length is `5` characters. The value must match regular expression `/^[0-9][0-9.]*$/`.

`--import` ([`Import`](#cli-import-example-schema))
:   The collection of import parameters. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--import=@path/to/file.json`.

`--labels` ([]string)
:   The list of labels that correspond to a rule.

    The list items must match regular expression `/[A-Za-z0-9]+/`. The maximum length is `32` items. The minimum length is `0` items.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--target-service-name` (string)
:   The target service name. This option provides a value for a sub-field of the JSON option 'target'. It is mutually exclusive with that option.

    The maximum length is `64` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--target-service-display-name` (string)
:   The display name of the target service. This option provides a value for a sub-field of the JSON option 'target'. It is mutually exclusive with that option.

    The maximum length is `64` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--target-resource-kind` (string)
:   The target resource kind. This option provides a value for a sub-field of the JSON option 'target'. It is mutually exclusive with that option.

    The maximum length is `99999` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--target-additional-target-attributes` (`AdditionalTargetAttribute[]`)
:   The list of targets supported properties. This option provides a value for a sub-field of the JSON option 'target'. It is mutually exclusive with that option.

    The maximum length is `99999` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--target-additional-target-attributes=@path/to/file.json`.

`--required-config-description` (string)
:   The required config description. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    The maximum length is `512` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--required-config-and` (`RequiredConfigItems[]`)
:   The `AND` required configurations. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    The maximum length is `64` items. The minimum length is `1` item.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--required-config-and=@path/to/file.json`.

`--required-config-or` (`RequiredConfigItems[]`)
:   The `OR` required configurations. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    The maximum length is `64` items. The minimum length is `1` item.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--required-config-or=@path/to/file.json`.

`--required-config-property` (string)
:   The property. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    The maximum length is `256` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--required-config-operator` (string)
:   The operator. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    Allowable values are: `string_equals`, `string_not_equals`, `string_match`, `string_not_match`, `string_contains`, `string_not_contains`, `num_equals`, `num_not_equals`, `num_less_than`, `num_less_than_equals`, `num_greater_than`, `num_greater_than_equals`, `is_empty`, `is_not_empty`, `is_true`, `is_false`, `strings_in_list`, `strings_allowed`, `strings_required`, `ips_in_range`, `ips_equals`, `ips_not_equals`, `days_less_than`. The maximum length is `23` characters. The minimum length is `7` characters.

`--required-config-value` (interface{})
:   Schema for any JSON type. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--required-config-value=@path/to/file.json`.

`--import-parameters` (`Parameter[]`)
:   The list of import parameters. This option provides a value for a sub-field of the JSON option 'import'. It is mutually exclusive with that option.

    The maximum length is `8` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--import-parameters=@path/to/file.json`.

#### Examples
{: #security-compliance-rules-create-examples}

```sh
ibmcloud security-compliance rule create \
    --description='Example rule' \
    --target='{"service_name": "cloud-object-storage", "service_display_name": "exampleString", "resource_kind": "bucket", "additional_target_attributes": [{"name": "location", "operator": "string_equals", "value": "us-east"}]}' \
    --required-config='{"description": "The Cloud Object Storage rule.", "and": [{"description": "exampleString", "property": "hard_quota", "operator": "num_equals", "value": "${hard_quota}"}]}' \
    --type=user_defined \
    --version=1.0.0 \
    --import='{"parameters": [{"name": "hard_quota", "display_name": "The Cloud Object Storage bucket quota.", "description": "The maximum bytes that are allocated to the Cloud Object Storage bucket.", "type": "numeric"}]}' \
    --labels=foo,bar \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

Alternatively, granular options are available for for the sub-fields of JSON string options:
```sh
ibmcloud security-compliance rule create \
    --description='Example rule' \
    --type=user_defined \
    --version=1.0.0 \
    --labels=foo,bar \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --target-service-name=exampleString \
    --target-service-display-name=exampleString \
    --target-resource-kind=exampleString \
    --target-additional-target-attributes='[additionalTargetAttribute]' \
    --required-config-description=exampleString \
    --required-config-and='[requiredConfigItems]' \
    --required-config-or='[requiredConfigItems]' \
    --required-config-property=exampleString \
    --required-config-operator=string_equals \
    --required-config-value="exampleString" \
    --import-parameters='[{"name": "hard_quota", "display_name": "The Cloud Object Storage bucket quota.", "description": "The maximum bytes that are allocated to the Cloud Object Storage bucket.", "type": "numeric"}]'
```
{: pre}

### `ibmcloud security-compliance rule delete`
{: #security-compliance-cli-rules-delete-command}

Delete a custom rule that you no longer require to evaluate your resources. For more information, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

```sh
ibmcloud security-compliance rule delete --rule-id RULE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-rules-delete-cli-options}

`--rule-id` (string)
:   The ID of the corresponding rule. Required.

    The maximum length is `41` characters. The minimum length is `41` characters. The value must match regular expression `/rule-[0-9A-Fa-f]{8}-[0-9A-Fa-f]{4}-[0-9A-Fa-f]{4}-[0-9A-Fa-f]{4}-[0-9A-Fa-f]{12}/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-rules-delete-examples}

```sh
ibmcloud security-compliance rule delete \
    --rule-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance rule get`
{: #security-compliance-cli-rules-get-command}

Retrieve a rule that you created to evaluate your resources.  For more information, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

```sh
ibmcloud security-compliance rule get --rule-id RULE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-rules-get-cli-options}

`--rule-id` (string)
:   The ID of the corresponding rule. Required.

    The maximum length is `41` characters. The minimum length is `41` characters. The value must match regular expression `/rule-[0-9A-Fa-f]{8}-[0-9A-Fa-f]{4}-[0-9A-Fa-f]{4}-[0-9A-Fa-f]{4}-[0-9A-Fa-f]{12}/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-rules-get-examples}

```sh
ibmcloud security-compliance rule get \
    --rule-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance rule update`
{: #security-compliance-cli-rules-update-command}

Update a custom rule that you use to target the exact configuration properties  that you need to evaluate your resources for compliance. For more information, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

```sh
ibmcloud security-compliance rule update --rule-id RULE-ID --if-match IF-MATCH --description DESCRIPTION [--target TARGET] [--required-config REQUIRED-CONFIG] [--type TYPE] [--version VERSION] [--import IMPORT] [--labels LABELS] [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-rules-update-cli-options}

`--rule-id` (string)
:   The ID of the corresponding rule. Required.

    The maximum length is `41` characters. The minimum length is `41` characters. The value must match regular expression `/rule-[0-9A-Fa-f]{8}-[0-9A-Fa-f]{4}-[0-9A-Fa-f]{4}-[0-9A-Fa-f]{4}-[0-9A-Fa-f]{12}/`.

`--if-match` (string)
:   This field compares a supplied `Etag` value with the version that is stored for the requested resource. If the values match, the server allows the request method to continue.

To find the `Etag` value, run a GET request on the resource that you want to modify, and check the response headers. Required.

    The maximum length is `128` characters. The minimum length is `4` characters. The value must match regular expression `/W\/"[^"]*"/`.

`--description` (string)
:   The rule description. Required.

    The maximum length is `512` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--target` ([`Target`](#cli-target-example-schema))
:   The rule target. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--target=@path/to/file.json`.

`--required-config` ([`RequiredConfig`](#cli-required-config-example-schema))
:   The required configurations. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--required-config=@path/to/file.json`.

`--type` (string)
:   The rule type (user_defined or system_defined).

    Allowable values are: `user_defined`, `system_defined`. The maximum length is `14` characters. The minimum length is `12` characters. The value must match regular expression `/[A-Za-z]+_[A-Za-z]+/`.

`--version` (string)
:   The rule version number.

    The maximum length is `10` characters. The minimum length is `5` characters. The value must match regular expression `/^[0-9][0-9.]*$/`.

`--import` ([`Import`](#cli-import-example-schema))
:   The collection of import parameters. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--import=@path/to/file.json`.

`--labels` ([]string)
:   The list of labels that correspond to a rule.

    The list items must match regular expression `/[A-Za-z0-9]+/`. The maximum length is `32` items. The minimum length is `0` items.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--target-service-name` (string)
:   The target service name. This option provides a value for a sub-field of the JSON option 'target'. It is mutually exclusive with that option.

    The maximum length is `64` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--target-service-display-name` (string)
:   The display name of the target service. This option provides a value for a sub-field of the JSON option 'target'. It is mutually exclusive with that option.

    The maximum length is `64` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--target-resource-kind` (string)
:   The target resource kind. This option provides a value for a sub-field of the JSON option 'target'. It is mutually exclusive with that option.

    The maximum length is `99999` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--target-additional-target-attributes` (`AdditionalTargetAttribute[]`)
:   The list of targets supported properties. This option provides a value for a sub-field of the JSON option 'target'. It is mutually exclusive with that option.

    The maximum length is `99999` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--target-additional-target-attributes=@path/to/file.json`.

`--required-config-description` (string)
:   The required config description. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    The maximum length is `512` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--required-config-and` (`RequiredConfigItems[]`)
:   The `AND` required configurations. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    The maximum length is `64` items. The minimum length is `1` item.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--required-config-and=@path/to/file.json`.

`--required-config-or` (`RequiredConfigItems[]`)
:   The `OR` required configurations. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    The maximum length is `64` items. The minimum length is `1` item.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--required-config-or=@path/to/file.json`.

`--required-config-property` (string)
:   The property. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    The maximum length is `256` characters. The minimum length is `0` characters. The value must match regular expression `/[A-Za-z0-9]+/`.

`--required-config-operator` (string)
:   The operator. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    Allowable values are: `string_equals`, `string_not_equals`, `string_match`, `string_not_match`, `string_contains`, `string_not_contains`, `num_equals`, `num_not_equals`, `num_less_than`, `num_less_than_equals`, `num_greater_than`, `num_greater_than_equals`, `is_empty`, `is_not_empty`, `is_true`, `is_false`, `strings_in_list`, `strings_allowed`, `strings_required`, `ips_in_range`, `ips_equals`, `ips_not_equals`, `days_less_than`. The maximum length is `23` characters. The minimum length is `7` characters.

`--required-config-value` (interface{})
:   Schema for any JSON type. This option provides a value for a sub-field of the JSON option 'required-config'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--required-config-value=@path/to/file.json`.

`--import-parameters` (`Parameter[]`)
:   The list of import parameters. This option provides a value for a sub-field of the JSON option 'import'. It is mutually exclusive with that option.

    The maximum length is `8` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--import-parameters=@path/to/file.json`.

#### Examples
{: #security-compliance-rules-update-examples}

```sh
ibmcloud security-compliance rule update \
    --rule-id=exampleString \
    --if-match=exampleString \
    --description='Example rule' \
    --target='{"service_name": "cloud-object-storage", "service_display_name": "Cloud Object Storage", "resource_kind": "bucket", "additional_target_attributes": [{"name": "location", "operator": "string_equals", "value": "us-south"}]}' \
    --required-config='{"description": "The Cloud Object Storage rule.", "and": [{"description": "exampleString", "property": "hard_quota", "operator": "num_equals", "value": "${hard_quota}"}]}' \
    --type=user_defined \
    --version=1.0.1 \
    --import='{"parameters": [{"name": "hard_quota", "display_name": "The Cloud Object Storage bucket quota.", "description": "The maximum bytes that are allocated to the Cloud Object Storage bucket.", "type": "numeric"}]}' \
    --labels=foo,bar \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

Alternatively, granular options are available for for the sub-fields of JSON string options:
```sh
ibmcloud security-compliance rule update \
    --rule-id=exampleString \
    --if-match=exampleString \
    --description='Example rule' \
    --type=user_defined \
    --version=1.0.1 \
    --labels=foo,bar \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --target-service-name=exampleString \
    --target-service-display-name=exampleString \
    --target-resource-kind=exampleString \
    --target-additional-target-attributes='[additionalTargetAttribute]' \
    --required-config-description=exampleString \
    --required-config-and='[requiredConfigItems]' \
    --required-config-or='[requiredConfigItems]' \
    --required-config-property=exampleString \
    --required-config-operator=string_equals \
    --required-config-value="exampleString" \
    --import-parameters='[{"name": "hard_quota", "display_name": "The Cloud Object Storage bucket quota.", "description": "The maximum bytes that are allocated to the Cloud Object Storage bucket.", "type": "numeric"}]'
```
{: pre}

## Attachments
{: #security-compliance-attachments-cli}

Commands for Attachment resources.

```sh
ibmcloud security-compliance attachment --help
```


### `ibmcloud security-compliance attachment create`
{: #security-compliance-cli-attachments-create-command}

Create an attachment to link to a profile to schedule evaluations  of your resources on a recurring schedule, or on-demand. For more information, see [Running an evaluation for IBM Cloud](/docs/security-compliance?topic=security-compliance-scan-resources).

```sh
ibmcloud security-compliance attachment create --profile-id PROFILE-ID --attachments ATTACHMENTS [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-attachments-create-cli-options}

`--profile-id` (string)
:   The profile ID. Required.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--attachments` ([`AttachmentsPrototype[]`](#cli-attachments-prototype-example-schema))
:   The array that displays all of the available attachments. Required.

    The maximum length is `50` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--attachments=@path/to/file.json`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-attachments-create-examples}

```sh
ibmcloud security-compliance attachment create \
    --profile-id=exampleString \
    --attachments='[{"id": "130003ea8bfa43c5aacea07a86da3000", "name": "account-0d8c3805dfea40aa8ad02265a18eb12b", "description": "Test description", "scope": [{"environment": "ibm-cloud", "properties": [{"name": "scope_id", "value": "cg3335893hh1428692d6747cf300yeb5"}]}], "status": "enabled", "schedule": "every_30_days", "notifications": {"enabled": false, "controls": {"threshold_limit": 15, "failed_control_ids": []}}, "attachment_parameters": [{"assessment_type": "Automated", "assessment_id": "rule-a637949b-7e51-46c4-afd4-b96619001bf1", "parameter_name": "session_invalidation_in_seconds", "parameter_value": "120", "parameter_display_name": "Sign out due to inactivity in seconds", "parameter_type": "numeric"}]}]' \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance attachment delete`
{: #security-compliance-cli-attachments-delete-command}

Delete an attachment. Alternatively, if you think that you might need  this configuration in the future, you can pause an attachment to stop being charged. For more information, see [Running an evaluation for IBM Cloud](/docs/security-compliance?topic=security-compliance-scan-resources).

```sh
ibmcloud security-compliance attachment delete --attachment-id ATTACHMENT-ID --profile-id PROFILE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-attachments-delete-cli-options}

`--attachment-id` (string)
:   The attachment ID. Required.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9A-Fa-f]{8}-[0-9A-Fa-f]{4}-4[0-9A-Fa-f]{3}-[89ABab][0-9A-Fa-f]{3}-[0-9A-Fa-f]{12}$|^$/`.

`--profile-id` (string)
:   The profile ID. Required.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-attachments-delete-examples}

```sh
ibmcloud security-compliance attachment delete \
    --attachment-id=exampleString \
    --profile-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance attachment get`
{: #security-compliance-cli-attachments-get-command}

View the details of an attachment a profile by providing the attachment ID.  You can find this value in the Security and Compliance Center UI. For more information, see [Running an evaluation for IBM Cloud](/docs/security-compliance?topic=security-compliance-scan-resources).

```sh
ibmcloud security-compliance attachment get --attachment-id ATTACHMENT-ID --profile-id PROFILE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-attachments-get-cli-options}

`--attachment-id` (string)
:   The attachment ID. Required.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9A-Fa-f]{8}-[0-9A-Fa-f]{4}-4[0-9A-Fa-f]{3}-[89ABab][0-9A-Fa-f]{3}-[0-9A-Fa-f]{12}$|^$/`.

`--profile-id` (string)
:   The profile ID. Required.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-attachments-get-examples}

```sh
ibmcloud security-compliance attachment get \
    --attachment-id=exampleString \
    --profile-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance attachment update`
{: #security-compliance-cli-attachments-update-command}

Update an attachment that is linked to a profile to evaluate your resources  on a recurring schedule, or on-demand. For more information, see [Running an evaluation for IBM Cloud](/docs/security-compliance?topic=security-compliance-scan-resources).

```sh
ibmcloud security-compliance attachment update --attachment-id ATTACHMENT-ID --profile-id PROFILE-ID [--id ID] [--account-id ACCOUNT-ID] [--instance-id INSTANCE-ID] [--scope SCOPE] [--created-on CREATED-ON] [--created-by CREATED-BY] [--updated-on UPDATED-ON] [--updated-by UPDATED-BY] [--status STATUS] [--schedule SCHEDULE] [--notifications NOTIFICATIONS] [--attachment-parameters ATTACHMENT-PARAMETERS] [--last-scan LAST-SCAN] [--next-scan-time NEXT-SCAN-TIME] [--name NAME] [--description DESCRIPTION] [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-attachments-update-cli-options}

`--attachment-id` (string)
:   The attachment ID. Required.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9A-Fa-f]{8}-[0-9A-Fa-f]{4}-4[0-9A-Fa-f]{3}-[89ABab][0-9A-Fa-f]{3}-[0-9A-Fa-f]{12}$|^$/`.

`--profile-id` (string)
:   The profile ID. Required.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$/`.

`--id` (string)
:   The ID of the attachment.

    The maximum length is `32` characters. The minimum length is `32` characters. The value must match regular expression `/^[a-zA-Z0-9-]*$/`.

`--account-id` (string)
:   The account ID that is associated to the attachment.

    The maximum length is `32` characters. The minimum length is `32` characters. The value must match regular expression `/^[a-zA-Z0-9-]*$/`.

`--instance-id` (string)
:   The instance ID of the account that is associated to the attachment.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[0-9A-Fa-f]{8}-[0-9A-Fa-f]{4}-4[0-9A-Fa-f]{3}-[89ABab][0-9A-Fa-f]{3}-[0-9A-Fa-f]{12}$|^$/`.

`--scope` ([`MultiCloudScope[]`](#cli-multi-cloud-scope-example-schema))
:   The scope payload for the multi cloud feature.

    The maximum length is `8` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--scope=@path/to/file.json`.

`--created-on` (strfmt.DateTime)
:   The date when the attachment was created.

`--created-by` (string)
:   The user who created the attachment.

    The maximum length is `255` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9-\\.:,_\\s]*$/`.

`--updated-on` (strfmt.DateTime)
:   The date when the attachment was updated.

`--updated-by` (string)
:   The user who updated the attachment.

    The maximum length is `255` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9-\\.:,_\\s]*$/`.

`--status` (string)
:   The status of an attachment evaluation.

    Allowable values are: `enabled`, `disabled`.

`--schedule` (string)
:   The schedule of an attachment evaluation.

    Allowable values are: `daily`, `every_7_days`, `every_30_days`.

`--notifications` ([`AttachmentsNotificationsPrototype`](#cli-attachments-notifications-prototype-example-schema))
:   The request payload of the attachment notifications. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--notifications=@path/to/file.json`.

`--attachment-parameters` ([`AttachmentParameterPrototype[]`](#cli-attachment-parameter-prototype-example-schema))
:   The profile parameters for the attachment.

    The maximum length is `512` items. The minimum length is `0` items.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--attachment-parameters=@path/to/file.json`.

`--last-scan` ([`LastScan`](#cli-last-scan-example-schema))
:   The details of the last scan of an attachment. This JSON option can instead be provided by setting individual fields with other options. It is mutually exclusive with those options.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--last-scan=@path/to/file.json`.

`--next-scan-time` (strfmt.DateTime)
:   The start time of the next scan.

`--name` (string)
:   The name of the attachment.

    The maximum length is `128` characters. The minimum length is `2` characters. The value must match regular expression `/^[a-zA-Z0-9-]*$/`.

`--description` (string)
:   The description for the attachment.

    The maximum length is `256` characters. The minimum length is `0` characters. The value must match regular expression `/^[a-zA-Z0-9_,'\\s\\-]*$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--notifications-enabled` (bool)
:   enabled notifications. This option provides a value for a sub-field of the JSON option 'notifications'. It is mutually exclusive with that option.

`--notifications-controls` (`FailedControls`)
:   The failed controls. This option provides a value for a sub-field of the JSON option 'notifications'. It is mutually exclusive with that option.

    Provide a JSON string option or specify a JSON file to read from by providing a filepath option that begins with a `@`, e.g. `--notifications-controls=@path/to/file.json`.

`--last-scan-id` (string)
:   The ID of the last scan of an attachment. This option provides a value for a sub-field of the JSON option 'last-scan'. It is mutually exclusive with that option.

    The maximum length is `36` characters. The minimum length is `36` characters. The value must match regular expression `/^[a-zA-Z0-9-]*$/`.

`--last-scan-status` (string)
:   The status of the last scan of an attachment. This option provides a value for a sub-field of the JSON option 'last-scan'. It is mutually exclusive with that option.

    Allowable values are: `in_progress`, `completed`.

`--last-scan-time` (strfmt.DateTime)
:   The time when the last scan started. This option provides a value for a sub-field of the JSON option 'last-scan'. It is mutually exclusive with that option.

#### Examples
{: #security-compliance-attachments-update-examples}

```sh
ibmcloud security-compliance attachment update \
    --attachment-id=exampleString \
    --profile-id=exampleString \
    --id=exampleString \
    --account-id=exampleString \
    --instance-id=exampleString \
    --scope='[{"environment": "ibm-cloud", "properties": [{"name": "scope_id", "value": "cg3335893hh1428692d6747cf300yeb5"}]}]' \
    --created-on=2019-01-01T12:00:00.000Z \
    --created-by=exampleString \
    --updated-on=2019-01-01T12:00:00.000Z \
    --updated-by=exampleString \
    --status=enabled \
    --schedule=every_30_days \
    --notifications='{"enabled": false, "controls": {"threshold_limit": 15, "failed_control_ids": []}}' \
    --attachment-parameters='[{"assessment_type": "Automated", "assessment_id": "rule-a637949b-7e51-46c4-afd4-b96619001bf1", "parameter_name": "session_invalidation_in_seconds", "parameter_value": "120", "parameter_display_name": "Sign out due to inactivity in seconds", "parameter_type": "numeric"}]' \
    --last-scan='{"id": "e8a39d25-0051-4328-8462-988ad321f49a", "status": "in_progress", "time": "2019-01-01T12:00:00.000Z"}' \
    --next-scan-time=2019-01-01T12:00:00.000Z \
    --name=account-0d8c3805dfea40aa8ad02265a18eb12b \
    --description='Test description' \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

Alternatively, granular options are available for for the sub-fields of JSON string options:
```sh
ibmcloud security-compliance attachment update \
    --attachment-id=exampleString \
    --profile-id=exampleString \
    --id=exampleString \
    --account-id=exampleString \
    --instance-id=exampleString \
    --scope=multiCloudScope \
    --created-on=2019-01-01T12:00:00.000Z \
    --created-by=exampleString \
    --updated-on=2019-01-01T12:00:00.000Z \
    --updated-by=exampleString \
    --status=enabled \
    --schedule=every_30_days \
    --attachment-parameters=attachmentParameterPrototype \
    --next-scan-time=2019-01-01T12:00:00.000Z \
    --name=account-0d8c3805dfea40aa8ad02265a18eb12b \
    --description='Test description' \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --notifications-enabled=true \
    --notifications-controls=failedControls \
    --last-scan-id=e8a39d25-0051-4328-8462-988ad321f49a \
    --last-scan-status=in_progress \
    --last-scan-time=2019-01-01T12:00:00.000Z
```
{: pre}

### `ibmcloud security-compliance attachment scan`
{: #security-compliance-cli-attachments-scan-command}

Create a scan to evaluate your resources on a recurring basis or on demand.

```sh
ibmcloud security-compliance attachment scan --attachment-id ATTACHMENT-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-attachments-scan-cli-options}

`--attachment-id` (string)
:   The attachment ID of a profile. Required.

    The maximum length is `32` characters. The minimum length is `32` characters. The value must match regular expression `/^[0-9a-f]{32}$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-attachments-scan-examples}

```sh
ibmcloud security-compliance attachment scan \
    --attachment-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance attachment list`
{: #security-compliance-cli-attachments-list-all-command}

View all of the attachments that are linked to an account. An attachment is the association between the set of resources that you want to evaluate  and a profile that contains the specific controls that you want to use. For more information, see [Running an evaluation for IBM Cloud](/docs/security-compliance?topic=security-compliance-scan-resources).
Note: If the `--all-pages` option is not set, the command will only retrieve a single page of the collection.

```sh
ibmcloud security-compliance attachment list [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID] [--limit LIMIT] [--start START]
```


#### Command options
{: #security-compliance-attachments-list-all-cli-options}

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is not used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--limit` (int64)
:   The indication of how many resources to return, unless the response is the last page of resources.

    The default value is `50`. The maximum value is `100`. The minimum value is `0`.

`--start` (string)
:   Determine what resource to start the page on or after.

    The maximum length is `1024` characters. The minimum length is `0` characters. The value must match regular expression `/.*/`.

`--all-pages` (bool)
:   Invoke multiple requests to display all pages of the collection for attachments-list-all.

#### Example
{: #security-compliance-attachments-list-all-examples}

```sh
ibmcloud security-compliance attachment list \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --limit=10 \
    --start=exampleString
```
{: pre}

## Reports
{: #security-compliance-reports-cli}

Commands for Report resources.

```sh
ibmcloud security-compliance report --help
```


### `ibmcloud security-compliance report latest`
{: #security-compliance-cli-reports-get-latest-command}

Retrieve the latest reports, which are grouped by profile ID, scope ID, and attachment ID. For more information, see [Viewing results](/docs/security-compliance?topic=security-compliance-results).

```sh
ibmcloud security-compliance report latest [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID] [--sort SORT]
```


#### Command options
{: #security-compliance-reports-get-latest-cli-options}

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--sort` (string)
:   This field sorts results by using a valid sort field. To learn more, see [Sorting](/docs/api-handbook?topic=api-handbook-sorting).

    The maximum length is `32` characters. The minimum length is `1` character. The value must match regular expression `/^[\\-]?[a-z0-9_]+$/`.

#### Example
{: #security-compliance-reports-get-latest-examples}

```sh
ibmcloud security-compliance report latest \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --sort=profile_name
```
{: pre}

### `ibmcloud security-compliance report list`
{: #security-compliance-cli-reports-list-command}

Retrieve a page of reports that are filtered by the specified parameters. For more information, see [Viewing results](/docs/security-compliance?topic=security-compliance-results).
Note: If the `--all-pages` option is not set, the command will only retrieve a single page of the collection.

```sh
ibmcloud security-compliance report list [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID] [--attachment-id ATTACHMENT-ID] [--group-id GROUP-ID] [--profile-id PROFILE-ID] [--type TYPE] [--start START] [--limit LIMIT] [--sort SORT]
```


#### Command options
{: #security-compliance-reports-list-cli-options}

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--attachment-id` (string)
:   The ID of the attachment.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--group-id` (string)
:   The report group ID.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--profile-id` (string)
:   The ID of the profile.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--type` (string)
:   The type of the scan.

    Allowable values are: `ondemand`, `scheduled`.

`--start` (string)
:   The indication of what resource to start the page on.

    The maximum length is `512` characters. The minimum length is `0` characters. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--limit` (int64)
:   The indication of many resources to return, unless the response is  the last page of resources.

    The default value is `50`. The maximum value is `100`. The minimum value is `0`.

`--sort` (string)
:   This field sorts results by using a valid sort field. To learn more, see [Sorting](/docs/api-handbook?topic=api-handbook-sorting).

    The maximum length is `32` characters. The minimum length is `1` character. The value must match regular expression `/^[\\-]?[a-z0-9_]+$/`.

`--all-pages` (bool)
:   Invoke multiple requests to display all pages of the collection for reports-list.

#### Example
{: #security-compliance-reports-list-examples}

```sh
ibmcloud security-compliance report list \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --attachment-id=exampleString \
    --group-id=exampleString \
    --profile-id=exampleString \
    --type=scheduled \
    --start=exampleString \
    --limit=10 \
    --sort=profile_name
```
{: pre}

### `ibmcloud security-compliance report get`
{: #security-compliance-cli-reports-get-command}

Retrieve a report by specifying its ID. For more information, see [Viewing results](/docs/security-compliance?topic=security-compliance-results).

```sh
ibmcloud security-compliance report get --report-id REPORT-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-reports-get-cli-options}

`--report-id` (string)
:   The ID of the scan that is associated with a report. Required.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-reports-get-examples}

```sh
ibmcloud security-compliance report get \
    --report-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance report summary`
{: #security-compliance-cli-reports-get-summary-command}

Retrieve the complete summarized information for a report. For more information, see [Viewing results](/docs/security-compliance?topic=security-compliance-results).

```sh
ibmcloud security-compliance report summary --report-id REPORT-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-reports-get-summary-cli-options}

`--report-id` (string)
:   The ID of the scan that is associated with a report. Required.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-reports-get-summary-examples}

```sh
ibmcloud security-compliance report summary \
    --report-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance report controls`
{: #security-compliance-cli-reports-get-controls-command}

Retrieve a sorted and filtered list of controls for the specified report. For more information, see [Viewing results](/docs/security-compliance?topic=security-compliance-results).

```sh
ibmcloud security-compliance report controls --report-id REPORT-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID] [--control-id CONTROL-ID] [--control-name CONTROL-NAME] [--control-description CONTROL-DESCRIPTION] [--control-category CONTROL-CATEGORY] [--status STATUS] [--sort SORT]
```


#### Command options
{: #security-compliance-reports-get-controls-cli-options}

`--report-id` (string)
:   The ID of the scan that is associated with a report. Required.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--control-id` (string)
:   The ID of the control.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--control-name` (string)
:   The name of the control.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--control-description` (string)
:   The description of the control.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\s]+$/`.

`--control-category` (string)
:   A control category value.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--status` (string)
:   The compliance status value.

    Allowable values are: `compliant`, `not_compliant`, `unable_to_perform`, `user_evaluation_required`.

`--sort` (string)
:   This field sorts controls by using a valid sort field. To learn more, see [Sorting](/docs/api-handbook?topic=api-handbook-sorting).

    Allowable values are: `control_name`, `control_category`, `status`.

#### Example
{: #security-compliance-reports-get-controls-examples}

```sh
ibmcloud security-compliance report controls \
    --report-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --control-id=exampleString \
    --control-name=exampleString \
    --control-description=exampleString \
    --control-category=exampleString \
    --status=compliant \
    --sort=control_name
```
{: pre}

### `ibmcloud security-compliance report rule`
{: #security-compliance-cli-reports-get-rule-command}

Retrieve the rule by specifying the report ID and rule ID. For more information, see [Viewing results](/docs/security-compliance?topic=security-compliance-results).

```sh
ibmcloud security-compliance report get-rule --report-id REPORT-ID --rule-id RULE-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-reports-get-rule-cli-options}

`--report-id` (string)
:   The ID of the scan that is associated with a report. Required.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--rule-id` (string)
:   The ID of a rule in a report. Required.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-reports-get-rule-examples}

```sh
ibmcloud security-compliance report rule \
    --report-id=exampleString \
    --rule-id=rule-8d444f8c-fd1d-48de-bcaa-f43732568761 \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance report evaluations`
{: #security-compliance-cli-reports-list-evaluations-command}

Get a paginated list of evaluations for the specified report. For more information, see [Viewing results](/docs/security-compliance?topic=security-compliance-results).
Note: If the `--all-pages` option is not set, the command will only retrieve a single page of the collection.

```sh
ibmcloud security-compliance report evaluations --report-id REPORT-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID] [--assessment-id ASSESSMENT-ID] [--component-id COMPONENT-ID] [--target-id TARGET-ID] [--target-name TARGET-NAME] [--status STATUS] [--start START] [--limit LIMIT]
```


#### Command options
{: #security-compliance-reports-list-evaluations-cli-options}

`--report-id` (string)
:   The ID of the scan that is associated with a report. Required.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--assessment-id` (string)
:   The ID of the assessment.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--component-id` (string)
:   The ID of component.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9.\\-]+$/`.

`--target-id` (string)
:   The ID of the evaluation target.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--target-name` (string)
:   The name of the evaluation target.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--status` (string)
:   The evaluation status value.

    Allowable values are: `pass`, `failure`, `error`, `skipped`.

`--start` (string)
:   The indication of what resource to start the page on.

    The maximum length is `512` characters. The minimum length is `0` characters. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--limit` (int64)
:   The indication of many resources to return, unless the response is  the last page of resources.

    The default value is `50`. The maximum value is `100`. The minimum value is `0`.

`--all-pages` (bool)
:   Invoke multiple requests to display all pages of the collection for reports-list-evaluations.

#### Example
{: #security-compliance-reports-list-evaluations-examples}

```sh
ibmcloud security-compliance report evaluations \
    --report-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --assessment-id=exampleString \
    --component-id=exampleString \
    --target-id=exampleString \
    --target-name=exampleString \
    --status=failure \
    --start=exampleString \
    --limit=10
```
{: pre}

### `ibmcloud security-compliance report resources`
{: #security-compliance-cli-reports-list-resources-command}

Get a paginated list of resources for the specified report. For more information, see [Viewing results](/docs/security-compliance?topic=security-compliance-results).
Note: If the `--all-pages` option is not set, the command will only retrieve a single page of the collection.

```sh
ibmcloud security-compliance report resources --report-id REPORT-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID] [--id ID] [--resource-name RESOURCE-NAME] [--account-id ACCOUNT-ID] [--component-id COMPONENT-ID] [--status STATUS] [--sort SORT] [--start START] [--limit LIMIT]
```


#### Command options
{: #security-compliance-reports-list-resources-cli-options}

`--report-id` (string)
:   The ID of the scan that is associated with a report. Required.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--id` (string)
:   The ID of the resource.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--resource-name` (string)
:   The name of the resource.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--account-id` (string)
:   The ID of the account owning a resource.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--component-id` (string)
:   The ID of component.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9.\\-]+$/`.

`--status` (string)
:   The compliance status value.

    Allowable values are: `compliant`, `not_compliant`, `unable_to_perform`, `user_evaluation_required`.

`--sort` (string)
:   This field sorts resources by using a valid sort field. To learn more, see [Sorting](/docs/api-handbook?topic=api-handbook-sorting).

    Allowable values are: `account_id`, `component_id`, `resource_name`, `status`.

`--start` (string)
:   The indication of what resource to start the page on.

    The maximum length is `512` characters. The minimum length is `0` characters. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--limit` (int64)
:   The indication of many resources to return, unless the response is  the last page of resources.

    The default value is `50`. The maximum value is `100`. The minimum value is `0`.

`--all-pages` (bool)
:   Invoke multiple requests to display all pages of the collection for reports-list-resources.

#### Example
{: #security-compliance-reports-list-resources-examples}

```sh
ibmcloud security-compliance report resources \
    --report-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --id=exampleString \
    --resource-name=exampleString \
    --account-id=exampleString \
    --component-id=exampleString \
    --status=compliant \
    --sort=account_id \
    --start=exampleString \
    --limit=10
```
{: pre}

### `ibmcloud security-compliance report tags`
{: #security-compliance-cli-reports-get-tags-command}

Retrieve a list of tags for the specified report. For more information, see [Viewing results](/docs/security-compliance?topic=security-compliance-results).

```sh
ibmcloud security-compliance report tags --report-id REPORT-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID]
```


#### Command options
{: #security-compliance-reports-get-tags-cli-options}

`--report-id` (string)
:   The ID of the scan that is associated with a report. Required.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

#### Example
{: #security-compliance-reports-get-tags-examples}

```sh
ibmcloud security-compliance report tags \
    --report-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString
```
{: pre}

### `ibmcloud security-compliance report violation-drift`
{: #security-compliance-cli-reports-get-violation-drift-command}

Get a list of report violation data points for the specified report and time frame. For more information, see [Viewing results](/docs/security-compliance?topic=security-compliance-results).

```sh
ibmcloud security-compliance report violation-drift --report-id REPORT-ID [--x-correlation-id X-CORRELATION-ID] [--x-request-id X-REQUEST-ID] [--scan-time-duration SCAN-TIME-DURATION]
```


#### Command options
{: #security-compliance-reports-get-violation-drift-cli-options}

`--report-id` (string)
:   The ID of the scan that is associated with a report. Required.

    The maximum length is `128` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9\\-]+$/`.

`--x-correlation-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header for the corresponding response. The same value is used for downstream requests and retries of those requests. If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--x-request-id` (string)
:   The supplied or generated value of this header is logged for a request and repeated in a response header  for the corresponding response.  The same value is not used for downstream requests and retries of those requests.  If a value of this header is not supplied in a request, the service generates a random (version 4) UUID.

    The maximum length is `1024` characters. The minimum length is `1` character. The value must match regular expression `/^[a-zA-Z0-9 ,\\-_]+$/`.

`--scan-time-duration` (int64)
:   The duration of the `scan_time` timestamp in number of days.

    The default value is `0`. The maximum value is `366`. The minimum value is `0`.

#### Example
{: #security-compliance-reports-get-violation-drift-examples}

```sh
ibmcloud security-compliance report violation-drift \
    --report-id=exampleString \
    --x-correlation-id=exampleString \
    --x-request-id=exampleString \
    --scan-time-duration=0
```
{: pre}

## Schema examples
{: #security-compliance-schema-examples}

The following schema examples represent the data that you need to specify for a command option. These examples model the data structure and include placeholder values for the expected value type. When you run a command, replace these values with the values that apply to your environment as appropriate.

### AttachmentParameterPrototype[]
{: #cli-attachment-parameter-prototype-example-schema}

The following example shows the format of the AttachmentParameterPrototype[] object.

```json

[ {
  "assessment_type" : "Automated",
  "assessment_id" : "rule-a637949b-7e51-46c4-afd4-b96619001bf1",
  "parameter_name" : "session_invalidation_in_seconds",
  "parameter_value" : "120",
  "parameter_display_name" : "Sign out due to inactivity in seconds",
  "parameter_type" : "numeric"
} ]
```
{: codeblock}

### AttachmentsNotificationsPrototype
{: #cli-attachments-notifications-prototype-example-schema}

The following example shows the format of the AttachmentsNotificationsPrototype object.

```json

{
  "enabled" : false,
  "controls" : {
    "threshold_limit" : 15,
    "failed_control_ids" : [ ]
  }
}
```
{: codeblock}

### AttachmentsPrototype[]
{: #cli-attachments-prototype-example-schema}

The following example shows the format of the AttachmentsPrototype[] object.

```json

[ {
  "id" : "130003ea8bfa43c5aacea07a86da3000",
  "name" : "account-0d8c3805dfea40aa8ad02265a18eb12b",
  "description" : "Test description",
  "scope" : [ {
    "environment" : "ibm-cloud",
    "properties" : [ {
      "name" : "scope_id",
      "value" : "cg3335893hh1428692d6747cf300yeb5"
    } ]
  } ],
  "status" : "enabled",
  "schedule" : "every_30_days",
  "notifications" : {
    "enabled" : false,
    "controls" : {
      "threshold_limit" : 15,
      "failed_control_ids" : [ ]
    }
  },
  "attachment_parameters" : [ {
    "assessment_type" : "Automated",
    "assessment_id" : "rule-a637949b-7e51-46c4-afd4-b96619001bf1",
    "parameter_name" : "session_invalidation_in_seconds",
    "parameter_value" : "120",
    "parameter_display_name" : "Sign out due to inactivity in seconds",
    "parameter_type" : "numeric"
  } ]
} ]
```
{: codeblock}

### ControlsInControlLib[]
{: #cli-controls-in-control-lib-example-schema}

The following example shows the format of the ControlsInControlLib[] object.

```json

[ {
  "control_name" : "SC-7",
  "control_id" : "1fa45e17-9322-4e6c-bbd6-1c51db08e790",
  "control_description" : "Boundary Protection",
  "control_category" : "System and Communications Protection",
  "control_parent" : "exampleString",
  "control_tags" : [ "1fa45e17-9322-4e6c-bbd6-1c51db08e790" ],
  "control_specifications" : [ {
    "control_specification_id" : "5c7d6f88-a92f-4734-9b49-bd22b0900184",
    "responsibility" : "user",
    "component_id" : "iam-identity",
    "component_name" : "exampleString",
    "environment" : "ibm-cloud",
    "control_specification_description" : "IBM cloud",
    "assessments_count" : 38,
    "assessments" : [ {
      "assessment_id" : "rule-a637949b-7e51-46c4-afd4-b96619001bf1",
      "assessment_method" : "ibm-cloud-rule",
      "assessment_type" : "automated",
      "assessment_description" : "Check that there is an Activity Tracker event route defined to collect global events generated by IBM Cloud services",
      "parameter_count" : 38,
      "parameters" : [ {
        "parameter_name" : "session_invalidation_in_seconds",
        "parameter_display_name" : "Sign out due to inactivity in seconds",
        "parameter_type" : "numeric",
        "parameter_value" : "public"
      } ]
    } ]
  } ],
  "control_docs" : {
    "control_docs_id" : "sc-7",
    "control_docs_type" : "ibm-cloud"
  },
  "control_requirement" : true,
  "status" : "enabled"
} ]
```
{: codeblock}

### DefaultParametersPrototype[]
{: #cli-default-parameters-prototype-example-schema}

The following example shows the format of the DefaultParametersPrototype[] object.

```json

[ {
  "assessment_type" : "Automated",
  "assessment_id" : "rule-a637949b-7e51-46c4-afd4-b96619001bf1",
  "parameter_name" : "session_invalidation_in_seconds",
  "parameter_default_value" : "120",
  "parameter_display_name" : "Sign out due to inactivity in seconds",
  "parameter_type" : "numeric"
} ]
```
{: codeblock}

### EventNotifications
{: #cli-event-notifications-example-schema}

The following example shows the format of the EventNotifications object.

```json

{
  "instance_crn" : "crn:v1:staging:public:event-notifications:us-south:a/ff88f007f9ff4622aac4fbc0eda36255:7199ae60-a214-4dd8-9bf7-ce571de49d01::",
  "updated_on" : "2019-01-01T12:00:00.000Z",
  "source_id" : "crn:v1:staging:public:event-notifications:us-south:a/ff88f007f9ff4622aac4fbc0eda36255:b8b07245-0bbe-4478-b11c-0dce523105fd::",
  "source_description" : "This source is used for integration with IBM Cloud Security and Compliance Center.",
  "source_name" : "compliance"
}
```
{: codeblock}

### Import
{: #cli-import-example-schema}

The following example shows the format of the Import object.

```json

{
  "parameters" : [ {
    "name" : "hard_quota",
    "display_name" : "The Cloud Object Storage bucket quota.",
    "description" : "The maximum bytes that are allocated to the Cloud Object Storage bucket.",
    "type" : "numeric"
  } ]
}
```
{: codeblock}

### LastScan
{: #cli-last-scan-example-schema}

The following example shows the format of the LastScan object.

```json

{
  "id" : "e8a39d25-0051-4328-8462-988ad321f49a",
  "status" : "in_progress",
  "time" : "2019-01-01T12:00:00.000Z"
}
```
{: codeblock}

### MultiCloudScope[]
{: #cli-multi-cloud-scope-example-schema}

The following example shows the format of the MultiCloudScope[] object.

```json

[ {
  "environment" : "ibm-cloud",
  "properties" : [ {
    "name" : "scope_id",
    "value" : "cg3335893hh1428692d6747cf300yeb5"
  } ]
} ]
```
{: codeblock}

### ObjectStorage
{: #cli-object-storage-example-schema}

The following example shows the format of the ObjectStorage object.

```json

{
  "instance_crn" : "crn:v1:staging:public:cloud-object-storage:global:a/ff88f007f9ff4622aac4fbc0eda36255:7199ae60-a214-4dd8-9bf7-ce571de49d01::",
  "bucket" : "px-scan-results",
  "bucket_location" : "us-south",
  "bucket_endpoint" : "exampleString",
  "updated_on" : "2019-01-01T12:00:00.000Z"
}
```
{: codeblock}

### ProfileControlsPrototype[]
{: #cli-profile-controls-prototype-example-schema}

The following example shows the format of the ProfileControlsPrototype[] object.

```json

[ {
  "control_library_id" : "e98a56ff-dc24-41d4-9875-1e188e2da6cd",
  "control_id" : "1fa45e17-9322-4e6c-bbd6-1c51db08e790"
} ]
```
{: codeblock}

### RequiredConfig
{: #cli-required-config-example-schema}

The following example shows the format of the RequiredConfig object.

```json

{
  "description" : "The Cloud Object Storage rule.",
  "and" : [ {
    "description" : "exampleString",
    "property" : "hard_quota",
    "operator" : "num_equals",
    "value" : "${hard_quota}"
  } ]
}
```
{: codeblock}

### Target
{: #cli-target-example-schema}

The following example shows the format of the Target object.

```json

{
  "service_name" : "cloud-object-storage",
  "service_display_name" : "exampleString",
  "resource_kind" : "bucket",
  "additional_target_attributes" : [ {
    "name" : "location",
    "operator" : "string_equals",
    "value" : "us-east"
  } ]
}
```
{: codeblock}


