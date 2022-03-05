---

copyright:
  years: 2017, 2022
lastupdated: "2022-03-05"

keywords: Centralized security, security management, alerts, security risk, insights, threat detection, alerts, callback URL, compliance, standards, roles, notification channel, verify payload, public key

subcollection: security-compliance

---

{:codeblock: .codeblock}
{:screen: .screen}
{:download: .download}
{:external: target="_blank" .external}
{:faq: data-hd-content-type='faq'}
{:gif: data-image-type='gif'}
{:important: .important}
{:note: .note}
{:pre: .pre}
{:tip: .tip}
{:preview: .preview}
{:deprecated: .deprecated}
{:beta: .beta}
{:term: .term}
{:shortdesc: .shortdesc}
{:script: data-hd-video='script'}
{:support: data-reuse='support'}
{:table: .aria-labeledby="caption"}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:help: data-hd-content-type='help'}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tsSymptoms: .tsSymptoms}
{:java: .ph data-hd-programlang='java'}
{:javascript: .ph data-hd-programlang='javascript'}
{:swift: .ph data-hd-programlang='swift'}
{:curl: .ph data-hd-programlang='curl'}
{:video: .video}
{:step: data-tutorial-type='step'}
{:tutorial: data-hd-content-type='tutorial'}
{:ui: .ph data-hd-interface='ui'}
{:cli: .ph data-hd-interface='cli'}
{:api: .ph data-hd-interface='api'}
{:release-note: data-hd-content-type='release-note'}

# Configuring alerts
{: #notifications}


As of 13 December 2021, alerts in the {{site.data.keyword.compliance_full}} are deprecated in favor of [{{site.data.keyword.en_short}}](/docs/security-compliance?topic=security-compliance-event-notifications). The ability to create alerts within the {{site.data.keyword.compliance_short}} is no longer supported. You can continue to view, enable, disable, or delete your existing alerts until 15 March 2022. After this date, any existing alerts will be deleted, and the feature will be removed from the UI.
{: deprecated}


By configuring a {{site.data.keyword.compliance_short}} notification channel, you can be alerted to any reported vulnerabilities as soon as the report is available. With a fast alert time, you're able to immediately start an investigation into any reported issue and fix the vulnerability before it becomes a larger problem in your application.
{: shortdesc}

Notifications are available for Security Insights only.
{: note}

With a process in place to handle alerts you can ensure that you're in compliance and prepared if or when an issue occurs. For example, some compliance standards require that issues must be responded to and closed within 24 hours, and the response is audited. With Security Advisor alerts in place, you are notified and can start resolving issues immediately.


## Before you begin
{: #alerts-before}

Before you get started, be sure that you have the required level of access to configure alerts. To configure alerts, you need the [**Manager** service role or higher for {{site.data.keyword.security-advisor_short}}](/docs/security-compliance?topic=security-compliance-access-management).

You can use [Cloud Functions](/docs/openwhisk?topic=openwhisk-getting-started) to forward your alerts to either a Slack message or to your email. For more information, check out [How to Get IBM Cloud Security Advisor Alerts via Slack or Email](https://www.ibm.com/cloud/blog/ibm-cloud-security-advisor-alerts-via-slack-or-email){: external}.
{: tip}


## Configuring alerts with the GUI
{: #channel-create-gui}
{: ui}

To start receiving alerts for findings, you can configure an alert channel by using the GUI. Alerts are configurable by severity and by source of the findings.

You can create up to 15 channels.
{: note}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Alerts**.
3. Click **Create**.
4. Provide a name and meaningful description for your channel.
5. To configure the threshold for alerts, select the severity of the notifications that you want to be alerted for. Severity choices include *critical*, *high*, *medium*, and *low*. Optionally, select the source of the findings that you want to receive alerts for. Check out the following table for more information about the available sources.

   | Source | Description |
   | --------- | ----------- |
   | Built-in Insights | You can continuously monitor and analyze your {{site.data.keyword.cloud_notm}} resources and apps for risks that can impact your environment. Potential sources include: [Vulnerability Advisor](/docs/security-compliance?topic=security-compliance-setup-services#setup-images), [Certificate Manager](/docs/security-compliance?topic=security-compliance-setup-services#setup-certificates), [Network Insights](/docs/security-compliance?topic=security-compliance-setup-network), and [Activity Insights](/docs/security-compliance?topic=security-compliance-setup-activity). |
   | Business partners | You can manage all your security notifications in one place by connecting your instance of one of IBM business partners to the {{site.data.keyword.compliance_short}}. Current business partners include: [Caveonix](/docs/security-compliance?topic=security-compliance-setup-caveonix), [NeuVector](/docs/security-compliance?topic=security-compliance-setup-neuvector), and [Twistlock](/docs/security-compliance?topic=security-compliance-setup-twistlock). |
   | Custom | You can connect a custom or proprietary security tool that your organization already works with to configure and manage alerts in one place. [Learn more](/docs/security-compliance?topic=security-compliance-setup_custom). |
   {: caption="Table 1. Alert sources" caption-side="top"}

   As an example, if you wanted to configure alerts for your [network flow logs](/docs/vpc?topic=vpc-flow-logs), you would select Network Insights as your source and then create a threshold for the alerts that you receive by selecting a severity.
   {: tip}

6. Click **Next**.
7. Enter the callback endpoint where you want to receive the alerts.

   Your callback URL endpoint must [1] Use the HTTPS protocol. [2] Not require HTTP headers - including authorization headers. [3] Return a `200 OK` status code to indicate that the alert is successfully delivered.

8. Click **Create**. Your channel is listed in the **Alerts** table.
9. Verify that your channel is configured correctly by selecting **Test connection** in the overflow menu. A test alert is sent to your endpoint. Be sure to remove any alerts that are sent by *Security Advisor Notification Test* after you've completed your testing.

Next, [verify that the payload](#verify-api) is sent directly from the {{site.data.keyword.compliance_short}}.



## Configuring alerts with the API
{: #channel-create-api}
{: api}

To start receiving alerts for findings, you can configure an alert channel by using the GUI. Alerts are configurable by severity and by source of the findings.

You can create up to 15 channels.
{: note}

1. Obtain an IAM bearer token by using the following steps. For more information, see the [IAM documentation](/docs/account?topic=account-access-getstarted).

   1. In the {{site.data.keyword.cloud_notm}} dashboard, click **Manage > Access (IAM)**.
   2. Select **{{site.data.keyword.cloud_notm}} API keys**.
   3. Click **Create an {{site.data.keyword.cloud_notm}} API key**
   4. Give your key a name and describe it. Click **Create**. A screen opens with your key.
   5. Click **Copy** or **Download** your key. When you close the screen, you can no longer access the key.
   6. Make the following cURL request with the API key that you created.

      ```sh
      curl -k -X POST \
      --header "Content-Type: application/x-www-form-urlencoded" \
      --header "Accept: application/json" \
      --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
      --data-urlencode "apikey={apikey}" \
      "https://iam.cloud.ibm.com/identity/token"
      ```
      {: codeblock}

2. Run the following cURL command.

   ```sh
   curl -x POST "https://{region}.secadvisor.cloud.ibm.com/alerts/v1/{account_id}/alerts/channels"
   -H "accept: application/json"
   -H "Authorization: Bearer <IAM_Token>"
   -d {
      "name": "test-notification-channel",
      "description": "test-notification",
      "type": "Webhook",
      "endpoint": "<Endpoint>"
      "enabled": true
      "severity": ["low"]
      "alertSource": [
      {
         "provider_name": "ALL",
         "finding_types": ["ALL"]
      }
      ]
   }
   ```
   {: code}

   | Variable | Description | 
   |:-----------------|:-----------------|
   | Name | The name of the channel. |
   | Description | Describe what the channel is used for. For example: *This channel sends high severity alerts as they happen.* |
   | Type | Current options include `Webhook`. |
   | Channel endpoint | The location where you want to be notified. Examples include a valid callback URL. |
   | Severity | The level of severity for the notification received. Options include: `low`, `medium`, `high` and `critical`. By default, `medium`, `high` and `critical` are turned on. |
   | Provider | The source and type of the finding that is received. `provider_name` is the ID of any provider in the account. If you're not sure which providers are available in your account, you can query the providers API: `/findings/v1/{accountId}/providers`. `finding_types` is the list of valid finding types for the provider name. If you're not sure which notes are available for each provider in your account, you can query the notes API: `/findings/v1/{account_id}/providers/{provider_id}/notes`. The `ALL` option can be specified for the `finding_types` which means that all notes for that provider are selected. There are 4 built-in providers in addition to custom alert source providers. For more information about the 4 providers and the supported finding types for each, review the following table. |
   {: class="simple-tab-table"}
   {: caption="Table 2. Configuring alerts with the API" caption-side="top"}
   {: #api-variables}
   {: tab-title="API variables"}
   {: tab-group="notifications"}

   | Provider name | Supported finding types | 
   |:-----------------|:-----------------|
   | `VA` | `image_with_vulnerabilities`, `image_with_config_issues` |
   | `NA` | `anonym_server`, `malware_server`, `bot_server`, `miner_server`, `server_suspected_ratio`, `server_response`, `data_extrusion`, `server_weaponized_total` |
   | `ATA` | `appid`, `cos`, `iks`, `iam`, `kms`, `cert`, `account`, `app` |
   | `CERT` | `expired_cert`, `expiring_1day_cert`, `expiring_10day_cert`, `expiring_30day_cert`, `expiring_60day_cert`, `expiring_90day_cert` |
   | ALL |  If `ALL` is specified as the `provider_name`, then a specific value can't be provided for `finding_types`. In this case, you can omit `finding_types` or specify `ALL`. |
   {: class="simple-tab-table"}
   {: caption="Table 2. Built-in providers and supported finding types" caption-side="top"}
   {: #finding-types}
   {: tab-title="Finding types"}
   {: tab-group="notifications"}

   Example response:

   ```json
   {
      "channel_id": "323fc870-78992-8ffa-97572ffe0205",
      "statusCode": 200
   }
   ```
   {: screen}

3. Test your connection.

   ```sh
   curl -X GET "https://{region}.secadvisor.cloud.ibm.com/alerts/v1/{ACCOUNT_ID}/test/notification/channel/{CHANNEL_ID}" -H "accept: application/json" -H "Authorization: {IAM_BEARER_TOKEN}"
   ```
   {: codeblock}

To edit your channel configuration, you can make an API call to the [`/update endpoint`](/apidocs/security-compliance/si-notifications?code=python#updatenotificationchannel){: external}.
{: tip}


## Verifying the payload with the UI
{: #verify-ui}
{: ui}

When a notification is sent, you can use a public key to decrypt and verify the payload that is received. By using a public key, you can ensure that the information in the payload is not tampered with in any way.

This action can be done through the API only. To see the steps, switch to the **API** instructions.
{: note}

## Verifying the payload with the API
{: #verify-api}
{: api}


When a notification is sent, you can use a public key to decrypt and verify the payload that is received. By using a public key, you can ensure that the information in the payload is not tampered with in any way.

Example payload:

```json
{
   "findings":[
      {
         "severity":"LOW",
         "issuer":"IBM Cloud Security Advisor",
         "issuer-url":"https://cloud.ibm.com/security-advisor#/findings?id=291266ca760e037c079edd4523242386/providers/test-provider/occurrences/ce90dc1-1-1-7",
         "id":"291266ca760e037c079edd4523242386/providers/test-provider/occurrences/ce90dc1-1-1-7",
         "payload-type":"findings",
         "payload-link":"https://us-south.secadvisor.cloud.ibm.com/findings",
         "provider":"cert-mgr",
         "payload":{
            "author":{
               "account_id":"291266ca760e037c079edd4523242386",
               "email":"user@test.com",
               "id":"IBMid-3100013FP0",
               "kind":"user"
            },
            "context":{
               "account_id":"291266ca760e037c079edd4523242386",
               "region":"US-South",
               "resource_crn":"cert-mgr",
               "service_crn":"cert-mgr-2"
            },
            "create_time":"2019-05-08T02:35:40.338757Z",
            "create_timestamp":1557282940339,
            "finding":{
               "certainty":"HIGH",
               "next_steps":[
                  {
                     "title":"Find your certificate."
                  },
                  {
                     "title":"Renew certificate with Certificate Authority."
                  },
                  {
                     "title":"Upload renewed certificate to Certificate Manager."
                  },
                  {
                     "title":"Redeploy certificate to SSL termination point."
                  },
                  {
                     "title":"Delete old certificate from Certificate Manager."
                  }
               ],
               "severity":"LOW"
            },
            "id":"ce90dc11-1",
            "insertion_timestamp":1557282940339,
            "kind":"FINDING",
            "long_description":"Certificate expiring in 90 days",
            "name":"291266ca760e037c079edd4523242386/providers/test-provider/occurrences/ce90dc1-1-1-7",
            "note_name":"29104aa4ec94471284be7d33bf1b1391/providers/security-advisor/notes/certmgr-expiring_90day_cert",
            "provider_id":"test-provider",
            "provider_name":"291266ca760e037c079edd4523242386/providers/test-provider",
            "reported_by":{
               "id":"certificate-manager",
               "title":"IBM Cloud Certificate Manager",
               "url":"https://cloud.ibm.com/docs/certificate-manager?topic=certificate-manager-gettingstarted#gettingstarted"
            },
            "short_description":"Certificate expiring in 90 days",
            "update_time":"2019-05-08T02:35:40.338792Z",
            "update_timestamp":1557282940339,
            "update_week_date":"2019-W19-3"
         }
      }
   ]
}
```
{: screen}

In the previous example, `payload-link` refers to the Security Advisor findings API endpoint where a user can get more information about the findings that they can use to take appropriate action.
{: note}

### Obtaining the public key with the GUI
{: #payload-gui}
{: ui}

You can obtain the payload by using the GUI.

1. Navigate to the **alerts channels** tab of the Security Advisor dashboard.
2. Click **Download key**.

### Obtaining the public key with the API
{: #payload-api}
{: api}

You can obtain the public key by using the API.

1. Obtain an IAM bearer token by using the following steps. For more information, see the [IAM documentation](/docs/account?topic=account-access-getstarted).

   1. In the {{site.data.keyword.cloud_notm}} dashboard, click **Manage > Access (IAM)**.
   2. Select **{{site.data.keyword.cloud_notm}} API keys**.
   3. Click **Create an {{site.data.keyword.cloud_notm}} API key**
   4. Give your key a name and describe it. Click **Create**. A screen opens with your key.
   5. Click **Copy** or **Download** your key. When you close the screen, you can no longer access the key.
   6. Make the following cURL request with the API key that you created.

      ```sh
      curl -k -X POST \
      --header "Content-Type: application/x-www-form-urlencoded" \
      --header "Accept: application/json" \
      --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
      --data-urlencode "apikey={apikey}" \
      "https://iam.cloud.ibm.com/identity/token"
      ```
      {: codeblock}

2. Download the public key.

   ```sh
   curl -X GET "https://{region}.secadvisor.cloud.ibm.com/alerts/v1/{Account_ID}/download_public_key" -H "accept: application/json" -H "Authorization: {IAM-token}"
   ```
   {: codeblock}


### Decrypting your public key
{: #channel-decrypt}


Now that you have your public key, you can use [JWT](https://jwt.io/){: external} to decrypt and verify your payload. If you are working with Node.JS, your code snippet would look similar to the following.

```sh
const jwt = require("jsonwebtoken");
var decodedData = {}
try {
    decodedData = jwt.verify(<encrypted_payload_received>, <public_key>, { algorithms: ["RS256"] });
  } catch (err) {
    console.log(`JWT error : ${JSON.stringify(err)}`);
}
```
{: codeblock}




## Deleting a channel with the GUI
{: #channel-delete-gui}
{: ui}

You can delete a channel or group of channels if you no longer need to monitor the information that is sent as an alert.

Want to take a break from receiving alerts but don't want to delete your configuration? No problem, disable your channel configuration instead. Then, when you're ready to use the configuration again, you can flip the switch to enabled and you're ready to go!
{: tip}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Alerts**.
3. Delete the channel or channels.

   If you want to delete a single channel, open the overflow menu in the row of the channel that you want to delete.

   If you want to delete multiple channels at once, check the boxes for the channels that you want to remove.

4. Click **Delete**.
5. Confirm that you want to delete the channel by clicking **Delete** again.


## Deleting a channel with the API
{: #channel-delete-api}
{: api}

You can delete a channel or group of channels if you no longer need to monitor the information that is sent as an alert.

Want to take a break from receiving alerts but don't want to delete your configuration? No problem, disable your channel configuration instead. Then, when you're ready to use the configuration again, you can flip the switch to enabled and you're ready to go!
{: tip}

1. Obtain an IAM bearer token by using the following steps. For more information, see the [IAM documentation](/docs/account?topic=account-access-getstarted).

   1. In the {{site.data.keyword.cloud_notm}} dashboard, click **Manage > Access (IAM)**.
   2. Select **{{site.data.keyword.cloud_notm}} API keys**.
   3. Click **Create an {{site.data.keyword.cloud_notm}} API key**
   4. Give your key a name and describe it. Click **Create**. A screen opens with your key.
   5. Click **Copy** or **Download** your key. When you close the screen, you can no longer access the key.
   6. Make the following cURL request with the API key that you created.

      ```sh
      curl -k -X POST \
      --header "Content-Type: application/x-www-form-urlencoded" \
      --header "Accept: application/json" \
      --data-urlencode "grant_type=urn:ibm:params:oauth:grant-type:apikey" \
      --data-urlencode "apikey={apikey}" \
      "https://iam.cloud.ibm.com/identity/token"
      ```
      {: codeblock}

2. Obtain your channel ID.

   ```sh
   curl -X GET "https://{region}.secadvisor.cloud.ibm.com/alerts/v1/{ACCOUNT_ID}/alerts/channels" -H "accept: application/json" -H "Authorization: {IAM_BEARER_TOKEN}"
   ```
   {: codeblock}

3. Delete the channel.

   ```sh
   curl -X DELETE "https://{region}.secadvisor.cloud.ibm.com/alerts/v1/{ACCOUNT_ID}/alerts/channels/{CHANNEL_ID}" -H "accept: application/json" -H "Authorization: {IAM_BEARER_TOKEN}"
   ```
   {: codeblock}

