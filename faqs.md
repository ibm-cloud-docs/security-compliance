---

copyright:
  years: 2020, 2023
lastupdated: "2023-06-28"

keywords: watchtower, supported environments, rule, profile, compliance issue, predefined rules, user-defined rules

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



## [deprecated]{: tag-deprecated} Why do I have to create a collector?
{: #faq-collector}
{: faq}
{: support}

In the original {{site.data.keyword.compliance_short}} architecture, a collector is used to gather information about your resource configuration and evaluate it against your defined profile. If you're working with the hybrid cloud flow, you must create a collector to complete the evaluation. For more information about collectors, see [Managing collectors](/docs/security-compliance?topic=security-compliance-collector).

