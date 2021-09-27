---

copyright:
  years: 2021
lastupdated: "2021-09-27"

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

# What are the required permissions? 
{: #permissions}

To scan your resources located in {{site.data.keyword.cloud_notm}}, Amazon Web Services, Azure, and Google Cloud Platform, you must grant various access levels to your collector. 
{: shortdesc}

## Understanding credentials
{: #understand-credentials}

Credentials are used by a collector to gather information about your resource configurations, assess them, and initiate any remediation that is needed. The collector acts as an intermediary between your resources and the {{site.data.keyword.compliance_short}}.

To enable communication between your resources and the collector, you must associate credentials with the collector through the {{site.data.keyword.compliance_short}}. The credentials that you associate with the collector must have `read` access to your resources. Depending on the type of credentials you provide and the environment where your resources are located, you can set up more granular access.
 
### Providing needed information based on credential type
{: #credentials-provide}

The credentials that you provide depend upon the type of resources that you want to scan. You might provide an API key, an access key file, or a username and password to a specific resource.

| Credential type | Needed information |
|:-------|:---------|
| {{site.data.keyword.cloud_notm}} | An {{site.data.keyword.cloud_notm}} API key with a service ID. For help with creating an API key, see [Understanding API keys](/docs/account?topic=account-manapikey). Occasionally, services require [additional permissions](/docs/security-compliance?topic=security-compliance-permissions#additional-permissions). To create an {{site.data.keyword.cloud_notm}} API key without a service ID, be sure that the user who creates the key has the required permissions for all of the resources that you want to scan. |
| Amazon Web Services | Your AWS user credentials, API Access Key ID, and Secret Access Key. Your secret access key is a large binary encoded string. [Learn more](/docs/security-compliance?topic=security-compliance-permissions#amazon-permissions) about the specific permissions you can enable for AWS. |
| Microsoft Azure | An Azure client ID (application ID), client secret (authentication key), tenant ID, and subscription ID. Additionally, you must provide the list of Resource Groups that are associated with the Subscription ID that is involved in the scan. [Learn more](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal#get-application-id-and-authentication-key){: external} about how to create your Azure credentials. You can find more information on the[specific permissions](/docs/security-compliance?topic=security-compliance-permissions#azure-permissions) you can enable for Azure. |
| Google Cloud Platform | A Google Cloud Platform service account Authentication Key. [Find more information](https://cloud.google.com/iam/docs/creating-managing-service-account-keys){: external} about how to create an Authentication Key. [Learn more](/docs/security-compliance?topic=security-compliance-permissions#google-permissions) about the specific permissions you can enable for GCP Cloud. |
| Database | The name of the database and the username and password that are needed to access it. |
| Username - password | A username and password combination that is needed to gain access to an on-premises resource. |
| Username - PEM | A username and password combination and PEM file that is needed to gain access to an on-premises resource. |
| Windows authentication | A username and password combination. You must also provide the type of authentication that your credential is configured to provide. Options include Basic, Kerberos, and Negotiate. You can also choose whether to Use SSL by checking the **Use SSL** box. |
{: caption="Table 1. Credential types and input information" caption-side="top"}



### Setting up the level of access for credentials 
{: #credential-access}

The level of access that your credentials need depends upon the actions that you want the {{site.data.keyword.compliance_short}} to take. If you want to run scans only on your resources, you must provide credentials that provide the collector `read` access to your resources. This way, the service is able to scan your resource configurations. If you also want to initiate remediation from the {{site.data.keyword.compliance_short}}, then the credentials that you provide must have `write` access.

For collectors that are run in on-premises environments, credentials must have sufficient privileges to collect operating system-related information. Credentials must also have sufficient access to query other services that run on the machines such as a database.

Some {{site.data.keyword.cloud_notm}} services require [additional permissions](#additional-permissions) for their goals to be monitored, be sure to review the information to ensure that your IAM policies are correctly configured.

### Storing credentials 
{: #credential-storage}

Credentials are stored securely by using encryption and are not visible in clear text at any point during the storage process. For more information about the security of your stored credentials, see [Storing and encrypting data in the {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).

## Assigning specific permissions
{: #additional-permissions}

You can provide more granular access to your collector to scan your resources located in {{site.data.keyword.cloud_notm}}, AWS, Azure, and Google Cloud Platform.
{: shortdesc}

### Specific permissions for {{site.data.keyword.cloud_notm}} 
{: #ibm-permissions}

You must assign your API key Viewer and Reader access to allow your collector to scan your resources that are located in {{site.data.keyword.cloud_notm}}.
{: shortdesc}

For each credential, you must manage reader or viewer permissions for the services that you want to scan. A few of the {{site.data.keyword.cloud_notm}} services have goals that require additional permissions to either complete the scan or to view the results. If the service is listed in the following table, be sure to assign the appropriate permissions to either your Service ID or the user that the credentials belong to. You can learn more about [mapping additional credentials](/docs/security-compliance?topic=security-compliance-map-credentials) to a collector.

| Service | Additional permission |
|---------|---------------|
| Key Protect | A credential must also have Manager access to the Key Protect service to run scans. |
| Cloud Object Storage | A credential must also have Writer access to the Key Protect service to run scans. |
| User Management - Billing | To view the results that are related to MFA, a user must have viewer access to the Billing service and to the {{site.data.keyword.compliance_short}}. |
| Classic Infrastructure | The provided credential must be a User API key. If a service ID is provided, the scan cannot complete. |
| Continuous Delivery | The provided credential must be a User API key. If a service ID is provided, the scan cannot complete. |
{: caption="Table 2. Additional required permissions" caption-side="top"}

If you enable a control that measures a specific number of days, it is monitored by using Activity Tracker. You must create a new credential using Activity Tracker's GUID and Service_key as the username and password. Then, map the credential to a specific collector by using the format AT=resource_guid.
{: note}


### Specific permissions for Amazon Web Services (AWS)
{: #amazon-permissions}

To scan resources located in AWS with the {{site.data.keyword.compliance_short}}, you must provide `ReadOnlyAccess` permissions to the collector. `ReadOnlyAccess` provides read-only access to all AWS object types, allowing the collector to scan your resource configurations. 
{: shortdesc}

You can also create a custom policy to read information that is related to Key AWS Management Service (KMS). You can use the following JSON to create the custom policy. 

```json
{
  "Version": "2012-10-17",
  "Statement": {
    "Effect" : "Allow", 
    "Action": [
      "kms:ListKeys",
      "kms:ListAliases"
    ],
    "Resource":"*"
  }
}
```
{: screen}

If you want to add more restrictions, see the following table for examples of granular access you can grant to the collector. 

| Access level | Permission |
| ------------ | ------- | 
| `AmazonECC2ReadOnlyAccess` | You can use `AmazonEC2ReadOnlyAccess` to allow the collector to access AWS services without allowing the collector to manage permissions management access. |
| `AmazonS3ReadOnlyAccess` | You can use `AmazonS3ReadOnlyAccess` to provide to the collector read-only access to Amazon S3 resources. |
| `AWSCloudTrailReadOnlyAccess` | You can use `AWSCloudTrailReadOnlyAccess` to allow the collector to view the CloudTrail console, including recent events and event history. The collector can also view existing trails and their buckets. Collectors with this level of access can download a file of event history, but they cannot create or update trails. |
| `IAMReadOnlyAccess` | You can use `IAMReadOnlyAccess` to grant to the collector read-only access to Amazon IAM resources. |
| `CloudWatchReadOnlyAccess` | You can use `CloudWatchReadOnlyAccess` to provide to the `collectorread`-only access to CloudWatch. | 
| `AWSConfigUserAccess` | You can use `AWSConfigUserAccess` to grant to the collector read-only access to AWS Config. |
{: caption="Table 3. Additional granular permissions for resources that are located in AWS" caption-side="top"}

### Specific permissions for Azure 
{: #azure-permissions}

You must assign the roles of **Reader** and **Directory Reader** to allow your collector to scan your resources located in an Azure environment.
{: shortdesc}

### Specific permissions for Google Cloud Platform (GCP)
{: #google-permissions}

You must assign the role of **Project-Viewer** to allow your collector to scan your resources located in GCP. By using the project-viewer role, you provide to the collector read-only access to all GCP object types.
{: shortdesc}

If you want to add more restrictions, see the following table for examples of granular access you can grant to the collector. 

| Access level | Permission description |
| ------------ | ------- | 
| `bigquery.datasets.get` | You can allow your collector to get metadata about a data set with this permission. |
| `cloudkms.keyRings.list` | You can allow your collector to list `KeyRings` with this permission. A `KeyRing` is a high-level logical grouping of `CryptoKeys`. A `CryptoKey` represents a logical key that can be used for cryptographic operations. |
| `cloudsql.databases.get` | You can allow your collector to retrieve a resource that contains information about a database inside a Cloud SQL instance with this permission. View also `cloudsql.databases.list`. |
| `cloudsql.instances.get`  | You can allow your collector retrieve a resource that contains information about a Cloud SQL instance with this permission. View also `cloudsql.instances.list`. |
| `compute.disks.list` | You can allow your collector to display all Google Compute Engine disks in a project with this permission. |
| `compute.firewalls.get` | You can allow your collector get the specified firewall with this permission. View also `compute.firewalls.list`. |
| `compute.instances.get` | You can allow your collector to get the specified Instance resource with this permission. You can get a list of available instances by making a `compute.instances.list` request. |
| `compute.projects.get` | You can allow your collector to get the specified Project resource with this permission. |
| `compute.regions.get` | You can allow your collector to retrieve the specified Region resource with this permission. You can get a list of available regions by making a `compute.regions.list` request. |
| `compute.subnetworks.get` | You can allow your collector to retrieve the specified subnetwork with this permission. You can get a list of available subnetworks `compute.subnetworks.list` request. View also `compute.subnetworks.getIamPolicy`. |
| `compute.targetHttpsProxies.list` | You can allow your collector to list Google Compute Engine target HTTPS proxies with this permission. |
| `compute.targetInstances.list` | You can allow your collector to read and manipulate Compute Engine virtual target instances with this permission. |
| `compute.targetPools.get` | You can allow your collector to retrieve the specified target pool with this permission. You can get a list of available target pools by making a `compute.targetPools.list` request. |
| `compute.targetSslProxies.get` | You can allow your collector to get the specified `TargetSslProxy` resource with this permission. You can get a list of available target SSL proxies by making a `compute.targetSslProxies.list` request. |
| `compute.targetTcpProxies.get` | You can allow your collector to retrieve the specified `TargetTcpProxy` resource with this permission. You can get a list of available target `TCP proxies` by making a `compute.targetTcpProxies.list` request. |
| `compute.zones.get` | You can allow your collector to get the specified zone resource with this permission. You can get a list of available zones by making a `compute.zones.list` request.
| `dns.managedZoneOperations.get` | You can allow your collector to fetch the representation of an existing Operation with this permission. View also `dns.managedZoneOperations.list` |
| `dns.managedZones.get` | You can allow your collector to retrieve the representation of an existing `ManagedZone` with this permission. View also `dns.managedZones.list`. |
| `dns.policies.get` | You can allow your collector to get the representation of an existing policy with this permission. View also `dns.policies.list`. |
| `dns.projects.get` | You can allow your collector to fetch the representation of an existing project with this permission. |
| `iam.roles.get` | You can allow your collector to get the definition of a role with this permission. View also `iam.roles.list`. |
| `iam.serviceAccountKeys.get` | You can allow your collector to retrieve a `ServiceAccountKey`with this permission. View also `iam.serviceAccountKeys.list`. |
{: caption="Table 4. Additional granular permissions for resources that are located in GCP" caption-side="top"}

