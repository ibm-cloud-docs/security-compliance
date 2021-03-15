---

copyright:
  years: 2021
lastupdated: "2021-03-15"

keywords: watchtower, supported environments, rule, profile, compliance issue, predefined rules, user-defined rules

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


# FAQs
{: #faqs}

Frequently asked questions for {{site.data.keyword.compliance_full}} might include questions about managing profiles, defining custom rules, attaching scopes, and evaluating resources for compliance. To find all FAQs for {{site.data.keyword.cloud_notm}}, see the [FAQ library](/docs/faqs).
{: shortdesc}

## Which environments are currently integrated with the service?
{: #environment-list}

You can use the {{site.data.keyword.compliance_short}} to monitor your security and compliance posture in the following environments:

* IBM Cloud
* Amazon Web Services
* Google Cloud Platform
* Microsoft Azure
* On-premises


## Which IBM Cloud services can I scan?
{: #resource-scan}

You can use the {{site.data.keyword.compliance_short}} to monitor your resources that pertain to the following services:

* {{site.data.keyword.at_short}}
* {{site.data.keyword.blockstorageshort}}
* {{site.data.keyword.cloudcerts_short}}
* {{site.data.keyword.databases-for}}
* {{site.data.keyword.iamshort}}
* {{site.data.keyword.registryshort}}
* {{site.data.keyword.contdelivery_short}}
* {{site.data.keyword.cloudant_short_notm}}
* {{site.data.keyword.vpc_short}}
* {{site.data.keyword.cis_short}}
* {{site.data.keyword.keymanagementserviceshort}}
* {{site.data.keyword.containershort_notm}}
* {{site.data.keyword.cos_short}}
* {{site.data.keyword.security-advisor_short}}



## What is the WatchTower image and how do I update it?
{: #watchtower}
{: faq}
{: support}

When you install a collector, you install two images: the collector image itself and a Watchtower image.

The collector image can be upgraded or patched automatically as the Watchtower image is used to continuously monitor for changes that are made to it. The Watchtower image cannot be upgraded or patched automatically. If there is a new vulnerability or update to the Watchtower image, you are responsible for updating or patching it.

For help with updating or more information about Watchtower, see the [open source docs](https://github.com/containrrr/watchtower){: external}.



## How do I attach a config rule to a profile?
{: #faq-rule-profile}
{: faq}
{: support}

Currently, you can't attach a rule to a profile. The {{site.data.keyword.compliance_short}} supports two types of rules, predefined and user-defined.

* Predefined rules can be goals that are offered as part of controls that exist in a profile.
* User-defined rules are created by you and can be attached directly to a scope for evaluation but cannot be included in a profile.

For more information about the types of rules, see [Working with config rules](/docs/security-compliance?topic=security-compliance-rules).


## Can I create a config rule for a service that I don't currently have provisioned?
{: #faq-service-not-provisioned}
{: faq}
{: support}

Yes, you can create rules for services or resources that are not already provisioned in your accounts. When a rule is in place, the service or resource is automatically evaluated according to the enforcement actions that you chose when you created the rule.



## How are config rules and templates different?
{: #faq-rule-template-differences}
{: faq}
{: support}

Rules provide the ability to enforce conditions and actions around the configuration of a target resource. With rules, you can use the {{site.data.keyword.compliance_short}}] UI to monitor for configuration changes in your accounts so that you understand which resources are noncompliant to the rules that you have in place.

Templates help you to customize the default property values that are associated with an {{site.data.keyword.cloud_notm}} resource. By creating templates for resources in your accounts, you're able to override IBM-defined default values for a resource, such as a bucket in Cloud Object Storage, with your preferred values. For more information, see [What is a template?](/docs/security-compliance?topic=security-compliance-what-is-template)



## Why can't I select a remediation option?
{: #remediate-gray}

Currently, you must be working with Amazon Web Services or Microsoft Azure to configure remediation. If you select a scope that does not support remediation, the option is unavailable and not able to be configured.

For more information about remediation, see [Remediating issues](/docs/security-compliance?topic=security-compliance-remediation).


