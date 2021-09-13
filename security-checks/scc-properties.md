---

copyright:
  years: 2021
lastupdated: "2021-09-09"

keywords: config rules, config properties, scc integrated services, 

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

# Available config rule properties
{: #available-rule-properties}

With the {{site.data.keyword.compliance_full}}, you can standardize resource configuration across your enterprise or account by defining rules for the way integrated {{site.data.keyword.cloud_notm}} services can be configured. The following tables provide information about the services and properties that can be added to a config rule.
{: shortdesc}

As a security or compliance focal, you are responsible for ensuring that the resources that are provisioned by your organization adhere to internal and external regulations. In addition to circulating the expected standards, you can define configuration rules that can monitor for misconfigurations or you can choose to block misconfigurations from occuring at all.

Ready to get started? Review the following tables and then see [Formatting rules and templates](/docs/security-compliance?topic=security-compliance-formatting-rules-templates) to learn more about how to construct your rule. Want to learn more about your options? Check out [What is Configuration Governance?](/docs/security-compliance?topic=security-compliance-what-is-governance).


## Billing Composite Service
{: #billing-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to BSS Billing Composite Service. If you're using the API to define your rule, use `billing` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| account-trait | eu_supported | undefined | A boolean indicating whether the account has the eu_supported flag enabled |
| account-trait | hipaa_accepted | undefined | A boolean indicating whether the account has the hipaa_accepted flag enabled |
{: caption="Table 1. Rule properties that are available for the Billing platform component" caption-side="bottom"}

## Cloud Object Storage
{: #cos-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to Cloud Object Storage. If you're using the API to define your rule, use `cloud-object-storage` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| bucket | location | string | Cloud Object Storage bucket location |
| bucket | storage_class | string | Cloud Object Storage bucket storage class. This is configured during bucket creation in the LocationConstraint field. |
| bucket | ibm_sse_kms_customer_root_key_crn | string | SSE Key Protect or Hyper Protect Crypto Services Customer Root Key CRN associated with a Cloud Object Storage bucket. This maps to the bucket configuration parameter, ibm-sse-kp-customer-root-key-crn. |
| bucket | public_access_block_configuration.block_public_acls | boolean | Setting to prevent future configuration of ACLs that permit public access on the Cloud Object Storage bucket and its objects. Prior public access configuration for the bucket and its objects is unchanged. |
| bucket | public_access_block_configuration.ignore_public_acls | boolean | Setting to ignore configuration of public ACLs on the Cloud Object Storage bucket and its objects, rendering effective access as private. GET Bucket ACL and GET Object ACL return effective (enforced) permissions for the resource. |
| bucket | firewall.allowed_network_type | string_list | List of network endpoint types (public, private, or direct) that are allowed. |
| bucket | firewall.allowed_ip | ip_list | List of allowed originating (source) IP addresses/ranges. The list can contain up to 1000 IPv4 or IPv6 addresses/ranges in CIDR notation. |
| bucket | firewall.denied_ip | ip_list | List of originating (source) IP addresses/ranges that are not permitted. The list can contain up to 1000 IPv4 or IPv6 addresses/ranges in CIDR notation. |
| bucket | activity_tracking.activity_tracker_crn | string | CRN of the Activity Tracker instance that receives both management (bucket-level) and data (object-level) events. Management events are sent automatically, but data events are opt-in. |
| bucket | activity_tracking.write_data_events | boolean | If set to true, the Cloud Object Storage bucket's object write data events (i.e. uploads) will be sent to the activity tracking service. |
| bucket | activity_tracking.read_data_events | boolean | If set to true, the Cloud Object Storage bucket's object read events (i.e. downloads) will be sent to the activity tracking service. |
| bucket | metrics_monitoring.metrics_monitoring_crn | string | CRN of the IBM Cloud Monitoring instance that receives the Cloud Object Storage bucket metrics. |
| bucket | metrics_monitoring.usage_metrics_enabled | boolean | If set to true, all usage metrics (i.e. bytes_used) will be sent to the monitoring service. |
| bucket | metrics_monitoring.request_metrics_enabled | boolean | If set to true, all request metrics will be sent to the monitoring service. |
| bucket | hard_quota | numeric | Maximum bytes allotted to the Cloud Object Storage bucket. |
{: caption="Table 2. Rule properties that are available for Cloud Object Storage" caption-side="bottom"}

## Certificate Manager
{: #cm-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to Certificate Manager. If you're using the API to define your rule, use `cloudcerts` for the service name.

Rules for the Certificate Manager service can be monitored but are not enforceable.
{: note}

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| instance | private_network_only | undefined | A boolean that indicates whether access to an instance is enabled only through a private network. |
| certificate | days_to_expiration | undefined | Number of days until expiration. |
{: caption="Table 3. Rule properties that are available for Certificate Manager" caption-side="bottom"}

## IBM Cloud Shell
{: #shell-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to IBM Cloud Shell. If you're using the API to define your rule, use `cloudshell` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| service | enabled | boolean | A boolean to enable or disable IBM Cloud Shell for an account |
{: caption="Table 4. Rule properties that are available for IBM Cloud Shell" caption-side="bottom"}


## Direct Link
{: #dl-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to Direct Link. If you're using the API to define your rule, use `directlink` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| service | cross_account_connection_approved | boolean | Indicates whether an incoming cross account connection request was approved. |
{: caption="Table 5. Rule properties that are available for Direct Link" caption-side="bottom"}


## Catalog Management
{: #catalog-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to Catalog Management. If you're using the API to define your rule, use `globalcatalog-collection` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| account-settings | allow_ibm_provider_only | boolean | Allow users to install only IBM software from the IBM Cloud catalog. Configure the filters set in the catalog management settings to comply with this rule.  Note: Must not be combined with other provider rules. |
| account-settings | allow_ibm_provider | boolean | Allow users to install IBM software from the IBM Cloud catalog. Configure the filters set in the catalog management settings to comply with this rule. |
| account-settings | allow_community_provider | boolean | Allow users to install community software from the IBM Cloud catalog. Configure the filters set in the catalog management settings to comply with this rule. |
| account-settings | allow_thirdparty_provider | boolean | Allow users to install third-party software from the IBM Cloud catalog. Configure the filters set in the catalog management settings to comply with this rule. |
{: caption="Table 6. Rule properties that are available for the Catalog Management platform component" caption-side="bottom"}


## Hyper Protect Crypto Services
{: #hpcs-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to Hyper Protect Crypto Services. If you're using the API to define your rule, use `hs-crypto` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| instance | allowed_network | string | Specifies the type of endpoint the HPCS instance can be accessed from. |
{: caption="Table 7. Rule properties that are available for Hyper Protect Crypto Services" caption-side="bottom"}


## IAM Access Groups
{: #iam-groups-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to The IAM Access Groups service. If you're using the API to define your rule, use `iam-groups` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| service | public_access_enabled | boolean | A boolean indicating whether the public access feature is enabled |
{: caption="Table 8. Rule properties that are available for the IAM Access Groups platform component" caption-side="bottom"}


## IAM Identity Service
{: #iam-identity-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to IAM Identity Service. If you're using the API to define your rule, use `iam-identity` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| accountsettings | restrict_create_service_id | string | Indicating whether the restriction on serviceId creation is enabled. |
| accountsettings | restrict_create_platform_apikey | string | Indicating whether the restriction on platform apikey creation is enabled. |
| accountsettings | mfa | string | Indicating the level of mfa that is required. |
{: caption="Table 9. Rule properties that are available for the IAM Identity Service platform component" caption-side="bottom"}


## Cloud Internet Services
{: #cis-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to Cloud Internet Services. If you're using the API to define your rule, use `internet-svcs` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| zone | waf_enabled | string | A string indicating whether the WAF is turned on or off. |
| zone | tls_mode | string | A string indicating the TLS mode for encryption. Values include 'off', 'flexible', 'full', 'strict', and 'origin_pull'. |
{: caption="Table 10. Rule properties that are available for Cloud Internet Services" caption-side="bottom"}


## Load Balancer for VPC
{: #lb-vpc-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to Load Balancer for VPC. If you're using the API to define your rule, use `is.load-balancer` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| instance | profile_family | string | A list of strings matching loadbalancer profile family name from loadbalancer profile family. Ex: [application, network] |
| instance | load_balancer_type | string | A list of strings indicating what type of the load balancer can be provisioned. Ex: [public, private] |
{: caption="Table 11. Rule properties that are available for Load Balancer for VPC" caption-side="bottom"}


## Key Protect
{: #kp-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to IBM Key Protect. If you're using the API to define your rule, use `kms` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| instance | dual_auth_delete | boolean | Require/Disallow enablement of dual authorization to delete keys in the Key Protect instance. Requirement applies to subsequently created keys and will not apply to pre-existing keys. Refer to Key Protect Instance Policies API. |
| instance | allowed_network | string | Specifies the type of endpoint the Key Protect instance can be accessed from. Refer to Key Protect Instance Policies API. |
| instance | key_create_and_import.create_root_key | boolean | Allow/Disallow root keys to be created in the Key Protect instance. | 
| instance | key_create_and_import.import_root_key | boolean | Allow/Disallow root keys to be imported into the Key Protect instance. |
| instance | key_create_and_import.create_standard_key | boolean | Allow/Disallow standard keys to be created in the Key Protect instance. |
| instance | key_create_and_import.import_standard_key | boolean | Allow/Disallow standard keys to be imported into the Key Protect instance. |
| instance | key_create_and_import.enforce_token | boolean | Restrict/Allow the import of key material into the Key Protect instance without using an import token. |
| instance | metrics | boolean | Require/Restrict Key Protect instance metrics to be forwarded to instance owner's IBM Cloud Monitoring Sysdig instance. Refer to Key Protect Instance Policies API. |
| key | dual_auth_delete | boolean | Require/Disallow dual authorization to delete the given key in the Key Protect instance. Refer to Key Protect Key Policies API. |
| key | rotation.enabled | boolean | Require/Disallow active rotation policy on specified key(s). Refer to Key Protect Key Policies API. |
| key | rotation.interval_month | numeric | Specifies the given key's rotation interval (in months). Automatic rotation policies can only be applied to root keys with non-imported material. Refer to Key Protect Key Policies API. |
{: caption="Table 12. Rule properties that are available for Key Protect" caption-side="bottom"}


## Event Streams
{: #es-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to Event Streams. If you're using the API to define your rule, use `messagehub` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| instance | public_network_enabled | undefined | A boolean indicating whether the public network is enabled |
| instance | private_network_enabled | undefined | A boolean indicating whether the private network is enabled |
| instance | private_access_allowlist | undefined | List of IPs where private network can be utilized |
{: caption="Table 13. Rule properties that are available for Event Streams" caption-side="bottom"}


## IBM Toolchains and Continuous Delivery
{: #cd-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to IBM Toolchains and Continuous Delivery. If you're using the API to define your rule, use `toolchain` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| instance | toolchain_allowed_tool_integration_ids | string_list | Define a list of allowed tools. e.g. [ hostedgit, orion, pipeline, draservicebroker ]. Tool id is at end of url when attempting to add. Full list at https://github.com/open-toolchain/sdk/wiki/services.md |
{: caption="Table 14. Rule properties that are available for Continuous Delivery" caption-side="bottom"}


## Transit Gateway
{: #tg-properties}

Review the following table to learn more about the resource kinds, properties, and operators that are used to build a configuration rule that applies to Transit Gateway. If you're using the API to define your rule, use `transit` for the service name.

| Resource kind | Property | Operator type | Description |
|:--------------|:---------|:--------------|:------------|
| service | cross_account_connection_approved | boolean | Indicates whether an incoming cross account connection request was approved. |
{: caption="Table 15. Rule properties that are available for Transit Gateway" caption-side="bottom"}
