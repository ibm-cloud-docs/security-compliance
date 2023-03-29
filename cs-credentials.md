---

copyright:
  years: 2020, 2023
lastupdated: "2023-03-29"

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

Credentials are how {{site.data.keyword.compliance_short}} gains access to the resource configurations in your account to evaluate them for compliance. Depending on the environment in which you are working and the types of resources that you want to evaluate, you need to provide different information.

The collector-based architecture is deprecated. For more information, see the [release notes](/docs/security-compliance?topic=security-compliance-releases).
{: deprecated}

If you're working with {{site.data.keyword.cloud_notm}}, you don't need to configure credentials! Check out our new and improved experience to get up and running in just a few steps.
{: tip}

## Before you begin
{: #before-credentials}

Before you get started, be sure that you have the required level of access to view and manage credentials. To manage credentials, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management). You must also have access to the credentials that are needed to access your resource configurations.

## Assigning permissions for your credential
{: #credential-access}

The level of access that {{site.data.keyword.compliance_short}} requires to perform an evaluation differs depending on the resource and environment. In general, credentials must be able to provide `read` or `view` access to your resource configuration. However, if you want {{site.data.keyword.compliance_short}} to initiate remediation, you must provide `write` access. Additionally, if you are scanning an on-premises environment, your credentials must have sufficient privileges to collect operating system-related information and query any other services that run on those machines.

Credentials are stored securely by using encryption and are not visible in clear text at any point during the storage process. For more information about the security of your stored credentials, see [Storing and encrypting data in the {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).

Some {{site.data.keyword.cloud_notm}} services require higher permissions to perform the evaluation.
{: note}

## Adding credentials to {{site.data.keyword.compliance_short}}
{: #create-credentials}

For {{site.data.keyword.compliance_short}} to use the credentials that you create, you must add them to the service. You can add your credentials through the console or by using the API. 

## Adding a credential through the UI
{: #create-credentials-ui}
{: ui}

To add a credential through the console, you can use the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Hybrid cloud configurations > Credentials**.
3. Click **Create**.
4. Give your credential a meaningful name and a description.
5. Select a **Credential type** from the following options:

   * AWS Cloud
   * Azure Cloud
   * GCP Cloud
   * IBM Cloud
   * Database
   * Username - password
   * Username - PEM
   * Windows authentication

6. Select a purpose for your credential. Options include **Discovery/Collection**, **Remediation**, or **Both**.

    If you select IBM Cloud as the credential type, the purpose section is not available. 
    {: note}

7. Click **Next**.

8. Add your credential configuration. Depending on the type of credential that you selected in step 4, the information that is required changes. Use the following table as a guide.

	| Credential type | Required input information |
	|:----------------|:---------------------------|
	| {{site.data.keyword.cloud_notm}} | An {{site.data.keyword.cloud_notm}} API key with a service ID. For help with creating an API key, see [Understanding API keys](/docs/account?topic=account-manapikey). Occasionally, services require [extra permissions](/docs/security-compliance?topic=security-compliance-permissions#additional-permissions). To create an {{site.data.keyword.cloud_notm}} API key without a service ID, be sure that the user who creates the key has the required permissions for all the resources that you want to scan. |
	| Amazon Web Services | Your AWS user credentials, API Access Key ID, and Secret Access Key. Your secret access key is a large binary encoded string. [Learn more](/docs/security-compliance?topic=security-compliance-permissions#amazon-permissions) about the specific permissions that you can enable for AWS. |
	| Microsoft Azure | An Azure client ID (application ID), client secret (authentication key), tenant ID, and subscription ID. Additionally, you must provide the list of Resource Groups that are associated with the Subscription ID that is involved in the scan. [Learn more](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal#get-application-id-and-authentication-key){: external} about how to create your Azure credentials. You can find more information on the specific permissions](/docs/security-compliance?topic=security-compliance-permissions#azure-permissions) you can enable for Azure. |
	| Google Cloud Platform | A Google Cloud Platform service account authentication key. [Find more information](https://cloud.google.com/iam/docs/creating-managing-service-account-keys){: external} about how to create an Authentication Key. [Learn more](/docs/security-compliance?topic=security-compliance-permissions#google-permissions) about the specific permissions that you can enable for Google Cloud Platform. |
	| Database | The name of the database and the username and password that are needed to access it. |
	| Username - password | A username and password combination that is needed to gain access to an on-premises resource. |
	| Username - PEM | A username and password combination and PEM file that is needed to gain access to an on-premises resource. |
	| Windows authentication | A username and password combination. You must also provide the type of authentication that your credential is configured to provide. Options include Basic, Kerberos, and Negotiate. You can also choose whether to use SSL by checking the **Use SSL** box. |
	{: caption="Table 1. Credential types and input information" caption-side="top"}

9. Verify your information and click **Create**. The credential is added to a list of available credentials.

To edit or delete existing credentials, click the **Actions** icon ![Actions icon](../icons/actions-icon-vertical.svg) in the row of the credential that you want to update and select **Edit** or **Delete**.
{: tip}


## Adding a credential by using the API
{: #create-credentials-api}
{: api}

To programmatically add a credential, you can use the {{site.data.keyword.compliance_short}} API.

```sh
curl POST 'https://<region>.compliance.cloud.ibm.com/posture/v2/credentials?account_id=<accountID>' 
  -H 'Authorization: <IAMToken>' 
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
| `accountID` | The ID of the account that manages the {{site.data.keyword.compliance_short}}. If you are the owner of the managing account, you can find this ID in the {{site.data.keyword.cloud_notm}} console by clicking **Manage > Account > Account Settings**.| 
| `IAMToken` | For help with creating your IAM token, see [Generating an {{site.data.keyword.cloud_notm}} IAM token by using an API key](/docs/account?topic=account-iamtoken_from_apikey).|
| `name` | The name that you want your credential to have. It must be unique to the {{site.data.keyword.compliance_short}} instance that you're working with.|
| `description`| Optional: A detailed description of how you intend to use your credential.|
| `purpose` | The purpose for which the credential is created. |
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

