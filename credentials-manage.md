---

copyright:
  years: 2021
lastupdated: "2021-09-22"

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
2. In the navigation, click **Configure > Settings > Credentials**.
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

You can create a new credential programmatically by using the {{site.data.keyword.compliance_short}} API. To call this method, you must be assigned one or more IAM access roles that include the following action. Using the UI, you can check your access by going to **Users >** ***Name*** **> Access policies**.

For more information about the associated status codes and the query and form request parameters, see [create a credential](/apidocs/security-compliance/posture#create-credential). 

A successful `POST /posture/v1/credentials` response returns the unique ID of your credential, along with other metadata. If your credential was successfully created, your response might look similar to the following code snippet. 

```bash
{
  "credential_id": "63",
  "credential_name": "cred",
  "created_time": "2021-04-08T10:22:04Z"
}
```
{: screen}
