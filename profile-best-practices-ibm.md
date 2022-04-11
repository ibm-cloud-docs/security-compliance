---

copyright:
  years: 2022
lastupdated: "2022-04-11"

keywords: best practices, security and compliance, governance, profile, predefined profiles, benchmark, controls, goals, security, compliance, ibm profiles, ibm best practices, best practices

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

# IBM Cloud Best Practices Controls 1.0
{: #ibm-best-practices}

xxxxxxx
{: shortdesc}

## Identity and Access Management
{: #iam-best-practices-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### Ensure IBMid password policy requires at least one uppercase letter 1.1
{: #ibmid-password-policy-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000001 | Check whether IBMid password policy requires at least one uppercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBMid password policy requires at least one lowercase letter 1.2
{: #ibmid-password-lowercase-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000002 | Check whether IBMid password policy requires at least one lowercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBMid password policy requires at least one number 1.3
{: #ibmid-password-number-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000003 | Check whether IBMid password policy requires at least one number | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBMid password policy requires minimum length of 12 characters 1.4
{: #ibmid-password-length-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000004 | Check whether IBMid password policy requires minimum length of 12 characters | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBMid password policy prevents password reuse below the minimum of # 1.5
{: #ibmid-password-reuse-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000005 | Check whether IBMid password policy prevents password reuse below the minimum of # | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBMid password contains only printable ASCII characters (in the range 33 - 126) 1.6
{: #ibmid-password-ascii-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000006 | Check whether IBMid password may contain only printable ASCII characters (in the range 33 - 126) | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBMid password password doesn't contain spaces or any of following characters: ;:(?)<>" 1.7
{: #ibmid-password-spaces-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000007 | Check whether IBMid password policy contains spaces or any of the following characters: \;:("?)<>) | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure the usage of a password meter that coaches users to create stronger passwords 1.8
{: #ibmid-password-strong-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000008 | Check whether IBMid uses a password meter that coaches users to create strong passwords that exceed the minimum requirements | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IAM roles are used to create IAM policies for IBM resources 1.9
{: #iam-roles-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000009 | Check whether IAM roles are used to create IAM policies for IBM resources | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure a support role has been assigned in IAM to manage cases in the IBM Cloud Support Center 1.10
{: #support-role-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000010 | Check whether a support role has been assigned in IAM to manage cases in the IBM Cloud Support Center | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure that IBM Cloud API keys are not created during the initial setup of IAM users 1.11
{: #api-key-setup-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000011 | Check whether API keys are not created in IAM during the initial setup of IAM users | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure that IBM Cloud API keys are not created during the initial setup of IAM users 1.12
{: #api-iam-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000012 | Check whether multifactor authentication (MFA) is enabled for each user at the user level |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure account has a contact email defined. Please verify manually 1.13
{: #email-verify-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000013 | Check whether account has a contact email defined |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

###  Ensure account has a contact phone number defined. Please verify manually 1.14
{: #phone-verify-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000014 | Check whether account has a contact phone number defined |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IAM users are attached to at least one access group 1.15
{: #iam-access-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000015 | Check whether IAM users are attached to at least one access group |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IAM policies are attached only to groups or roles 1.16
{: #iam-groups-goals}

xxxxxxxx

#### Ensure IAM policies for users are attached only to groups or roles 1.16.1
{: #iam-policies-roles-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000016 | Check whether IAM policies for users are attached only to groups or roles |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure IAM policies for service IDs are attached only to groups or roles 1.16.2
{: #iam-policies-service-id-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000030 | Check whether IAM policies for service IDs are attached only to groups or roles |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure multifactor authentication (MFA) is enabled at the account level 1.17
{: #mfa-account-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000017 | Check whether multifactor authentication (MFA) is enabled at the account level |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure multifactor authentication (MFA) is enabled for the account owner 1.18
{: #mfa-account-owner-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000018 | Check whether multifactor authentication (MFA) is enabled for the account owner |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure security questions are registered by the account owner 1.19
{: #security-questions-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000019 | Check whether security questions are registered by the account owner |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure authorized IP ranges are configured by the account owner 1.20
{: #authorized-ip-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000020 | Check whether authorized IP ranges are configured by the account owner |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure there are no more than # IAM administrators configured per account 1.21
{: #iam-administrators-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000021 | Check whether there are no more than # IAM administrators configured per account |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage public access is disabled in IAM settings (not applicable to ACLs managed using S3 APIs) 1.22
{: #iam-public-access-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000022 | Check whether Cloud Object Storage public access is disabled in IAM settings (not applicable to ACLs managed using S3 APIs)
 |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure the account owner does not have an IBM Cloud API key created in IAM 1.23
{: #api-key-owner-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000023 | Check whether the account owner does not have an IBM Cloud API key created in IAM |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Cloud API keys that are managed in IAM are rotated at least every # days 1.24
{: #api-key-rotated-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000024 | Check whether IBM Cloud API keys that are managed in IAM are rotated at least every # days |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure an account owner has logged in to IBM Cloud in the past # days 1.25
{: #owner-login-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000025 | Check whether an account owner has logged in to IBM Cloud in the past # days |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure an account owner has logged in to IBM Cloud in the past # days 1.25
{: #owner-login-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000025 | Check whether an account owner has logged in to IBM Cloud in the past # days |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure user list visibility restrictions are configured in IAM settings # days 1.26
{: #visibility-iam-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000026 | Check whether user list visibility restrictions are configured in IAM settings for the account owner |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure permissions for API key creation are limited and configured in IAM settings 1.27
{: #api-key-settings-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000027 | Check whether permissions for API key creation are limited and configured in IAM settings for the account owner |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure permissions for service ID creation are limited and configured in IAM settings 1.28
{: #service-id-settings-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000028 | Check whether permissions for service ID creation are limited and configured in IAM settings for the account owner |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure IAM-enabled services have no more than # users with the IAM administrator role 1.29
{: #iam-admin-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000029 | Check whether IAM-enabled services have no more than # users with the IAM administrator role |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure IAM-enabled services have no more than # service IDs with the IAM administrator role 1.30
{: #service-id-admin-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000032 | Check whether IAM-enabled services have no more than # service IDs with the IAM administrator role |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Hyper Protect Crypto Services have at least # users with the IAM manager role 1.31
{: #hyper-protect-manager-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000033 | Check whether Hyper Protect Crypto Services have at least # users with the IAM manager role |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Hyper Protect Crypto Services have at least # service IDs with the IAM manager role 1.32
{: #hyper-protect-service-id-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000034 | Check whether Hyper Protect Crypto Services have at least # service IDs with the IAM manager role |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure account service access is managed only by IAM access groups 1.33
{: #iam-access-groups-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000035 | Check whether account service access is managed only by IAM access groups |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure the EU supported setting is enabled in account settings 1.34
{: #eu-settings-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000036 | Check whether the EU supported setting is enabled in account settings |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure the HIPAA supported setting is enabled in account settings 1.35
{: #hipaa-settings-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000037 | Check whether the HIPAA supported setting is enabled in account settings |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Cloud Shell is enabled in account settings 1.36
{: #shell-settings-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000041 | Check whether Cloud Shell is enabled in account settings |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Cloud Shell has one or more locations enabled in account settings 1.37
{: #shell-locations-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000042 | Check whether Cloud Shell has one or more locations enabled in account settings |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Cloud Shell has the file upload and download features enabled in account settings 1.38
{: #shell-features-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000043 | Check whether Cloud Shell has the file upload and download features enabled in account settings |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Cloud Shell has the web preview feature enabled in account settings 1.39
{: #shell-preview-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000044 | Check whether Cloud Shell has the web preview feature enabled in account settings |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure the Financial Services Validated setting is enabled in account settings 1.40
{: #financial-setting-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000045 | Check whether the Financial Services Validated setting is enabled in account settings |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure audit logging is enabled for IBM Cloud IAM 1.41
{: #audit-logging-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000031 | Check whether Identity and Access Management (IAM) is enabled with audit logging |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Minimize the number of Service IDs with admin privileges in the account 1.42
{: #service-id-admin-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000038 | Check whether account has no more than # service IDs with admin privileges |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure API keys unused for 180 days are detected and optionally disabled 1.43
{: #api-key-detected-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000039 | Check whether IBM Cloud API keys that are unused for 180 days are detected and optionally disabled |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure inactive user accounts are suspended 1.44
{: #inactive-accounts-suspended-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000040 | Check whether inactive user accounts are suspended |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure inactive user accounts are suspended 1.44
{: #inactive-accounts-suspended-goals}

xxxxxxxx


| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000040 | Check whether inactive user accounts are suspended |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

## Data Protection
{: #data-protection-controls}

xxxxxxxxx

### Ensure Cloud Object Storage is enabled with encryption 2.1
{: #cloud-onject-storage-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000101 | Check whether Cloud Object Storage is enabled with encryption | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage is enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.2
{: #cloud-onject-storage-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000102 | Check whether Cloud Object Storage is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Certificate Manager certificates that are generated by the service are renewed automatically before they expire 2.3
{: #certificate-manager-renew-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000229 | Check whether Certificate Manager certificates that are generated by the service are renewed automatically before they expire |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloudant is accessible only through HTTPS 2.4
{: #cloudant-access-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000104 | Check whether Cloudant is accessible only through HTTPS |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage is accessible only through private endpoints HTTPS 2.5
{: #cloudant-private-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000105 | Check whether Cloud Object Storage is accessible only by using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage bucket access is restricted by using IAM and S3 access control 2.6
{: #bucket-access-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000106 | Check whether Cloud Object Storage bucket access is restricted by using IAM and S3 access control |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

###  Ensure Cloud Object Storage network access is restricted to a specific IP range 2.7
{: #network-access-ip-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000107 | Check whether Cloud Object Storage network access is restricted to a specific IP range |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage is enabled with customer-managed encryption and Keep Your Own Key (KYOK) 2.8
{: #customer-encrypt-kyok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000108 | Check whether Cloud Object Storage is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for MongoDB is enabled with encryption 2.9
{: #mongodb-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000201 | Check whether Databases for MongoDB is enabled with encryption |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for MongoDB is enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.10
{: #mongodb-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000202 | Check whether Databases for MongoDB is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for MongoDB is accessible only through HTTPS 2.11
{: #mongodb-https-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000203 | Check whether Databases for MongoDB is accessible only through HTTPS | ![Checkmark icon](../../icons/checkmark-icon.svg) |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for MongoDB is accessible only through private endpoints 2.12
{: #mongodb-private-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000204 | Check whether Databases for MongoDB is accessible only by using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Redis is enabled with encryption 2.13
{: #redis-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000206 | Check whether Databases for Redis is enabled with encryption |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Redis is enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.14
{: #redis-encrypt-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000207 | Check whether Databases for Redis is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Redis is accessible only through HTTPS 2.15
{: #redis-access-https-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000208 | Check whether Databases for Redis is accessible only through HTTPS | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Redis is accessible only through private endpoints 2.16
{: #redis-access-private-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000209 | Check whether Databases for Redis is accessible only by using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch encryption is enabled 2.17
{: #elasticsearch-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000211 | Check whether Databases for Elasticsearch is enabled with encryption |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch encryption is enabled with BYOK 2.18
{: #elasticsearch-encrypt-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000212 | Check whether Databases for Elasticsearch is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch encryption is enabled with BYOK 2.18
{: #elasticsearch-encrypt-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000212 | Check whether Databases for Elasticsearch is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch is accessible only through HTTPS 2.19
{: #elasticsearch-https-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000213 | Check whether Databases for Elasticsearch is accessible only through HTTPS | ![Checkmark icon](../../icons/checkmark-icon.svg) |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch is accessible only through private endpoints 2.20
{: #elasticsearch-private-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000214 | Check whether Databases for Elasticsearch is accessible only by using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for etcd is enabled with encryption 2.21
{: #etcd-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000216 | Check whether Databases for etcd is enabled with encryption |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for etcd is enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.22
{: #etcd-encrypt-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000217 | Check whether Databases for etcd is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

###  Ensure Databases for etcd is accessible only through HTTPS 2.23
{: #etcd-access-https-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000218 | Check whether Databases for etcd is accessible only through HTTPS | ![Checkmark icon](../../icons/checkmark-icon.svg) |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for etcd is accessible only through private endpoints 2.24
{: #etcd-private-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000219 | Check whether Databases for etcd is accessible only by using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for PostgreSQL is enabled with encryption 2.25
{: #postgresql-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000221 | Check whether Databases for PostgreSQL is enabled with encryption |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for PostgreSQL is enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.26
{: #postgresql-encrypt-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000222 | Check whether Databases for PostgreSQL is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for PostgreSQL is accessible only through HTTPS 2.27
{: #postgresql-https-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000223 | Check whether Databases for PostgreSQL is accessible only through HTTPS |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for PostgreSQL is accessible only through private endpoints 2.28
{: #postgresql-private-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000224 | Check whether Databases for PostgreSQL is accessible only by using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloudant is enabled with encryption 2.29
{: #cloudant-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000501 | Check whether Cloudant is enabled with encryption |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloudant is enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.30
{: #cloudant-encrypt-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000502 | Check whether Cloudant is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Block Storage for VPC OS disks are encrypted 2.31
{: #vpc-os-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000226 | Check whether Block Storage for VPC OS disks are encrypted |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Block Storage for VPC data disks are encrypted 2.32
{: #vpc-data-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000227 | Check whether Block Storage for VPC data disks are encrypted |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Block Storage for VPC unattached disks are encrypted 2.33
{: #vpc-unattached-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000228 | Check whether Block Storage for VPC unattached disks are encrypted |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for MongoDB network access is restricted to a specific IP range 2.34
{: #mongodb-network-ip-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000228 | Check whether Databases for MongoDB network access is restricted to a specific IP range |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Redis network access is restricted to specific IP range 2.35
{: #redis-network-ip-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000210 | Check whether Databases for Redis network access is restricted to specific IP range |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch network access is restricted to a specific IP range 2.36
{: #elasticsearch-network-ip-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000215 | Check whether Databases for Elasticsearch network access is restricted to a specific IP range |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for etcd network access is restricted to a specific IP range 2.37
{: #etcd-network-ip-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000220 | Check whether Databases for etcd network access is restricted to a specific IP range |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for PostgreSQL network access is restricted to a specific IP range 2.38
{: #postgresql-network-ip-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000225 | Check whether Databases for PostgreSQL network access is restricted to a specific IP range |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Key Protect encryption keys that are generated by the service are enabled with automatic rotation 2.39
{: #key-protect-encrypt-rotation-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000230 | Check whether Key Protect encryption keys that are generated by the service are enabled with automatic rotation |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Key Protect has high availability 2.40
{: #key-protect-high-availability-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000231 | Check whether Key Protect has high availability | ![Checkmark icon](../../icons/checkmark-icon.svg) |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Kubernetes Service is configured with role-based access control (RBAC) 2.41
{: #kubernetes-rbac-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000232 | Check whether Kubernetes Service is configured with role-based access control (RBAC) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect Crypto Services instance has at least # crypto units 2.42
{: #hyper-protect-units-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000233 | Check whether Hyper Protect Crypto Services instance has at least # crypto units |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect Crypto Services instance is enabled with a dual authorization deletion policy 2.43
{: #hyper-protect-units-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000234 | Check whether Hyper Protect Crypto Services instance is enabled with a dual authorization deletion policy |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect Crypto Services encryption keys are generated by the service are rotated automatically at least every # months 2.44
{: #hyper-protect-rotated-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000235 | Check whether Hyper Protect Crypto Services encryption keys that are generated by the service are rotated automatically at least every # months |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Bare Metal Servers that are ordered are configured for UEFI BIOS and Secure Boot 2.45
{: #uefi-bios-secure-boot-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000236 | Check whether Bare Metal Servers that are ordered are configured for UEFI BIOS and Secure Boot |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Bare Metal Servers include TPM/TXT modules 2.46
{: #tpm-txt-modules-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000237 | Check whether Bare Metal Servers include TPM/TXT modules |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

###  Ensure Bare Metal Servers have secure passwords and/or are configured with SSH keys 2.47
{: #bare-metal-ssh-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000238 | Check whether Bare Metal Servers have secure passwords and/or are configured with SSH keys |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

###  Ensure Bare Metal Servers do not allow remote administration over the public network 2.48
{: #bare-metal-remote-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000239 | Check whether Bare Metal Servers do not allow remote administration over the public network |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Bare Metal Servers are ordered with redundant power supplies to ensure workload protection 2.49
{: #bare-metal-workload-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000240 | Check whether Bare Metal Servers are ordered with redundant power supplies to ensure workload protection |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Bare Metal Servers are protected by a hardware firewall 2.50
{: #bare-metal-hardware-firewall-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000241 | Check whether Bare Metal Servers are protected by a hardware firewall |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Redis has no more than # users with the IAM administrator role 2.51
{: #redis-iam-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000242 | Check whether Databases for Redis has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for PostreSQL has no more than # users with the IAM administrator role 2.52
{: #postresql-iam-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000243 | Check whether Databases for PostreSQL has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for MongoDB has no more than # users with the IAM administrator role 2.53
{: #mongodb-iam-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000244 | Check whether Databases for MongoDB has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch has no more than # users with the IAM administrator role 2.54
{: #elasticsearch-iam-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000245 | Check whether Databases for Elasticsearch has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Cloudant has no more than # users with the IAM administrator role 2.55
{: #cloudant-iam-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000109 | Check whether Cloudant has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Key Protect has no more than # users with the IAM administrator role 2.56
{: #key-protect-iam-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000247 | Check whether Key Protect has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for etcd has no more than # users with the IAM administrator role 2.57
{: #etcd-iam-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000246 | Check whether Databases for etcd has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Kubernetes Service has no more than # users with the IAM administrator role 2.58
{: #kubernetes-iam-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000248 | Check whether Kubernetes Service has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for EnterpriseDB has no more than # users with the IAM administrator role 2.59
{: #enterprisedb-iam-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000249 | Check whether Databases for EnterpriseDB has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Block Storage for VPC is encrypted with customer-managed keys 2.60
{: #vpc-encrypt-customer-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000435 | Check whether Block Storage for VPC is encrypted with customer-managed keys |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Block Storage for VPC is enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.61
{: #vpc-encrypt-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000436 | Check whether Block Storage for VPC is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Block Storage for VPC is enabled with IBM Cloud Monitoring 2.62
{: #vpc-cloud-monitoring-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000250 | Check whether Block Storage for VPC is enabled with IBM Cloud Monitoring |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch has no more than # service IDs with the IAM administrator role 2.63
{: #elasticsearch-service-id-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000251 | Check whether Databases for Elasticsearch has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Key Protect has no more than # service IDs with the IAM administrator role 2.64
{: #key-protect-service-id-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000252 | Check whether Key Protect has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for etcd has no more than # service IDs with the IAM administrator role 2.65
{: #etcd-service-id-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000253 | Check whether Databases for etcd has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Kubernetes Service has no more than # service IDs with the IAM administrator role 2.66
{: #kubernetes-service-id-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000254 | Check whether Kubernetes Service has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for EnterpriseDB has no more than # service IDs with the IAM administrator role 2.67
{: #enterprisedb-service-id-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000255 | Check whether Databases for EnterpriseDB has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for MongoDB has no more than # service IDs with the IAM administrator role 2.68
{: #mongodb-service-id-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000312 | Check whether Databases for MongoDB has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Redis has no more than # service IDs with the IAM administrator role 2.69
{: #redis-service-id-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000313 | Check whether Databases for Redis has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for PostgreSQL has no more than # service IDs with the IAM administrator role 2.70
{: #postgresql-service-id-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000314 | Check whether Databases for PostgreSQL has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloudant has no more than # service IDs with the IAM administrator role 2.71
{: #cloudant-service-id-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000110 | Check whether Cloudant has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloudant has at least # users with the IAM manager role 2.72
{: #cloudant-users-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000111 | Check whether Cloudant has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloudant has at least # service IDs with the IAM manager role 2.73
{: #cloudant-service-id-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000112 | Check whether Cloudant has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID has at least # users with the IAM manager role 2.74
{: #appid-users-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000256 | Check whether App ID has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID has at least # service IDs with the IAM manager role 2.75
{: #appid-users-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000257 | Check whether App ID has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage has at least # users with the IAM manager role 2.76
{: #cloud-object-storage-users-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000258 | Check whether Cloud Object Storage has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage has at least # service IDs with the IAM manager role 2.77
{: #cloud-object-storage-serviceid-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000259 | Check whether Cloud Object Storage has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Event Streams has at least # users with the IAM manager role 2.78
{: #event-streams-users-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000260 | Check whether Event Streams has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Event Streams has at least # service IDs with the IAM manager role 2.79
{: #event-streams-service-id-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000261 | Check whether Event Streams has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure schematics has at least # users with the IAM manager role 2.80
{: #schematics-user-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000262 | Check whether Schematics has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure schematics has at least # service IDs with the IAM manager role 2.81
{: #schematics-service-id-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000263 | Check whether Schematics has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Transit Gateway has at least # users with the IAM manager role 2.82
{: #transit-gateway-users-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000264 | Check whether Transit Gateway has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Transit Gateway has at least # service IDs with the IAM manager role 2.83
{: #transit-gateway-service-id-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000265 | Check whether Transit Gateway has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Key Protect has at least # users with the IAM manager role 2.84
{: #key-protect-users-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000266 | Check whether Key Protect has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Key Protect has at least # service IDs with the IAM manager role 2.85
{: #key-protect-service-id-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000267 | Check whether Key Protect has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Kubernetes Service has at least # users with the IAM manager role 2.86
{: #kubernetes-users-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000268 | Check whether Kubernetes Service has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Kubernetes Service has at least # service IDs with the IAM manager role 2.87
{: #kubernetes-service-id-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000269 | Check whether Kubernetes Service has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Certificate Manager has at least # users with the IAM manager role 2.88
{: #certificate-manager-users-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000270 | Check whether Certificate Manager has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Certificate Manager has at least # service IDs with the IAM manager role 2.89
{: #certificate-manager-service-id-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000271 | Check whether Certificate Manager has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloudant service access is managed only by IAM access groups 2.90
{: #cloudant-access-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000113 | Check whether Cloudant service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Redis service access is managed only by IAM access groups 2.91
{: #redis-access-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000272 | Check whether Databases for Redis service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

###  Ensure Databases for PostgreSQL service access is managed only by IAM access groups 2.92
{: #postgresql-access-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000273 | Check whether Databases for PostgreSQL access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for MongoDB service access is managed only by IAM access groups 2.93
{: #mongodb-access-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000274 | Check whether Databases for MongoDB service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch service access is managed only by IAM access groups 2.94
{: #elasticsearch-access-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000275 | Check whether Databases for Elasticsearch service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for etcd service access is managed only by IAM access groups 2.95
{: #etcd-access-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000276 | Check whether Databases for etcd service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Key Protect service access is managed only by IAM access groups 2.96
{: #key-protect-access-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000277 | Check whether Key Protect service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Kubernetes Service access is managed only by IAM access groups 2.97
{: #kubernetes-access-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000278 | Check whether Kubernetes Service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for EnterpriseDB service access is managed only by IAM access groups 2.98
{: #enterprisedb-access-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000279 | Check whether Databases for EnterpriseDB service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage buckets are enabled with IBM Activity Tracker 2.99
{: #cloud-object-storage-activity-tracker-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000114 | Check whether Cloud Object Storage buckets are enabled with IBM Activity Tracker |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage buckets are enabled with IBM Cloud Monitoring 2.100
{: #cloud-object-storage-monitoring-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000115 | Check whether Cloud Object Storage buckets are enabled with IBM Cloud Monitoring |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage bucket resiliency is set to cross region 2.101
{: #cloud-object-storage-resiliency-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000116 | Check whether Cloud Object Storage bucket resiliency is set to cross region |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Schematics resources and actions must run in a designated location 2.102
{: #schematics-location-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000503 | Check whether Schematics resources and actions must run in a designated location |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Schematics is enabled with encryption 2.103
{: #schematics-encryption-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000504 | Check whether Schematics is enabled with encryption |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Schematics is enabled with IBM Log Analysis 2.104
{: #schematics-log-analysis-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000505 | Check whether Schematics is enabled with IBM Log Analysis |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Schematics has role-based access control (RBAC) for users 2.105
{: #schematics-access-control-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000506 | Check whether Schematics has role-based access control (RBAC) for users |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Schematics is enabled with IBM Cloud Monitoring 2.106
{: #schematics-monitoring-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000507 | Check whether Schematics is enabled with IBM Cloud Monitoring |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Schematics workspace is configured with a specific Terraform version 2.107
{: #schematics-terraform-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000508 | Check whether Schematics workspace is configured with a specific Terraform version |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Cloud Catalog is configured with limited provider options 2.108
{: #cloud-catalog-provider-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000509 | Check whether IBM Cloud Catalog is configured with limited provider options |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect Crypto Services is accessible only through private endpoints 2.109
{: #hyper-protect-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000510 | Check whether Hyper Protect Crypto Services is accessible only through private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for MongoDB backups are enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.110
{: #mongodb-encryption-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000511 | Check whether Databases for MongoDB backups are enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Redis backups are enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.111
{: #redis-encryption-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000512 | Check whether Databases for Redis backups are enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch backups are enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.112
{: #elasticsearch-encryption-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000513 | Check whether Databases for Elasticsearch backups are enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for etcd backups are enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.113
{: #elasticsearch-encryption-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000514 | Check whether Databases for etcd backups are enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for PostgreSQL backups are enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.114
{: #postgresql-encryption-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000515 | Check whether Databases for PostgreSQL backups are enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for MongoDB version is up-to-date 2.115
{: #mongodb-version-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000516 | Check whether Databases for MongoDB version is up-to-date |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Redis version is up-to-date 2.116
{: #redis-version-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000517 | Check whether Databases for Redis version is up-to-date |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch version is up-to-date 2.117
{: #elasticsearch-version-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000518 | Check whether Databases for Elasticsearch version is up-to-date |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for etcd version is up-to-date 2.118
{: #etcd-version-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000519 | Check whether Databases for etcd version is up-to-date |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for PostgreSQL version is up-to-date 2.119
{: #postgresql-version-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000520 | Check whether Databases for PostgreSQL version is up-to-date |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for MongoDB disk space autoscales to avoid database downtime 2.120
{: #mongodb-downtime-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000521 | Check whether Databases for MongoDB disk space autoscales to avoid database downtime |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Redis disk space autoscales to avoid database downtime 2.121
{: #redis-downtime-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000522 | Check whether Databases for Redis disk space autoscales to avoid database downtime |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for Elasticsearch disk space autoscales to avoid database downtime 2.122
{: #elasticsearch-downtime-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000523 | Check whether Databases for Elasticsearch disk space autoscales to avoid database downtime |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for etcd disk space autoscales to avoid database downtime 2.123
{: #etcd-downtime-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000524 | Check whether Databases for etcd disk space autoscales to avoid database downtime |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Databases for PostgreSQL disk space autoscales to avoid database downtime 2.124
{: #postgresql-downtime-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000525 | Check whether Databases for PostgreSQL disk space autoscales to avoid database downtime |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for MongoDB is accessible only using private endpoints 2.125
{: #mongodb-enpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000526 | Check whether Hyper Protect DBaaS for MongoDB is accessible only using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for MongoDB is enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.126
{: #mongodb-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000527 | Check whether Hyper Protect DBaaS for MongoDB is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for MongoDB is enabled with customer-managed encryption and Keep Your Own Key (KYOK) 2.127
{: #mongodb-kyok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000528 | Check whether Hyper Protect DBaaS for MongoDB is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for MongoDB has no more than # users with the IAM administrator 2.128
{: #mongodb-hyper-protect-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000529 | Check whether Hyper Protect DBaaS for MongoDB has no more than # users with the IAM administrator |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for MongoDB has no more than # service IDs with the IAM administrator role 2.129
{: #mongodb-iam-administrator-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000530 | Check whether Hyper Protect DBaaS for MongoDB has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for MongoDB has at least # users with the IAM manager role 2.130
{: #mongodb-iam-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000531 | Check whether Hyper Protect DBaaS for MongoDB has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for MongoDB has at least # service IDs with the IAM manager role 2.131
{: #mongodb-service-id-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000532 | Check whether Hyper Protect DBaaS for MongoDB has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for MongoDB service access is managed only by IAM access groups 2.132
{: #mongodb-access-groups-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000533 | Check whether Hyper Protect DBaaS for MongoDB service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for PostgreSQL is accessible only using private endpoints 2.133
{: #postgresql-private-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000534 | Check whether Hyper Protect DBaaS for PostgreSQL is accessible only using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for PostgreSQL is enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.134
{: #postgresql-customer-encryption-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000535 | Check whether Hyper Protect DBaaS for PostgreSQL is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for PostgreSQL is enabled with customer-managed encryption and Keep Your Own Key (KYOK) 2.135
{: #postgresql-customer-encryption-kyok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000536 | Check whether Hyper Protect DBaaS for PostgreSQL is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for PostgreSQL has no more than # users with the IAM administrator 2.136
{: #postgresql-administrator-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000537 | Check whether Hyper Protect DBaaS for PostgreSQL has no more than # users with the IAM administrator |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for PostgreSQL has no more than # service IDs with the IAM administrator role 2.137
{: #postgresql-id-iam-administrator-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000538 | Check whether Hyper Protect DBaaS for PostgreSQL has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for PostgreSQL has at least # users with the IAM manager role 2.138
{: #postgresql-user-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000539 | Check whether Hyper Protect DBaaS for PostgreSQL has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for PostgreSQL has at least # service IDs with the IAM manager role 2.139
{: #postgresql-id-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000540 | Check whether Hyper Protect DBaaS for PostgreSQL has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Hyper Protect DBaaS for PostgreSQL service access is managed only by IAM access groups 2.140
{: #postgresql-iam-access-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000541 | Check whether Hyper Protect DBaaS for PostgreSQL service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Key Protect is accessible only by using private endpoints 2.141
{: #key-protect-private-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000542 | Check whether Key Protect is accessible only by using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure dual authorization for deletion of all keys in a Key Protect instance is enabled 2.142
{: #key-protect-deletion-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000543 | Check whether dual authorization for deletion of all keys in a Key Protect instance is enabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure all encryption root key material is imported into Key Protect using an import token 2.143
{: #key-protect-import-token-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000544 | Check whether dual authorization for deletion of all keys in a Key Protect instance is enabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Key Protect is enabled with IBM Cloud Monitoring 2.144
{: #key-protect-monitoring-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000544 | Check whether all encryption root key material is imported into Key Protect using an import token |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Block Storage Snapshots for VPC is enabled with customer-managed encryption and Bring Your Own Key (BYOK) 2.145
{: #block-storage-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000280 | Check whether Block Storage Snapshots for VPC is enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Block Storage Snapshots for VPC is in a resource group other than "Default" 2.146
{: #block-storage-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000281 | Check whether Block Storage Snapshots for VPC is in a resource group other than "Default" |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage quota enforcement is enabled for buckets that are configured to use Activity Tracker event routing 2.147
{: #cloud-object-storage-activity-tracker-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000282 | Check whether Cloud Object Storage quota enforcement is enabled for buckets that are configured to use Activity Tracker event routing |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage buckets with a quota have threshold-based alerts enabled 2.148
{: #cloud-object-storage-alerts-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000283 | Check whether Cloud Object Storage buckets with a quota have threshold-based alerts enabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Object Storage buckets are located in only authorized regions 2.149
{: #cloud-object-storage-regions-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000284 | Check whether Cloud Object Storage buckets are located in only authorized regions |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

## Monitoring and Audit Logging
{: #monitoring-audit-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### Ensure IBM Activity Tracker is provisioned in multiple regions in an account 3.1
{: #activity-tracker-regions-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000301 | Check whether IBM Activity Tracker is provisioned in multiple regions in an account |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Activity Tracker trails are integrated with LogDNA logs 3.2
{: #activity-tracker-logdna-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000302 | Check whether IBM Activity Tracker trails are integrated with LogDNA logs | ![Checkmark icon](../../icons/checkmark-icon.svg) |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Activity Tracker logs are encrypted at rest 3.3
{: #activity-tracker-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000303 | Check whether IBM Activity Tracker logs are encrypted at rest | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Cloud Monitoring has no more than # users with the IAM administor role 3.4
{: #monitoring-administrator-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000304 | Check whether IBM Cloud Monitoring has no more than # users with the IAM administor role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Activity Tracker has no more than # users with the IAM administrator role 3.5
{: #activity-tracker-administrator-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000308 | Check whether IBM Activity Tracker has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Activity Tracker has no more than # service IDs with the IAM administrator role 3.6
{: #activity-tracker-service-id-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000309 | Check whether IBM Activity Tracker has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Cloud Monitoring has no more than # service IDs with the IAM administrator role 3.7
{: #cloud-monitoring-service-id-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000310 | Check whether IBM Cloud Monitoring has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Block Storage for VPC is enabled with IBM Activity Tracker 3.8
{: #block-storage-vpc-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000310 | Check whether IBM Cloud Monitoring has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Cloud Internet Services (CIS) has at least # users with the IAM manager role 3.9
{: #cis-users-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000315 | Check whether IBM Cloud Internet Services (CIS) has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Cloud Internet Services (CIS) has at least # service IDs with the IAM manager role 3.10
{: #cis-service-id-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000316 | Check whether IBM Cloud Internet Services (CIS) has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Activity Tracker has at least # users with the IAM manager role 3.11
{: #activity-tracker-users-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000317 | Check whether IBM Activity Tracker has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Activity Tracker has at least # service IDs with the IAM manager role 3.12
{: #activity-tracker-service-id-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000318 | Check whether IBM Activity Tracker has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Cloud Monitoring service access is managed only by IAM access groups 3.13
{: #monitoring-iam-access-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000319 | Check whether IBM Cloud Monitoring service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure IBM Activity Tracker service access is managed only by IAM access groups 3.14
{: #activity-tracker-access-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000320 | Check whether IBM Activity Tracker service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

## Networking
{: #networking-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### Ensure Cloud Internet Services (CIS) has web application firewall enabled 4.1
{: #cis-firewall-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000401 | Check whether Cloud Internet Services (CIS) has web application firewall enabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Internet Services (CIS) has DDoS protection enabled 4.2
{: #cis-ddos-protection-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000402 | Check whether Cloud Internet Services (CIS) has DDoS protection enabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Internet Services (CIS) is configured with at least TLS v1.2 for all inbound traffic 4.3
{: #cis-tls-traffic-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000403 | Check whether Cloud Internet Services (CIS) is configured with at least TLS v1.2 for all inbound traffic |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

###  Ensure Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to SSH port 4.4
{: #vpc-source-ip-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000404 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to SSH port |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

###  Ensure Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to RDP port 4.5
{: #vpc-rdp-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000405 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to RDP port |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) has no rules in the default security group 4.6
{: #vpc-security-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000406 | Check whether Virtual Private Cloud (VPC) has no rules in the default security group |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) is configured with at least TLS v1.2 for all inbound traffic through a load balancer 4.7
{: #vpc-tls-inbound-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000407 | Check whether Virtual Private Cloud (VPC) is configured with at least TLS v1.2 for all inbound traffic through a load balancer |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Flow Logs for VPC are enabled 4.8
{: #vpc-flow-logs-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000408 | Check whether Flow Logs for VPC are enabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Kubernetes Service Ingress is configured with at least TLS v1.2 for all inbound traffic 4.9
{: #kubernetes-tls-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000409 | Check whether Kubernetes Service Ingress is configured with at least TLS v1.2 for all inbound traffic |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) security groups have no inbound ports open to the internet (0.0.0.0/0) 4.10
{: #vpc-inbound-ports-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000410 | Check whether Virtual Private Cloud (VPC) security groups have no inbound ports open to the internet (0.0.0.0/0) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) security groups have no outbound ports open to the internet (0.0.0.0/0) 4.11
{: #vpc-outbound-ports-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000411 | Check whether Virtual Private Cloud (VPC) security groups have no outbound ports open to the internet (0.0.0.0/0) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure all virtual server instances have at least one Virtual Private Cloud (VPC) security group attached 4.12
{: #vpc-virtual-server-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000412 | Check whether all virtual server instances have at least one Virtual Private Cloud (VPC) security group attached |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure all network interfaces of a virtual server instance have at least one Virtual Private Cloud (VPC) security group attached 4.13
{: #vpc-virtual-server-security-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000413 | Check whether all network interfaces of a virtual server instance have at least one Virtual Private Cloud (VPC) security group attached |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure all network interfaces of a virtual server instance have at least one Virtual Private Cloud (VPC) security group attached 4.13
{: #vpc-virtual-server-security-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000413 | Check whether all network interfaces of a virtual server instance have at least one Virtual Private Cloud (VPC) security group attached |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Direct Link (2.0) allows no cross account connection approvals at the account level 4.14
{: #direct-link-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000414 | Check whether Direct Link (2.0) allows no cross account connection approvals at the account level |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Direct Link (2.0) allows no cross account connection requests at the account level 4.15
{: #direct-account-level-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000415 | Check whether Direct Link (2.0) allows no cross account connection requests at the account level |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Transit Gateway allows no cross account connection approvals at the account level 4.16
{: #transit-gateway-level-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000416 | Check whether Transit Gateway allows no cross account connection approvals at the account level |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Transit Gateway allows no cross account connection requests at the account level 4.17
{: #transit-gateway-connection-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000417 | Check whether Transit Gateway allows no cross account connection requests at the account level |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure account has at least one VPN or Direct Link configured 4.18
{: #vpn-direct-link-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000418 | Check whether account has at least one VPN or Direct Link configured |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure VPN for VPC has Internet Key Exchange (IKE) policy encryption that is not set to 'triple_des' 4.19
{: #vpn-vpc-ike-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000419 | Check whether VPN for VPC has Internet Key Exchange (IKE) policy encryption that is not set to "triple_des" |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure VPN for VPC has Internet Key Exchange (IKE) policy authentication that is set to minimum 'sha256' 4.20
{: #vpc-ike-auth-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000420 | Check whether VPN for VPC has Internet Key Exchange (IKE) policy authentication that is set to minimum "sha256" |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure VPN for VPC has a Diffie-Hellman group set to at least group # 4.21
{: #vpc-vpn-group-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000421 | Check whether VPN for VPC has a Diffie-Hellman group set to at least group # |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure VPN for VPC has IPsec policy encryption that is not set to 'triple_des' 4.22
{: #vpc-vpn-ipsec-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000422 | Check whether VPN for VPC has IPsec policy encryption that is not set to "triple_des" |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure VPN for VPC has IPsec policy authentication that is set to minimum 'sha256' 4.23
{: #vpc-vpn-auth-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000423 | Check whether VPN for VPC has IPsec policy authentication that is set to minimum "sha256" |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure VPN for VPC has an IPsec policy that does not have Perfect Forward Secrecy (PFS) disabled 4.24
{: #vpc-vpn-pfs-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000424 | Check whether VPN for VPC has an IPsec policy that does not have Perfect Forward Secrecy (PFS) disabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure VPN for VPC authentication is configured with a strong pre-shared key with at least # alphanumeric characters 4.25
{: #vpc-authentication-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000425 | Check whether VPN for VPC authentication is configured with a strong pre-shared key with at least # alphanumeric characters |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure VPN for VPC has a Dead Peer Detection policy that is set to 'restart' 4.26
{: #vpc-vpn-detection-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000426 | Check whether VPN for VPC has a Dead Peer Detection policy that is set to "restart" |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Block Storage for VPC is enabled with customer-managed encryption and Keep Your Own Key (KYOK) 4.27
{: #vpc-block-storage-kyok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000437 | Check whether Block Storage for VPC is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC has public access disabled 4.28
{: #vpc-load-balancer-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000427 | Check whether Application Load Balancer for VPC has public access disabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC is configured with multiple members in the pool 4.29
{: #vpc-load-balancer-pool-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000428 | Check whether Application Load Balancer for VPC is configured with multiple members in the pool |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC listener is configured with default pool 4.30
{: #vpc-load-balancer-listener-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000429 | Check whether Application Load Balancer for VPC listener is configured with default pool |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC has health check configured when created 4.31
{: #vpc-load-balancer-health-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000430 | Check whether Application Load Balancer for VPC has health check configured when created |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC has a health check protocol that is either HTTP or HTTPS 4.32
{: #vpc-load-balancer-http-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000431 | Check whether Application Load Balancer for VPC has a health check protocol that is either HTTP or HTTPS |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC pool uses the HTTPS protocol for HTTPS listeners 4.33
{: #vpc-load-balancer-https-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000432 | Check whether Application Load Balancer for VPC pool uses the HTTPS protocol for HTTPS listeners |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC is configured to convert HTTP client requests to HTTPS 4.34
{: #vpc-load-balancer-convert-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000433 | Check whether Application Load Balancer for VPC is configured to convert HTTP client requests to HTTPS |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC uses HTTPS (SSL & TLS) instead of HTTP 4.35
{: #vpc-load-balancer-ssl-tls-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000434 | Check whether Application Load Balancer for VPC uses HTTPS (SSL & TLS) instead of HTTP |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Security Groups for VPC contains no outbound rules in security groups that specify source IP 8.8.8.8/32 to DNS port 4.36
{: #vpc-security-groups-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000444 | Check whether Security Groups for VPC contains no outbound rules in security groups that specify source IP 8.8.8.8/32 to DNS port |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Security Groups for VPC doesn't allow SSH for the default security group 4.37
{: #vpc-ssh-security-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000445 | Check whether Security Groups for VPC doesn't allow SSH for the default security group |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Security Groups for VPC doesn't allow PING for the default security group 4.38
{: #vpc-default-security-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000446 | Check whether Security Groups for VPC doesn't allow PING for the default security group |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) classic access is disabled 4.39
{: #vpc-classic-access-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000447 | Check whether Virtual Private Cloud (VPC) classic access is disabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) has no public gateways attached at the time of provisioning 4.40
{: #vpc-public-gateway-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000448 | Check whether Virtual Private Cloud (VPC) has no public gateways attached at the time of provisioning |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) has no public gateways attached 4.41
{: #vpc-public-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000449 | Check whether Virtual Private Cloud (VPC) has no public gateways attached |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to any port 4.42
{: #vpc-ingress-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000451 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to any port |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to SSH port 4.43
{: #vpc-ingress-ssh-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000451 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to any port |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to RDP port 4.44
{: #vpc-ingress-rdp-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000442 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to RDP port |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) network access control lists don't allow egress from 0.0.0.0/0 to any port 4.45
{: #vpc-egress-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000452 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow egress from 0.0.0.0/0 to any port |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Servers for VPC instance has the minimum # interfaces 4.46
{: #virtual-servers-vpc-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000453 | Check whether Virtual Servers for VPC instance has the minimum # interfaces |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Servers for VPC instance doesn't have a floating IP 4.47
{: #vpc-floating-ip-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000454 | Check whether Virtual Servers for VPC instance doesn't have a floating IP |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Servers for VPC instance has all interfaces with IP-spoofing disabled 4.48
{: #vpc-spoofing-ip-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000455 | Check whether Virtual Servers for VPC instance has all interfaces with IP-spoofing disabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Servers for VPC resource group other than "Default" is selected 4.49
{: #vpc-resource-group-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000456 | Check whether Virtual Servers for VPC is in a resource group other than "Default" |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Servers for VPC boot volumes are enabled with customer-managed encryption and Bring Your Own Key (BYOK) 4.50
{: #vpc-encrypt-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000457 | Check whether Virtual Servers for VPC boot volumes are enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Servers for VPC boot volumes are enabled with customer-managed encryption and Keep Your Own Key (KYOK) 4.51
{: #vpc-encrypt-kyok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000458 | Check whether Virtual Servers for VPC boot volumes are enabled with customer-managed encryption and Keep Your Own Key (KYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Servers for VPC data volumes are enabled with customer-managed encryption and Bring Your Own Key (BYOK) 4.52
{: #vpc-data-volumes-byok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000459 | Check whether Virtual Servers for VPC data volumes are enabled with customer-managed encryption and Bring Your Own Key (BYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Servers for VPC data volumes are enabled with customer-managed encryption and Keep Your Own Key (KYOK) 4.53
{: #vpc-data-volumes-kyok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000460 | Check whether Virtual Servers for VPC data volumes are enabled with customer-managed encryption and Keep Your Own Key (KYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Servers for VPC is provisioned from an encrypted image 4.54
{: #vpc-encrypt-image-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000461 | Check whether Virtual Servers for VPC is provisioned from an encrypted image |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Servers for VPC is provisioned from customer-defined list of images 4.55
{: #vpc-provision-image-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000462 | Check whether Virtual Servers for VPC is provisioned from customer-defined list of images |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Servers for VPC instances are identifable by the workload they are running based on the Auto Scale for VPC instance group definition 4.56
{: #vpc-auto-scale-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000463 | Check whether Virtual Servers for VPC instances are identifable by the workload they are running based on the Auto Scale for VPC instance group definition |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC has application port of the workload that is identifiable by the Auto Scale for VPC instance group definition 4.57
{: #vpc-auto-scale-instance-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000464 | Check whether Application Load Balancer for VPC has application port of the workload that is identifiable by the Auto Scale for VPC instance group definition |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC has subnet identifiers of the workload that are identifiable by the Auto Scale for VPC instance group definition 4.58
{: #vpc-subnet-instance-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000465 | Check whether Application Load Balancer for VPC has subnet identifiers of the workload that are identifiable by the Auto Scale for VPC instance group definition |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC is attached with an Auto Scale for VPC instance group provided with health check 4.59
{: #vpc-auto-scale-check-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000466 | Check whether Application Load Balancer for VPC is attached with an Auto Scale for VPC instance group provided with health check |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) has no subnet with public gateway attached 4.60
{: #vpc-auto-scale-check-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000467 | Check whether Virtual Private Cloud (VPC) has no subnet with public gateway attached |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Virtual Private Cloud (VPC) is configured with public gateways that are provisionable only within permitted zones 4.61
{: #vpc-public-gateway-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000468 | Check whether Virtual Private Cloud (VPC) is configured with public gateways that are provisionable only within permitted zones |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Application Load Balancer for VPC is configured with at least one VPC security group 4.62
{: #vpc-security-group-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000469 | Check whether Application Load Balancer for VPC is configured with at least one VPC security group |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Cloud Internet Services (CIS) has TLS mode set to End-to-End CA signed 4.63
{: #cis-tls-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000470 | Check whether Cloud Internet Services (CIS) has TLS mode set to End-to-End CA signed |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Block Storage is encrypted with KYOK 4.64
{: #block-storage-kyok-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000437 | Check whether Block Storage for VPC is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure data disks are encrypted with customer managed keys 4.65
{: #data-disk-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000439 | Check whether data disks are encrypted with customer-managed keys |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure unattached disks are encrypted with customer managed keys 4.66
{: #unattached-data-disk-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000440 | Check whether unattached disks are encrypted with customer-managed keys |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure there are at least at least # Virtual Private Cloud virtual servers in the account 4.67
{: #vpc-account-servers-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000471 | Check whether there are at least # Virtual Private Cloud virtual servers in the account |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure there are at least at least # Transit Gateways in the account 4.68
{: #transit-gateway-account-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000472 | Check whether there are at least # transit gateways configured in Transit Gateway |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

## Vulnerability Management
{: #vulnerability-management-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### Ensure Container Registry Vulnerabity Advisor scans for critical or high vulnerabilities in the system at least every # day(s) 5.1
{: #container-registry-vulnerabilities-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000601 | Check whether Container Registry Vulnerability Advisor scans for critical or high vulnerabilities in the system at least every # day(s)|  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Security Insights sends alerts for critical, high, or medium vulnerabilities for images in Container Registry 5.2
{: #security-insights-alerts-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000602 | Check whether Security Insights sends alerts for critical, high, or medium vulnerabilities for images in Container Registry |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Container Registry has no more than # users with the IAM administrator role 5.3
{: #container-registry-admin-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000623 | Check whether Container Registry has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Container Registry image pushes and pulls take place only over private endpoints 5.4
{: #container-registry-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000625 | Check whether Container Registry image pushes and pulls take place only over private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Container Registry IAM access controls are configured for account 5.5
{: #container-registry-access-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000626 | Check whether Container Registry IAM access controls are configured for account |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Container Registry is enabled with IBM Cloud Monitoring 5.6
{: #container-registry-monitoring-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000627 | Check whether Container Registry is enabled with IBM Cloud Monitoring |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Container Registry has no more than # service IDs with the IAM administrator role 5.7
{: #container-registry-service-id-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000628 | Check whether Container Registry has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Container Registry has at least # users with the IAM manager role 5.8
{: #container-registry-users-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000635 | Check whether Container Registry has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Container Registry has at least # service IDs with the IAM manager role 5.9
{: #container-registry-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000636 | Check whether Container Registry has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Container Registry service access is managed only by IAM access groups 5.10
{: #container-registry-access-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000639 | Check whether Container Registry service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

## Continuous compliance
{: #continuous-compliance-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### Ensure Toolchain scans during continuous integration the source code to identify vulnerabilities 6.1
{: #toolchain-vulnerabilities-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000603 | Check whether Toolchain scans during continuous integration the source code to identify vulnerabilities |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Toolchain has unit tests that are continuously run to validate source code changes 6.2
{: #toolchain-code-changes-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000604 | Check whether Toolchain has unit tests that are continuously run to validate source code changes |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Toolchain has Code Risk Analyzer configured that collects a bill of materials for pipeline run 6.3
{: #toolchain-code-risk-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000605 | Check whether Toolchain has Code Risk Analyzer configured that collects a bill of materials for pipeline run |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Toolchain is configured with image signing 6.4
{: #toolchain-image-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000606 | Check whether Toolchain is configured with image signing |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Toolchain source code meets Center for Internet Security Docker benchmarks 6.5
{: #toolchain-docker-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000607 | Check whether Toolchain source code meets Center for Internet Security Docker benchmarks |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Toolchain has branch protection rules enabled 6.6
{: #toolchain-protection-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000608 | Check whether Toolchain has branch protection rules enabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Toochain has secret detection scans enabled for source code 6.7
{: #toolchain-secret-detection-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000609 | Check whether Toochain has secret detection scans enabled for source code |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Toolchain production change request exists and is approved 6.8
{: #toolchain-production-change-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000610 | Check whether Toolchain production change request exists and is approved |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Container Registry Vulnerability Advisor scans images for OS vulnerability detection 6.9
{: #toolchain-vulnerability-advisor-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000611 | Check whether Container Registry Vulnerability Advisor scans images for OS vulnerability detection |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Toolchain has no more than # users with the IAM administrator role 6.10
{: #toolchain-administrator-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000622 | Check whether Toolchain has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Toolchain has no more than # service IDs with the IAM administrator role 6.11
{: #toolchain-administrator-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000629 | Check whether Toolchain has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Toolchain acceptance tests exist and have passed 6.12
{: #toolchain-acceptance-tests-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000624 | Check whether Toolchain acceptance tests exist and have passed |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Continuous Delivery has at least # users with the IAM manager role 6.13
{: #continuous-delivery-user-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000633 | Check whether Continuous Delivery has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Continuous Delivery has at least # service IDs with the IAM manager role 6.14
{: #continuous-delivery-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000634 | Check whether Continuous Delivery has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Toolchain service access is managed only by IAM access groups 6.15
{: #toolchain-access-group-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000638 | Check whether Toolchain service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure that only the tool integrations within the toolchain are included in the allow list parameter array 6.16
{: #toolchain-integrations-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000640 | Check whether only the tool integrations within the toolchain are included in the allow list parameter array |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

## Secrets Manager
{: #secrets-manager-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### Ensure Secrets Manager arbitrary secrets are not expired 7.1
{: #secrets-arbitrary-expire-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000612 | Check whether Secrets Manager arbitrary secrets are not expired |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Secrets Manager user credentials are not expired 7.2
{: #secrets-user-credentials-expire-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000613 | Check whether Secrets Manager user credentials are not expired |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure all Secret Manager IAM API keys managed by secrets manager have not expired 7.3
{: #secrets-iam-api-expire-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000614 | Check whether all Secret Manager IAM API keys managed by secrets manager have not expired |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Secrets Manager is provisioned in authorized regions only 7.4
{: #secrets-regions-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000615 | Check whether Secrets Manager is provisioned in authorized regions only |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Secrets Manager default secret group contains no secrets 7.5
{: #secrets-default-group-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000616 | Check whether Secrets Manager default secret group contains no secrets |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Secrets Manager arbitrary secrets are rotated at least every # days 7.6
{: #secrets-rotated-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000617 | Check whether Secrets Manager arbitrary secrets are rotated at least every # days |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Secrets Manager user credentials are rotated at least every # days 7.7
{: #secrets-arbitrary-rotated-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000618 | Check whether Secrets Manager user credentials are rotated at least every # days |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Secrets Manager IAM credentials are rotated at least every # days 7.8
{: #secrets-iam-credentials-rotated-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000619 | Check whether Secrets Manager IAM credentials are rotated at least every # days |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Secrets Manager instance contains no empty secret groups 7.9
{: #secrets-empty-group-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000620 | Check whether Secrets Manager instance contains no empty secret groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Secrets Manager has no more than # users with the IAM administrator role 7.10
{: #secrets-iam-administrator-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000621 | Check whether Secrets Manager has no more than # users with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Secrets Manager has no more than # service IDs with the IAM administrator role 7.11
{: #secrets-iam-administrator-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000630 | Check whether Secrets Manager has no more than # service IDs with the IAM administrator role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Secrets Manager has at least # users with the IAM manager role 7.12
{: #secrets-iam-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000631 | Check whether Secrets Manager has at least # users with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Secrets Manager has at least # service IDs with the IAM manager role 7.13
{: #secrets-service-id-manager-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000632 | Check whether Secrets Manager has at least # service IDs with the IAM manager role |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

### Ensure Secrets Manager service access is managed only by IAM access groups 7.14
{: #secrets-iam-access-groups-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000637 | Check whether Secrets Manager service access is managed only by IAM access groups |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"

## App ID
{: #appid-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### Ensure App ID webhooks are using HTTPS only 8.1
{: #appid-webhooks-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000701 | Check whether App ID webhooks are using HTTPS only |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID email dispatchers are using HTTPS only 8.2
{: #appid-dispatchers-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000702 | Check whether App ID email dispatchers are using HTTPS only |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID redirect URIs are using HTTPS only 8.3
{: #appid-redirect-uri-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000703 | Check whether App ID redirect URIs are using HTTPS only |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID redirect URIs are not using localhost or 127.0.0.1  8.4
{: #appid-redirect-uri-localhost-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000704 | Check whether App ID redirect URIs are not using localhost or 127.0.0.1 |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID redirect URIs are not using wildcards (*) 8.5
{: #appid-redirect-uri-wildcards-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000705 | Check whether App ID redirect URIs are not using wildcards (*) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID user data is encrypted 8.6
{: #appid-data-encrypt-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000706 | Check whether App ID user data is encrypted |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID user profile updates from client apps is disabled 8.7
{: #appid-client-apps-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000707 | Check whether App ID user profile updates from client apps is disabled | ![Checkmark icon](../../icons/checkmark-icon.svg) |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID Cloud Directory users aren't able to update their own accounts 8.8
{: #appid-directory-users-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000708 | Check whether App ID Cloud Directory users aren't able to update their own accounts |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID Cloud Directory users aren't able to self-sign up to applications 8.9
{: #appid-directory-signup-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000709 | Check whether App ID Cloud Directory users aren't able to self-sign up to applications |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID runtime activity capture is enabled 8.10
{: #appid-directory-runtime-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000710 | Check whether App ID runtime activity capture is enabled |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID social identity providers are disabled 8.11
{: #appid-directory-providers-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000711 | Check whether App ID social identity providers are disabled |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID anonymous authentication is disabled 8.12
{: #appid-anonymous-auth-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000712 | Check whether App ID anonymous authentication is disabled |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID password strength regex is configured 8.13
{: #appid-password-regex-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000713 | Check whether App ID password strength regex is configured |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID advanced password policies are enabled 8.14
{: #appid-password-policies-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000714 | Check whether App ID advanced password policies are enabled |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID avoid password reuse policy is enabled 8.15
{: #appid-password-reuse-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000715 | Check whether App ID avoid password reuse policy is enabled |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID lockout policy after failed # of sign-in attempts is enabled 8.16
{: #appid-lockout-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000716 | Check whether App ID lockout policy after failed # of sign-in attempts is enabled |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID lockout policy after a maximum specified time is set to # minute(s) 8.17
{: #appid-lockout-max-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000717 | Check whether App ID lockout policy after a maximum specified time is set to # minute(s) |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID minimum period between password changes policy is set to greater than 0  8.18
{: #appid-password-changes-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000718 | Check whether App ID minimum period between password changes policy is set to greater than 0 |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID password expiration policy is enabled 8.19
{: #appid-password-expiration-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000719 | Check whether App ID password expiration policy is enabled |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID prevent username in password policy is enabled 8.20
{: #appid-password-username-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000720 | Check whether App ID prevent username in password policy is enabled |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID email verification is enabled for Cloud Directory users 8.21
{: #appid-email-verification-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000721 | Check whether App ID email verification is enabled for Cloud Directory users |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID customer-provided email service is used 8.22
{: #appid-email-customer-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000722 | Check whether App ID customer-provided email service is used |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID multifactor authentication (MFA) is enabled for Cloud Directory users 8.23
{: #appid-mfa-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000723 | Check whether App ID multifactor authentication (MFA) is enabled for Cloud Directory users |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID access tokens are configured to expire within # minutes 8.24
{: #appid-tokens-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000724 | Check whether App ID access tokens are configured to expire within # minutes |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure App ID is enabled with customer-managed encryption and Keep Your Own Key (KYOK) 8.25
{: #appid-encrypt-kyok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000323 | Check whether App ID is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

## Integration
{: #integration-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### Ensure Event Streams is accessible through public endpoints 9.1
{: #event-streams-endpoint-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000305 | Check whether Event Streams is accessible through public endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Event Streams is accessible only through private endpoints 9.2
{: #event-streams-private-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000306 | Check whether Event Streams is accessible only by using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Event Streams network access is restricted to a specific IP range 9.3
{: #event-streams-ip-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000307 | Check whether Event Streams network access is restricted to a specific IP range |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Ensure Event Streams is enabled with customer-managed encryption and Keep Your Own Key (KYOK) 9.4
{: #event-streams-encrypt-kyok-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000322 | Check whether Event Streams is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

## Containers
{: #containers-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### IBM Cloud Kubernetes Service 10.1
{: #kubernetes-goals}

XXXX

#### Ensure Kubernetes Service version is up-to-date 10.1.1
{: #kubernetes-version-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000450 | Check whether Kubernetes Service version is up-to-date |  |
| 3000801 | Check whether Kubernetes Service worker nodes are updated to the latest image to ensure patching of vulnerabilities |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure Kubernetes Service is accessible only by using private endpoints 10.1.2
{: #kubernetes-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000802 | Check whether Kubernetes Service clusters are accessible only by using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure Kubernetes Service cluster has image pull secrets enabled 10.1.3
{: #kubernetes-image-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000803 | Check whether Kubernetes Service cluster has image pull secrets enabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure Kubernetes Service clusters are enabled with IBM Cloud Monitoring 10.1.4
{: #kubernetes-monitoring-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000804 | Check whether Kubernetes Service clusters are enabled with IBM Cloud Monitoring |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### IBM Cloud RedHat OpenShift Kubernetes Service 10.2
{: #openshift-goals}

XXXX

#### Ensure Kubernetes Service version is up-to-date 10.2.1
{: #kubernetes-version-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000906 | Check whether OpenShift Ingress is configured with at least TLS v1.2 for all inbound traffic |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure OpenShift clusters worker nodes are updated to the latest image to ensure patching of vulnerabilities 10.2.2
{: #openshift-vulnerabilities-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000901 | Check whether OpenShift worker nodes are updated to the latest image to ensure patching of vulnerabilities |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure OpenShift clusters version is up-to-date 10.2.3
{: #openshift-version-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000901 | Check whether OpenShift worker nodes are updated to the latest image to ensure patching of vulnerabilities |  |
| 3000907 | Check whether OpenShift version is up-to-date |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure OpenShift clusters is accessible only by using private endpoints 10.2.4
{: #openshift-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000902 | Check whether OpenShift clusters are accessible only by using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure OpenShift cluster has image pull secrets enabled 10.2.5
{: #openshift-image-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000903 | Check whether OpenShift cluster has image pull secrets enabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure OpenShift clusters are enabled with IBM Cloud Monitoring 10.2.6
{: #openshift-monitoring-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000904 | Check whether OpenShift clusters are enabled with IBM Cloud Monitoring |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure OpenShift clusters are enabled with IBM Log Analysis 10.2.7
{: #openshift-log-analysis-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000905 | Check whether OpenShift clusters are enabled with IBM Log Analysis |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure an OpenShift cluster has worker nodes across multiple zones 10.2.8
{: #openshift-worker-nodes-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000915 | Check whether an OpenShift cluster has worker nodes across multiple zones |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### IBM Cloud Satellite RedHat OpenShift Kubernetes Service 10.3
{: #openshift-sattelite-goals}

XXXX

#### Ensure Satellite OpenShift Ingress is configured with at least TLS v1.2 for all inbound traffic 10.3.1
{: #satellite-tls-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000914 | Check whether Satellite OpenShift Ingress is configured with at least TLS v1.2 for all inbound traffic |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure Satellite OpenShift clusters worker nodes are updated to the latest image to ensure patching of vulnerabilities 10.3.2
{: #satellite-vulnerabilities-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000909 | Check whether Satellite OpenShift clusters worker nodes are updated to the latest image to ensure patching of vulnerabilities |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure Satellite OpenShift clusters version is up-to-date 10.3.3
{: #satellite-version-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000909 | Check whether Satellite OpenShift clusters worker nodes are updated to the latest image to ensure patching of vulnerabilities |  |
| 3000908 | Check whether Satellite OpenShift clusters version is up-to-date |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure Satellite OpenShift clusters is accessible only by using private endpoints 10.3.4
{: #satellite-endpoints-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000910 | Check whether Satellite OpenShift clusters is accessible only by using private endpoints |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure Satellite OpenShift cluster has image pull secrets enabled 10.3.5
{: #satellite-image-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000911 | Check whether Satellite OpenShift cluster has image pull secrets enabled |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Ensure Satellite OpenShift clusters are enabled with IBM Cloud Monitoring 10.3.6
{: #satellite-monitoring-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000912 | Check whether Satellite OpenShift clusters are enabled with IBM Cloud Monitoring |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

## Code Engine
{: #code-engine-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### Ensure Code Engine projects are located in authorized regions only 11.1
{: #code-engine-regions-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000321 | Check whether Code Engine projects are located in authorized regions only |  |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}