---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-10"

keywords: available insights rules, Activity Insights, Network Insights, iks, key protect, kms, rules, app id, iam, cos, certificates, bucket, object storage,

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

# Available Activity Insights rule packages
{: #insights-rules}

Activity Insights compares your user and application activity against predefined rule packages to identify suspicious behavior.
{: shortdesc}



## App ID
{: #app-id}

The App ID service helps you to manage authentication and authorization of your applications. [Learn more](/docs/appid?topic=appid-getting-started).

| Rule          |  Finding Type     |  Description     |
|:--------------|:------------------|:-----------------|
| `Very high risk App ID activity` | `ata-appid-sec-conf` | Reports when an update of the identity provider configuration was performed. |
| `Failed logins per app exceed threshold within time window` | `ata-app-failed-login-attempts` | Reports when within a 10 minute window more than 100 user authentication are observed. |
| `App ID delete exceeded threshold within time window` | `ata-appid-delete-users` | Reports when within a 30 minutes window more than 100 Cloud Directory users and profiles were deleted.|
| `Service instance high risk API` | `ata-appid-service` | Reports when one of the following are observed:  \n An App ID instance is created.  \n An App ID instance is renamed or a service plan is changed.  \n An App ID instance is deleted.  \n An API key is created for an App ID instance through the service credentials section of the service instance UI.  \n An API key that is associated with an App ID instance is deleted from the service credentials section of the service instance UI.  \n When binding an App ID instance to an application.  \n When unbinding an App ID instance from an application |
{: caption="Table 1. Rules that are available in the App ID rule package" caption-side="bottom"}


## Certificate Manager
{: #certificate-manager}

The Certificate Manager service helps you to obtain, store, and manage the certificates that you use for cloud or on-premises deployments. [Learn more](/docs/certificate-manager?topic=certificate-manager-getting-started).

| Rule          |  Finding Type     |  Description     |
|:--------------|:------------------|:-----------------|
| `Very high risk certificate manager activity` | `ata-cert-notification-conf` | Reports when changes are made to a notification channel. These changes include: deletion, update and enabling and disabling a notification channel. |
| `Certificate reimport threshold within time window` | `ata-cert-reimport` | Reports when within a 24 hour time window more than 2 certificate imports are unsuccessful. |
| `Certificate notification failure` | `ata-cert-notification-fail` | Reports when within a 24 hour time window more than 2 notification channel sends are unsuccessful. |
| `Certificate manager indicative API outside` | `ata-cert-ccw` | Reports when a certificate is deleted, reimported or download outside of the hours 1700 to 0800 (next day). |
| `Service instance high risk API` | `ata-cert-service` | Reports when any one of the following is observed more than twice within a 24 hour window:  \n A Certificate Manager instance is created.  \n A Certificate Manager instance is deleted.  \n A Certificate Manager instance is renamed or service plan changed. |
{: caption="Table 2. Rules that are available in the Certificate Manager rule package" caption-side="bottom"}


## Cloud Databases
{: #icd}

IBM Cloud Databases allow you to take control of your highly sensitive data by storing it in a tamper-proof environment. Rules apply to IBM Cloud Databases for [MongoDB](/docs/databases-for-mongodb?topic=databases-for-mongodb-getting-started), [PostgreSQL](/docs/databases-for-postgresql?topic=databases-for-postgresql-getting-started), [Redis](/docs/databases-for-redis?topic=databases-for-redis-getting-started), [etcd](/docs/databases-for-etcd?topic=databases-for-etcd-getting-started), and [ElasticSearch](/docs/databases-for-elasticsearch?topic=databases-for-elasticsearch-getting-started).


| Rule          |  Finding Type     |  Description     |
|:--------------|:------------------|:-----------------|
| `ICD service endpoints, allowlist-ips update - high risk API` | `ata-icd-high-risk` | Reports when one of the following are observed:  \n A change was made to the service endpoints configuration of MongoDB, Redis, PostgreSQL, ElasticSearch or etcd instance.  \n The allowlist IPs were modified for MongoDB, Redis, PostgreSQL, ElasticSearch or etcd instance. |
{: caption="Table 3. Rules that are available in the Cloud Databases rule package" caption-side="bottom"}


## Cloud Object Storage
{: #cloud-object-storage}

The Cloud Object Storage service helps you to store encrypted and dispersed data across multiple geographic locations. [Learn more](/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage).


| Rule          |  Finding Type     |  Description     |
|:--------------|:------------------|:-----------------|
| `Very high risk Cloud Object Storage activity` | `ata-cos-sec-conf` | Reports when an ACL is created for a bucket or when a CORS configuration is created or deleted.  |
| `Cloud Object Storage bucket create or delete exceeded threshold within time window` | `ata-cos-bucket-create-delete-threshold` | Reports when in a time window of 30 minutes more than 1000 buckets are created or deleted. |
| `Service instance high risk API` | `ata-cos-service` | Reports when any one of the following is observed more than twice within a 24 hour window:  \n A Cloud Object Storage instance is created.  \n A Cloud Object Storage instance is renamed or service plan changed.  \n A Cloud Object Storage instance is deleted.  \n An API key is created for a Cloud Object Storage instance through the Service credentials section of the service instance UI.  \n  An API key that is associated with a Cloud Object Storage instance is deleted from the Service credentials section of the service instance UI.  \n When binding a Cloud Object Storage instance to an application.  \n When unbinding a Cloud Object Storage instance from an application |
{: caption="Table 4. Rules that are available in the Cloud Object Storage rule package" caption-side="bottom"}


## Cloud Shell
{: #cloudshell}

IBM Cloud Shell is a cloud-based shell workspace that you can access through your browser. It's preconfigured with the full IBM Cloud CLI and tons of plug-ins and tools that you can use to manage apps, resources, and infrastructure. [Learn more](/docs/cloud-shell?topic=cloud-shell-getting-started).

| Rule          |  Finding Type     |  Description     |
|:--------------|:------------------|:-----------------|
| `Cloud Shell session is created or configured - high risk API` | `ata-cloudshell-high-risk` | Reports when a new Cloud Shell session is created or configured. |
{: caption="Table 5. Rules that are available in the Cloud Shell rule package" caption-side="bottom"}


## Classic infrastructure
{: #infra-gen1}

Classic infrastructure is a type of cloud computing that allows you to allocate your resources on demand. You can monitor [Virtual Servers](/docs/virtual-servers?topic=virtual-servers-getting-started-tutorial) or [Bare Metal Servers](/docs/bare-metal?topic=bare-metal-getting-started) with Activity Insights.


| Rule          |  Finding Type     |  Description     |
|:--------------|:------------------|:-----------------|
| `Instance provision - high risk API` | `ata-classic-compute-high-risk` | Reports when a virtual server instance or a bare metal server is provisioned with a public VLAN. |
{: caption="Table 6. Rules that are available in the Classic Infrastructure rule package" caption-side="bottom"}




## Identity and Access Management
{: #iam}

Identity and Access Management enables you to securely authenticate users for platform services and control access to resources consistently across IBM Cloud. [Learn more](/docs/account?topic=account-iamoverview).


| Rule          |  Finding Type     |  Description     |
|:--------------|:------------------|:-----------------|
| `Very high risk IAM activity` | `ata-iam-sec-conf` | Reports when any one of the following is observed:  \n A member is added to an access group.  \n A rule is added to an access group.  \n A rule name is modified.  \n An API key for a service ID is created.  \n An API key is created.  \n A policy to a user or access group is added.  \n A policy that is assigned to a user or access group is deleted. |
| `Failed logins per account exceed threshold within time window` | `ata-account-failed-login-attempts` | Reports when within a 30 minute time window more than 100 login attempts fail. The login attempts can be one of the following:  \n When a user logs in to the IBM Cloud by using an API key.  \n When logging in to the IBM Cloud by using an API key that is associated with a service ID.  \n When requesting an identity cookie to run an action.  \n When logging in to the IBM Cloud or requests a new refresh token to run an action when already logged in to the IBM Cloud. |
| `Account reads exceed threshold within time window` | `ata-account-iam-reads-threshold` | Reports when within a 30 minutes time window more than 100 read events are observed. These read events include:  \n Checking a member's membership.  \n Viewing a rule in an access group.  \n Looking at information that is related with access groups. |
| `Account delete outside change control window` | `ata-iam-delete-account-threshold` | Reports a delete event is observed occurring between 1700 and 0800 (next day). The delete event may be any of the following:  \n Deleting an access group.  \n Removing a member from an access group.  \n Deleting a rule from an access group.  \n Deleting a service ID.  \n Deleting an API key.  \n Deleting an API key for a service ID.  \n Modifying permissions to a policy of a user or access group |
| `Account delete exceed threshold within time window` | `ata-iam-delete-ccw` | Reports a delete event is observed occurring between 1700 and 0800 (next day). The delete event may be any of the following:  \n Deleting an access group.  \n Removing a member from an access group.  \n Deleting a rule from an access group.  \n Deleting a service ID.  \n Deleting an API key.  \n Deleting an API key for a service ID.  \n Modifying permissions to a policy of a user or access group. |
{: caption="Table 7. Rules that are available in the Identity and Access Management rule package" caption-side="bottom"}



## Key Protect
{: #key-protect}

Key Protect helps you provision encrypted keys for apps across IBM Cloud services. [Learn more](/docs/key-protect?topic=key-protect-getting-started-tutorial).

| Rule          |  Finding Type     |  Description     |
|:--------------|:------------------|:-----------------|
| `kms secrets delete - high risk API` | `ata-kms-key-deleted` | Reports when a key is deleted. |
| `kms.secrets.unwrap outside change control window - indicative API` | `ata-kms-key-unwrap-ccw` | Reports when a key is unwrapped between 1700 and 0800 (next day). |
| `The following is a service instance rule instantiated for KMS. high risk API.` | `ata-kms-service` | Reports when one of the following are observed:  \n A KMS instance is created.  \n A KMS instance is renamed or service plan changed.  \n A KMS instance is deleted.  \n An API key is created for a KMS instance through the Service credentials section of the service instance UI.  \n An API key that is associated with a KMS instance is deleted from the Service credentials section of the service instance UI.  \n When binding a KMS instance to an application.  \n When unbinding a KMS instance to an application. |
{: caption="Table 8. Rules that are available in the Key Protect rule package" caption-side="bottom"}



## Kubernetes Service
{: #kubernetes-service}

Kubernetes Service helps you to deploy highly available containerized apps in a way that allows you to automate, isolate, secure, manage, and monitor your workloads across zones and regions. [Learn more](/docs/containers?topic=containers-getting-started).


| Rule          |  Finding Type     |  Description     |
|:--------------|:------------------|:-----------------|
| `Very high risk Kubernetes Service activity` | `ata-iks-high-risk` | Reports when one of the following behaviors are observed:  \n A public or private ALB is created in the cluster.  \n An existing IBM Cloud infrastructure subnet is added to a cluster.  \n Public endpoint is enabled for a cluster.  \n A subnet is created for public endpoint.  \n Enables the private service endpoint allowlist feature for a cluster.  \n Add or remove subnets from a cluster's private service endpoint allowlist.  \n Cluster is accessed via Kubernetes native dashboard, web terminal |
| `Kubernetes Service change to logging detected` | `ata-iks-logging-change` | Reports when changes to logging settings occur. These changes include the following:  \n A logging filter is created.  \n A logging filter is updated.  \n A log forwarding configuration is created.  \n An API key is created.  \n A log forwarding configuration is deleted.  \n A log forwarding configuration is refreshed. |
| `Indicative IKS API exceed threshold within time window` | `ata-iks-indicative-api-threshold` |  Reports when within 30 minutes more than 10 worker nodes are updated. |
| `Indicative IKS API outside of change control window` | `ata-iks-indicative-api-ccw` | Reports when a worker node is updated between 1700 and 0800 (next day). |
| `Service instance high risk API` | `ata-iks-service` | Reports when one of the following are observed:  \n A Kubernetes Service instance is created.  \n A Kubernetes Service instance is renamed or service plan changed.  \n A Kubernetes Service instance is deleted.  \n An API key is created for a Kubernetes Service instance through the Service credentials section of the service instance UI.  \n An API key that is associated with a Kubernetes Service instance is deleted from the Service credentials section of the service instance UI.  \n When binding a Kubernetes Service instance to an application.  \n When unbinding a Kubernetes Service instance to an application.  |
{: caption="Table 9. Rules that are available in the Kubernetes Service rule package" caption-side="bottom"}


