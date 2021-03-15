---

copyright:
  years: 2021
lastupdated: "2021-03-10"

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
{:ui: .ph data-hd-interface='ui'}
{:cli: .ph data-hd-interface='cli'}
{:api: .ph data-hd-interface='api'}

# What is a config rule?
{: #what-is-rule}

A configuration rule is a JSON document that defines the configuration of resources. With the {{site.data.keyword.compliance_full}}, you can create rules for specific {{site.data.keyword.cloud_notm}} resource types to govern the way that resources in your account can be provisioned or configured.
{: shortdesc}


## What makes up a rule?
{: #config-rule-components}

A rule consists of a target, one or more property conditions, and enforcement actions. You can create rules with simple properties, or you can build more complex rules with nested properties that contain multiple conditions.

Check out the following image to see how a config rule is structured.

![This image shows the components of a config rule, including its target, required configuration, and the enforcement actions. The information in the image is detailed in the surrounding content.](/images/example-rule.svg){: caption="Figure 1. Components of a config rule" caption-side="bottom"}

1. The `target` object contains the details about the {{site.data.keyword.cloud_notm}} service and resource type that you want to target with the rule. It is important to note that the `service_name` is the [CRN-qualified service name of an {{site.data.keyword.cloud_notm}} service](/docs/account?topic=account-crn#service-name-crn). Optionally, you can include `additional_target_attributes`, such as the location or ID of a resource, as an extra qualifier for the resource kind.

  So for example, if you wanted to create a rule that was limited to a specific bucket within object storage, it might look similar to the following truncated example.

  ```json
  {
    "target": {
      "service_name": "cloud-object-storage",
      "resource_kind": "bucket",
      "additional_target_attributes": [
        {
          "name": "resource_id",
          "operator": "is_equal",
          "value": "My_bucket"
        }
      ]
    }
  }
  ```
  {: screen}

2. The `required_config` object contains the property conditions that you want to apply to the target. Property conditions contain three basic elements: a `property`, an `operator`, and a `value`. The available properties and the defined elements depend on the service and resource kind that you want to configure. [Learn more](#rule-properties).

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

3. The `enforcement_actions` object contains the actions that {{site.data.keyword.compliance_short}} takes on your behalf if the property conditions that you defined are not met. When the {{site.data.keyword.compliance_short}}, evaluates the state of the target resource against your defined rule, it checks to ensure its defined conditions are evaluated to true. If they do not, IBM carries out your defined enforcement actions. The `disallow` action blocks a noncompliance request from completing, and the `audit_log` action registers an event in Activity Tracker with LogDNA so that you're able to track potential issues.


### How do properties work?
{: #rule-properties}

As mentioned earlier in this topic, a property is a resource configuration variable that you can use as a security checkpoint. Occasionally, creating a rule with a single simple property won't fully address your need. To create more complex rules, you can include multiple conditions and nested properties.

Multiple conditions allow for you to define the relationship between two or more property conditions. To define multiple property conditions in one rule, you can use the logical operators `and` and `or` to express the relationship between them.

So, as an example, the code snippets shown in the following image evaluate to true only:

1. If **(A and B and C)** are true.
2. If **(A or B or C)** are true.
3. If **(A or (B and C))** are true.

![The diagram shows the correlation between multiple conditions. All of the information is conveyed in the surrounding text.](images/config-rules-property.svg){: caption="Figure 2. The ways in which properties can relate to each other." caption-side="bottom"}


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



### What are the supported operators?
{: #rule-operators}

An operator is the type of comparison that you want to make between a property and its value. Check out the following table to learn more about each type.

String-based operators are case-sensitive.
{: note}

| Operator | Type | Description | Requires `value` parameter |
|:--------|:-----------|:------------------------|
| `is_empty`  | General | The property value is not specified, null, or an empty string | No |
| `is_not_empty`  | General |  The property value is specified, not null, and not an empty string (any value). | No |
| `is_true`  | Boolean | The property value is true. | No |
| `is_false`  | Boolean | The property value is false. | No |
| `string_equals`[^string_equals] | String |  The property value is an exact match to the condition value. | Yes |
| `string_not_equals` | String |  The property value is not an exact match to the condition value. |Yes|
| `string_match` | String |  The property value matches the condition value by using the [Krauss wildcarding algorithm](https://en.wikipedia.org/wiki/Krauss_wildcard-matching_algorithm){: external}. | Yes |
| `string_not_match` | String |  The property value does not match the condition value by using [Krauss wildcarding algorithm](https://en.wikipedia.org/wiki/Krauss_wildcard-matching_algorithm){: external}.| Yes |
| `strings_in_list`[^strings_in_list] | String list |  All property values are in the condition value list. | Yes |
| `ips_in_range`[^ips_in_range] | IP list |  All property values, in IPv4 or IPv6 format, are in the condition value list. | Yes |
| `num_equals` | Numeric | The property value numerically matches to the condition value. | Yes |
| `num_not_equals` | Numeric | The property value does not numerically match the condition value.| Yes |
| `num_less_than` | Numeric | The property value is numerically less than the condition value.| Yes |
| `num_less_than_equals` | Numeric | The property value is numerically less than or equal to the condition value. | Yes |
| `num_greater_than` | Numeric | The property value is numerically greater than the condition value.|Yes|
| `num_greater_than_equals` | Numeric | The property value is numerically greater than or equal to the condition value. | Yes |
{: caption="Table 2. Supported operator types" caption-side="top"}

[^string_equals]: To include multiple values, use a list. For example, `{"value": ["A", "B," "C"]}`

[^strings_in_list]: To create a rule with a property that supports the `strings_in_list` operator, include a list of strings for the `value` parameter. For example, `{"value": ["A", "B," "C"]}`.

[^ips_in_range]: To create a rule with a property that supports the `ips_in_range` operator, include a list of CIDR or IP addresses for the `value` parameter. For example, `{"value": ["10.168.175.0/24", "2000:db8:ffff:ffff:ffff:ffff:ffff:ffff"]}`.


## Which services can I apply rules to?
{: #rule-supported}

The properties that are available in the {{site.data.keyword.compliance_short}} vary depending on the service that you create a rule for. To see the available properties and understand how they can be formatted to create a rule, you can visit the service documentation.

* [Certificate Manager](/docs/certificate-manager?topic=certificate-manager-manage-security-compliance)
* [Cloud Object Storage](/docs/cloud-object-storage?topic=cloud-object-storage-manage-security-compliance)
* [Key Protect](/docs/key-protect?topic=key-protect-manage-security-compliance)
* [Platform components](/docs/overview?topic=overview-manage-security-compliance)



## How can I use a rule in {{site.data.keyword.cloud_notm}}?
{: #config-rule-use-cases}

Rules help you to standardize the fine-grained configurations of your {{site.data.keyword.cloud_notm}} services. As an administrator, you can determine where your organization might benefit from guardrails around resource configuration and then use the {{site.data.keyword.compliance_short}} to create and monitor them. By attaching your rule to a specific [scope](/docs/security-compliance?topic=security-compliance-rules#evaluate-rules-ui), you can limit the rule to a specific section of your business. Then, every 24 hours, a report is generated that details the results of your compliance in the {{site.data.keyword.compliance_short}} UI that you can use to investigate potential issues.


Check out the following diagram to see an example rule sequence:

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

To get started with rules, you can go to the **Menu icon** ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Configure rules**, or check out the [API reference](/apidocs/security-compliance/config){: external} to learn more about creating rules programmatically.

For more specific information about how to define rules, see [Working with config rules](/docs/security-compliance?topic=security-compliance-rules).


