---

copyright:
  years: 2020, 2022
lastupdated: "2022-10-03"

keywords: credentials, security and compliance, collector access, collector communication, resource scan, configuration scanning, credentials storage, aws permissions, azure permissions, google cloud permissions

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

# What are credentials? 
{: #what-are-credentials}

Credentials are used by a collector to gather information about your resource configurations, assess them, and initiate any remediation that is needed. The collector acts as an intermediary between your resources and the {{site.data.keyword.compliance_short}}.
{: shortdesc}

To enable communication between your resources and the collector, you must associate credentials with the collector through the {{site.data.keyword.compliance_short}}. The credentials that you associate with the collector must have `read` or `viewer` access to your resources. Depending on the type of credentials you provide and the environment where your resources are located, you can set up more granular access.
 
## Understanding credential types
{: #credentials-provide}

The credentials that you provide depend upon the type of resources that you want to scan. You might provide an API key, an access key file, or a username and password to a specific resource.

| Credential type | Needed information |
|:-------|:---------|
| {{site.data.keyword.cloud_notm}} | An {{site.data.keyword.cloud_notm}} API key with a service ID. For help with creating an API key, see [Understanding API keys](/docs/account?topic=account-manapikey). Occasionally, services require [additional permissions](/docs/security-compliance?topic=security-compliance-permissions#additional-permissions). To create an {{site.data.keyword.cloud_notm}} API key without a service ID, be sure that the user who creates the key has the required permissions for all the resources that you want to scan. |
| Amazon Web Services | Your AWS user credentials, API Access Key ID, and Secret Access Key. Your secret access key is a large binary encoded string. [Learn more](/docs/security-compliance?topic=security-compliance-permissions#amazon-permissions) about the specific permissions you can enable for AWS. |
| Microsoft Azure | An Azure client ID (application ID), client secret (authentication key), tenant ID, and subscription ID. Additionally, you must provide the list of Resource Groups that are associated with the Subscription ID that is involved in the scan. [Learn more](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal#get-application-id-and-authentication-key){: external} about how to create your Azure credentials. You can find more information on the[specific permissions](/docs/security-compliance?topic=security-compliance-permissions#azure-permissions) you can enable for Azure. |
| Google Cloud Platform | A Google Cloud Platform service account Authentication Key. [Find more information](https://cloud.google.com/iam/docs/creating-managing-service-account-keys){: external} about how to create an Authentication Key. [Learn more](/docs/security-compliance?topic=security-compliance-permissions#google-permissions) about the specific permissions you can enable for GCP Cloud. |
| Database | The name of the database and the username and password that are needed to access it. |
| Username - password | A username and password combination that is needed to gain access to an on-premises resource. |
| Username - PEM | A username and password combination and PEM file that is needed to gain access to an on-premises resource. |
| Windows authentication | A username and password combination. You must also provide the type of authentication that your credential is configured to provide. Options include Basic, Kerberos, and Negotiate. You can also choose whether to Use SSL by checking the **Use SSL** box. |
{: caption="Table 1. Credential types and input information" caption-side="top"}


## Setting up the level of access for credentials 
{: #credential-access}

The level of access that your credentials need depends upon the actions that you want the {{site.data.keyword.compliance_short}} to take. If you want to run scans only on your resources, you must provide credentials that provide the collector `read` access to your resources. This way, the service is able to scan your resource configurations. If you also want to initiate remediation from the {{site.data.keyword.compliance_short}}, then the credentials that you provide must have `write` access.

For collectors that are run in on-premises environments, credentials must have sufficient privileges to collect operating system-related information. Credentials must also have sufficient access to query other services that run on the machines such as a database.

Some {{site.data.keyword.cloud_notm}} services require [additional permissions](#additional-permissions) for their goals to be monitored, be sure to review the information to ensure that your IAM policies are correctly configured.

## Storing credentials 
{: #credential-storage}

Credentials are stored securely by using encryption and are not visible in clear text at any point during the storage process. For more information about the security of your stored credentials, see [Storing and encrypting data in the {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).

