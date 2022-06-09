---

copyright:
  years: 2020, 2022
lastupdated: "2022-06-09"

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

# What are the required permissions? 
{: #permissions}

To scan your resources located in {{site.data.keyword.cloud_notm}}, Amazon Web Services, Azure, and Google Cloud Platform, you must grant various access levels to your collector. 
{: shortdesc}

## Understanding credentials
{: #understand-credentials}

Credentials are used by a collector to gather information about your resource configurations, assess them, and initiate any remediation that is needed. The collector acts as an intermediary between your resources and the {{site.data.keyword.compliance_short}}.

To enable communication between your resources and the collector, you must associate credentials with the collector through the {{site.data.keyword.compliance_short}}. The credentials that you associate with the collector must have `read` or `viewer` access to your resources. Depending on the type of credentials you provide and the environment where your resources are located, you can set up more granular access.
 
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

## Assigning specific permissions for {{site.data.keyword.cloud_notm}}
{: #ibm-permissions}

You must assign your service ID API key `viewer` access to all of the resources that want the service to evaluate and for all of the account management services that are used as part of the evaluation.

For more help assigning these permissions, check out the tutorial [Managing credentials for IBM Cloud resources](/docs/security-compliance?topic=security-compliance-ibm-credential-setup).
{: tip}

In addition to `viewer` access, a few {{site.data.keyword.cloud_notm}} services have goals that require additional permissions to either complete the scan or to view the results. If the service is listed in the following table, be sure to assign the additional permissions to your service ID API key.


   | Service | Additional permission |
   |---------|---------------|
   | Activity Tracker | Operator and Manager |
   | App ID | Reader |
   | Certificate Manager | Reader |
   | Cloud Catalog | Publisher |
   | Cloud Shell | Cloud Operator |
   | Cloud Object Storage | Reader and Writer |
   | <ul>Databases <li>etcd</li> <li>ElasticSearch</li> <li>MongoDB</li> <li>PostgreSQL</li> <li>Redis</li></ul>| Operator |
   | Event streams | Reader |
   | Hyper Protect Crypto Services | Operator and Manager |
   | Key Protect | ReaderPlus, Manager and Editor |
   | Kubernetes Service | Reader |
   | OpenShift | Reader |
   | Satellite | Operator and Writer |
   | Secrets Manager | Reader |
   | <ul>Virtual Private Cloud <li>Application Load Balancer</li> <li>Block Storage</li> <li>Block Storage Snapshots</li> <li>File Storage</li> <li>Security Groups</li></ul>| Reader |
   {: caption="Table 1. Additional required permissions" caption-side="top"}


### Additional required actions by service
{: #ibm-permissions-actions}

If you are working with Classic Infrastructure or the Continuous Delivery service, the provided credential must be a user API key. If a service ID is provided the scan can't complete.
{: note}

Activity Tracker
:   If you enable a control that measures a specific number of days, it is monitored by using Activity Tracker. To ensure that the controls can be evaluated, you must create a new credential specific to Activity Tracker of type *Username / password* and then [map the credential to your scope](/docs/security-compliance?topic=security-compliance-map-credentials). For **Username**, provide the GUID for the instance of Activity Tracker that you want to scan. For **Password**, enter your service key.

{{site.data.keyword.containershort}}
:   To enable scanning of your clusters, you must [map additional information](/docs/security-compliance?topic=security-compliance-map-credentials) and configure your cluster through the CLI by logging in to IBM Cloud by using the API key that you want to use to evaluate your clusters. Be sure to trigger fact collection after you log in. For more help, see [Managing credentials for IBM Cloud resources](/docs/security-compliance?topic=security-compliance-ibm-credential-setup).

{{site.data.keyword.openshiftshort}}
:   To enable scanning of your clusters, you must [map additional information](/docs/security-compliance?topic=security-compliance-map-credentials) and configure your cluster through the CLI by logging in to IBM Cloud by using the API key that you want to use to evaluate your clusters. Be sure to trigger fact collection after you log in. You must also configure the OSCO integration. For more help, see [Managing credentials for IBM Cloud resources](/docs/security-compliance?topic=security-compliance-ibm-credential-setup).

Virtual Private Cloud
:   To scan your Virtual Private Cloud's you must provide the name of the private cloud that you want to evaluate by [mapping additional credentials](/docs/security-compliance?topic=security-compliance-map-credentials).


## Assigning specific permissions for other environments
{: #additional-permissions}

You can provide more granular access to your collector to scan your resources located in AWS, Azure, and Google Cloud Platform.


### Specific permissions for Amazon Web Services (AWS)
{: #amazon-permissions}

To scan resources located in AWS with the {{site.data.keyword.compliance_short}}, you must provide `ReadOnlyAccess` permissions to the collector. `ReadOnlyAccess` provides read-only access to all AWS object types, allowing the collector to scan your resource configurations. 


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


### Specific permissions for Google Cloud Platform (GCP)
{: #google-permissions}

You must assign the role of **Project-Viewer** to allow your collector to scan your resources located in GCP. By using the project-viewer role, you provide to the collector read-only access to all GCP object types.


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

