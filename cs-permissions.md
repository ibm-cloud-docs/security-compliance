---

copyright:
  years: 2020, 2023
lastupdated: "2023-03-29"

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

# Understanding the required permissions
{: #permissions}

To evaluate resources that do not run on {{site.data.keyword.cloud_notm}}, you must provide {{site.data.keyword.compliance_full}} access to the resources through an API Key. The credentials that you provide are used by the collector to obtain your resource configurations. Each service and environment has differing requirements. 
{: shortdesc}



If you're working with {{site.data.keyword.cloud_notm}}, you don't need to configure credentials! Check out our new and improved experience to get up and running in just a few steps.
{: tip}

## Assigning specific permissions for {{site.data.keyword.cloud_notm}}
{: #ibm-permissions}

You must assign your service ID API key `viewer` access to all the resources that you want the service to evaluate and all the account management services that are used as part of the evaluation. For more help with assigning these permissions, check out the tutorial [Managing credentials for {{site.data.keyword.cloud_notm}} resources](/docs/security-compliance?topic=security-compliance-credentials).

These permissions are not required when you evaluate your resources by using the new architecture. If you're working with {{site.data.keyword.cloud_notm}} try [our new experience](/docs/security-compliance?topic=security-compliance-scan-resources).
{: tip}

In addition to `viewer` access, a few {{site.data.keyword.cloud_notm}} services have goals that require more permissions to complete the scan or view the results. If the service is listed in the following table, be sure to assign the additional permissions to your service ID API key.


   | Service | Additional permission |
   |---------|---------------|
   | Activity Tracker Event Routing | Operator |
   | App ID | Reader |
   | Certificate Manager | Reader |
   | Cloud Catalog | Publisher |
   | Cloud Shell | Cloud Operator |
   | Cloud Object Storage | Reader and Writer |
   | Databases  \n * etcd  \n * ElasticSearch  \n * MongoDB  \n * PostgreSQL  \n * Redis| Operator |
   | Event streams | Reader |
   | Hyper Protect Crypto Services | Operator and Manager |
   | Key Protect | ReaderPlus, Manager and Editor |
   | Kubernetes Service | Reader |
   | OpenShift | Reader |
   | Satellite | Operator and Writer |
   | Secrets Manager | Reader |
   | Virtual Private Cloud  \n * Application Load Balancer  \n * Block Storage  \n * Block Storage Snapshots  \n * File Storage  \n * Security Groups | Reader |
   {: caption="Table 1. Additional required permissions" caption-side="top"}


### Additional requirements
{: #ibm-permissions-actions}

If you are working with Classic Infrastructure or the Continuous Delivery service, the provided credential must be a user API key. If a service ID is provided, the scan can't complete.
{: note}

Activity Tracker
:   If you enable a control that measures a specific number of days, it is monitored by using Activity Tracker. To ensure that the controls can be evaluated, you must create a new credential that is specific to Activity Tracker of type *username / password*, and then [map the credential to your scope](/docs/security-compliance?topic=security-compliance-credentials). For **username**, provide the GUID for the instance of Activity Tracker that you want to scan. For **Password**, enter your service key.

{{site.data.keyword.containershort}}
:   To enable scanning of your clusters, you must [map additional information](/docs/security-compliance?topic=security-compliance-credentials) and configure your cluster through the CLI by logging in to {{site.data.keyword.cloud_notm}} by using the API key that you want to use to evaluate your clusters. Be sure to trigger fact collection after you log in. For more help, see [Managing credentials for {{site.data.keyword.cloud_notm}} resources](/docs/security-compliance?topic=security-compliance-credentials).

{{site.data.keyword.openshiftshort}}
:   To enable scanning of your clusters, you must [map additional information](/docs/security-compliance?topic=security-compliance-credentials) and configure your cluster through the CLI by logging in to {{site.data.keyword.cloud_notm}} by using the API key that you want to use to evaluate your clusters. Be sure to trigger fact collection after you log in. You must also configure the OSCO integration. For more help, see [Managing credentials for {{site.data.keyword.cloud_notm}} resources](/docs/security-compliance?topic=security-compliance-credentials).

Virtual Private Cloud
:   To scan your Virtual Private Cloud's, you must provide the name of the private cloud that you want to evaluate by [mapping extra credentials](/docs/security-compliance?topic=security-compliance-credentials).


## Assigning specific permissions for other environments
{: #additional-permissions}

You can provide more granular access to your collector to scan your resources that are located in AWS, Azure, and Google Cloud Platform.

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

If you want to add more restrictions, see the following table for examples of granular access that you can grant to the collector. 

| Access level | Permission |
| ------------ | ------- | 
| `AmazonECC2ReadOnlyAccess` | You can use `AmazonEC2ReadOnlyAccess` to allow the collector to access AWS services without allowing the collector to manage permissions management access. |
| `AmazonS3ReadOnlyAccess` | You can use `AmazonS3ReadOnlyAccess` to provide to the collector read-only access to Amazon S3 resources. |
| `AWSCloudTrailReadOnlyAccess` | You can use `AWSCloudTrailReadOnlyAccess` to allow the collector to view the CloudTrail console, including recent events and event history. The collector can also view existing trails and their buckets. Collectors with this level of access can download a file of event history, but they cannot create or update trails. |
| `IAMReadOnlyAccess` | You can use `IAMReadOnlyAccess` to grant to the collector read-only access to Amazon IAM resources. |
| `CloudWatchReadOnlyAccess` | You can use `CloudWatchReadOnlyAccess` to provide to the collector read-only access to CloudWatch. | 
| `AWSConfigUserAccess` | You can use `AWSConfigUserAccess` to grant to the collector read-only access to AWS Config. |
{: caption="Table 3. Additional granular permissions for resources that are located in AWS" caption-side="top"}

### Specific permissions for Azure 
{: #azure-permissions}

You must assign the roles of **Reader** and **Directory Reader** to allow your collector to scan your resources located in an Azure environment.


### Specific permissions for Google Cloud Platform (GCP)
{: #google-permissions}

You must assign the role of **Project-Viewer** to allow your collector to scan your resources located in GCP. By using the project-viewer role, you provide to the collector read-only access to all GCP object types.


If you want to add more restrictions, see the following table for examples of granular access that you can grant to the collector. 

| Access level | Permission description |
| ------------ | ------- | 
| `bigquery.datasets.get` | You can allow your collector to get metadata about a data set with this permission. |
| `cloudkms.keyRings.list` | You can allow your collector to list `KeyRings` with this permission. A `KeyRing` is a high-level logical grouping of `CryptoKeys`. A `CryptoKey` represents a logical key that can be used for cryptographic operations. |
| `cloudsql.databases.get` | You can allow your collector to retrieve a resource that contains information about a database inside a Cloud SQL instance with this permission. View also `cloudsql.databases.list`. |
| `cloudsql.instances.get`  | You can allow your collector to retrieve a resource that contains information about a Cloud SQL instance with this permission. View also `cloudsql.instances.list`. |
| `compute.disks.list` | You can allow your collector to display all Google Compute Engine disks in a project with this permission. |
| `compute.firewalls.get` | You can allow your collector to get the specified firewall with this permission. View also `compute.firewalls.list`. |
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
| `dns.managedZoneOperations.get` | You can allow your collector to fetch the representation of an existing Operation with this permission. View also `dns.managedZoneOperations.list`. |
| `dns.managedZones.get` | You can allow your collector to retrieve the representation of an existing `ManagedZone` with this permission. View also `dns.managedZones.list`. |
| `dns.policies.get` | You can allow your collector to get the representation of an existing policy with this permission. View also `dns.policies.list`. |
| `dns.projects.get` | You can allow your collector to fetch the representation of an existing project with this permission. |
| `iam.roles.get` | You can allow your collector to get the definition of a role with this permission. View also `iam.roles.list`. |
| `iam.serviceAccountKeys.get` | You can allow your collector to retrieve a `ServiceAccountKey`with this permission. View also `iam.serviceAccountKeys.list`. |
{: caption="Table 4. Additional granular permissions for resources that are located in GCP" caption-side="top"}

