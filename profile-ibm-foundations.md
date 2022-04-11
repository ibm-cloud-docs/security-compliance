---

copyright:
  years: 2022
lastupdated: "2022-04-11"

keywords: best practices, security and compliance, governance, profile, predefined profiles, benchmark, controls, goals, security, compliance, ibm profiles, ibm foundations, 

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

# CIS IBM Cloud Foundations Benchmark controls
{: #cis-ibm-benchmark}

With CIS IBM Cloud Benchmarks, you can transform your organization with IBM Cloud while achieving a standardized level of security and compliance controls. 
{: shortdesc}

The CIS Benchmarks are a collection of industry best practices for securely configuring IT systems, software, and networks. The recommendations provided in the CIS IBM Cloud Benchmark are important security considerations when you are designing your infrastructure on IBM Cloud services.

You can configure the CIS IBM Cloud Foundations Benchmark controls to monitor resources through the IBM Cloud Security and Compliance Center.

## Identity and Access Management
{: #iam-controls}

With Identity and Access Management (IAM), you can securely authenticate users for platform services and control access to resources consistently across IBM Cloud. By enabling the controls that belong to the IAM category, you can increase the security of your account. 

### Ensure API keys unused for 180 days are detected and optionally disabled 1.2
{: #unused-api-keys-goals}

Monitor the usage of API keys in your account that are unused for a long time. As a security best practice, if an API key is unused for a long time, it must be locked. All API keys, even those that are used infrequently, must be rotated periodically to reduce the likelihood of accidental exposure or leaking. API key monitoring is not enabled by default.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000039 | Check whether IBM Cloud API keys that are unused for 180 days are detected and optionally disabled |   |
{: caption="Table 1. Unused API key goal" caption-side="top"}

### Ensure API keys are rotated every 90 days 1.3
{: #api-keys-rotated-goals}

Rotate the production API keys that are associated with your account regularly. By rotating your API keys, you can reduce the impact to your organization if an API key is exposed or compromised. If you suspect that a key was leaked or compromised, you must rotate the key out of production or delete it. 

Any resource that is using an API key that is rotated out of production encounters errors until the API key is updated. The API key rotation mechanism is not enabled by default.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000024 | Check whether IBM Cloud API keys that are managed in IAM are rotated at least every # days |   |
{: caption="Table 2. Key rotation goal" caption-side="top"}

### Restrict user API key creation and service ID creation in the account via IAM roles 1.4
{: #api-keys-restrict-goals}

Restrict user API key creation and service ID creation in your account by using IAM settings. You must enable both settings to restrict all users in the account from creating user API keys and service IDs, except those who have an IAM policy that explicitly allows it. To prevent the creation of unauthorized API keys and service IDs, it is recommended that only users with a need for this action be given the privilege to do so.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000027 | Check whether permissions for API key creation are limited and configured in IAM settings for the account owner |   |
| 3000028 | Check whether permissions for service ID creation are limited and configured in IAM settings for the account owner |    |
{: caption="Table 3. API key and service ID restriction goals" caption-side="top"}'

### Ensure no owner account API key exists 1.5
{: #api-keys-no-owner-account-goals}

An API key that is created by an account owner has account-owner level access to resources in the account. To honor the practice of granting the least privilege that is required, if you are an account owner, you should not create API keys because the level of privilege is automatically granted to account owner-created API keys.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000023 | Check whether the account owner does not have an IBM Cloud API key created in IAM |   |
{: caption="Table 4. Account owner-created API key goal" caption-side="top"}

### Ensure compliance with IBM Cloud password requirements 1.6
{: #ibm-cloud-password-compliance-goals}

Never share your password with anyone and follow the strong password requirements. A strong password can help prevent unauthorized access to an IBM Cloud account. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000001 | Check whether IBMid password policy requires at least one uppercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000002 | Check whether IBMid password policy requires at least one lowercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg) | 
| 3000003 | Check whether IBMid password policy requires at least one number | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| 3000004 | Check whether IBMid password policy requires minimum length of 12 characters | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| 3000005 | Check whether IBMid password policy prevents password reuse below the minimum of # | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| 3000006 | Check whether IBMid password may contain only printable ASCII characters (in the range 33 - 126) | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| 3000007 | Check whether IBMid password policy contains spaces or any of the following characters: \;:("?)<> | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| 3000008 | Check whether IBMid uses a password meter that coaches users to create strong passwords that exceed the minimum requirements | ![Checkmark icon](../../icons/checkmark-icon.svg) |
{: caption="Table 5. Password requirements goals" caption-side="top"}

### Ensure multi-factor authentication (MFA) is enabled for all users in account 1.7
{: #mfa-enabled-goals}

Require users to provide multiple factors of login credentials to authenticate their identity and gain access to IBM Cloud resources. By using Multifactor authentication (MFA), you can add an additional layer of security to an account by requiring users to provide an additional login credential. Help protect accounts from being affected by stolen, phished, or weak passwords. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000012 | Check whether multifactor authentication (MFA) is enabled for each user at the user level |   |
{: caption="Table 6. MFA enabled for all users goal" caption-side="top"}

### Ensure multi-factor authentication (MFA) is enabled for the account owner 1.8
{: #mfa-enabled-owner-goals}

Require account owners to provide multiple factors of login credentials to authenticate their identity and gain access to IBM Cloud resources. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000018 | Check whether multifactor authentication (MFA) is enabled for the account owner |   |
{: caption="Table 7. MFA enabled for account owner goal" caption-side="top"}

### Ensure multi-factor authentication (MFA) is enabled at the account level 1.9
{: #mfa-enabled-account-goals}

Enable MFA at the account level to allow users to authenticate their identity and gain access to IBM Cloud resources.


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000017 | Check whether multifactor authentication (MFA) is enabled at the account level |   |
{: caption="Table 8. MFA enabled at account level goal" caption-side="top"}

### Ensure contact email is valid 1.10
{: #email-valid-goals}

Keep a valid email address on record with IBM Cloud in order to receive emails and account alerts that are related to an IBM Cloud account. Update your email address on record as needed to ensure that you remain updated. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000013 | Check whether account has a contact email defined |   |
{: caption="Table 9. Valid contact email goal" caption-side="top"}

### Ensure contact phone number is valid 1.11
{: #phone-number-valid-goals}

Keep a valid phone number on record with IBM Cloud in the event that IBM needs to contact you regarding your IBM Cloud account.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000014 | Check whether account has a contact phone number defined |   |
{: caption="Table 10. Valid phone number goal" caption-side="top"}

### Ensure IAM users are members of access groups and IAM policies are assigned only to access 1.12
{: #iam-user-policies-access-goals}

Simplify and secure the access management process by using access groups when you assign access to groups of users with identical access needs. To organize a set of users and service IDs into a single entity, you can create an access group. THen, you can assign a single policy to the group instead of assigning the same access multiple times for each individual user or service ID. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000015 | Check whether IAM users are attached to at least one access group |   |
| 3000016 | Check whether IAM policies for users are attached only to groups or roles |   | 
{: caption="Table 11. Access groups policies goals" caption-side="top"}

### Ensure a support access group has been created to manage incidents with IBM Support 1.13
{: #ibm-support-access-group-incidents-goals}

By using the Support Center, you can use support cases to get help if you experience problems with IBM cloud such as technical, access (IAM), billing and usage, and invoice, or sales inquiry issues. To access the Support Center, you must have a viewer role or higher on the Support Center service. To create or edit service cases, you must have an editor role or higher. 

You will have access to the support team based on your support level of the account. Users do not have access to IBM Cloud Support Center by default. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000010| Check whether a support role has been assigned in IAM to manage cases in the IBM Cloud Support Center | ![Checkmark icon](../../icons/checkmark-icon.svg) |
{: caption="Table 12. Support access group goal" caption-side="top"}

### Minimize the number of users with admin privileges in the account 1.14
{: #users-admin-privileges-goals}

Manage admin privileges based on the principle of granting least privilege by using access groups and by avoiding the use of broadly scoped access policies. When managing large numbers of users, it can be hard to maintain the principle of only giving users access to the resources that are required to complete their task. Create access froups with administrative privileges and the ability to add or remove users as needed, instead of granting privileges to individual users. There are no administrator access groups in the account by default.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000021| Check whether there are no more than # IAM administrators configured per account |   |
{: caption="Table 13. User privileges goal" caption-side="top"}

### Minimize the number of Service IDs with admin privileges in the account 1.15
{: #service-id-admin-privileges-goals}

Manage admin privileges based on the principle of granting least privilege by using access groups and by avoiding the use of broadly scoped access policies. When managing large numbers of users, it can be hard to maintain the principle of only giving an individual service ID access to the resources that are required to complete their task. Create access froups with administrative privileges and the ability to add or remove service IDs as needed, instead of granting privileges to individual service IDs. There are no administrator access groups in the account by default.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000038| Check whether account has no more than # service IDs with admin privileges |   |
{: caption="Table 14. Service ID privileges goal" caption-side="top"}

### Ensure IAM does not allow public access to Cloud Object Storage 1.16
{: #iam-public-access-cloud-object-storage-goals}

With IBM Cloud, your users with specific access roles can create access policies that allow all users (authenticated and non-authenticated) to access resources in the account. Certain files or data might be required to be made available for all users to access. The public access group is enabled by default and there is no public access that is allowed to IBM Cloud Object Storage. If your organization does not require this capablity, you must disable it to prevent unintentional misuse.

Resources in your account are not publicly accessible unless a user with administrator privileges explicitly creates a policy to allow public access for a resource. 
{: note}

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000022| Check whether Cloud Object Storage public access is disabled in IAM settings (not applicable to ACLs managed using S3 APIs) |   |
{: caption="Table 15. Cloud Object Storage public access goal" caption-side="top"}

### Ensure inactive user accounts are suspended 1.17
{: #inactive-users-suspended-goals}

Revoke access privileges for inactive users in an IBM Cloud account. Users can be come inactive for many reasons including vacation, parental or sick leave, or new roles within the company. If you need to temporarily revoke a user's access, you can suspend a user account to prevent a login. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000040| Check whether inactive user accounts are suspended |   |
{: caption="Table 16. Inactive accounts suspension goal" caption-side="top"}

### Ensure audit logging is enabled for IBM Cloud IAM 1.18
{: #audit-logging-enabled-goals}

Monitor certain IAM events by using the IBM Cloud Activity Tracker with LogDNA service. You can use this service to investigate abnormal activity and critical actions and comply with regulatory audit requirements. Audit logging with Activity Tracker with LogDNA is not enabled.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000031| Check whether Identity and Access Management (IAM) is enabled with audit logging |   |
{: caption="Table 17. IAM audit logging goal" caption-side="top"}

## Storage
{: #storage-controls}

Your organization might need to store your clients' data. By enabling the controls that belong to the storage category, you can increase the data security of your clients. 

### Cloud Object Storage 2.1
{: #cloud-object-storage-controls}

With IBM Cloud Object Storage, you can store encryped and dispersed data across multiple geographic locations. The data that is stored can be accessed over popular protocols like HTTPS that uses a modern RESTful API.

#### Cloud Object Storage Encryption 2.1.1
{: #cloud-object-storage-encryption-controls}

The objects that you store in IBM Cloud Object Storage must be encrypted at all times for client data security. By default, all the objects that you store in IBM Cloud Object Storage are encrypted at-rest by using provider-managed keys. No user action is needed. To add another layer of encryption to the Data Encryption Keys (DEKs) that are associated with the objects that are stored in Cloud Object Storage buckets, you can integrate Cloud Object Storage with IBM Cloud Key Management Services.

#####  Ensure Cloud Object Storage encryption is enabled with BYOK 2.1.1.2
{: #cloud-object-storage-byok-goals}

Bring your own root key (BYOK) to IBM Cloud and use it to add envelope encryption for your data that is stored in IBM Cloud Object Storage buckets, by using IBM Cloud encryption key management service such as Key Protect. By using BYOK, you can ensure that no one outside of your organization has access to the root key. You can also manage the lifecycle of your customer root keys (CRK) where you can create, rotate, and delete those keys. 

With the support of BYOK, you have a significant level of control in managing those CRKs, which allows you to increase security control and meet relevant compliance requirements. The use of Key Protect encryption key management service with IBM Cloud Object Storag bucks is not enabled by default.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000102 | Check whether Cloud Object Storage is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |   |
{: caption="Table 18. BYOK encryption goal" caption-side="top"}

#####  Ensure Cloud Object Storage encryption is enabled with KYOK 2.1.1.3
{: #cloud-object-storage-kyok-goals}

You can use IBM Cloud encryption key management services such as Hyper Protect Crypto Services to keep and manage exclusive control over the root keys that are used to add envelope encryption for data that is stored in IBM Cloud Object Storage buckets. The best practice is to allow customers to use encryption capabilities that are offered by Hardware Security Module crypto service, when it comes to encryption of data at rest in IBM Cloud. 

With IBM Cloud Hyper Protect Crypto Services and its Keep Your Own Key (KYOK) capabilities, you can have exclusive key control over encryption keys. The use of Hyper Protect Crypto Services key management service with IBM Cloud Object Storage buckets is not enabled by default.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000108 | Check whether Cloud Object Storage is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
{: caption="Table 19. KYOK encryption goal" caption-side="top"}

#### Ensure network access for Cloud Object Storage is set to be exposed only on private endpoint 2.1.3
{: #cloud-object-storage-private-endpoint-goals}

Restrict access to the data you stored in Cloud Object Storage buckets and enhance security controls by creating a firewall rull that only allows data access to the list of IP addresses that are part of your private subnet. By default, Cloud Object Storage buckets can only be accessed by authenticated users.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000105 | Check whether Cloud Object Storage is accessible only by using private endpoints |   |
{: caption="Table 20. Cloud Object Storage private endpoints goal" caption-side="top"}

#### Ensure Cloud Object Storage bucket access is restricted by using IAM and S3 access control 2.1.4
{: #cloud-object-storage-bucket-access-goals}

Access controls on the Cloud Object Storage buckets are governed by IBM Identity and Access Management (IAM). Create policies to assign IAM access roles for users and service IDs against buckets by using the UI or the CLI. You can also grant or restrict some permissions through S3 access controls.

To ensure data access is restricted to only those who have a valid business need, you need to carefully review and plan around access controls that are provided by the IBM Cloud environment when you are creating a new Cloud Object Storage bucket.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000106 | Check whether Cloud Object Storage bucket access is restricted by using IAM and S3 access control |   |
{: caption="Table 21. Best Practices predefined profiles" caption-side="top"}

#### Disable public (anonymous) access to IBM Cloud Object Storage buckets 2.1.5
{: #cloud-object-storage-public-access-goals}

Disable public or anonymous access to IBM Cloud Object Storage buckets. When buckets contain non-public data such as restricted, internal, confidential, or sensitive data, you must disable public access. To disable public access, you must remove a previously defined access policy. Public access to Cloud Object Storage is disabled by default.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000022 | Check whether Cloud Object Storage public access is disabled in IAM settings (not applicable to ACLs managed using S3 APIs) |   |
{: caption="Table 22. Buckets public access goal" caption-side="top"}

### File Block Storage 2.2
{: #file-block-storage-goals}

Your organization might need persistent, high-performance iSCSI storage that is provisioned and managed independently of compute instances. With IBM Block Storage, you can benefit from industry-standard levels of durability and availability with an unmatched feature set that is built by using best practices. You can protect the integrity of your data, maintain availability through maintenance events and unplanned failures, and provide a consistent performance baseline with Block Storage. 

#### Cloud Object Storage Encryption 2.2.1
{: #cloud-object-storage-encryption-file-goals}

By default, all objects that you store in IBM Cloud Block Storage are encrypted at-rest by ensuring that you select an encryption key from various available options. These options include using provider-managed keys, IBM Cloud Key Protect Service, and IBM Cloud hardware HSM-supported Hyper Protect service for managing encryption keys.

#####  Ensure Block Storage is encrypted with customer managed keys 2.2.1.1
{: #block-storage-encrypted-goals}

Only your organization can access and manage your master root with customer-managed keys, giving you full control over your data security. For enhanced security, you can bring your own encryption keys and manage them through IBM Key Management Services such as Key Protect or Hyper Protect Crypto Services (HPCS). By default, provider-managed encryption is turned on through IBM Cloud Block Storage and you can't turn it off once your data is already written to a Cloud Block Storage volume.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000435 | Check whether Block Storage for VPC is encrypted with customer-managed keys |   |
{: caption="Table 23. Block storage encryption with customer keys goal" caption-side="top"}

#####  Ensure Block Storage is encrypted with BYOK 2.2.1.2
{: #block-storage-encrypted-byok-goals}

With Bring your Own Key (BYOK), you can ensure that no one outside of your organization has access to the root key. You can manage the lifecycle of your customer root keys by creating, rotating, or deleting those keys through IBM Key Management Service such as Key Protect. By default, IBM Block Storage provides provider-managed encryption for all data.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000436 | Check whether Block Storage for VPC is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |   |
{: caption="Table 24. BYOK Block Storage encryption goal" caption-side="top"}

#####  Ensure Block Storage is encrypted with KYOK 2.2.1.3
{: #block-storage-encrypted-kyok-goals}

For enhanced security, you can bring your own encryption key and manage them through IBM Key Management Service such as Hyper Protect Crypto Services (HPCS). With IBM Cloud Hyper Protect Crypto Services, you can have exclusive control over encryption keys through the service's Keep Your Own Key (KYOK) capabilities. With this significant level of control over encryption keys, you can ensure that only authorized users have access to encryption keys. By default, IBM Block Storage provides provider-managed encryption for all data. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000437 | Check whether Block Storage for VPC is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
{: caption="Table 25. KYOK Block Storage encryption goal" caption-side="top"}

#### Ensure OS disk is encrypted with customer-managed keys 2.2.2
{: #os-disk-encryption-customer-keys-goals}

For enhanced security, you can bring your own encryption key and manage them through IBM Key Management Service such as Key Protect or Hyper Protect Crypto Services (HPCS). Only your organization can access and manage your master root with customer-managed keys, giving you full control over your data security. By default, provider-managed encryption is turned on through IBM Cloud Block Storage and you can't turn it off once your data is already written to a Cloud Block Storage volume.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000438 | Check whether OS disks are encrypted with customer-managed keys
 |   |
{: caption="Table 26. OS disk encryption customer-managed keys goal" caption-side="top"}

#### Ensure data disks are encrypted with customer managed keys 2.2.3
{: #data-disk-encryption-customer-keys-goals}

For enhanced security, you can bring your own encryption key and manage them through IBM Key Management Service such as Key Protect or Hyper Protect Crypto Services (HPCS). Only your organization can access and manage your master root with customer-managed keys, giving you full control over your data security. By default, provider-managed encryption is turned on through IBM Cloud Block Storage and you can't turn it off once your data is already written to a Cloud Block Storage volume.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000439 | Check whether data disks are encrypted with customer-managed keys
 |   |
{: caption="Table 27. Data disk encryption customer-managed keys goal" caption-side="top"}

#### Ensure unattached disks are encrypted with customer-managed keys 2.2.4
{: #unattached-disk-encryption-customer-keys-goals}

For enhanced security, you can bring your own encryption key and manage them through IBM Key Management Service such as Key Protect or Hyper Protect Crypto Services (HPCS). Only your organization can access and manage your master root with customer-managed keys, giving you full control over your data security. By default, provider-managed encryption is turned on through IBM Cloud Block Storage and you can't turn it off once your data is already written to a Cloud Block Storage volume.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000440 | Check whether unattached disks are encrypted with customer-managed keys |   |
{: caption="Table 28. Unattached disk encryption customer-managed keys goal" caption-side="top"}

## Maintenance
{: #maintenance-controls}

Collect, manage, and analyze audit logs of events that can help detect, understand, or recover from an attack.

### Ensure auditing is configured in the IBM Cloud account 3.1
{: #activity-tracker-cloud-goals}

Monitor activity in your IBM Cloud account by collecting audit events from IBM Cloud resources. You can use IBM Cloud Activity Tracker with LogDNA to investigate abnormal activity and critical actions, and comply with regulatory audit requirements, for example. If you do not meet this control, your ability to monitor activity in your IBM Cloud account is limited. Additionally, your ability to identity the initiator of actions in your account, the resources that are affected, and details about the request is restricted.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000301 | Check whether IBM Activity Tracker is provisioned in multiple regions in an account |   |
{: caption="Table 29. Audit configuration goal" caption-side="top"}

### Ensure the account owner can login only from a list of authorized countries/IP ranges 3.5
{: #account-owner-login-countries-goals}

Monitor the account owner's access to the IBM Cloud account and restrict access from controlled locations. With this configuration, for example, you can monitor and be notified when a user such as the account owner logs in by using Activity Tracker. You can also obtain information about logins from an unauthorized location.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000020 | Check whether authorized IP ranges are configured by the account owner |   |
{: caption="Table 30. Authorized countries restriction goal" caption-side="top"}

### Ensure Activity Tracker data is encrypted at rest 3.6
{: #activity-tracker-encryption-goals}

Ensure Activity Tracker data is encrypted at rest. You can choose to archive the Activity Tracker data to an IBM Cloud Object Storage (COS) bucket for long-term storage. You have the option to manage your own keys with IBM Cloud Key Management Services such as Key Protect and Juper Protect Crypto services. 

If you fail to adopt a customer-managed encryption model to audit data that is archived for longer storage, you expose yourself to breaches in infrastructure compliance where you are required to use your keys for encrypting the data that you maange. By default, all objects that you store in COS are encrypted by using randomly generated keys and an all-or-nothing-transform (AONT).

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000303 | Check whether IBM Activity Tracker logs are encrypted at rest | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 31. Activity Tracker encryption at rest goal" caption-side="top"}

### Ensure Activity Tracker trails are integrated with LogDNA Logs 3.7
{: #activity-tracker-logdna-goals}

Ensure that Activity Tracker trails are integrated with LogDNA logs. If you fail to meet this control, you are prevented from managing long-term data, logs, and audit events from a common location. By default, archiving of events and logs is not enabled for any LogDNA instance.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000302 | Check whether IBM Activity Tracker trails are integrated with LogDNA logs | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 32. Activity Tracker and LogDNA logs integration goal" caption-side="top"}

## IBM Cloud Databases Family
{: #ibm-cloud-databases-controls}

The IBM Cloud Databases family is a selection of industry databases that run as a cloud-native service with a common consumption, security, and architectural model. With the IBM Cloud Databases family, you can implement and audit platform-level security control and it will be exactly the same across a variety of different database technology. The only difference would be changing the name of the requested resource to match your desired product. 

The databases that belong to the IBM Cloud Databases family are: Databases for PostgreSQL, Databases for MongoDB, Databases for Elasticsearch, Databases for RabbitMQ, Databases for Redis, Databases for etcd, Databases for EDB, and Databases for DataStax.

### Ensure IBM Cloud Databases disk encryption is enabled with customer managed keys 4.1
{: #ibm-cloud-databases-encryption-goals}

IBM Cloud Databases provides automatic encryption at rest when it is provisioning the service. You are able to bring your own encryption key at provision time for the database by using the service's integration with IBM Key Protect. If you do not bring your own encryption key at provision time, you are not able to cryptoshred the database or revoke the database's access to the encryption key, which renders it unable to boot storage. 

By default, when you are creating a deployment, IBM Cloud Databases manages the automatic disk and backup encryptio key.

| ID | Goal | Met by default |
| -- | ---- | ------------- | 
| 3000202 | Check whether Databases for MongoDB is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |   |
| 3000207 | Check whether Databases for Redis is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
| 3000212 | Check whether Databases for Elasticsearch is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |    | 
| 3000222 | Check whether Databases for PostgreSQL is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |    | 
{: caption="Table 33. Cloud Databases encryption goals" caption-side="top"}

### Ensure IBM Cloud Databases are only accessible via HTTPS or TLS Connections 4.2
{: #ibm-cloud-databases-https-access-goals}

If your organization uses IBM Cloud databases to store business-critical data, when these kinds of data are uploaded or accessed, keep the channel encrypted to ensure data cannot be accessed by a bad actor or incorrect entity. Only encrypted communication to the database is accepted. You can only connect to the IBM Cloud Databases services over TLS or HTTPS connections by default. 

| ID | Goal | Met by default |
| -- | ---- | ------------- | 
| 3000203 | Check whether Databases for MongoDB is accessible only through HTTPS | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000208 | Check whether Databases for Redis is accessible only through HTTPS | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| 3000213 | Check whether Databases for Elasticsearch is accessible only through HTTPS | ![Checkmark icon](../../icons/checkmark-icon.svg)   | 
| 3000223 | Check whether Databases for PostgreSQL is accessible only through HTTPS | ![Checkmark icon](../../icons/checkmark-icon.svg)  | 
{: caption="Table 34. Databases HTTPS or TLS connection goals" caption-side="top"}

### Ensure IBM Cloud Databases disk encryption is enabled 4.4
{: #ibm-cloud-databases-disk-encryption-goals}

The data that you store in IBM Cloud Databases need to be encrypted at rest at all times for client security. This process is done by default and no action is required on your part. 

| ID | Goal | Met by default |
| -- | ---- | ------------- | 
| 3000201 | Check whether Databases for MongoDB is enabled with encryption |   |
| 3000206 | Check whether Databases for Redis is enabled with encryption |  |
| 3000211 | Check whether Databases for Elasticsearch is enabled with encryption |    | 
| 3000221 | Check whether Databases for PostgreSQL is enabled with encryption |    | 
{: caption="Table 35. Data encryption goals" caption-side="top"}

## Cloudant
{: #cloudant-controls}

Cloudant is a database service in IBM Cloud. With Cloudant, you can store your application's data securely and retreve it quickly and efficiently. 

### Ensure Cloudant encryption is set to On 5.1
{: #cloudant-encryption-on-goals}

The data that you store in IBM Cloudant must be encrypted at rest at all times to enhance clience data security. This process is done by default and no action is required on your part.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000501 | Check whether Cloudant is enabled with encryption |   |
{: caption="Table 36. Cloudant encryption goal" caption-side="top"}

### Ensure IBM Cloudant encryption is enabled with customer managed keys 5.2
{: #cloudant-encryption-customer-goals}

If you are using a Dedicated Hardware plan instance, you have the option to use the service's integration with IBM Key Protect to bring your own encryption key at provision time for the instance. With the support of Bring Your Own Key (BYOK), you can manage the lifecycle of your customer root key where you can create, rotate, and delete those keys.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000502 | Check whether Cloudant is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |   |
{: caption="Table 37. Cloudant encryption BYOK goal" caption-side="top"}

### Ensure IBM Cloudant is only accessible via HTTPS or TLS Connections 5.3
{: #cloudant-encryption-customer-goals}

You can only connect to IBM Cloudant instances over TLS or HTTPS connections by default. No action is required on your part to ensure that all data in transit is encrypted. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000104 | Check whether Cloudant is accessible only through HTTPS |   |
{: caption="Table 38. Cloudant connections goal" caption-side="top"}

## Networking
{: #networking-controls}

Enhance your workflow by using IBM Cloud Internet Services and IBM Virtual Private Cloud.


### IBM Cloud Internet Services 6.1
{: #ibm-cloud-internet-goals}

With IBM Cloud Internet Services (CIS), powered by Cloudflare, you can enhance your workglow by using the service's three main capabilities: security, reliability, and performance.

#### Enable TLS 1.2 at minimum for all inbound traffic on IBM Cloud Internet Services proxy 6.1.1
{: #ibm-cloud-internet-goals}

Control whether visitors can browse your website over a secure connection with the Transport Layer Security (TLS) options. When they do, IBM Cloud Internet Services connects to your origin server. Ensure minimum TLS level for TLS termination is set to the most recent version of the protocol. TLS1.1 is considered obsolete and has some vulnerabilities. The default TLS mode is set to TLS1.2 for any TLS termination on Cloud Internet Services.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000403 | Check whether Cloud Internet Services (CIS) is configured with at least TLS v1.2 for all inbound traffic |   |
{: caption="Table 39. CIS TLS proxy goal" caption-side="top"}

#### Ensure Web application firewall is enabled in IBM Cloud Internet Services 6.1.2
{: #ibm-cloud-internet-goals}

With the IBM Cloud Internet Services Web Application Firewall, you can set up, manage, and customize security rules to protect your web applications from common web threats. With a Web Application Firewall, you can protect your web applications by filtering and monitoring HTTP traffic between a web application and the internet. By default, the Web Application Firewall's value is `off` in Cloud Internet Services.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000401 | Check whether Cloud Internet Services (CIS) has web application firewall enabled |   |
{: caption="Table 40. Web application firewall CIS goal" caption-side="top"}

#### Ensure DDoS protection is active on IBM Cloud Internet Services 6.1.3
{: #ibm-cloud-internet-goals}

The DNS records in Cloud Internet Services for any of your networks or applications that you have to protect mustbe proxied. Additionally, you must allowlist only IPs from the Cloud Internet Services on your application ingress points. Cloud Internet Services pprovides automatic DDoS protection for any proxied DNS records or a Range Application. By default, Proxy for all DNS records and GLBs are disabled.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000402 | Check whether Cloud Internet Services (CIS) has DDoS protection enabled|   |
{: caption="Table 41. DDoS protection goal" caption-side="top"}

### IBM Virtual Private Cloud 6.2
{: #ibm-virtual-private-cloud-profiles}

With IBM Cloud Virtual Private Cloud (VPC), you can quickly provision generation 2 virtual server instances for VPC with high network performance by using the UI, CLI, and API.

####  Ensure no VPC access control lists allow ingress from 0.0.0.0/0 to SSH port 6.2.1
{: #vpc-access-ingress-goals}

To reduce a server's exposure to risk, remove uncontrolled connectivity to remote console services, such as SSH. Ensure that no ACL allows unrestricted ingress access to port 22.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000441 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to SSH port |   |
{: caption="Table 42. VPC access ingress goal" caption-side="top"}

####  Ensure the default security group of every VPC restricts all traffic 6.2.2
{: #vpc-default-security-goals}

To reduce a server's exposure to risk, remove uncontrolled connectivity to a virtual server. No security group can allow unrestricted ingress access to a virtual server. Unless you modify it, the default security group allows inbound traffic from all other virtual servers that are attached to this security group.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000406 | Check whether Virtual Private Cloud (VPC) has no rules in the default security group |   |
{: caption="Table 43. Default security group restrictions goal" caption-side="top"}

####  Ensure no VPC security groups allow ingress from 0.0.0.0/0 to RDP port 6.2.3
{: #vpc-security-ingress-goals}

To reduce a server's exposure to risk, remove uncontrolled connectivity to remote console services, such as RDP. No security group can allow unrestricted ingress access to port 3389. There are no default rules in the default security group with a value of 3389.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000405 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to RDP port |   |
{: caption="Table 44. VPC security group restrictions" caption-side="top"}

####  Ensure no VPC security groups allow ingress from 0.0.0.0/0 to SSH port 6.2.4
{: #vpc-ingress-allow-goals}

To reduce a server's exposure to risk, remove uncontrolled connectivity to remote console services, such as SSH. No security group can allow unrestricted ingress access to port 22. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000404 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to SSH port |   |
{: caption="Table 45. VPC security group restrictions ingress to SSH goal" caption-side="top"}

####  Ensure no VPC access control lists allow ingress from 0.0.0.0/0 to RDP port 6.2.5
{: #vpc-ingress-access-goals}

To reduce a server's exposure to risk, remove uncontrolled connectivity to remote console services, such as RDP. VPC access control lists filter all incoming and outgoing traffic in IBM Cloud Virtual Private Cloud. No ACL can allow unrestricted ingress access to port 3389.  

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000442 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to RDP port |   |
{: caption="Table 46. VPC security group restrictions ingress to RDP goal" caption-side="top"}

## Containers
{: #containers-controls}

Enhance your workflow by using IBM Kubernetes service.

### IBM Kubernetes service 7.1
{: #kubernetes-service-profiles}

Deploy highly available containerized apps in Kubernetes clusers and use the powerful tools of IBM Cloud Kubernetes Service to automate, isolate, secure, manage, and monitor your workloads across zones or regions.

####  Ensure TLS 1.2 for all inbound traffic at Kubernetes service ingress 7.1.2
{: #tls-inbound-kubernetes-ingress-goals}

Ensure that all insecure (HTTP) client requests to applications and services that are hosted on IBM Cloud Kubernetes Service are redirected to secure TLS connections (HTTPS), and ensure that TLS versions 1.2+ are supported. By using this protocol, you can secure incoming requests to protect users from attack. 

It is recommended for you to set up IBM Cloud Kubernetes service to allow HTTPS. If you do not use this configuration, insecure HTTP requests are not converted into HTTPS by default and might expose unencrypted confidential information to the public.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000409 | Check whether Kubernetes Service Ingress is configured with at least TLS v1.2 for all inbound traffic |   |
{: caption="Table 47. TLS inbound traffic at Kubernetes goal" caption-side="top"}

####  Ensure Kubernetes service worker nodes are updated to the latest image to ensure patching of vulnerabilities 7.1.3
{: #kubernetes-nodes-vulnerabilities-goals}

Update the worker nodes in a cluster to the latest patch version so that security fixes are applied to those worker nodes. As security updates and patches are put in place for the API server and other master components, you must ensure that the worker modes remain in sync. By updating the patch version in a timely manner, you ensure patching of known vulnerabilities andkeep your worker nodes more secure. By default, worker nodes are not updated unless the user initiates an update. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000801 | Check whether Kubernetes Service worker nodes are updated to the latest image to ensure patching of vulnerabilities |   |
{: caption="Table 48. Kubernetes service worker nodes goal" caption-side="top"}

####  Ensure that clusters are accessible only by using private endpoints 7.1.4
{: #clusters-private-endpoints-goals}

Disable the public service endpoint so that communications to the master from both the worker nodes and cluster users is established over the private network through the private service endpoint. It is more secure and increasingly common for cloud consumers to want limited or no access to the public internet from any of their services.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000802 | Check whether Kubernetes Service clusters are accessible only by using private endpoints |   |
{: caption="Table 49. Cluster access through private endpoints goal" caption-side="top"}

####  Ensure clusters has image pull secrets enabled 7.1.5
{: #clusters-secrets-goals}

Image pull secrets are credentials that authorize your cluster to pull images from a private image registry. IBM Cloud Kubernetes Service clusters pull images from image registries to run containers.

Kubernetes service integrates with IBM Cloud Container Registry and provides pull secrets for IBM Cloud Container Registry in the `default` Kubernetes namespace. By default, image pull secrets are enabled unless the user that created the cluster did not have the required permissions for IBM Cloud Container Registry in IAM.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000803 | Check whether Kubernetes Service cluster has image pull secrets enabled |   |
{: caption="Table 50. Cluster image pull secrets goal" caption-side="top"}

####  Ensure clusters have the monitoring service enabled 7.1.6
{: #clusters-monitoring-goals}

Create a monitoring configuration to forward cluster and app metrics to IBM Cloud Monitoring with Sysdig by using the IBM Cloud Kubernetes observability plug-in. With IBM Cloud Monitoring with Sysdig, you can collect cluster and pod metrics, incoming and outgoing HTTP traffic for your pods, and data about several infrastructure components. IBM Cloud Monitoring with Sysdig is not configured by default.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000804 | Check whether Kubernetes Service clusters are enabled with IBM Cloud Monitoring |   |
{: caption="Table 51. Cluster monitoring service goal" caption-side="top"}

####  Ensure clusters have the logging service enabled 7.1.7
{: #clusters-logging-goals}

Create a logging configuration to forward cluster and app logs to IBM Log Analysis with LogDNA. With IBM Log Analysis with LogDNA, your organization's administrators, DevOps teams, and developers have access to advanced features to filter, search, and tail log data, define alerts, and design custom views to monitor application and system logs. By default, the logging service for collecting, forwarding, and viewing the logs is not enabled.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000805 | Check whether Kubernetes Service clusters are enabled with IBM Log Analysis |   |
{: caption="Table 52. Cluster logging service goal" caption-side="top"}

## Key Management
{: #key-management-controls}

Enhance your compliance to industry standards and cryptographic best practices.

### IBM Key Protect for IBM Cloud 8.1
{: #key-protect-profiles}

With IBM Key Protect for IBM Cloud, you can provision encrypted keys for appps across IBM Cloud services. You can create new keys for cryptography, or you can import your existing keys.

####  Ensure IBM Key Protect has automated rotation for customer managed keys enabled 8.1.1
{: #key-protect-automated-rotation-goals}

Set a rotation policy for a key or manually rotate the key. Key protect automatically replaces the root key with new key material when it's time to rotate the key based on the rotation interval that you specify. Rotate your keys regularly, for example every 30 days, to meet cryptographic best practices and meet industry standards. By default, IBM Cloud accounts customer master keys (CKMs) and data encryption keys (DEKs) depend on the account admin to set key rotation policy.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000230 | Check whether Key Protect encryption keys that are generated by the service are enabled with automatic rotation |   |
{: caption="Table 53. Key Protect rotation policy goal" caption-side="top"}

####  Ensure the IBM Key Protect service has high availability 8.1.2
{: #key-protect-high-availability-goals}

You can configure IBM Key Protect for IBM Cloud to provide high availability capabilities, such as IBM-owned infrastructure in multizone regions, to meet local access and low latency requirements for each supported region. You can also configure Key Portect to continuously backup keys in the region that the service where Key Protect operates and automatically recover and restart service components after any disaster event. By default, IBM Cloud Key Protect Service is ready, but not configured for high availability. You have the discretion to configure HA according to your needs. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000231 | Check whether Key Protect has high availability | [Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 54. Key Protect high availability goal" caption-side="top"}

## Security and Compliance
{: #security-compliance-controls}

You can embed security checks into your every day workflows to help monitor for security in compliance with IBM Cloud Security and Compliance Center. By monitoring for risks, you can identify security vulnerabilities and quickly work to mitigate the impact and fix the issue.

###  Ensure alerts are enabled for vulnerabilities discovered in container images in Container Registry 9.1
{: #container-registry-vulnerabilities-goals}

Enable alerts for critical, high, and medium vulnerabilities that are discovered in container images in Container Registry. When you receive these alerts, you can ensure that workload vulnerabilities are addressed in a timely manner and not deployed to a production environment. 

Additionally, you can instantly view the security posture of your IBM Cloud services through a single, centralized dashboard with IBM Cloud Security Advisor. With Container Registry, you have access to Vulnerability Advisor, which continuously scans the images in your Container Registry instance for potential security issues. By default, Vulnerability Advisor alerts are not configured for container images in Container Registry. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000602 | Check whether Security Insights sends alerts for critical, high, or medium vulnerabilities for images in Container Registry |   |
{: caption="Table 55. Vulnerabilities in container images goal" caption-side="top"}

## IBM Cloud Certificate Manager
{: #certificate-manager-controls}

With IBM Cloud Certificate Manager, you can securely manage the lifecycle of digital certificates and ensure certificates are valid and renewed before expiration. Certificate Manager provides you with an integrated experience with various components of IBM Cloud such as Kubernetes Service, API Gateway, VPC Load Balancer, Cloud Internet Services, Activity Tracker, and more.

###  Ensure certificates generated through IBM Cloud Certificate Manager are automatically renewed before expiration 10.1
{: #certificate-manager-renew-goals}

Ensure that your certificates are stored securely, and renewed before they expire to maintain high security posture. On the IBM Cloud Certificate Manager dashboard, you can manage certificates that you obtain from third-party issuers, or order form Certificate Manager, to use with your IBM cloud-based apps or services. You can renew certificates that you order through Certificate Manager automatically or manually. By default, auto-renew is turned off and certificates must be manually renewed.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000602 | Check whether Security Insights sends alerts for critical, high, or medium vulnerabilities for images in Container Registry |   |
{: caption="Table 56. Certificate renewal goal" caption-side="top"}

