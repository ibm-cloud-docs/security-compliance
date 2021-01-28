---

copyright:
  years: 2021
lastupdated: "2021-01-28"

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

A configuration rule is a JSON document that defines the configuration of resources. With the {{site.data.keyword.compliance_full}}, you can create rules for specific {{site.data.keyword.cloud_notm}} resource types to govern the way that resources in your account can be provisioned or configured.
{: shortdesc}


## What makes up a rule?
{: #config-rule-components}

A rule consists of a target, one or more property conditions, and enforcement actions. You can create rules with simple properties, or you can build more complex rules with nested properties that contain multiple conditions.

Check out the following image to see how a config rule is structured.

![This image shows the components of a config rule, including its target, required configuration, and the enforcement actions. The information in the image is detailed in the surrounding content.](/images/example-rule.svg){: caption="Figure 1. Components of a config rule" caption-side="bottom"}

1. The `target` object contains the details about the {{site.data.keyword.cloud_notm}} service and resource type that you want to target with the rule.

  An example target object might resemble the following JSON snippet, where the `service_name` is the [CRN-qualified service name of an {{site.data.keyword.cloud_notm}} service](/docs/account?topic=account-crn#service-name-crn), and the `resource_kind` is the type of resource that you want to create a rule for.

  ```json
  {
    "target": {
      "service_name": "cloudcerts",
      "resource_kind": "instance"
    }
  }
  ```
  {: screen}

  Optionally, you can include `additional_target_attributes`, such as the location or ID of a resource, as an extra qualifier for the resource kind. Additional target attributes vary depending on the service that you want to target.

2. The `required_config` object contains the property conditions that you want to apply to the target. Property conditions contain three basic elements: a `property`, an `operator`, and a `value`. The available properties and the defined elements depend on the service and resource kind that you want to configure.

  <table>
    <caption>Table 1. Properties, operators, and values</caption>
    <tr>
      <th>Parameter</th>
      <th>Description</th>
      <th>Required</th>
    </tr>
    <tr>
      <td><code>property</code></td>
      <td>A resource configuration variable. Available options depend on the service and resource kind that you want to target.</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td><code>operator</code></td>
      <td>A type of comparison between the property value and its condition value.</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td><code>value</code></td>
      <td>The condition value. This value is a polymorphic variable that can either be a single value or a list of alternative values.</td>
      <td>Applicable for some operators</td>
    </tr>
  </table>
  
  For example, if you work with the Certificate Manager service and you wanted to be alerted 10 days before a certificate expires, you could create a rule that uses the `days_to_expiration` property. It would look similar to the following code snippet.

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

3. The `enforcement_actions` object contains the actions that {{site.data.keyword.compliance_short}} takes on your behalf if the property conditions that you defined are not met.

  When the {{site.data.keyword.compliance_short}}, evaluates the state of the target resource against your defined rule, it checks to ensure its defined conditions are evaluated to true. If they do not, IBM carries out your defined enforcement actions.

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

  The `disallow` action blocks a noncompliance request from completing, and the `audit_log` action registers an event in Activity Tracker with LogDNA so that you're able to track potential issues.


## What is a property?
{: #rule-properties}

As mentioned earlier in this topic, a property is a resource configuration variable that you can use as a security checkpoint. Occasionally, creating a rule with a single simple property won't fully address your need. To create more complex rules, you can include multiple conditions and nested properties.

Multiple conditions allow for you to define the relationship between two or more property conditions. To define multiple property conditions in one rule, you can use the logical operators `and` and `or` to express the relationship between them.

So, as an example, the code snippets shown in the following image evaluate to true only:

1. If **(A and B and C)** are true.
2. If **(A or B or C)** are true.
3. If **(A or (B and C))** are true.

![The diagram shows the correlation between multiple conditions. All of the information is conveyed in the surrounding text.](images/config-rules-property.svg){: caption="Figure 2. The ways in which properties can relate to each other." caption-side="bottom"}



In addition to allowing multiple conditions, some {{site.data.keyword.cloud_notm}} services, such as Cloud Object Storage, support nested or sub-parameters within the main definition. To create a rule with nested properties, you can use dot notation in the form of `<main_property>.<sub_property>` to indicate the relationship between the two properties.

For example, you can resrict access to a Cloud Object Storage bucket by determining which IP addresses are authorized to access the firewall. In this example, `firewall` is the main property while `allowed_ip` and `denied_ip` are nested. 

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


### Supported properties
{: #rule-properties-supported}

The properties that are available in the {{site.data.keyword.compliance_short}} vary depending on the service that you create a rule for. To see the available properties and understand how they can be formatted to create a rule, you can visit the service documentation.

* [Certificate Manager](/docs/certificate-manager?topic=certificate-manager-manage-security-compliance)
* [Cloud Object Storage](/docs/cloud-object-storage?topic=cloud-object-storage-manage-security-compliance)
* [Key Protect](/docs/key-protect?topic=key-protect-manage-security-compliance)
* [Platform components](/docs/overview?topic=overview-manage-security-compliance)




## What are the supported operators?
{: #rule-operators}

An operator is the type of comparison that you want to make between a property and its value. You can use four types of operators to create config rules: general, string, numeric, and boolean. Check out the following table to learn more about each type.

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


## How can I use a rule in {{site.data.keyword.cloud_notm}}?
{: #config-rule-use-cases}

After you create a rule, you can use it to standardize the configuration of its target {{site.data.keyword.cloud_notm}} service and resource type in your selected accounts. You can start to monitor your resources by [attaching the rule to a scope](/docs/security-compliance?topic=security-compliance-rules#evaluate-rules). Every 24 hours, a report is generated so that you can [view your rule results](/docs/security-compliance?topic=security-compliance-results) in the {{site.data.keyword.compliance_short}} UI and investigate potential issues. 

The following diagram describes an example rule sequence:

![The image shows an example rule sequence.](/images/config-rule-sequence.svg){: caption="Figure 3. Config rule sequence flow" caption-side="bottom"}

1. As a security focal, you create a config rule for a target resource and attach it to a scope.
2. A developer makes a request to create or modify a resource that is owned by the target resource.
3. The target resource evaluates the request against your defined rule.
4. The target resource blocks or allows the action to complete.


### Use case: Configuring {{site.data.keyword.cloudcerts_short}} instances
{: #config-rule-use-case-certificate-manager}

Let's say that your business is looking for a way to standardize how its {{site.data.keyword.cloudcerts_short}} instances are configured across multiple accounts. To meet an organizational guideline, your business wants to prove that it manages its SSL and TLS certificates only over a private network. 

You decide to define the following rule:

```json
{ 
  "rule": {
    "name": "Private network only - {{site.data.keyword.cloudcerts_short}}",
    "description": "Access to {{site.data.keyword.cloudcerts_short}} instances is allowed only over a private network",
    "target": {
      "service_name": "cloudcerts",
      "resource_kind": "instance"
    },
    "required_config": {
	  "description": "Private network check",
      "and": [
        { 
          "property": "private_network_only",
          "operator": "is_true"
        }
      ]
    },
    "enforcement_actions": [
      {
        "action": "disallow"
      },
      {
        "action": "audit_log"
      }
    ]
  }
}
```
{: screen}

Later, a user makes a request to create a {{site.data.keyword.cloudcerts_short}} service instance in your account. To validate the request, {{site.data.keyword.cloudcerts_short}} service now uses the conditions that you defined in your config rule. If the account user creates the instance over a private network, {{site.data.keyword.cloudcerts_short}} allows the action to complete because it is compliant with your rule. But, if the account user creates the instance over a public network, {{site.data.keyword.cloudcerts_short}} blocks the request and returns the following message to the account user:

```
Requested change is not compliant with configuration rules.
```
{: screen}


From the {{site.data.keyword.compliance_short}} UI, you can monitor for results on your defined rules by clicking the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > View results**.



## How are rules inherited across accounts?
{: #config-rule-hierarchy}

As you create rules and attach them to scopes, your defined configurations move down your account hierarchy. If you attach a rule to your entire enterprise, the rule is applied to the target resources that exist within the enterprise. Likewise, if you limit a rule to a specific account group, its properties are inherited by the accounts that exist in that group. You can choose to exclude scopes, such as accounts that are used for testing, so that your rule is applied only where you need it.

The following diagram shows how two rules are applied across an enterprise.

![The image shows how two rules are applied across an enterprise. One rule moves down the hierarchy. Another rule is attached only to a specific account, so its properties are applied only to the resources that it contains.](/images/rule-hierarchy.svg){: caption="Figure 4. Config rule inheritance" caption-side="bottom"}

## How can I get started?
{: #config-rule-next-steps}

To get started with rules, you can go to the **Menu icon** ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Configure rules**, or check out the [API reference](/apidocs/security-compliance/config){: external} to learn more about creating rules programmatically.

For more specific information about how to define rules, see [Working with config rules](/docs/security-compliance?topic=security-compliance-rules).


