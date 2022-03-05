---

copyright:
  years: 2020, 2022
lastupdated: "2022-03-05"

keywords: credentials, security and compliance, collector access, collector communication, resource scan, configuration scanning, credentials stored

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

# Managing credentials
{: #credentials}

When you work with the {{site.data.keyword.compliance_long}}, you must provide credentials to be used by a collector to gather information about your resources and initiate remediation. To learn more about what types of credentials you must provide and what level of access do your credentials need to have see [what are the required permissions](/docs/security-compliance?topic=security-compliance-permissions)? 
{: shortdesc}

## Before you begin
{: #before-credentials}

Before you get started, be sure that you have the required level of access to view and manage credentials. To manage credentials, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management). You must also have access to the credentials that are needed to access your resource configurations.


## Creating a credential in the UI
{: #create-credentials-ui}
{: ui}

To create a new credential, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Credentials**.
3. Click **Create**.
4. Give your credential a meaningful name and a description.
5. Select a purpose for your credential. Options include **Discovery/Collection**, **Remediation**, or **Both**.  
6. Click **Next**.
7. Choose a **Credential type** from the following options:

   * AWS Cloud
   * Azure Cloud
   * GCP Cloud
   * IBM Cloud
   * Database
   * Username - password
   * Username - PEM
   * Windows authentication

   The type of credential that you create depends on the type of resources that you want to scan.
   {: note}

8. Add the access information. Depending on the type of credential that you selected in step 4, the options on the page change. To learn more about what information you need to input depending on the type of credential that you selected, see [what are the required permissions?](/docs/security-compliance?topic=security-compliance-permissions)

   The level of access that your credentials need depends upon the actions that you want the {{site.data.keyword.compliance_short}} to take. If you want to run scans only on your resources, you must provide credentials that provide the collector `read` access to your resources. [Learn more](/docs/security-compliance?topic=security-compliance-permissions#understand-credentials).
   {: note}

9. If a passphrase is configured, enter the passphrase. 
10. Verify your information and click **Create**. The credential is added to a list of available credentials. 

To edit or delete existing credentials, click the **Actions** icon ![Actions icon](../icons/actions-icon-vertical.svg) and click **Edit** or **Delete**.
{: tip}


## Creating a credential with the API
{: #create-credentials-api}
{: api}

You can create a new credential programmatically by using the {{site.data.keyword.compliance_short}} API. 

```sh
curl POST 'https://{region}.compliance.cloud.ibm.com/posture/v2/credentials?account_id={account_id}' 
  -H 'Authorization: {IAM_token}' 
  -H 'Content-Type: application/json' 
  -d '{
      "name": "testcredential",
      "description": "testcredential",
      "purpose": "discovery_fact_collection_remediation",
      "enabled": true,
      "group": {},
      "type": "ibm_cloud",
      "display_fields": {
        "ibm_api_key": "ibm_api_key"
        }
      }
```
{: codeblock}

| Variable   | Description |
|:-----------|:------------|
| `region` | The region in which you want to create a credential. Be sure that your region matches the location that is configured for {{site.data.keyword.compliance_short}}. You can view your account settings by making a POST request to the [Admin API](/apidocs/security-compliance-admin#getsettings). For example, `eu`.|
| `account_id` | The ID of the account that manages the {{site.data.keyword.compliance_short}}. If you are the owner of the managing account, can find this ID in the {{site.data.keyword.cloud_notm}} console by clicking **Manage > Account > Account Settings**.| 
| `IAM_token` | For help with creating your IAM token, see [Generating an {{site.data.keyword.cloud_notm}} IAM token by using an API key](/docs/account?topic=account-iamtoken_from_apikey).|
| `name` | The name that you want your credential to have. It must be unique to the {{site.data.keyword.compliance_short}} instance that you're working with.|
| `description`| Optional: A detailed description of how you intend to use your credential.|
|  `purpose` | The purpose for which the credential is created. |
| `enabled` | The status of the credential is enabled or disabled. | 
| `group` | The details of the credential group. | 
| `type` | The type of credential. | 
| `display_fields` | The details of the credential. The details change as the selected credential type varies. |
{: caption="Table 1. Understanding the variables used to create a credential with the API" caption-side="top"}

For more information about the associated status codes and the query and form request parameters, see [create a credential](/apidocs/security-compliance/posture-v2.0#create-credential). 

A successful `POST /posture/v2/credentials` response returns the unique ID of your credential, along with other metadata. If your credential was successfully created, your response might look similar to the following code snippet. 

```json
{
    "enabled": true,
    "id": "00000",
    "type": "IBM_CLOUD",
    "name": "testcredential",
    "description": "testcredential",
    "display_fields": {
        "ibm_api_key": "**********"
    },
    "created_by": "iam-ServiceId-9c000000-f00d-000e-0b02-ed6b40000",
    "created_at": "2022-02-10T16:13:27Z",
    "updated_by": "iam-ServiceId-9c000000-f00d-000e-0b02-ed6b4000",
    "updated_at": "2022-02-10T16:13:27Z",
    "group": null,
    "purpose": "DISCOVERY_COLLECTION_REMEDIATION"
}
```
{: screen}
