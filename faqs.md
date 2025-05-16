---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: supported controls, controls available, supported environments, rule, profile, compliance issue, predefined rules, user-defined rules

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# FAQ for {{site.data.keyword.compliance_short}}
{: #faqs}


As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


Frequently asked questions for {{site.data.keyword.compliance_full}} might include questions about managing profiles, defining custom rules, attaching scopes, and evaluating resources for compliance. To find all FAQs for {{site.data.keyword.cloud_notm}}, see the [FAQ library](/docs/faqs).


## How do I start monitoring a rule?
{: #faq-monitor-rule}
{: faq}
{: support}

{{site.data.keyword.compliance_short}} supports two types of rules - predefined and custom. Predefined rules are associated with specifications by default and are automatically monitored when you create an attachment to a profile. Custom rules can be monitored after they are associated with a specification by customizing a control library. Then, you select those controls when you create an attachment.


## Can I create a rule for a service that I didn't provision?
{: #faq-provisioned-rule}
{: faq}
{: support}

Yes, you can create rules for services or resources that are not already provisioned in your accounts. When the service or resource is created, it is automatically evaluated according to your rule definition.

## Why don't I see additional details for everything?
{: #faq-evidence}
{: faq}
{: support}

The results that have "Additional details" are associated with the Toolchain service. The Toolchain pipeline sends the associated details and evidence along with the results to {{site.data.keyword.compliance_short}}.


## Which controls are supported by {{site.data.keyword.compliance_short}}?
{: #faq-control-support}
{: faq}
{: support}

{{site.data.keyword.compliance_short}} supports various controls that are designed to help organizations manage and maintain the security and compliance of their systems and data. To view a list of available profiles, see [Available predefined profiles](/docs/security-compliance?topic=security-compliance-predefined-profiles). To view all of the controls that are supported by the product, go to the {{site.data.keyword.compliance_short}} UI in the {{site.data.keyword.cloud_notm}} console.



## Is there a difference between exclusions when it comes to subscopes and scopes?
{: #faq-exclusions}
{: faq}

As a user, you can define exclusions at both the scope and subscope level. Exclusions at the scope level exclude the resource from an evaluation. The resource is not part of the scope and is not being evaluated, or charged by {{site.data.keyword.compliance_short}}. Exclusions at the subscope level are more like a filter. The excluded resource still exists in your scope and is being evaluated. But, the results are not visible at the subscope level. 
