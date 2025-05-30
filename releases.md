---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: "release notes for {{site.data.keyword.compliance_short}}, what's new, enhancements, fixes, improvements"

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Release notes for {{site.data.keyword.compliance_short}}
{: #release-notes}

The following changes to the service were made available with the associated date.



## 16 May 2025
{: #security-compliance-may1625}
{: release-note}

Service announcement

:   Starting on 16 June 2025, users will no longer be able to create new instances of the service. All of the cloud security posture management capabilities have been transitioned to {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}} and are already available for you to get started. If you are a new user, you’re encouraged to get started in {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}} to minimize the need for transition. Existing users will continue to receive support during a transition period, but all feature development will be targeted to {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information about the timeline, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition).




## 18 April 2025
{: #security-compliance-apr1525}
{: release-note}

Rules changes are available

:   The following rule is updated.
    Check whether {{site.data.keyword.cloudant}} is enabled with encryption. Rule ID: `rule-de62d315-278f-4943-a9b5-1293ec242a64`. This is a default rule that ensures all IBM Cloudant instances are encrypted at the disk level.

## 3 April 2025
{: #security-compliance-apr0325}
{: release-note}

Changes to Observability Service
:   With the deprecation and subsequent replacement of the Observability services, you cannot create any new rules or control libraries that refer to these deprecated services. Also, the control libraries do not allow you to add the rules associated with these services. Any existing rules, control libraries, or profiles that are associated with these services are no longer evaluated.

Rules changes are available

:   The following rules were removed in this release:
   - Check whether Identity and Access Management (IAM) is enabled with audit logging

   These rules are removed from the following profiles.
   - {{site.data.keyword.cloud_notm}} Framework for Financial Services (Moderate)(1.2.0). For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-moderate-fs-change-log).
   - Information Technology Security Guidance (ITSG -33 1.1.0). For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-itsg-change-log).





## 29 October 2024
{: #security-compliance-oct2924}
{: release-note}

Information Technology Security Guidance (ITSG) profile
:   Version 1.0.0 of the Information Technology Security Guidance (ITSG) profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-itsg-change-log).

Rules changes are available
:   The following rules were updated in this release. With these changes, the rules are compliant based on the following conditions:

   * Private endpoint is selected for at least one context based restriction
   * If the `public_endpoints_mfa_enabled` input parameter is set to `ON` and public endpoints are selected, then MFA is mandatory. The allowed IP list on public endpoints also should not be empty.
   * If `public_endpoints_mfa_enabled` input parameter is set to `OFF` and public endpoints are selected, then the MFA settings check is ignored. The allowed IP list on public endpoints should not be empty.
   * Any allowed IP list for private endpoints and public endpoints on a context based restriction should also match the {{site.data.keyword.compliance_short}} rule allowed IP list.


   The following rules were updated:

   * Check whether App Configuration can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Code Engine can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Security and Compliance Center can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Container Registry can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Direct Link can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether DNS Services can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Event Notifications can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Hyper Protect Crypto Services can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether IAM access management can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether IAM access groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Key Protect can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Event Streams can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Schematics can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Secrets Manager can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether IBM Cloud Monitoring can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Transit Gateway can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether User Management can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Cloud Object Storage can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Virtual Private Cloud can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Backup for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Bare Metal Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Dedicated Host for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Virtual Private Endpoints for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether VPC floating IPs can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Flow Logs for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether VPC images can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Auto scale for VPC can be accessed only through a private endpoint (Context-based restrictions or service)  and allowed IPs with MFA enabled or not
   * Check whether Virtual Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether VPC SSH keys can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Load Balancer for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether VPC network access control lists can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether VPC placement groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether VPC public gateways can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether VPC security groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Block Storage Snapshots for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether VPC subnets can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Block Storage for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Client VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not
   * Check whether Cloud Object Storage buckets attached to IBM watsonx project can be accessed only through a private endpoint or direct endpoint (Context-based restrictions or service) and allowed IPs with MFA enabled or not


   Most of these rules are mapped to following profiles.

   - IBM Cloud Framework for Financial Services(1.7.0)
   - IBM Cloud Framework for Financial Services (Moderate)(1.1.0)
   - ISO/IEC 27001:2022
   - AI Security Guardrails 2.0 (1.1.0)

## 15 October 2024
{: #security-compliance-oct1524}
{: release-note}

Rules changes are available
:   The following rule was updated.

   * Check whether Virtual Private Cloud (VPC) has no rules in the default security group. Rule ID: `rule-96527f89-1867-4581-b923-1400e04661e0`

Control annotations
:   You can now add annotations to controls to include important details or notes related to the controls in a profile. The annotations are visible in the results and are added as part of the creating an attachment flow. Additionally, the audit history for annotations can be used to track any changes or updates made to them over time. To get started with annotations, [create an attachment](/docs/security-compliance?topic=security-compliance-attachments).


## 7 October 2024
{: #security-compliance-Oct0724}
{: release-note}

Subscopes
:   You can now segment a scope to ensure that only those users who need to have access to certain resource information have it. For more information see, [Segmenting your scope](/docs/security-compliance?topic=security-compliance-subscopes).


## 17 September 2024
{: #security-compliance-sep1724}
{: release-note}

Rules changes are available
:   The following rules are updated. Most of these rules are mapped to following profiles.

   - IBM Cloud Framework for Financial Services(1.5.0),
   - IBM Cloud Framework for Financial Services(1.6.0),
   - IBM Cloud Framework for Financial Services (Moderate)(1.0.0).
   - IBM Cloud Framework for Financial Services(1.7.0)
   - IBM Cloud Framework for Financial Services (Moderate)(1.1.0)
   - ISO/IEC 27001:2022

   A new input parameter was added to the following set of rules to check if all CBR-allowed IP CIDRs that are configured allow access to too many IP addresses to prvent allowing access to unforeseen IP addresses. You can then block any inadvertent changes to the netmask bit portion of CIDR.

   With this input parameter (`netmask_bits_length`), you can specify the netmask bit length that applies to your network setup. If any CBR rules have the allowed IP CIDR netmask bit length set to less than or equal to `netmask_bits_length`, then the rule is considered noncompliant.

   For example, if the parameter `netmask_bits_length` is set to `8`, then all netmask bit lengths that are in the IP CIDRs that are allowed by CBR rule must be greater than 8 (9 thru 32).

   This rule, in all pre-defined profiles, has 256 as the default value to allow all configured netmask bit lengths. You can set this parameter to the value that you need.

   The following rules are updated:

   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list Flow Logs for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for App Configuration (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Auto Scale for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Backup for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Bare Metal Servers for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Block Storage for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Block Storage Snapshots for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Client VPN for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Cloud Object Storage (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Code Engine (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Container Registry (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Dedicated Host for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Direct Link (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for DNS Services (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Event Notifications (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Event Streams (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Hyper Protect Crypto Services (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for IAM access groups (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for IAM access management (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for IAM identities (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Kubernetes Service (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Load Balancer for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Schematics (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Secrets Manager (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Security and Compliance Center (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Transit Gateway (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for User Management (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Virtual Private Cloud (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Virtual Private Endpoints for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Virtual Servers for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for VPC floating IPs (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for VPC images (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for VPC network access control lists (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for VPC placement groups (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for VPC public gateways (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for VPC security groups (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for VPC SSH key (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for VPC subnets (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for VPN for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for IBM Cloud Monitoring (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Databases for EDB (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Databases for ElasticSearch (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Databases for etcd (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Databases for Mongodb (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Databases for MySql (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Databases for PostgreSQL (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Databases for Redis (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Key Protect (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Messages for Rabbitmq (Context-based restrictions or service)
   * Check whether there are no wild cards and wideflows in the private and public endpoints allow list for Security and Compliance Center Workload Protection(Context-based restrictions or service)
   * Check whether Virtual Private Cloud (VPC) has no public gateways attached
   * Check whether Virtual Private Cloud (VPC) has no public gateways attached at the time of provisioning
   * Check whether Cloud Object Storage buckets attached to IBM watsonx projects are enabled with IBM Cloud Monitoring


## 10 September 2024
{: #security-compliance-sep1024}
{: release-note}

New version of the AI Security Guardrails 2.0 profile
:   Version 1.1.0 of the AI Security Guardrails 2.0 profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-ai-security-change-log).


New rules available
:   The following rules are now available:

   * Check whether App ID email dispatchers are using HTTPS only
   * Check whether App ID webhooks are using HTTPS only
   * Check whether App ID is enabled with customer-managed encryption and Keep Your Own Key (KYOK)



## 27 August 2024
{: #security-compliance-aug2724}
{: release-note}

ISO/IEC 27001:2022 profile
:   Version 1.0.0 of the ISO/IEC 27001:2022 profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-iso-iec-change-log).

New version of the {{site.data.keyword.cloud_notm}} Framework for Financial Services profile
:   Version 1.7.0 of the {{site.data.keyword.cloud_notm}} Framework for Financial Services profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-fs-change-log).

New version of the {{site.data.keyword.cloud_notm}} Framework for Financial Services (Moderate) profile
:   Version 1.1.0 of the {{site.data.keyword.cloud_notm}} Framework for Financial Services (Moderate) profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-moderate-fs-change-log).

Updated rules
:   The following rules were updated:

   * Check whether there are no wild cards in the private and public endpoints allow list Flow Logs for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for App Configuration (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Auto Scale for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Backup for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Bare Metal Servers for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Block Storage for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Block Storage Snapshots for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Client VPN for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Cloud Object Storage (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Code Engine (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Container Registry (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Dedicated Host for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Direct Link (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for DNS Services (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Event Notifications (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Event Streams (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Hyper Protect Crypto Services (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for IAM access groups (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for IAM access management (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for IAM identities (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Kubernetes Service (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Load Balancer for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Schematics (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Secrets Manager (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Security and Compliance Center (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Transit Gateway (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for User Management (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Virtual Private Cloud (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Virtual Private Endpoints for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Virtual Servers for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for VPC floating IPs (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for VPC images (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for VPC network access control lists (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for VPC placement groups (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for VPC public gateways (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for VPC security groups (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for VPC SSH key (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for VPC subnets (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for VPN for VPC (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for IBM Cloud Monitoring (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Databases for EDB (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Databases for ElasticSearch (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Databases for etcd (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Databases for Mongodb (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Databases for MySql (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Databases for PostgreSQL (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Databases for Redis (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Key Protect (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Messages for Rabbitmq (Context-based restrictions or service)
   * Check whether there are no wild cards in the private and public endpoints allow list for Security and Compliance Center Workload Protection(Context-based restrictions or service)
   * Check whether Cloud Object Storage can be accessed only through a private endpoint or direct endpoint(Context-based restrictions or service) and allowed IPs


## 9 July 2024
{: #security-compliance-Jul0924}
{: release-note}

AI Security Guardrails 2.0 profile
:   Version 1.0.0 of the AI Security Guardrails 2.0 profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-ai-security-change-log).

Scanning Watson Machine Learning resources is now available with {{site.data.keyword.compliance_short}}
:   You can now scan your Watson Machine Learning resources against the AI Security Guardrails 2.0 profile. You can enable access for {{site.data.keyword.compliance_short}} to scan your Watson Machine Learning resources by assigning customer credentials (API keys) that are stored in {{site.data.keyword.secrets-manager_short}}. For more information, see Scanning Watson Machine Learning resources.


Using trusted profiles to scan your main account
:   As of 9 July 2024, when you are enabling scanning of resources across accounts, if you add your main account as a target, you have to use trusted profiles to run the scans. If you change the trusted profile, the scan results are impacted.

   To change the trusted profile and avoid issues with your scan results, you must delete the target and all the attachments that are on the account first. Then, you can create a new target with the updated trusted profile. No action is required at this time.



## 25 June 2024
{: #security-compliance-Jun2524}
{: release-note}

CIS {{site.data.keyword.cloud_notm}} Foundations Benchmark profile version 1.1.0
:   Version 1.1.0 of the CIS {{site.data.keyword.cloud_notm}} Foundations Benchmark profile is now available in {{site.data.keyword.compliance_short}}. The following major changes are included.

   Control ID:3.1 was updated to remove the existing rule from the control and to map 2 new rules. If the control fails, follow the remediation steps that are documented in the remediation section of these rules.

   For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-cis-benchmark-profile).

New rules available
:   The following rules are now available:

   * Check whether Code engine instances are provisioned in authorized(specified) regions only
   * Check whether Schematics is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Databases for Elasticsearch is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Databases for MongoDB is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether App ID is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Cloud Object Storage is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Block Storage for VPC is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Databases for PostgreSQL is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Databases for MySql is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Event Streams is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Kubernetes Service Cluster is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Red Hat OpenShift cluster is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Databases for Redis is enabled with customer-managed encryption using either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether IBM Cloud Kubernetes Service Ingress has TLS 1.2 enabled for all inbound traffic



## 6 June 2024
{: #security-compliance-Jun0624}
{: release-note}

{{site.data.keyword.cloud_notm}} Framework for Financial Services (Moderate)
:   Version 1.0.0 of the {{site.data.keyword.cloud_notm}} Framework for Financial Services (Moderate) profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see the [Change log](/docs/security-compliance?topic=security-compliance-moderate-fs-change-log).

## 4 June 2024
{: #security-compliance-Jun0424}
{: release-note}

New rules available
:   The following rules are now available:

   * Check whether VPN for VPC has an "establish mode" configuration that is different from 'peer_only'
   * Check whether no public access is granted to buckets attached to IBM watsonx projects via the IAM public access group
   * Check whether Databases for MySql is accessible only through TLS 1.2 or higher
   * Check whether Databases for MySql is accessible only through private endpoints
   * Check whether Databases for MySql is enabled with encryption

## 28 May 2024
{: #security-compliance-May2824}
{: release-note}

Updates to IAM roles for {{site.data.keyword.compliance_short}}
:   Last year, {{site.data.keyword.compliance_short}} started the migration from a global service to a regional service. Starting 7 June 2024, the next phase of the migration, which is focused on updating IAM roles, will begin. Currently, actions for the {{site.data.keyword.compliance_short}} service are mapped to platform-based roles. Now that the service has moved to a regional model, the actions for the product will be mapped to the service roles. As an administrator of an account, it is your responsibility to assign access and ensure that each user is assigned the minimum role to perform the actions required for their position. If your account actively uses {{site.data.keyword.compliance_short}} you must review the permissions assigned to those that work with the service to ensure that they have the appropriate service level role.To evaluate which roles are currently assigned in your account, you can use the IAM UI. To get to the IAM UI, go to the IBM Cloud console, and click **Manage (IAM)** and select the user, trusted profile, or access group that you want to validate. For more information about the new mappings and role requirements, see [Managing IAM access for {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-access-management).

   As you determine the impact of this change to your organization, please keep the following dates in mind.

   * **7 June 2024**: Starting on this date, the action to role mapping for {{site.data.keyword.compliance_short}} will be updated to include the service level roles and the change will be visible in the IAM UI. The platform roles will continue to function. During this time period, you must evaluate and reassign permissions as needed for the members of your organization.

   * **28 May 2025**: On this date, the action to role mapping will be updated to remove the platform roles that are associated with specific {{site.data.keyword.compliance_short}} actions. Actions that are no longer used by the service will also be removed on this date. If you have not completed the evaluation and assigned access to the service roles prior to this date, users might lose the access that is required to perform their tasks in {{site.data.keyword.compliance_short}}.

   Additionally, the following unused or stale actions will be removed from the IAM definition as part of the migration.

   * `compliance.configuration-governance.results-create`
   * `compliance.configuration-governance.results-delete`
   * `compliance.configuration-governance.results-read`
   * `compliance.configuration-governance.results-update`
   * `compliance.configuration-governance.attachments-update`
   * `compliance.configuration-governance.templates-create`
   * `compliance.configuration-governance.templates-delete`
   * `compliance.configuration-governance.templates-read`
   * `compliance.configuration-governance.templates-update`
   * `compliance.posture-management.collectors-create`
   * `compliance.posture-management.collectors-delete`
   * `compliance.posture-management.collectors-read`
   * `compliance.posture-management.collectors-update`
   * `compliance.posture-management.credentials-create`
   * `compliance.posture-management.credentials-delete`
   * `compliance.posture-management.credentials-read`
   * `compliance.posture-management.credentials-update`
   * `compliance.posture-management.credentialsmap-create`
   * `compliance.posture-management.credentialsmap-delete`
   * `compliance.posture-management.credentialsmap-read`
   * `compliance.posture-management.credentialsmap-update`
   * `compliance.posture-management.keys-delete`
   * `compliance.posture-management.keys-read`
   * `compliance.posture-management.keys-write`
   * `compliance.posture-management.scopes-create`
   * `compliance.posture-management.scopes-delete`
   * `compliance.posture-management.scopes-read`
   * `compliance.posture-management.scopes-update`
   * `compliance.posture-management.tags-create`
   * `compliance.posture-management.tags-delete`
   * `compliance.posture-management.tags-read`
   * `compliance.posture-management.tags-update`
   * `compliance.posture-management.tenants-create`
   * `compliance.posture-management.tenants-delete`
   * `compliance.posture-management.tenants-read`
   * `compliance.posture-management.tenants-update`
   * `compliance.posture-management.validations-create`
   * `compliance.posture-management.validations-delete`
   * `compliance.posture-management.validations-read`
   * `compliance.posture-management.validations-update`
   * `compliance.posture-management.values-create`
   * `compliance.posture-management.values-read`
   * `compliance.posture-management.values-update`
   * `compliance.posture-management.events-view`
   * `compliance.posture-management.events-create`

New rules available
:   The following rules are now available:

   * Check whether Cloud Object Storage buckets attached to IBM watsonx project can be accessed only through a private endpoint (Context-based restrictions or service) and allowed Ips
   * Check whether resiliency is set to cross region or regional in Cloud Object Storage buckets attached to IBM watsonx projects
   * Check whether network access is restricted to a specific IP range in Cloud Object Storage buckets attached to IBM watsonx projects
   * Check whether Cloud Object Storage buckets attached to IBM watsonx projects are enabled with encryptions
   * Check whether Cloud Object Storage buckets attached to IBM watsonx projects are enabled with IBM Cloud Monitoring
   * Check whether Cloud Object Storage buckets attached to IBM watsonx projects are accessible only through TLS 1.2 or higher
   * Check whether Cloud Object Storage Storage buckets attached to IBM watsonx projects are enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Cloud Object Storage buckets are enabled with IBM Cloud Monitoring
   * Check whether Databases for Elasticsearch is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Databases for MongoDB is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Databases for PostgreSQL is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Databases for MySql is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Databases for Redis is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether IAM users are attached to at least one access group, exempt account owned
   * Check whether Cloud Object Storage buckets are encrypted with customer-managed keys
   * Check whether Cloud Object Storage buckets are deployed to allowed locations
   * Check whether Databases for Elasticsearch is enabled with customer-managed encryption
   * Check whether Databases for Elasticsearch backups are enabled with customer-managed encryption
   * Check whether Databases for etcd backups are enabled with customer-managed encryption
   * Check whether Databases for etcd is enabled with customer-managed encryption
   * Check whether Hyper Protect Crypto Services is provisioned in allowed region
   * Check whether Databases for MongoDB is enabled with customer-managed encryption
   * Check whether Databases for MongDB backups are enabled with customer-managed encryption
   * Check whether Databases for PostgreSQL is enabled with customer-managed encryption
   * Check whether Databases for PostgreSQL backups are enabled with customer-managed encryption
   * Check whether Databases for Redis is enabled with customer-managed encryption
   * Check whether Databases for Redis backups are enabled with customer-managed encryption


## 14 May 2024
{: #security-compliance-May1424}
{: release-note}

New rules available
:   The following rules are now available:

   * Check whether Security and Compliance Center Workload Protection can be accessed only through a private endpoint (Context-based restrictions or service)
   * Check whether there are no wild cards in the private endpoint allow list for Security and Compliance Center Workload Protection (Context-based restrictions or service)
   * Check whether Security and Compliance Center Workload Protection can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether no owner account API key exists

## 7 May 2024
{: #security-compliance-May0724}
{: release-note}

New rules available
:   The following rules are now available:

   * Check whether there are at least # users with admin role are assigned as collaborators in IBM Watsonx project
   * Check whether there are no Service IDs with admin role are assigned as collaborators in IBM Watsonx project
   * Check whether sensitive data is not exported/moved out of the IBM Watsonx project
   * Check whether asset metadata reporting is not selected in the IBM Watsonx project
   * Check whether Virtual Servers for VPC data volumes are enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Virtual Servers for VPC boot volumes are enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether IAM users contact number is valid


## 23 April 2024
{: #security-compliance-april2324}
{: release-note}

Updated rules
:   The following rules were updated:

   * Check whether Cloud Object Storage bucket resiliency is set to cross region or regional
   * Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to SSH port
   * Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to RDP port
   * Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from wildcard IP addresses to SSH port
   * Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to RDP port


## 20 March 2024
{: #security-compliance-march2024}
{: release-note}

New rules available
:   The following rules are now available:

   * Check whether there is at least one {{site.data.keyword.at_full_notm}} instance in the region where Watson Machine Learning Service is available
   * Check whether all endpoints exposed by {{site.data.keyword.watson}} Machine Learning instance are accessible only through TLS 1.2 or higher
   * Check whether all {{site.data.keyword.watson}} Machine Learning Service instance are accessed only through a private endpoints
   * Check whether {{site.data.keyword.cloud_notm}} IAM establishes minimum and maximum lifetime restrictions and reuse conditions for authenticators used in {{site.data.keyword.watson}} Machine Learning services, such as API keys and Service IDs

## 19 March 2024
{: #security-compliance-march1924}
{: release-note}

Scanning resources in other accounts is now available

:   You can now scan resources in other {{site.data.keyword.cloud_notm}} accounts that are either part of an enterprise or outside of an enterprise. You can enable scanning across other accounts by adding these accounts to your attachment as target accounts. For more information about scanning resources in other {{site.data.keyword.cloud_notm}} accounts, see [Scanning resources across accounts](/docs/security-compliance?topic=security-compliance-scopes).

   You can take advantage of an automation script that can help you to automatically register to scan resources across accounts. For more information, check out the [script in GitHub](https://github.com/IBM/security-compliance-automation){: external}.
   {: note}

## 13 March 2024
{: #security-compliance-march1224}
{: release-note}

{{site.data.keyword.cloud_notm}} Framework for Financial Services profile version 1.6.0
:   Version 1.6.0 of the {{site.data.keyword.cloud_notm}} Framework for Financial Services profile is now available. For more information, see the [Change log](/docs/security-compliance?topic=security-compliance-fs-change-log).

New rules and rule changes are available
:   The following rules have been added or updated. They are not currently mapped to any profile, including the IBM Cloud Framework for Financial Services profile. Users can now override the default value and specify an allowed IP or IP range as a parameter. Rules related to context-based restrictions only evaluate for public and private configurations. If you have configured direct endpoints, it will not evaluated by the following rules.

   When a context-based restriction is set regarding private endpoints, your users will not be able to access a service through the UI unless an allowed IP address is set through your account settings.
   {: note}

:   The following rules are now available:

   * Check whether App Configuration can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Code Engine can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Security and Compliance Center can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Container Registry can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Kubernetes Service can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Databases for ElasticSearch can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Databases for EDB can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Databases for etcd can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Databases for MongoDB can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Databases for MySql can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Databases for PostgreSQL can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Databases for Redis can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Direct Link can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether DNS Services can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Event Notifications can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Hyper Protect Crypto Services can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether IAM access management can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether IAM access groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether IAM identities can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Key Protect can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Event Streams can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Messages for RabbitMQ can be accessed only through a private endpoint (Context-based restrictions and service) and allowed IPs
   * Check whether Schematics can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Secrets Manager can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether IBM Cloud Monitoring can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Transit Gateway can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether User Management can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs

:   The following rules are updated:

   * Check whether Code Engine can be accessed only through a private endpoint (Context-based restrictions or service)
   * Check whether there are no wild cards in the private endpoint allow list for Code Engine (Context-based restrictions or service)

   For more information about rules, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

OSPAR profile
:   Version 1.0.0 of the Outsourced Service Provider’s Audit Report (OSPAR) profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see the [Change log](/docs/security-compliance?topic=security-compliance-ospar-change-log).

## 27 February 2024
{: #security-compliance-feb2724}
{: release-note}

New rules available

:   The following rules are now available:

   * Check whether App ID is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Schematics is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Block Storage for VPC is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Cloud Object Storage is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Red Hat OpenShift cluster is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)
   * Check whether Kubernetes Service Cluster is enabled with customer-managed encryption and either Bring Your Own Key (BYOK) or Keep Your Own Key (KYOK)

   For more information about rules, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

## 20 February 2024
{: #security-compliance-feb2024}
{: release-note}

New rules and rule changes are available
:   The following rules have been added or updated. They are not currently mapped to any profile, including the IBM Cloud Framework for Financial Services profile. Users can now override the default value and specify an allowed IP or IP range as a parameter. Rules related to context-based restrictions only evaluate for public and private configurations. If you have configured direct endpoints, it will not evaluated by the following rules.

   When a context-based restriction is set regarding private endpoints, your users will not be able to access a service through the UI unless an allowed IP address is set through your account settings.
   {: note}

: The following rules have been added:

   * Check whether Cloud Object Storage can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Virtual Private Cloud can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Backup for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Bare Metal Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Dedicated Host for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Virtual Private Endpoints for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether VPC floating IPs can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Flow Logs for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether VPC images can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Auto scale for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Virtual Servers for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether VPC SSH keys can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Load Balancer for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether VPC network access control lists can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether VPC placement groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether VPC public gateways can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether VPC security groups can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Block Storage Snapshots for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether VPC subnets can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Block Storage for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether Client VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs
   * Check whether VPN for VPC can be accessed only through a private endpoint (Context-based restrictions or service) and allowed IPs

   For more information about rules, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

## 13 February 2024
{: #security-compliance-feb1324}
{: release-note}

New rules available

:   The following rules are now available:

   * Check whether App ID is enabled with customer-managed encryption and Bring Your Own Key (BYOK)
   * Check whether Schematics is enabled with customer-managed encryption and Bring Your Own Key (BYOK)
   * Check whether Event Streams is enabled with customer-managed encryption and Keep Your Own Key (KYOK)
   * Check whether a Red Hat OpenShift cluster has at least # worker nodes across multiple zones

   For more information about rules, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

## 23 January 2024
{: #security-compliance-jan2324}
{: release-note}

New rules available

:   The following rules are now available:

   * Check whether Databases for EDB can be evaluated to determine whether it can be accessed only through a private endpoint (Context-based restrictions or service)
   * Check whether Databases for EDB can be evaluated to determine there are no wild cards in the private endpoint allow list (Context-based restrictions or service)
   * Check whether Databases for MySql can be evaluated to determine whether it can be accessed only through a private endpoint (Context-based restrictions or service)
   * Check whether Databases for MySql can be evaluated to determine there are no wild cards in the private endpoint allow list (Context-based restrictions or service)
   * Check whether IBM Cloud Monitoring can be evaluated to determine whether it can be accessed only through a private endpoint (Context-based restrictions or service)
   * Check whether IBM Cloud Monitoring can be evaluated to determine there are no wild cards in the private endpoint allow list (Context-based restrictions or service)
   * Check whether Messages for Rabbitmq can be evaluated to determine whether it can be accessed only through a private endpoint (Context-based restrictions or service)
   * Check whether Messages for Rabbitmq can be evaluated to determine there are no wild cards in the private endpoint allow list (Context-based restrictions or service)

Updated rules

:   The following rules are updated:

   * Check whether Container Registry can be evaluated to determine there are no wild cards in the private endpoint allow list (Context-based restrictions or service)

   For more information about rules, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).


## 17 January 2024
{: #security-compliance-jan1724}
{: release-note}

Updated rule
:   The rule logic for `Check whether Kubernetes Service version is up-to-date` has changed. In a previous version of the evaluation, the logic compared the recommended version. Now, the logic compares the recommended version and supported versions. The rule ID is `rule-e0686900-c022-4434-b04f-f7032bea1050`.



## 15 December 2023
{: #security-compliance-dec1523}
{: release-note}

Caveonix Security Baselines for VMware profile
:   Version 1.0.0 of the Caveonix Security Baselines for VMware profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-soc2-change-log).

Command Line Interface
:   You can now interact with {{site.data.keyword.compliance_short}} through the CLI. You can review the updates in the [CLI reference](/docs/security-compliance?topic=security-compliance-security-compliance-cli).


## 12 December 2023
{: #security-compliance-dec1223}
{: release-note}

{{site.data.keyword.cloud_notm}} Security Best Practices profile has been removed
:   The {{site.data.keyword.cloud_notm}} Security Best Practices profile has been removed. The profile was deprecated on September 12, 2023 and was removed according to schedule today.

{{site.data.keyword.cloud_notm}} Red Hat OpenShift Kubernetes OCP4 (Version 1.1.0) profile has been removed.
:   Version 1.1.0 of the {{site.data.keyword.cloud_notm}} Red Hat OpenShift Kubernetes OCP4 has been removed from the service.

## 11 December 2023
{: #security-compliance-dec1123}
{: release-note}

Version 1.0.0 of the ISMAP profile
:   Version 1.0.0 of the ISMAP profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-ismap-change-log).

Version 1.0.0 of the AI ICT Guardrails profile
:   Version 1.0.0 of the AI ICT Guardrails profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-ai-ict-change-log).

## 7 December 2023
{: #security-compliance-dec0723}
{: release-note}

Madrid availability
:   {{site.data.keyword.compliance_short}} is now available in the Madrid (`eu-es`) region. For more information about the availability of the service, see [Regions and endpoints](/docs/security-compliance?topic=security-compliance-endpoints).


## 6 December 2023
{: #security-compliance-dec0623}
{: release-note}

Profile versioning now available
:   Profile versioning is now available in {{site.data.keyword.compliance_short}}. With profile versioning, you can upgrade to the latest version of a profile as updates are released. For more information about profile versioning, including timelines, see [Managing profile versions](/docs/security-compliance?topic=security-compliance-profile-versioning).

Version 1.0.0 of the SOC 2
:   Version 1.0.0 of the SOC 2 is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-soc2-change-log).

Version 1.2.0 of the CIS Amazon Elastic Kubernetes Service (EKS) Benchmark
:   Version 1.2.0 of the CIS Amazon Elastic Kubernetes Service (EKS) Benchmark is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-cis-amazon-eks-benchmark).

Version 1.2.0 of the AWS Foundational Security Best Practices
:   Version 1.2.0 of the AWS Foundational Security Best Practices is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-aws-fs-benchmark).

Version 1.2.0 of the AWS Well-Architected Framework
:   Version 1.2.0 of the AWS Well-Architected Framework is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-aws-waf-benchmark).

Version 1.2.0 of the NIST SP 800-53 (Security and Privacy Controls for Information Systems and Organizations)
:   Version 1.2.0 of the NIST SP 800-53 (Security and Privacy Controls for Information Systems and Organizations) is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-nist-800-53-change-log).

Version 1.2.0 of the CIS Azure Kubernetes Service (AKS) Benchmark
:   Version 1.2.0 of the CIS Azure Kubernetes Service (AKS) Benchmark is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-cis-azure-ks-benchmark).


## 21 November 2023
{: #security-compliance-nov2123}
{: release-note}

Version 1.1.0 of the AWS Foundational Security Best Practices
:   Version 1.1.0 of the AWS Foundational Security Best Practices is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-aws-fs-benchmark).

Version 1.1.0 of the AWS Well-Architected Framework
:   Version 1.1.0 of the AWS Well-Architected Framework is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-aws-waf-benchmark).

Version 1.1.0 of the NIST SP 800-53 (Security and Privacy Controls for Information Systems and Organizations)
:   Version 1.1.0 of the NIST SP 800-53 (Security and Privacy Controls for Information Systems and Organizations) is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-nist-800-53-change-log).

## 16 November 2023
{: #security-compliance-nov1423}
{: release-note}

Version 1.0.0 of the C5:2020 profile
:   Version 1.0.0 of the C5:2020 profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-bsi-c5-change-log).

## 7 November 2023
{: #security-compliance-nov723}
{: release-note}

New rules available

:   The following rules are now available:

   * Check whether DevSecOps Toolchain verifies all changes to source code have been manually reviewed
   * Check whether DevSecOps Toolchain validates signature provenance of each deployed artifact
   * Check whether the Identity and Access Management service can now be evaluated to determine whether a user's contact email is valid
   * Check whether Secrets Manager can now be evaluated to determine whether certificates that are generated through the service are configured to be renewed before they expire
   * Check whether Event Notifications is configured to work with Security and Compliance Center

   For more information about rules, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

Version 1.1.0 of the CIS Amazon Web Services Foundations Benchmark
:   Version 1.1.0 of the CIS Amazon Web Services Foundations Benchmark is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-cis-amazon-benchmark).

Version 1.1.0 of the CIS Amazon Elastic Kubernetes Service (EKS) Benchmark
:   Version 1.1.0 of the CIS Amazon Elastic Kubernetes Service (EKS) Benchmark is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-cis-amazon-eks-benchmark).

Version 1.1.0 of the CIS Azure Kubernetes Service (AKS) Benchmark
:   Version 1.1.0 of the CIS Azure Kubernetes Service (AKS) Benchmark is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-cis-azure-ks-benchmark).


## 24 October 2023
{: #security-compliance-oct2423}
{: release-note}

Remediation
:   For a select group of controls, remediation informaiton is now available in the {{site.data.keyword.compliance_short}} UI. To see remediation, navigate to your results, and select the control. A side panel opens with additional information, click the **Non-compliant properties** tab.


## 17 October 2023
{: #security-compliance-oct172023}
{: release-note}

Version 1.1.0 of the IBM Cloud Kubernetes Service Benchmark
:   Version 1.1.0 of the IBM Cloud Kubernetes Service Benchmark is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-iks-profile&interface=ui).


Version 1.1.0 of the CIS Microsoft Azure Foundations Benchmark
:   Version 1.1.0 of the CIS Microsoft Azure Foundations Benchmark is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-cis-benchmark-profile).

Logging
:   You can view and analyze {{site.data.keyword.compliance_short}} logs by using the {{site.data.keyword.la_full}} service and enabling platform logs in each region where you operate in {{site.data.keyword.cloud_notm}}. For more information, see [Logging for {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-logging).



## 10 October 2023
{: #security-compliance-oct92023}
{: release-note}

Version 1.0.0 of the ENS High profile
:   Version 1.0.0 of the ENS High profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-ens-high-change-log).

Version 1.2.0 of the IBM Cloud Red Hat OpenShift Kubernetes OCP4 profile
:   Version 1.2.0 of the IBM Cloud Red Hat OpenShift Kubernetes profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-openshift-profile).


## 28 September 2023
{: #security-compliance-sep282023}
{: release-note}

Terraform support
:   If you're already using Terraform with {{site.data.keyword.cloud_notm}}, you can continue to use [Terraform with {{site.data.keyword.compliance_short}}](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/scc_rule){: external} to read data sources and create resources.


## 23 September 2023
{: #security-compliance-sep212023}
{: release-note}

Profile name change
:   The following profile names have been updated:

   * {{site.data.keyword.cloud_notm}} for Financial Services is now known as {{site.data.keyword.cloud_notm}} Framework for Financial Services
   * CIS IBM Foundations Benchmark is now known as CIS {{site.data.keyword.cloud_notm}} Foundations Benchmark

   There is no impact to your scans, just the name of the profile has been changed.

PCI DSS v4.0 profile
:   Version 1.0.0 of the PCI DSS v4.0 profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-pci-dss-change-log).

Version 5 of the {{site.data.keyword.cloud_notm}} Framework for Financial Services profile
:   Version 5 of the {{site.data.keyword.cloud_notm}} Framework for Financial Services profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-fs-change-log). This version of the profile has been renamed to {{site.data.keyword.cloud_notm}} Framework for Financial Services.

New version of the {{site.data.keyword.cloud_notm}} Red Hat OpenShift Kubernetes OCP4 profile
:   Version 1.1.0 of the {{site.data.keyword.cloud_notm}} Red Hat OpenShift Kubernetes OCP4 profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-openshift-profile).

NIST SP 800-53 (Security and Privacy Controls for Information Systems and Organizations) profile
:   Version 1.0.0 of the NIST SP 800-53 (Security and Privacy Controls for Information Systems and Organizations) profile is now available in {{site.data.keyword.compliance_short}}. For more information about the profile, see [the change log](/docs/security-compliance?topic=security-compliance-nist-800-53-change-log).

Multi-environment profiles
:   You can now evaluate multiple environments by using the same profile. To get started with the multi-cloud flow, [create a custom profile](/docs/security-compliance?topic=security-compliance-build-custom-profiles) and then [run an evaluation](/docs/security-compliance?topic=security-compliance-tutorial-tags&interface=ui#tutorial-tag-scan-resources).

## 15 September 2023
{: #security-compliance-sep1523}
{: release-note}

Now available: Java SDK v5.0.0
:   A new version of the {{site.data.keyword.compliance_short}} [Java SDK](https://github.com/IBM/scc-java-sdk){: external} is now available. You can review the updates in the [API docs](/apidocs/security-compliance#introduction).

Now available: Node SDK v5.0.0
:   A new version of the {{site.data.keyword.compliance_short}} [Node.js SDK](https://github.com/IBM/scc-node-sdk){: external} is now available. You can review the updates in the [API docs](/apidocs/security-compliance#introduction).

Now available: Python SDK v5.0.0
:   A new version of the {{site.data.keyword.compliance_short}} [Python SDK](https://github.com/IBM/scc-python-sdk) is now available. You can review the updates in the [API docs](/apidocs/security-compliance#introduction).


## 12 September 2023
{: #security-compliance-sep1223}
{: release-note}

Profile deprecation: {{site.data.keyword.cloud_notm}} Security Best Practices
:   As of 12 September 2023, the {{site.data.keyword.cloud_notm}} Security Best Practices profile is deprecated. If you are currently working with the profile, be sure to keep the following timeline in mind.

   * 12 September 2023: Profile officially deprecated. There is no functionality change.
   * 12 October 2023: The creation of new and editing of existing attachments will be blocked starting on this date. Additionally, the profile will no longer be visible in the Profile page of the service UI. Previously created attachments will continue to be scanned.
   * 11 December 2023: The profile will be removed from the product. If an attachment exists with the profile, the scans will stop.

   It is recommended that you move to another profile, such as CIS IBM Cloud Foundations Benchmark, to ensure continued support. However, if you want to continue working with the controls or assessments that are associated with the {{site.data.keyword.cloud_notm}} Security Best Practices, you can use the profile to create a custom profile until the 12 October. You must then create a new attachment with your custom profile to initiate scanning.

   If you're already working with the controls or assessments through a custom profile, you do not need to make any changes. Your scans will continue to run.



## 29 August 2023
{: #security-compliance-aug2923}
{: release-note}

Now available: Go SDK v5.0.2
:   A new version of the {{site.data.keyword.compliance_short}} [Go SDK](https://github.com/IBM/scc-go-sdk){: external} is now available. You can review the updates in the [API docs](/apidocs/security-compliance#introduction).


## 9 August 2023
{: #security-compliance-Aug092023}
{: release-note}

New rules available
:   The context based restrictions platform service is now available for you to create custom rules. Additionally, rules surrounding private endpoints are now available. For more information about rules, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

{{site.data.keyword.cloud_notm}} for Financial Services profile version 1.4.0
:   Version 1.4.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available. For more information, see the [Change log](/docs/security-compliance?topic=security-compliance-fs-change-log).


## 17 July 2023
{: #security-compliance-july172023}
{: release-note}

Results from multiple environments are now available
:   You can now pull results from multiple environments, including Amazon Web Services and Microsoft Azure into {{site.data.keyword.compliance_short}} by connecting an instance of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}} to the service. For help getting started, see [Connecting {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}](/docs/security-compliance?topic=security-compliance-setup-workload-protection).

New profiles are now available
:   Version 1.0.0 of the the following profiles are now available:
   * [CIS Amazon Elastic Kubernetes Service (EKS) Benchmark](/docs/security-compliance?topic=security-compliance-cis-amazon-eks-benchmark)
   * [CIS Azure Kubernetes Service (AKS) Benchmark](/docs/security-compliance?topic=security-compliance-cis-azure-ks-benchmark)
   * [CIS Amazon Web Services Foundations Benchmark](/docs/security-compliance?topic=security-compliance-cis-amazon-benchmark)
   * [CIS Microsoft Azure Foundations Benchmark](/docs/security-compliance?topic=security-compliance-cis-azure-benchmark)

New API version available
:   The {{site.data.keyword.compliance_short}} version 3.0.0 is now available. All endpoints have changed to support the new architecture. For more details, review the [API reference](/apidocs/security-compliance#introduction).


## 12 July 2023
{: #security-compliance-july122023}
{: release-note}

{{site.data.keyword.cloud_notm}} Kubernetes Service Benchmark profile version 1.0.0
:   Version 1.0.0 of the {{site.data.keyword.cloud_notm}} Kubernetes Service Benchmark profile is now available. This profile introduces the new assessment format `wp-rule`. For more information, see the [Change log](/docs/security-compliance?topic=security-compliance-iks-profile). To view results by using this profile, you must have a connected instance of Workload Protection. For help getting started, see [Connecting {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}](/docs/security-compliance?topic=security-compliance-setup-workload-protection).

New rule operators
:   You can now use the operators `strings allowed`, `strings_required`, `string_contains`, and `string_not_contains` to create custom rules. For more information about the new operators or help getting started with custom rules, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

## 8 July 2023
{: #security-compliance-july082023}
{: release-note}

{{site.data.keyword.compliance_short}} is now an instance-based, regional offering
:   You now have full control over the region that is used when {{site.data.keyword.compliance_short}} processes your data. To process data in different regions, you can create multiple instances of the service in a single account. As part of this architecture change, any Identity and Access Management (IAM) access policies or context-based restrictions that are scoped to “All Account Management Services” will no longer apply to {{site.data.keyword.compliance_short}}. Users who have access to “All Identity and Access Enabled Services” will now have access to {{site.data.keyword.compliance_short}}. Additionally, if you are working with private catalogs, {{site.data.keyword.compliance_short}} must be added to the private catalog as an approved service in order for members of your organization to create an instance.

   If users have a quota on the number of resources for their account that has already been met, instances of the service will not be able to be created.
   {: note}

## 1 July 2023
{: #security-compliance-july012023}
{: release-note}

Support removed for the collector-based architecture
:   The collector-based architecture has been removed from the product in preparation for an upcoming architectural change to a regional offering.

   The events related to collector-based evaluations have also been removed. To continue to receive events for your evaluations you must [update your topics in Event Notifications](/docs/security-compliance?topic=security-compliance-event-notifications).


## 23 June 2023
{: #security-compliance-june232023}
{: release-note}

New rules available
:   The Global Search and Tagging platform service is now available for you to create custom rules. Rules can be written to evaluate resources that have been assigned specific tags. For more information about rules, see [Defining custom rules](/docs/security-compliance?topic=security-compliance-rules-define).

Attachment details available
:   The create attachment flow has been updated to include details as an input. Profiles that were previously created will now see a name comprised of the combination of a `scope-type and scope ID` in the profiles table.. You can add a custom name at any time by editing your profile.



## 20 June 2023
{: #security-compliance-june202023}
{: release-note}

{{site.data.keyword.cloud_notm}} for Financial Services profile version 1.3.0
:   Version 1.3.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available. For more information, see the [Change log](/docs/security-compliance?topic=security-compliance-fs-change-log).

{{site.data.keyword.cloud_notm}} Security Best Practices profile version 1.2.0
:   Updates to version 1.2.0 of the {{site.data.keyword.cloud_notm}} Security Best Practices library and profile are now available. For more information, see the Change log.


## 7 June 2023
{: #security-compliance-june072023}

OpenShift Compliance Operator (OSCO)
:   You can now evaluate your OpenShift clusters by using the OSCO integration in the updated architecture. For help getting started or customizing your workflow, see [Evaluate the compliance of your RedHat OpenShift Clusters](/docs/security-compliance?topic=security-compliance-osco-scan).


## 29 May 2023
{: #security-compliance-may292023}

Reminder: {{site.data.keyword.compliance_short}} will become regional
:   Starting 8 July 2023 {{site.data.keyword.compliance_short}} will be a provisionable, regional service offering in the IBM Cloud catalog. With this change, you will have full control over the region that is used when {{site.data.keyword.compliance_short}} processes your data. To process data in different regions, you can create multiple instances of the service in a single account.

   [deprecated]{: tag-deprecated} To support this change, support for the collector-based architecture was deprecated. This means that all of the configurations surrounding collectors, goal-based profiles, collector-based scans, goal-based results, and credentials will be removed at the end of support on 1 July 2023.

   Additionally, the following changes will be made:
   * Any Identity and Access Management (IAM) access policies or context-based restrictions that are scoped to “All Account Management Services” will no longer apply to {{site.data.keyword.compliance_short}}. Users who have access to “All Identity and Access Enabled Services” will now have access to {{site.data.keyword.compliance_short}}.
   * If users have access only to products added to a private catalog and not the full IBM Cloud catalog, then {{site.data.keyword.compliance_short}} must be added to their private catalog to enable them to create an instance.
   * If users have a quota on the number of resources for their account that has already been met, instances of the service will not be able to be created.

   During this update, you are responsible for the migration of your scan configurations to the new architecture. You can start this migration at any time.

   As you begin your migration, please keep the following dates in mind:
   * 8 June 2023: The location setting in {{site.data.keyword.compliance_short}} will be frozen until the upgrade is complete. The location that is specified in the service is the region in which your new instance will be created. Additional instances can be created starting in July.
   * 1 July 2023: The collector-based architecture will be removed from {{site.data.keyword.compliance_short}}.
   * 8 July 2023: A regional instance of {{site.data.keyword.compliance_short}} will be available in your account based on your set location and the global instance will be removed. Additionally, the changes to IAM and context-based restrictions take effect.

   You might see two instances of {{site.data.keyword.compliance_short}} through the Billing page during the migration period although you can’t see two instances in your account. This is due to the way that the migration is being conducted. You are only billed through one. When the migration is complete, the global instance will be removed from your account.
   {: note}


## 2 May 2023
{: #security-compliance-may022023}
{: release-note}

Schedule the frequency of your scans
:   You can now schedule the frequency at which your scans are run in the updated architecture. Options include everyday, every 7 days, and every 30 days. You can also now pause your scans. It is recommended that you continue to scan your environments daily. To get started, see [Scanning {{site.data.keyword.cloud_notm}} resources](/docs/security-compliance?topic=security-compliance-tutorial-tags&interface=ui#tutorial-tag-scan-resources).


## 1 May 2023
{: #security-compliance-may012023}
{: release-note}

Support for context-based restrictions (CBR)
:   Manage user and service access to your {{site.data.keyword.compliance_short}} resources by using context-based restrictions, based on defined criteria. For more information, see [Protecting {{site.data.keyword.compliance_short}} resources with context-based restrictions](/docs/security-compliance?topic=security-compliance-cbr).



## 25 April 2023
{: #security-compliance-april252023}
{: release-note}

Filter results by tag
:   You can now filter your results by specific tags. For more information about viewing and filtering results, see [Viewing results in the dashboard](/docs/security-compliance?topic=security-compliance-results).


## 24 April 2023
{: #security-compliance-april242023}
{: release-note}

Now available: Toronto location
:   Toronto is now available as a location for processing your data. To learn more about how data is processed in {{site.data.keyword.compliance_short}}, see [Storing and encrypting](/docs/security-compliance?topic=security-compliance-mng-data).


## 20 April 2023
{: #security-compliance-april202023}
{: release-note}

Updates to the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 1.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile are now available. For more information, see the [Change log](/docs/security-compliance?topic=security-compliance-fs-change-log).



## 17 April 2023
{: #security-compliance-april172023}
{: release-note}

Updates to the {{site.data.keyword.cloud_notm}} Security Best Practices library and profile
:   Updates to version 1.1.0 of the {{site.data.keyword.cloud_notm}} Security Best Practices library and profile are now available. For more information, see the change log.


## 10 April 2023
{: #security-compliance-april102023}
{: release-note}

Customize notifications per attachment
:   As part of creating an attachment, you can now configure notifications by attachment. You can set a customized failure threshold or select specific controls that you want to be alerted for. By default, when notifications are enabled for your account, you are notified if 15% of the controls in a single scan fail. To adjust this you can adjust the threshold or you can turn off notifications as you create an attachment.

If you already have notifications configured they were migrated to the new format. To update your notification settings, you can do so in the settings of each attachment.
{: note}


## 31 March 2023
{: #security-compliance-march312023}
{: release-note}

[deprecated]{: tag-deprecated} Collector-based architecture

:   Starting 30 June 2023 {{site.data.keyword.compliance_short}} will be a provision-able, regional service offering in the IBM Cloud catalog. As this change is made, support for the collector-based architecture (v1) that currently resides in the Hybrid Cloud section of the UI will be removed. If you are exclusively evaluating IBM Cloud resources, you can start migrating at any time to the improved user experience by creating an attachment. If you are working using a collector to evaluate a hybrid cloud scenario, additional information will be available about your migration plan soon.



## 13 March 2023
{: #security-compliance-march132023}
{: release-note}

New version of the {{site.data.keyword.cloud_notm}} Security Best Practices library
:   Version 1.1.0 of the {{site.data.keyword.cloud_notm}} Security Best Practices library and profile are now available. For more information, see the Change log.


## 3 February 2023
{: #security-compliance-feb032023}
{: release-note}

New version of the {{site.data.keyword.cloud_notm}} for Financial Services library
:   Version 1.1.0 of the {{site.data.keyword.cloud_notm}} for Financial Services library and profile are now available. For more information, see the [Change log](/docs/security-compliance?topic=security-compliance-fs-change-log).



## 14 December 2022
{: #security-compliance-dec1422}
{: release-note}

A new and improved experience for {{site.data.keyword.compliance_short}} is now available!
:   We've been working in the background for the past several months to incorporate all of the feedback that we've received and we’re excited to share our new and improved architecture with you. When you work with our new architecture, there are a few changes to terminology and functionality that you’ll need to be aware of.

   * **Enterprise support**: Hierarchical management of organizational compliance

   * **Simplified setup**: There is no need to create service IDs, write IAM policies, or manage API keys when working with {{site.data.keyword.cloud_notm}}.

   * **More customization**: Create version-able controls, profiles, and assessments through simple declarative rules and then customize evaluation parameters for each attachment.

   * **New profile format**: Moving from a goal-based architecture to an assessment based architecture to provide more transparency into how evaluations are conducted.

   * **Customer-owned storage**: Duration and capacity limits for saved monitoring results are removed by allowing you to secure your compliance data in your own Cloud Object Storage bucket

   * **Terminology**: With the introduction of our new architecture, terminology has been re-evaluated and updated to ensure a more cohesive experience of the product.

   As previously announced, the Configuration Governance component has been removed as part of this release. This means that any rules that previously existed in your account have been removed and are no longer being enforced.
   {: important}


## 10 October 2022
{: #security-compliance-oct1022}
{: release-note}

Updates coming soon!
:   A new and improved experience for {{site.data.keyword.compliance_short}} is on its way! We've been working in the background for the past several months to incorporate all the feedback that we've received and we're almost ready to share it with you. To ensure the best experience possible, there are a few changes to the current functionality that you'll need to be aware of. When our new experience is released, you can expect to see:

   **A more seamless integration for {{site.data.keyword.cloud_notm}} resources!** Not only will you no longer be required to configure and deploy a collector to scan resources that run on {{site.data.keyword.cloud_notm}}, but your experience in the UI will now be more consistent throughout the product.

   **The removal of Configuration Governance**. Although rules will continue to exist in the new experience, we are temporarily removing the Configuration Governance component of the service which is currently used for enforcement. While there is no timeline in place for this functionality to return, we will keep you updated.



## 21 September 2022
{: #security-compliance-sept2122}
{: release-note}

Now available: New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.6.0  of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-change-log).




## 1 September 2022
{: #security-compliance-sept0122}
{: release-note}

New properties available for Virtual Private Cloud
:   {{site.data.keyword.cloud_notm}} Virtual Private Cloud now has additional properties available as part of the Configuration Governance component. You can create guardrails for virtual servers such as restricting the use of floating IPs and service metadata.

Removed: Credential passphrase
:   As of today, 1 September 2022, the ability to use a passphrase to manage the security of your credentials is deprecated in favor of Bring Your Own Key (BYOK) functionality. If you did not disable your passphrase and return to IBM-managed, you must recreate all of your credentials to continue to scan your resources. For help enabling BYOK or to learn more about how your credentials are protected, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).



## 11 August 2022
{: #security-compliance-aug1222}
{: release-note}

Now available: New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.5.0  of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-change-log).


## 9 August 2022
{: #security-compliance-aug0922}
{: release-note}

New available: Longer default storage
:   The data that is generated during a scan is now stored for 180 days. This is an increase from 30 days. For more information about how your data is stored, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).


## 3 August 2022
{: #security-compliance-aug-0322}

Change to permission requirements for integrations
:   As of today, Security and Compliance Integrations permissions for viewing, creating, updating, and deleting integrations in {{site.data.keyword.compliance_short}} are no longer supported. To work with integrations use the following action to role mappings:

   * `compliance.posture-management.integrations-read`: View an integration in {{site.data.keyword.compliance_short}}.
   * `compliance.posture-management.integrations-create`: Create an integration in {{site.data.keyword.compliance_short}}.
   * `compliance.posture-management.integrations-update`: Update an integration in {{site.data.keyword.compliance_short}}.
   * `compliance.posture-management.integrations-delete`: Delete an integration in {{site.data.keyword.compliance_short}}.

   For more information about required permissions, view [Managing IAM access for {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-access-management).


## 2 August 2022
{: #security-compliance-aug-0222}

Deprecated: Credential passphrase
:   As of today, the ability to create a passphrase to manage the security of your credentials is deprecated in favor of the Bring Your Own Key (BYOK) functionality. If you are currently using a passphrase to protect your credentials, you must disable the passphrase by returning to IBM-managed encryption before 1 September 2022. Then, you can enable BYOK on the **Settings** page of the {{site.data.keyword.compliance_short}} UI. For more information about how your credentials are protected, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).

## 25 July 2022
{: #security-compliance-july2522}
{: release-note}

Now available: Profile updates
:   Goal updates are now available {{site.data.keyword.cloud_notm}} Security Best Practices Profiles. For more information see the {{site.data.keyword.cloud_notm}} Security Best Practices change log.


## 12 July 2022
{: #security-compliance-july1222}
{: release-note}

Now available: New region - WDC
:   {{site.data.keyword.compliance_short}} is now configured to use the Washington DC region as a back up should a disaster scenario occur.


## 23 June 2022
{: #security-compliance-june2322}
{: release-note}

Now available: New version of the {{site.data.keyword.cloud_notm}} for Financial Services
:   Version 0.4.0  of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-change-log).


## 1 June 2022
{: #security-compliance-June0122}
{: release-note}

As of 1 June 2022, the Security Insights component of {{site.data.keyword.compliance_short}} is deprecated and support was removed. A replacement has not yet been found. Please note, this discontinuation does not affect the other features in {{site.data.keyword.compliance_short}}. If you have comments, questions, or concerns, please reach out to Jessica Doherty by email at `jpbonner@us.ibm.com`.


## 27 May 2022
{: #security-compliance-may2722}
{: release-note}

Profiles are constantly expanding and are not an exhaustive list of all the controls that might be required for every organization. Users can validate the available goals and determine where a need to supplement their workloads with other security and compliance measures exists.
{: note}

Now available: {{site.data.keyword.cloud_notm}} Security Best Practices Controls profile
:    Released today, the {{site.data.keyword.cloud_notm}} Security Best Practices profile is a collection of goals that can help an organization to ensure that they are adhering to best practices as defined by {{site.data.keyword.cloud_notm}} security.

Now available: The {{site.data.keyword.cloud_notm}} Control Library profile
:    As part of this release the {{site.data.keyword.cloud_notm}} Best Practices Controls 1.0 profile was renamed to the {{site.data.keyword.cloud_notm}} Control Library. The {{site.data.keyword.cloud_notm}} Control Library is a profile that contains all the available controls and goals that are available for {{site.data.keyword.cloud_notm}}. The library cannot be used to scan your resources directly, but you are able to create a custom profile from the library.

Now available: New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.3.0  of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-change-log).


## 13 May 2022
{: #security-compliance-may1322}
{: release-note}

New pricing plans available
:    The Posture Management component of the {{site.data.keyword.compliance_short}} is now a paid component. For more information about how pricing works and the available plans, see [How does {{site.data.keyword.compliance_short}} calculate pricing?](/docs/security-compliance?topic=security-compliance-scc-pricing)

For the most up-to-date pricing information, you can create a cost estimate by clicking **Add to estimate** from either the [provisioning](/security-compliance/catalog) or [plan page](/security-compliance/plan).



## 5 May 2022
{: #security-compliance-may0522}
{: release-note}

In addition to bug fixes and general updates, version 0.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is updated with the following changes as of 4 May 2022.

| Goal ID   | Associated controls | Update |
|:----------|:-------------|:------------|
| `3000906` | `SC-8-0`, `SC-8(1)`, `SC-13`, and `SC-23` | Updated goal and fact collection logic. |
| `3000601` | `CM-8(3)(a)`, `RA-5(a)`, `SI-2(2)`, and `SI-2(a)` | Updated goal logic to consider whether the status is either unscanned or incomplete. |
| `3000601` | `CM-8(3)(a)`, `RA-5(a)`, `SI-2(2)`, and `SI-2(a)` | Updated messaging. |
| `3000407` | `SC-8-0`, `SC-8(1)`, `SC-13`, and `SC-23` | Updated goal and fact collection logic. |
| `3000462` | `CM-2`, `CM-7(a)`, `CM-8(3)(a)`, and `SA-3(a)` | Updated goal and fact collection logic. |
| `3000029`* | `AC-3`, `AC-5(b)`, `AC-6-0`, and `AC-2(i)` | Goal is removed. |
{: caption="Table. Summary of {{site.data.keyword.cloud_notm}} for Financial Services profile changes for 4 May 2022" caption-side="top"}

*This goal is also removed from version 0.1.4.


## 5 April 2022
{: #security-compliance-apr0522}
{: release-note}

New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.1.4 and Version 0.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile are now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-change-log).


## 23 March 2022
{: #security-compliance-mar2322}
{: release-note}

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000046` - `3000048` and `3000473` - `3000474`.


## 10 March 2022
{: #security-compliance-mar1022}
{: release-note}

Create rule flow updates
:   When you create a rule by using the console, the flow now includes the attachment of a scope. To try out the new flow, see [the {{site.data.keyword.compliance_short}} UI](/security-compliance/rules){: external}.

Quick start: Posture Management
:   The {{site.data.keyword.compliance_short}} UI was updated to include more information in the overview page and a new Quick Start wizard for the Posture Management component of the service. To try it out, see [the {{site.data.keyword.compliance_short}} UI](/security-compliance/overview){: external}.


## 1 March 2022
{: #security-compliance-mar0122}
{: release-note}

Create scope flow updates
:   The create scope flow is now updated in the GUI to include the scheduling of scans as part of the creation of a scope. To try out the new flow, see [the {{site.data.keyword.compliance_short}} UI](/security-compliance/scopes){: external}.


## 17 February 2022
{: #security-compliance-feb1722}
{: release-note}

New service available in Configuration Governance
:   VPN for Virtual Private Cloud is now available as part of the Configuration Governance component. You can create guardrails for VPN for VPC such as enforcing specific IPsec and IKE policies for authentication and encryption.



## 27 January 2022
{: #security-compliance-jan2722}
{: release-note}

Add parameters during credential mapping
:   When resources such as an instance of {{site.data.keyword.containershort}} clusters are scanned, additional parameters must be provided in order for the collector to access all their configuration data. If so, additional fields are displayed in the {{site.data.keyword.compliance_short}} UI when you are mapping credentials.



Now available: New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.1.3 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-change-log).

## 21 January 2022
{: #security-compliance-jan2122}
{: release-note}

New service available in Configuration Governance
:   {{site.data.keyword.cloud_notm}} App ID is now available as part of the Configuration Governance component. You can create guardrails for App ID such as enforcing whether monitoring of runtime activity that is made by application users is tracked.


## 11 January 2022
{: #security-compliance-jan1122}
{: release-note}

New service available in Configuration Governance
:   {{site.data.keyword.cloud_notm}} Code Engine is now available as part of the Configuration Governance component. You can create guardrails for Code Engine such as ensuring that projects can be created only within specific regions.


## 13 December 2021
{: #security-compliance-dec1321}
{: release-note}

{{site.data.keyword.en_short}} integration
:   You can now integrate with [{{site.data.keyword.en_full_notm}}](/catalog/services/event-notifications){: external} so that you can view and manage all your {{site.data.keyword.compliance_short}} alerts in a single location. With a fast alert time, you're able to immediately start an investigation into any reported issue and fix the vulnerability before it becomes a problem in your application.

   To connect the {{site.data.keyword.compliance_short}} with the {{site.data.keyword.en_short}} service, see [Enabling event notifications](/docs/security-compliance?topic=security-compliance-event-notifications).

Deprecation of the alerts capability
:   As of 13 December 2021, alerts are deprecated in favor of [{{site.data.keyword.en_short}}](/docs/security-compliance?topic=security-compliance-event-notifications). The ability to create alerts within the {{site.data.keyword.compliance_short}} is no longer supported. You can continue to view, enable, disable, or delete your existing alerts until 15 March 2021. After this date, any existing alerts will be deleted, and the feature will be removed from the UI.

   To enable the new notifications capability, you can go to the **Global settings > Event Notifications** section of the {{site.data.keyword.compliance_short}} UI. For more information, see [Enabling event notifications](/docs/security-compliance?topic=security-compliance-event-notifications).


## 9 December 2021
{: #security-compliance-dec921}
{: release-note}

Customer-managed collectors can now be installed on a cluster
:   You can now install your customer-managed collector on to an {{site.data.keyword.cloud_notm}} Kubernetes Service or OpenShift cluster.

New service available in Configuration Governance
:   {{site.data.keyword.cloud_notm}} Container Registry is now available as part of the Configuration Governance component. You can create guardrails for Container Registry such as restricting an account so that it can push and pull images only over private connections.


## 22 November 2021
{: #security-compliance-nov2221}
{: release-note}

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000542` - `3000544` and `3000321`.

## 1 November 2021
{: #security-compliance-nov012021}
{: release-note}

Scan your OpenShift clusters
:   The ability to scan your OpenShift clusters is now available through the OpenShift Compliance Operator(OSCO) integration

## 27 October 2021
{: #security-compliance-oct272021}
{: release-note}

Deprecation of the bookmarks capability
:   The ability to create bookmarks or direct connections within the {{site.data.keyword.compliance_short}} will be deprecated on 30 November 2021, when the feature will be removed from the UI. Be sure to save any bookmarked URLs that you need to before the deprecation date.

## 16 September 2021
{: #security-compliance-sept152021}
{: release-note}

New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.1.2 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-change-log).



## 2 September 2021
{: #security-compliance-sept0221}
{: release-note}

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000526` - `3000533`


## 18 August 2021
{: #security-compliance-aug1821}
{: release-note}

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000510` - `3000525` and `3000640`.

## 22 July 2021
{: #security-compliance-jul2221}
{: release-note}

New Posture Management API endpoints
:   With this release, 9 new API endpoints for the Posture Management API are available. To get started, see the Posture Management API documentation.

Consolidated SDK package
:   To make it easier to programmatically access the API from your code, {{site.data.keyword.compliance_short}} SDK packages are now available. The SDKs implement best practices for using the API and reduces the amount of code that you need to write. For more information, see the documentation for the following APIs:

* Admin
* Configuration Governance
* Posture Management


New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000509`

## 24 June 2021
{: #security-compliance-june242021}
{: release-note}


New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.1.1 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-change-log).


## 22 June 2021
{: #security-compliance-jun2221}
{: release-note}

Tanium integration
:   Now, you can configure [Tanium Comply](https://help.tanium.com/bundle/ug_comply_cloud/page/comply/index.html){: external} to forward your compliance data. With Tanium Comply, you can evaluate your organizations endpoints for potential vulnerabilities and misconfigurations against industry security standards, vulnerability definitions, and custom compliance checks. When you integrate Tanium with the {{site.data.keyword.compliance_short}}, you can view all your compliance data in one location in the same format.


## 14 June 2021
{: #security-compliance-jun1421}
{: release-note}

IBM-managed collector
:   A collector is used to gather the configuration information about your resources and then validate it against a specified standard. Previously, you were responsible for the installation and lifecycle management of the collector. Now, you can get a proof of concept up and running quickly by configuring an IBM-managed collector.

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000901` - `3000907`

## 5 April 2021
{: #security-compliance-april0521}

Initial Posture Management API support
:   As part of this release, the Posture Management component of the service provides three external APIs that you can use as part of your security and compliance automation. For more information, see the Posture Management API docs.

Proxy support for discovery and fact collection
:   With this release, you can configure your collector to use a proxy to access the public endpoints to enhance the security of your scans.

New goal mapping
:   The goal `3000045` is now mapped to CM-2 NIST 800 and were added to an additional profile.

{{site.data.keyword.cloud_notm}} for Financial Services profile
:   Released today, the {{site.data.keyword.cloud_notm}} for Financial Services profile is a collection of curated goals. These goals can help organizations on the path to meeting the NIST 800-53 security controls that are required for financial institutions. By validating your resources against the {{site.data.keyword.cloud_notm}} for Financial Services profile, you can be more confident that your {{site.data.keyword.cloud_notm}} resources are following best practices for security and compliance.

   *Important*: The {{site.data.keyword.cloud_notm}} for Financial Services profile are constantly expanding and is not an exhaustive list of all the controls that might be required for every organization. Users can validate the available goals and determine where a need to supplement their workloads with other security measures exists.



## 23 March 2021
{: #security-compliance-march0321}
{: release-note}

Manage the location in which your data is stored
:   Have specific regulations around where your data is stored and processed? With {{site.data.keyword.compliance_short}}, you can now choose the location in which the data that is generated by the service is managed. To set your location preferences, you can go to the **Settings** page of the {{site.data.keyword.compliance_short}} UI. For more information, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).


## 15 March 2021
{: #security-compliance-march1521}
{: release-note}

Customize default values for your resources
:   Looking for more options to help you govern {{site.data.keyword.cloud_notm}} resources? With {{site.data.keyword.compliance_short}}, you can now create templates that define your preferred property values for target resources in your selected {{site.data.keyword.cloud_notm}} accounts. After you create a template and attach it to a scope, your customized defaults override the default values that are provided by IBM.


## 17 February 2021
{: #security-compliance-feb1721}
{: release-note}

Manage your own encryption
:   If you're using {{site.data.keyword.compliance_short}} to monitor your current posture, you can now manage your encryption settings in the **Data settings** tab of the service UI.

   By default, the data that is generated by the {{site.data.keyword.compliance_short}} is encrypted at rest by IBM. To control the encryption of your data, you can enable a key management service and select your own key. For more information, see [Protecting your sensitive data](/docs/security-compliance?topic=security-compliance-mng-data).

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. 51 new goals were added to the IBM profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the IBM Best Practices Controls 1.0 profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000110` - `3000117`
* Goal ID's: `3000256` - `3000279`
* Goal ID's: `3000311` - `3000320`
* Goal ID's: `3000631` - `3000639`



## 15 December 2020
{: #security-compliance-dec1520}
{: release-note}

Updated Scopes page
:   An improved experience is now available for viewing, creating, and deleting scopes.

Updated Inventory page
:   You can now delete inventories that you no longer require.

New dashboard widget
:   Monitor your overall security and compliance at a glance by adding a {{site.data.keyword.compliance_short}} widget to your dashboard in the {{site.data.keyword.cloud_notm}} console. To learn more about customizing your dashboard, check out [Working with scoped dashboards](/docs/account?topic=account-custom-dashboard).

## 8 December 2020
{: #security-compliance-dec0820}
{: release-note}

Updated Goals page
:   An improved experience is now available for viewing and customizing goals.

Updated Profiles page
:   An improved experience is now available for viewing and managing profiles. For more information, see [Working with profiles](/docs/security-compliance?topic=security-compliance-build-custom-profiles).

## 19 November 2020
{: #security-compliance-dec1920}
{: release-note}

Updated Settings page
:   An improved experience is now available for protecting the credentials that you use in the {{site.data.keyword.compliance_short}}.

## 1 September 2020
{: #security-compliance-sept0120}
{: release-note}

General availability of the {{site.data.keyword.compliance_short}}
:   The {{site.data.keyword.compliance_short}} is now generally available on {{site.data.keyword.cloud_notm}}!

   In this release, the {{site.data.keyword.compliance_short}} offers support for profiles that you can use to monitor your accounts for compliance and config rules for governing the use of resources across your accounts.
