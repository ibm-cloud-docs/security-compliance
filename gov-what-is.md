---

copyright:
  years: 2021
lastupdated: "2021-08-17"

keywords: rule, config rule, what is a config rule, resource configuration, resource governance, governance, properties, conditions, templates, properties, govern

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

# What is Configuration Governance?
{: #what-is-governance}

By using the Configuration Governance component of the {{site.data.keyword.compliance_full}}, you can create rules and templates that set guardrails around the way that your resources can be configured. By defining rules and customized defaults, you can ensure that your resource configurations are always in line with the guidelines that your organization has in place, which significantly decreases the likelihood of a misconfiguration-related security issue.
{: shortdesc}

## Understanding your options
{: #gov-understand-options}



The following diagram describes both the synchronous and asynchronous flows for retrieving resource states.

![The diagram shows both the synchronous and asynchronous flows that can be used to retrieve resource states.](../images/adopt-cip-pattern.svg){: caption="Figure 1. The CIP request flow patterns" caption-side="bottom"}

![The image shows an example rule sequence.](/images/config-rule-sequence.svg){: caption="Figure 3. Config rule sequence flow" caption-side="bottom"}

1. As a security focal, you create a config rule for a target resource and attach it to a scope.
2. A developer makes a request to create or modify a resource that is owned by the target resource.
3. The target resource evaluates the request against your defined rule.
4. The target resource blocks or allows the action to complete.

| Rules request|
|:-----------|
| <ol><li>Configuration Governance sends a request to the service provider's CIP to get the resource state of a target. Learn more by [viewing the API](https://pages.github.ibm.com/project-fortress/adoption/#/Synchronous%20Pattern/get_v2_config){: external}. </li><li>Service provider collects the requested resource state. </li><li>Service provider returns the resource state to the Configuration Governance component.</li></ol> |
{: caption="Table 2. Synchronous CIP pattern flow" caption-side="top"}
{: #rule-table}
{: tab-title="Rules"}
{: tab-group="gov"}
{: class="simple-tab-table"}

| Templates request flow|
|:-----------|
| <ol><li>Configuration Governance sends a request to the service provider’s CIP to request resource state of a target. [Learn more about the API specs](https://pages.github.ibm.com/project-fortress/adoption/#/Asynchronous%20Pattern/post_v1_config){: external}. </li><li>Service provider asynchronously collects the requested resource state. </li><li>Service provider sends a request to Configuration Governance to signal that the resource state collection on the requested target is complete. </li><li>Configuration Governance sends a request to the service provider’s CIP to fetch the resource state of the requested target. [Learn more about the API specs](https://pages.github.ibm.com/project-fortress/adoption/#/Asynchronous%20Pattern/get_v1_config__config_request_id_){: external}.</li></ol> |
{: caption="Table 2. Asynchronous CIP pattern flow" caption-side="top"}
{: #template-table}
{: tab-title="Templates"}
{: tab-group="gov"}
{: class="simple-tab-table"}



## Understanding how to use rules
{: #config-rule-use-cases}

Rules help you to standardize the fine-grained configurations of your {{site.data.keyword.cloud_notm}} services. As an administrator, you can determine where your organization might benefit from guardrails around resource configuration and then use the {{site.data.keyword.compliance_short}} to create and monitor them. By attaching your rule to a specific [scope](/docs/security-compliance?topic=security-compliance-rules#evaluate-rules-ui), you can limit the rule to a specific section of your business. Then, every 24 hours, an evaluation is done and the results are updated in the {{site.data.keyword.compliance_short}} UI where you can start investigating potential issues.


Check out the following diagram to see an example rule sequence:





Want to see rules in action? Check out [Preventing public network access on {{site.data.keyword.keymanagementserviceshort}} with the {{site.data.keyword.compliance_short}}](https://www.ibm.com/cloud/blog/prevent-public-network-access-on-key-protect-instances-with-the-security-and-compliance-center){: external}!
{: note}


## Customizing default values for your resources
{: #customize-default-values}

With templates, you can define your preferred values, or customized defaults, on properties that are used to configure an {{site.data.keyword.cloud_notm}} resource. By creating templates that users in your accounts can regularly review and reference, you set guidelines for teams to follow. After you attach a template to a [scope](#x2037763){:term}, your customized defaults are applied by target services to ensure that your selections override the IBM-defined values each time that a target resource is created.

You can use templates to override IBM-defined property values only. Configurations that are selected by users at resource creation aren't replaced by the values that you define as part of a template. To avoid duplicated definitions, you can add each property to one template per scope.
{: note}

Check out the following diagram to see an example template sequence:

![The image shows an example template sequence.](images/template-sequence.svg){: caption="Figure 1. Template sequence flow" caption-side="bottom"}

1. As a security focal, you create a template for a target resource and attach it to a scope.
2. A developer makes a request to create a resource that is owned by the target service.
3. The target service checks for an existing template in the {{site.data.keyword.compliance_short}}.
4. The target service uses the template data to apply your customized default values on the new resource.




## How are rules inherited across accounts?
{: #config-rule-hierarchy}

As you create rules and attach them to scopes, your defined configurations move down your account hierarchy. If you attach a rule to your entire enterprise, the rule is applied to the target resources that exist within the enterprise. Likewise, if you limit a rule to a specific account group, its properties are inherited by the accounts that exist in that group. You can choose to exclude scopes, such as accounts that are used for testing, so that your rule is applied only where you need it.

The following diagram shows how two rules are applied across an enterprise.

![The image shows how two rules are applied across an enterprise. One rule moves down the hierarchy. Another rule is attached only to a specific account, so its properties are applied only to the resources that it contains.](/images/rule-hierarchy.svg){: caption="Figure 4. Config rule inheritance" caption-side="bottom"}



## Supported {{site.data.keyword.cloud_notm}} services
{: #rule-supported}

The properties that are available in the {{site.data.keyword.compliance_short}} vary depending on the service that you create a rule or template for. To see the available properties and understand how they can be formatted to create a rule or a template, you can visit the service documentation that is linked in the following table.

| Service | Rules | Templates |
|:--------|:------|:----------|
| [Certificate Manager](/docs/certificate-manager?topic=certificate-manager-manage-security-compliance) | ![Checkmark icon](../icons/checkmark-icon.svg)| |
| [Cloud Object Storage](/docs/cloud-object-storage?topic=cloud-object-storage-manage-security-compliance) | ![Checkmark icon](../icons/checkmark-icon.svg)| ![Checkmark icon](../icons/checkmark-icon.svg) |
| [Cloud Shell](/docs/cloud-shell?topic=cloud-shell-manage-security-compliance) | ![Checkmark icon](../icons/checkmark-icon.svg)| |
| [Direct Link](/docs/dl?topic=dl-manage-security-compliance) | ![Checkmark icon](../icons/checkmark-icon.svg)| |
| [Event Streams](/docs/EventStreams?topic=EventStreams-manage-security-compliance) | ![Checkmark icon](../icons/checkmark-icon.svg)| |
| [Internet Services](/docs/cis?topic=cis-manage-security-compliance) | ![Checkmark icon](../icons/checkmark-icon.svg)| |
| [Load Balancer for VPC](/docs/vpc?topic=vpc-manage-security-compliance-lb) | ![Checkmark icon](../icons/checkmark-icon.svg)| |
| [Key Protect](/docs/key-protect?topic=key-protect-manage-security-compliance) | ![Checkmark icon](../icons/checkmark-icon.svg)| ![Checkmark icon](../icons/checkmark-icon.svg) |
| [Platform components](/docs/overview?topic=overview-manage-security-compliance) | ![Checkmark icon](../icons/checkmark-icon.svg)| |
| [Transit Gateway](/docs/transit-gateway?topic=transit-gateway-manage-security-compliance) | ![Checkmark icon](../icons/checkmark-icon.svg)| |
{: caption="Table 1. Supported {{site.data.keyword.cloud_notm}} services" caption-side="top"}


## How can I get started?
{: #gov-next-steps}

To get started with rules, you can go to the **Menu icon** ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Configure**, or check out the [API reference](/apidocs/security-compliance/config){: external} to learn more about creating rules and templates programmatically. 

[![This image is a visual link to the instructions for creating templates.](images/gs-templates.svg)](/docs/security-compliance?topic=security-compliance-templates)     [![This image is a visual link to the instructions for creating rules.](images/gs-rules.svg)](/docs/security-compliance?topic=security-compliance-rules)
