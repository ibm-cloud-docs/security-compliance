---

copyright:
  years: 2020
lastupdated: "2020-11-06"

keywords: rule, config rule, what is a config rule, resource configuration, resource governance, governance, rule, config rule, properties, conditions, enforcement actions

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

# What is a config rule?
{: #what-is-rule}

A config rule is a JSON document that defines the configuration of resources. With the {{site.data.keyword.compliance_full}}, you can create rules for specific {{site.data.keyword.cloud_notm}} resource types to govern the way that resources in your accounts can be provisioned or configured.
{: shortdesc}

## What makes up a rule?
{: #config-rule-components}

A rule consists of a target, one or more property conditions, and enforcement actions. You can create rules with [simple properties](#config-rule-simple), or you can build more complex rules with [nested properties](#config-rule-nested) and [multiple conditions](#config-rule-multiple-conditions).

The following image shows the components of a config rule.

![The image shows the components of a config rule, including its target, required configuration, and enforcement actions. The target represents the IBM Cloud service and resource type that you want to target. The required configuration section details the property checks and conditions that you want to apply. The enforcement actions are the actions that IBM takes on your behalf in cases of noncompliance.](/images/example-rule.svg){: caption="Figure 1. Components of a config rule" caption-side="bottom"}

1. The `target` object contains details about the {{site.data.keyword.cloud_notm}} service and resource type that you want to target with the rule.

    An example target object might resemble the following JSON snippet, where the `service_name` is the [CRN-qualified service name of an {{site.data.keyword.cloud_notm}} service](/docs/account?topic=account-crn#service-name-crn), and the `resource_kind` is the resource type that you want to target.

    ```json
    {
      "target": {
        "service_name": "cloudcerts",
        "resource_kind": "instance"
      }
    }
    ```
    {: screen}

    Optionally, you can include `additional_target_attributes`, such as the location or ID of a resource, as an extra qualifier for the resource kind. Additional target attributes vary depending on the service that you are targeting.
    {: note}
2. The `required_config` object contains the property conditions that you want to apply to the target.

    Property conditions contain three basic elements: a `property`, an `operator`, and a `value` (for applicable conditions). Available properties depend on the service and resource kind that you want to configure. The following example shows the `private_network_only` property, which is a [supported property for {{site.data.keyword.cloudcerts_long_notm}} instances](/docs/certificate-manager?topic=certificate-manager-manage-security-compliance).
    
    ```json
    {
      "required_config": {
        "description": "Private network access check",
        "and": [
          {
            "property": "private_network_only",
            "operator": "is_false"
          }
        ]
      }
    }
    ```
    {: screen}

    For more examples, check out rules with [simple properties](#config-rule-simple), [nested properties](#config-rule-nested), and [multiple conditions](#config-rule-multiple-conditions). 
3. The `enforcement_actions` object contains the actions that {{site.data.keyword.compliance_short}} must run on your behalf in case the property conditions aren't met.

   When the {{site.data.keyword.compliance_short}} evaluates the state of the target resource against your defined rule, it checks to ensure that its defined conditions evaluate to true. If they are not true, IBM carries out your wanted enforcement actions. 

    ```json
    {
      "enforcement_actions": [
        {
          "action": "disallow"
        },
        {
          "action": "audit_log"
        }
      ]
    }
    ```
    {: screen}

    The `disallow` action blocks a noncompliant request from completing, and the `audit_log` action logs event in Activity Tracker with LogDNA.

### Rules with simple properties
{: #config-rule-simple}

Rules with simple property conditions contain the basic components of a rule. The following truncated example shows a [{{site.data.keyword.cloudcerts_short}} rule](/docs/certificate-manager?topic=certificate-manager-manage-security-compliance) that checks whether the number of days before a certificate expires is greater than 10. 

```json
{
  "required_config": {
    "description": "Certificates that expire in 10 days",
    "and": [
      {
        "property": "days_to_expiration",
        "operator": "num_greater_than",
        "value": 10
      }
    ]
  }
}
```
{: screen}

| Parameter | Description | Required |
|--------------|-----------|--------|
| `property` | A resource configuration variable. Available options depend on the service and resource kind that you want to target. | Yes |
| `operator` | A type of comparison between the property value and its condition value. | Yes |
| `value` | The condition value. This value is a polymorphic variable that can either be a single value or a list of alternative values. | Applicable for some operators |
{: caption="Table 1. Properties, operators, and values" caption-side="top"}

#### Supported operators
{: #config-rule-operators}

You can use four types of operators to create config rules: general, string, numeric, and boolean. The following table describes the supported operators types.

String-based operators are case-sensitive.
{: note}

| Operator | Type | Description | Requires `value` parameter |
|:--------|:-----------|:------------------------|
| `is_empty`  | General | The property value is not specified, null, or an empty string | No |
| `is_not_empty`  | General |  The property value is specified, not null, and not an empty string (any value). | No |
| `is_true`  | Boolean | The property value is true. | No |
| `is_false`  | Boolean | The property value is false. | No |
| `string_equals` | String |  The property value is an exact match to the condition value.  | Yes |
| `string_not_equals` | String |  The property value is not an exact match to the condition value. |Yes|
| `string_match` | String |  The property value matches the condition value by using the [Krauss wildcarding algorithm](https://en.wikipedia.org/wiki/Krauss_wildcard-matching_algorithm){: external}. | Yes | 
| `string_not_match` | String |  The property value does not match the condition value by using [Krauss wildcarding algorithm](https://en.wikipedia.org/wiki/Krauss_wildcard-matching_algorithm){: external}.| Yes |
| `strings_in_list`[^strings_in_list] | String |  All property values are in the condition value list. | Yes |
| `ips_in_range`[^ips_in_range] | String |  All property values, in IPv4 or IPv6 format, are in the condition value list. | Yes |
| `num_equals` | Numeric | The property value numerically matches to the condition value. | Yes |
| `num_not_equals` | Numeric | The property value does not numerically match the condition value.| Yes |
| `num_less_than` | Numeric | The property value is numerically less than the condition value.| Yes |
| `num_less_than_equals` | Numeric | The property value is numerically less than or equal to the condition value. | Yes |
| `num_greater_than` | Numeric | The property value is numerically greater than the condition value.|Yes|
| `num_greater_than_equals` | Numeric | The property value is numerically greater than or equal to the condition value. | Yes |
{: caption="Table 2. Supported operator types" caption-side="top"}

[^strings_in_list]: To create a rule with a property that supports the `strings_in_list` operator, include a list of strings for the `value` parameter. For example, `{"value": ["A", "B," "C"]}`. 

[^ips_in_range]: To create a rule with a property that supports the `ips_in_range` operator, include a list of CIDR or IP addresses for the `value` parameter. For example, `{"value": ["10.168.175.0/24", "2000:db8:ffff:ffff:ffff:ffff:ffff:ffff"]}`. 

### Rules with nested properties
{: #config-rule-nested}

Some {{site.data.keyword.cloud_notm}} services support composite policies, or subpolicies within a main policy, to manage their resources. For example, you can restrict access to a Cloud Object Storage bucket by setting a firewall (main policy), and optionally you can select the IP addresses that are authorized to access it (subpolicy). 

To create a rule for a resource that supports a composite policy, you use nested properties. Rules with nested properties use dot notation in the form of `<main_property>.<sub_property>` to indicate a nested relationship between two properties.

The following truncated example shows a property condition for the `firewall` property. 

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
          "10.168.177.0/24",
          "10.168.179.0/24",
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

The `firewall.allowed_ip` and `firewall.denied_ip` properties show a nested relationship between `firewall` and its subproperties.

### Rules with multiple conditions
{: #config-rule-multiple-conditions}

You might want to define even more complex relationships between a set of property conditions. To define multiple property conditions in one rule definition, you can use logical operators (`and` / `or`) to express the relationships between property conditions. 

In the following examples, **`A`**, **`B`**, and **`C`** are property conditions that I want to define and require for a target resource. The following statement evaluates to true only if **`(A and B and C)`** is true.

```json
{
  "and": [
    A,
    B, 
    C
  ]
}
```
{: screen}

The following statement evaluates to true only if **`(A or B or C)`** is true.

```json
{
  "or": [
    A,
    B, 
    C
  ]
}
```
{: screen}

The following statement evaluates to true only if **`(A or (B and C))`** is true.

```json
{
  "or": [
    A,
    "and": [
      B, 
      C
    ]
  ]
}
```
{: screen}

## How can I use a rule in {{site.data.keyword.cloud_notm}}?
{: #config-rule-use-cases}

After you create a rule, you can use it to standardize the configuration of its target {{site.data.keyword.cloud_notm}} service and resource type in your selected accounts. You can start to monitor your resources by [attaching the rule to a scope](/docs/security-compliance?topic=security-compliance-rules#evaluate-rules). Every 24 hours, a report is generated so that you can [view your rule results](/docs/security-compliance?topic=security-compliance-results) in the {{site.data.keyword.compliance_short}} UI and investigate potential issues. 

The following diagram describes an example rule sequence:

![The image shows an example rule sequence.](/images/config-rule-sequence.svg){: caption="Figure 3. Config rule sequence flow" caption-side="bottom"}

1. As a security focal, you create a config rule for a target resource and attach it to a scope.
2. A developer makes a request to create or modify a resource that is owned by the target resource.
3. The target resource evaluates the request against your defined rule.
4. The target resource blocks or allows the action to complete.



## How are rules inherited across accounts?
{: #config-rule-hierarchy}

As you create rules and attach them to scopes, your defined configurations move down your account hierarchy. If you attach a rule to your entire enterprise, the rule is applied to the target resources that exist within the enterprise. Likewise, if you limit a rule to a specific account group, its properties are inherited by the accounts that exist in that group. You can choose to exclude scopes, such as accounts that are used for testing, so that your rule is applied only where you need it.

The following diagram shows how two rules are applied across an enterprise.

![The image shows how two rules are applied across an enterprise. One rule moves down the hierarchy. Another rule is attached only to a specific account, so its properties are applied only to the resources that it contains.](/images/rule-hierarchy.svg){: caption="Figure 4. Config rule inheritance" caption-side="bottom"}

## How can I get started?
{: #config-rule-next-steps}

To get started with rules, you can go to the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Configure rules**, or check out the [API reference](/apidocs/security-compliance/config){: external} to learn more about creating rules programmatically.

For more information about defining rules, see [Working with config rules](/docs/security-compliance?topic=security-compliance-rules). 





