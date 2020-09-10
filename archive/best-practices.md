---

copyright:
  years: 2020
lastupdated: "2020-08-20"

keywords: 

subcollection: security-compliance

---

{:codeblock: .codeblock}
{:screen: .screen}
{:download: .download}
{:external: target="_blank" .external}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}
{:gif: data-image-type='gif'}
{:term: .term}
{:important: .important}
{:note: .note}
{:pre: .pre}
{:tip: .tip}
{:preview: .preview}
{:deprecated: .deprecated}
{:shortdesc: .shortdesc}
{:support: data-reuse='support'}
{:script: data-hd-video='script'}
{:table: .aria-labeledby="caption"}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:help: data-hd-content-type='help'}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tsSymptoms: .tsSymptoms}
{:beta: .beta}

# Meeting your security and compliance goals
{: #best-practices}

{{site.data.keyword.compliance_full}} provides a secure by default experience that allows you to create a culture of compliance that begins at the start of development and holds through the end of an external audit. With automation in place to stop catastrophic mistakes, you're able to build and scale your workloads with full control while your teams are able to code with accountability and confidence. All while saving your business time and money.
{: shortdesc}

For highly regulated industries, such as financial services, achieving continuous security within a cloud environment is an important first step towards protecting customer and application data. Historically, that process has been difficult and manual, which placed your organization at risk. But, with {{site.data.keyword.cloud_notm}} you can integrate automatic security checks into every day workflows that are designed to minimize risk, standardize resource configuration, and ensure adherence to both internal and external requirements.


With the {{site.data.keyword.compliance_short}} you can:

* Work with predefined controls that are implemented across your {{site.data.keyword.cloud_notm}} accounts
* Define configuration rules that you can target to specific resources
* Monitor your resource configurations in a single dashboard for any potential risk
* Investigate the evaluation results to see which accounts or services are most at risk
* Retain and access your results to prepare for internal and external audits

Currently, the {{site.data.keyword.compliance_short}} is available for enterprise accounts only. To learn more about enterprise accounts, see [What is an enterprise?](/docs/account?topic=account-what-is-enterprise)
{: important}


## Defining your strategy
{: #strategy}

Security and compliance are two concepts that are often spoken of interchangeably. But, there are some significant differences between them. For example, compliance regulations change slowly and are generally measured as a snapshot in time. Whereas, security threats are constant and always changing. By implementing guardrails across your accounts for how resources can be used, you can ensure that you're always monitoring for new risks and continually enforcing the regulations and laws for your industry.

Depending on the role that you fill in your organization, you might focus on ensuring compliance to industry regulations or you might focus more on mitigating incoming security threats. As shown in the following diagram, you can achieve your end goals differently by starting with either a [profile](#x2034950){: term} or a [config rule](#x2037526){: term}. 


![The diagram describes the information that is included when creating profiles and rules. The information in the diagram is explained in more detail in the surrounding text.](../images/profile-rules-scenarios.svg){: caption="Figure 1. Defining your use case" caption-side="bottom"}


Most often, as a compliance focal, you need to adhere to multiple regulations or laws at once. You are responsible for understanding and implementing the controls that are required for your business. You also have a responsibility to gather evidence that proves to external auditors that your compliance checks are in place and in continuous compliance.

As a security focal, your focus is threat detection and mitigation. To address your main concerns, you need to be sure that everyone in your organization is following the mandated guidelines. By building security checks into everyday workflows, you can regulate the way that resources can be provisioned and configured across all of {{site.data.keyword.cloud_notm}}.


## How can you use the {{site.data.keyword.compliance_short}}?
{: #use-security-compliance}

With the {{site.data.keyword.compliance_short}}, you can implement predefined controls and create configuration rules for your {{site.data.keyword.cloud_notm}} resources. Built on the [Open Security Control Assessment Language (OSCAL)](https://pages.nist.gov/OSCAL/learnmore/){: external}, the {{site.data.keyword.compliance_short}} delivers machine-readable representations of security and compliance data to {{site.data.keyword.cloud_notm}}. You can quickly evaluate your posture, identify areas that are most vulnerable, and remediate findings in a standardized format.

When you use the {{site.data.keyword.compliance_short}}, you interact with several interrelated components, including profiles, configuration rules, and scopes. The following diagram and text shows how these components work together to help you manage and evaluate compliance in {{site.data.keyword.cloud_notm}}.

![The diagram shows how you can create profiles and rules, enforce them across accounts that you specify, and continuously evaluate your {{site.data.keyword.cloud_notm}} for compliance. The information in the diagram is explained in further detail in the surrounding text.](../images/profiles-rules-scopes.svg){: caption="Figure 2. {{site.data.keyword.compliance_short}} components" caption-side="bottom"}


### Scopes
{: #scopes}

Scopes are organizational boundaries that help you to determine where to evaluate a profile or rule in your enterprise or account hierarchy.

A profile or a rule can be evaluated across one or more scopes, such as specific accounts or even your entire enterprise. When you attach an existing profile or rule to a scope, you decide which accounts to include or exclude for monitoring. After you attach your profile or rule to a scope, the {{site.data.keyword.compliance_short}} generates a report every 24 hours that show your current posture. The results are delivered on a rolling basis with a new scan for each resource completed every 24 hours.


## Next steps
{: #start}

Ready to start building security and compliance into your every day workflows? {{site.data.keyword.compliance_short}} is integrated directly into the {{site.data.keyword.cloud_notm}} platform, so you can get started without deploying a new resource by choosing to create either a profile or a rule.


[![This image is a visual link to the instructions for defining a profile.](images/profile-start.svg)](/docs/security-compliance?topic=security-compliance-profiles)     [![This image is a visual link to the instructions for defining a rule.](images/rule-start.svg)](/docs/security-compliance?topic=security-compliance-rules)


