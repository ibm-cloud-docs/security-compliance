---

copyright:
  years: 2020, 2022
lastupdated: "2022-10-04"

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

# Formatting rules and templates
{: #formatting-rules-templates}

 You can choose to create rules and templates with a single property, or you can build a more complex rule with nested properties that contains multiple conditions.


## Understanding the format
{: #gov-format-understand}

Rules and templates are comprised of several different building blocks, including a target, one or more property conditions, and a value. Check out the following image to see a simple breakdown of how rules and templates are structured.

![This image shows the breakdown of a rule and a template by component.](../../images/example-gov.svg){: caption="Figure 1. Components of a config rule and a template" caption-side="bottom"}

| Rule components explained |
|:-----------|
| <ol><li>The `target` object contains the details about the {{site.data.keyword.cloud_notm}} service and resource type that you want to target with the rule. It is important to note that the `service_name` is the [CRN-qualified service name of an {{site.data.keyword.cloud_notm}} service](/docs/account?topic=account-crn#service-name-crn). The `resource_kind` is the specific resource for the service that you want to set a configuration for.  </li><li>Optionally, when the properties support them, you can include `additional_target_attributes`, such as the location or ID of a resource, as an extra qualifier for the resource kind. </li><li>The `required_config` object contains the property conditions that you want to apply to the target. Property conditions contain three basic elements: a `property`, an `operator`, and a `value`. The available properties and the defined elements depend on the service and resource kind that you want to configure. [Learn more](/docs/security-compliance?topic=security-compliance-available-rule-properties). <ul>**Property**:  A configuration variable that applies to a specific resource. The available options are dependent upon the service and resource kind that you want to target.</ul> <ul>**Operator**: A type of comparison between the property value and its condition value.</ul> <ul>**Value**:  A polymorphic variable that can be either a single value or alist of alternative values that quantifies the conditions that are defined. Values are only required for some operators.</ul></li><li> The <code>enforcement_actions</code> object contains the actions that {{site.data.keyword.compliance_short}} takes on your behalf if the property conditions that you defined are not met. When the {{site.data.keyword.compliance_short}} evaluates the state of the target resource against your defined rule, it checks to ensure its defined conditions are evaluated to true. If they do not, IBM carries out your defined enforcement actions. The `disallow` action blocks a noncompliant request from completing.</li></ol> |
{: caption="Table 1. Rule components explained" caption-side="top"}
{: #rule-components}
{: tab-title="Rule components"}
{: tab-group="gov-components"}
{: class="simple-tab-table"}

| Template components explained |
|:-----------|
| <ol><li>The <code>target</code> object contains the details about the {{site.data.keyword.cloud_notm}} service and resource type that you want to target with the template. It is important to note that the <code>service_name</code> is the [CRN-qualified service name of an {{site.data.keyword.cloud_notm}} service](/docs/account?topic=account-crn#service-name-crn). </li><li>Optionally, when the properties support them, you can include <code>additional_target_attributes</code>, such as the location or ID of a resource, as an extra qualifier for the resource kind. </li><li>The <code>customized_defaults</code> object contains the property conditions that you want to apply to the target. Property conditions contain three basic elements: a <code>property</code> and a <code>value</code>. The available properties and the defined elements depend on the service and resource kind that you want to configure. [Learn more](/docs/security-compliance?topic=security-compliance-available-rule-properties). <ul>**Property**: A configuration variable that applies to a specific resource. The available options are dependent upon the service and resource kind that you want to target.</ul><ul>**Value**:  A polymorphic variable that can be either a single value or alist of alternative values that quantifies the conditions that are defined.</ul></li></ol> |
{: caption="Table 1. Template components explained" caption-side="top"}
{: #template-components}
{: tab-title="Template components"}
{: tab-group="gov-components"}
{: class="simple-tab-table"}

### Integrated services
{: #integrated-services}

The properties that are available in the {{site.data.keyword.compliance_short}} vary depending on the service that you create a rule or template for. To see the available properties and understand how they can be formatted to create a rule or a template, you can visit the service documentation that is linked in the following table, or you can view a [full list of available properties](/docs/security-compliance?topic=security-compliance-available-rule-properties).

| Service | Rules | Templates |
|:--------|:------|:----------|
| [Billing Composite Service](/docs/overview?topic=overview-manage-security-compliance)  | ![Checkmark icon](../../icons/checkmark-icon.svg)| | 
| [Catalog Management](/docs/overview?topic=overview-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Certificate Manager](/docs/certificate-manager?topic=certificate-manager-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Cloud Object Storage](/docs/cloud-object-storage?topic=cloud-object-storage-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| ![Checkmark icon](../../icons/checkmark-icon.svg) |
| [Code Engine](/docs/codeengine?topic=codeengine-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Container Registry](/docs/Registry?topic=Registry-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Direct Link](/docs/dl?topic=dl-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Event Streams](/docs/EventStreams?topic=EventStreams-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Hyper Protect Crypto Services](/docs/hs-crypto?topic=hs-crypto-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Hyper Protect DBaaS for MongoDB](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Hyper Protect DBaaS for PostgreSQL](/docs/hyper-protect-dbaas-for-postgresql?topic=hyper-protect-dbaas-for-postgresql-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [IAM Access Groups Service](/docs/overview?topic=overview-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [IAM Identity Service](/docs/overview?topic=overview-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [IBM Cloud Shell](/docs/cloud-shell?topic=cloud-shell-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Internet Services](/docs/cis?topic=cis-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Key Protect](/docs/key-protect?topic=key-protect-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| ![Checkmark icon](../../icons/checkmark-icon.svg) |
| [Load Balancer for VPC](/docs/vpc?topic=vpc-manage-security-compliance-lb) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Toolchain](/docs/ContinuousDelivery?topic=ContinuousDelivery-cd-manage-security-compliance) |  ![Checkmark icon](../../icons/checkmark-icon.svg)| |
| [Transit Gateway](/docs/transit-gateway?topic=transit-gateway-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| |
{: caption="Table 2. Supported {{site.data.keyword.cloud_notm}} services" caption-side="top"}


### Available operators
{: #operators}

An operator is the type of comparison that you want to make between a property and its value. Check out the following table to learn more about each type.

String-based operators are case-sensitive.
{: note}

| Operator | Type | Description | Requires `value` parameter |
|:--------|:-----------|:-----------|:------------------------|
| `is_empty`  | General | The property value is not specified, null, or an empty string | No |
| `is_not_empty`  | General |  The property value is specified, not null, and not an empty string (any value). | No |
| `is_true`  | Boolean | The property value is true. | No |
| `is_false`  | Boolean | The property value is false. | No |
| `string_equals`[^string_equals] | String |  The property value is an exact match to the condition value. | Yes |
| `string_not_equals`[^string_not_equals] | String |  The property value is not an exact match to the condition value. |Yes|
| `string_match` | String |  The property value matches the condition value by using the [Krauss wildcarding algorithm](https://en.wikipedia.org/wiki/Krauss_wildcard-matching_algorithm){: external}. | Yes |
| `string_not_match` | String |  The property value does not match the condition value by using [Krauss wildcarding algorithm](https://en.wikipedia.org/wiki/Krauss_wildcard-matching_algorithm){: external}.| Yes |
| `strings_in_list`[^strings_in_list] | String list |  All property values are in the condition value list. | Yes |
| `ips_in_range`[^ips_in_range] | IP list |  All property values, in IPv4 or IPv6 format, are in the condition value list. | Yes |
| `num_equals`[^num_equals] | Numeric | The property value numerically matches to the condition value. | Yes |
| `num_not_equals`[^num_not_equals] | Numeric | The property value does not numerically match the condition value.| Yes |
| `num_less_than` | Numeric | The property value is numerically less than the condition value.| Yes |
| `num_less_than_equals` | Numeric | The property value is numerically less than or equal to the condition value. | Yes |
| `num_greater_than` | Numeric | The property value is numerically greater than the condition value.|Yes|
| `num_greater_than_equals` | Numeric | The property value is numerically greater than or equal to the condition value. | Yes |
{: caption="Table 3. Supported operator types" caption-side="top"}

[^string_equals]: To include multiple values, use an array. For example, `{"value": ["A", "B," "C"]}`.

[^string_not_equals]: To include multiple values, use an array. For example, `{"value": ["A", "B," "C"]}`.

[^strings_in_list]: To create a rule with a property that supports the `strings_in_list` operator, include a list of strings for the `value` parameter. For example, `{"value": ["A", "B," "C"]}`.

[^ips_in_range]: To create a rule with a property that supports the `ips_in_range` operator, include a list of CIDR or IP addresses for the `value` parameter. For example, `{"value": ["10.168.175.0/24", "2000:db8:ffff:ffff:ffff:ffff:ffff:ffff"]}`.

[^num_equals]: To include multiple values, use an array. For example, `{"value": ["1", "2," "3"]}`.

[^num_not_equals]: To include multiple values, use an array. For example, `{"value": ["1", "2," "3"]}`.

## Formatting complex rules
{: #format-rules}

Most often, rule are more complex than a single property. To create more complex scenarios, you can include multiple conditions and take advantage of nested properties. 


### Defining multiple conditions
{: #gov-multiple-conditions}

With multiple conditions, you can define the relationship between two or more property conditions. To define multiple property conditions in a single rule, you can use the logical operators `and` and `or` to express the relationship between them.

So, as an example, the code snippets shown in the following image evaluate to true only:

1. If **(A and B and C)** are true.
2. If **(A or B or C)** are true.
3. If **(A or (B and C))** are true.

![The diagram shows the correlation between multiple conditions. The information is conveyed in the surrounding text.](../../images/config-rules-property.svg){: caption="Figure 2. The ways in which properties can relate to each other." caption-side="bottom"}


### Defining nested properties
{: #gov-nested-properties}

In addition to allowing multiple conditions, some {{site.data.keyword.cloud_notm}} services, such as Cloud Object Storage, support nested or sub-parameters within the main definition. To create a rule with nested properties, you can use dot notation in the form of `<main_property>.<sub_property>` to indicate the relationship between the two properties.

For example, you can restrict access to a Cloud Object Storage bucket by determining which IP addresses are authorized to access the firewall. In this truncated example, `firewall` is the main property while `allowed_ip` and `denied_ip` are nested.

```json
{
  "required_config": {
    "description": "IP addresses authorized to access storage buckets.",
    "and": [
      {
        "property": "firewall.allowed_ip",
        "operator": "ips_in_range",
        "value":  [
          "10.168.175.0/24",
          "10.168.243.79",
          "2001:db8::/32",
          "2000:db8:ffff:ffff:ffff:ffff:ffff:ffff"
        ]
      },
      {
        "property": "firewall.denied_ip",
        "operator": "ips_in_range",
        "value":  [
          "10.168.171.0/24",
          "10.168.173.0/24"
        ]
      }
    ]
  }
}
```
{: screen}


## Formatting complex templates
{: #format-templates}

When services make multiple API calls to set your defined configurations, you must have a template in place that sets your preferred default to ensure that your resource can be configured. So, for example, say that your team is looking for a way to ensure that Cloud Object Storage buckets are always configured with the default values that are required by your organization. You want to create a bucket that:

* is in the Dallas region,
* is only accessible at a specific IP address,
* is only accessible through a private network,
* is a smart storage class,
* and has a hard quota.

But, the storage class, firewall, and hard quota configurations are set as secondary API calls during bucket creation. So, to allow the bucket to create with your rules in place, you create the following template:

```json
{
  "target": {
    "service_name": "cloud-object-storage",
    "resource_kind": "bucket",
    "additional_target_attributes": [
      {
        "name": "location",
        "value": "us-south"
      }
    ]
  },
  "customized_defaults": [
      {
        "property": "storage_class",
        "value": "us-south-smart"    
      },
      {
        "property": "firewall.allowed_network_type",
        "value": [
          "private"
        ]
      },
      {
        "property": "firewall.allowed_ip",
        "value": [
          "fe80:021b::0/64"
        ]
      },
      {
        "property": "hard_quota",
        "value": "10995116277760"
      }
    ]
  }
}

```
{: screen}

For more information about the available Cloud Object Storage properties, see the [service documentation](/docs/cloud-object-storage?topic=cloud-object-storage-manage-security-compliance).

