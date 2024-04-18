---

copyright:
  years: 2020, 2024
lastupdated: "2024-04-18"

keywords: supported controls, controls available, supported environments, rule, profile, compliance issue, predefined rules, user-defined rules

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# FAQs
{: #faqs}

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

When you look at your results in the UI, you see that some results have "Additional details". This is because the results are associated with the Toolchain service. The Toolchain pipeline sends the associated details and evidence along with the results to {{site.data.keyword.compliance_short}}.


## Which controls are supported by {{site.data.keyword.compliance_short}}?
{: #faq-control-support}
{: faq}
{: support}

{{site.data.keyword.compliance_short}} supports various controls that are designed to help organizations manage and maintain the security and compliance of their systems and data. To view a list of available profiles, see [Available predefined profiles](/docs/security-compliance?topic=security-compliance-predefined-profiles). To view all of the controls that are supported by the product, go to the {{site.data.keyword.compliance_short}} UI in the {{site.data.keyword.cloud_notm}} console.

