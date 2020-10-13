---
copyright:
  years: 2020
lastupdated: "2020-10-12"

keywords: documenting security and compliance, security and compliance for *service_name*, integrated services, security for *service_name*, compliance for *service_name*

subcollection: security-compliance

---

{:external: target="_blank" .external}
{:note: .note}
{:term: .term}
{:shortdesc: .shortdesc}
{:table: .aria-labeledby="caption"}


# Managing Security and Compliance with *service_name*
{: #manage-security-compliance}



The {{site.data.keyword.compliance_short}} is built directly into the platform and integrated with *service_name* to help you manage security and compliance for your organization.
{: shortdesc}

With the {{site.data.keyword.compliance_short}}, you can:

* Monitor for controls and goals that pertain to *service_name*
* Define rules for *service_name* that can help to standardize resource configuration




## Monitoring security and compliance posture with *service_name*
{: #monitor-*service_name*}

As a security or compliance focal, you can use the *service_name* goals to help ensure that your organization is adhereing to the external and internal standards for your industry. By using the {{site.data.keyword.compliance_short}} to validate the resource configurations in your account against a profile, you can identity potential issues as they arise.

All of the goals for *service_name* are added to the {{site.data.keyword.cloud_notm}} Best Practices Controls 1.0 profile by can also be mapped to other profiles.
{: note}

To start monitoring your resources, check out [Getting started with {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic-security-compliance-getting-started)

**Available goals for *service_name***

* *Check whether certificates are automatically renewed before expiration*
* <additional_goal>



## Governing *service_name* resource configuration
{: #govern-service_name}

As a security or compliance focal, you can use the {{site.data.keyword.compliance_short}} to define config rules for the instances of *service_name* that you create.

Config rules are defined as a JSON object and are used to enforce the configuration standards that you want to implement across your accounts. Each rule is comprised of a target and required configuration that detail the the specific properties within a target service that you want to define a rule for. To learn more about governing the configuration of resources in your accounts, check out [Working with config rules](/docs/security-compliance?topic=security-compliance-rules).

The following table details the information that you need to create a config rule for the *service_name* service.

| Resource kind | Property | Operator type | Value | Description |
|:--------------|:---------|:--------------|:------|:------------|
| *instance* | *private_network_only* | Boolean | - | *Indicates whether access to a Certificate Manager instance is allowed only through a private network. |
| <resource_kind> | <property_name> | <operator> | <value> | <description> |
{: caption="Table 1. Rule properties for *service_name*" caption-side="top"}

