<staging>---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-15"

keywords: documenting security and compliance, onboard security and compliance, onboard fortress, onboard scc, integrated services, fortress, scc, enable rules, enable scc, enable fortress, enable goals, goal writing, define goals,

subcollection: security-compliance

content-type: tutorial
services: security-compliance

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

# Onboarding to Posture Management
{: #internal-onboard-monitoring}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance"}

As a service provider in IBM Cloud, onboarding to the {{site.data.keyword.compliance_short}} is part of completing Service Framework requirements. The time-frame for each service varies, but is tracked as part of FS Cloud and Hamilton waves [[Wave 2]](https://github.ibm.com/ibmcloud/Portfolio-Offering/issues/183){: external}. This tutorial can help you to onboard to Posture Management by walking you through the process of identifying and documenting the goals that can help users of your service to monitor their security and compliance posture. Note: To onboard to Posture Management you do not need to [define rules](/docs/security-compliance?topic=security-compliance-internal-onboard-config).
{: shortdesc}

To learn more about the Posture Management component of the {{site.data.keyword.compliance_short}}, check out our [overview video](https://secure.video.ibm.com/channel/23887899/playlist/636374/video/129254715){: external} to see some example use-cases, or read more about goals in [the docs](/docs/security-compliance?topic=security-compliance-posture-management).
{: tip}

## Summary
{: #internal-posture-summary}

Onboarding to Posture Management is a service framework requirement. To adopt Posture Management, {{site.data.keyword.cloud_notm}} service providers are required to fulfill four onboarding steps:

1. Identify your goals
2. Write and edit your goals
3. Submit your goals
4. Prepare end-user documentation


## Identify your goals
{: #internal-determine-controls}
{: step}

The first stage of onboarding to the {{site.data.keyword.compliance_short}} is to enable your service to be monitored by the Posture Management component. This phase of onboarding **typically does NOT require any development work** from service teams - it is an exercise in documenting APIs so that the {{site.data.keyword.compliance_short}} team can implement goals to perform monitoring for your service.

The {{site.data.keyword.compliance_short}} maps external databases of controls, such as NIST 800-53, to predefined profiles that end users can use to monitor and assess compliance across their cloud environments. Each control is mapped to a goal which is a checkpoint for a specific control that allows the {{site.data.keyword.compliance_short}} to assess your level of compliance to that control.

To onboard to the Posture Management component, you must first determine which goals are applicable to your service. When determining your goals there are a couple things to consider aside from security controls: what is configurable by the user, what type of access is required to do these configurations, and what are best practices recommended by the service. When thinking about what is configurable by the user, be sure to include configurations available before, during and after resource provisioning. If your service does not provision any resources, be sure to include any settings configurable at the account level for your service.

## Write and edit your goals
{: #internal-define-goals}
{: step}

With the knowledge that you have of your service, assess whether there are any additional configuration parameters that users would want to check in your service in order to meet security and compliance goals. If so, add these additional goals to the list. Anything that is configurable, might impact the security of your service, or is considered a best practice should be considered as a goal.

For each goal, you must provide the APIs that are called to determine whether your service's resources in a customer account are compliant to the goal. Along with the APIs, please explain any non-trivial logic that would be needed to check the API results to see if the control is met.

### Goal writing tips
{: #goal-writing-tips}

* We recommend offering managers and technical leads work together to determine applicable goals that customers will use to secure their workloads.
* Write goals using the following goal statement template: _Check whether `<service_name>` `<details>`..._ where `<service_name>` is the legal short name of your offering. For example:
    * _Check whether Cloud Object Storage is accessible only using private endpoints_
    * _Check whether Cloud Object Storage is enabled with customer-managed encryption and Bring Your Own Key (BYOK)_
    * _Check whether Cloud Object Storage buckets are enabled with IBM Activity Tracker_
* Do not use abbreviations that are not legally approved. For example: `COS`, `BSS`, and `IKS`.
* Take advantage of your service's content team and have them review your goals for any spelling / grammar or potential IBM style conflicts.

To help you get started, you can refer to the goals of the [IBM Cloud Best Practices Controls profile](https://cloud.ibm.com/security-compliance/profiles/48?details=controls&type=1){: external} that you can use to determine whether there is something in your service that a user could configure to affect whether the control is met in their account.

A goal is not applicable to your service if your internal service operations team has to meet the goal but users don't meet this goal by configuring your service. For example, if the IAM Access Groups team is assessing whether the goal *All data must be encrypted at rest* applies to their services, they would note that there is nothing that a user could configure in the Access Groups services that would validate the goal. This is true even though the Access Groups service stores data in a Cloudant database that their operations team is responsible for ensuring is encrypted. Because, in order to check whether that goal is met, a Cloudant API would be called, not an Access Groups API.
{: note}

To see the goals that are already available for customer use, visit the [Profiles page](https://cloud.ibm.com/security-compliance/profiles) and search for *{{site.data.keyword.cloud_notm}} Best Practices Controls 1.0*. Toggle each category to see the specific goals.

## Submit your goals
{: #internal-submit-goals}
{: step}

Follow the instructions [here](https://github.ibm.com/project-fortress/compliance-adoption) to submit your service goals information.

If you believe your service has no applicable goals, we ask that you follow the [guidelines](/docs/security-compliance?topic=security-compliance-internal-onboard-faq#internal-faq-extension) to request an extension.

## Prepare end user documentation
{: #internal-monitoring-docs}
{: step}

The final step of Posture Management Onboarding is to share your service goals information with your content team so that they can prepare the end-user documentation. Your content team must [review the goals](/docs/security-compliance?topic=security-compliance-doc-scc#scc-review-goals) for your service and update your docs with the [{{site.data.keyword.compliance_short}} template](https://github.ibm.com/cloud-docs-internal/writing/blob/draft/content-kit/manage-scc-template.md). As part of Posture Management, your docs must include the `Managing security and compliance with _service_name_` and `Monitoring security and compliance posture with _service_name_` sections.

</staging>
