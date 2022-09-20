---

copyright:
  years: 2020, 2022
lastupdated: "2022-09-20"

keywords: profiles, user-defined, predefined profiles, controls, goals, nist, best practices, security, compliance

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
{:release-note: data-hd-content-type='release-note'}


# What is a profile?
{: #profiles}

A profile is a collection of related controls. After you gather the configuration information of your resources and ready your accounts for monitoring, you can create profiles to define the list of controls that you'd like to validate against.
{: shortdesc} 


Running a scan against a specific profile does not ensure regulatory compliance. The scan is intended to provide a point in time statement of your current posture for a specific group of resources.
{: important}


Profiles consist of several interrelated components, including controls and goals. Learn how profiles bring these components together to help you templatize the requirements that you want to monitor for across an environment.

## Learning about controls, goals, and libraries
{: #understand-profiles}

The basic building block of a profile is a [control](#x2018434){: term}. Controls can be broad guidelines, such as security requirements to encrypt data at rest or prevent unprivileged access to confidential systems.

You can implement a control by meeting one or more [goals](#x2117978){: term}. In {{site.data.keyword.compliance_short}}, goals are used to evaluate whether a control is being met. {{site.data.keyword.compliance_short}} maps goals to external regulatory libraries of controls, which are divided into families (groups), that are used to prove that you are compliant with the required standards for your industry. Each control can apply to one or more profiles and one or more goals might be required to be fully compliant with each control. To see how control libraries map to goals, check out the following image.

![Profile layout shown in diagram format. The information that is shown in the image is described in the surrounding text.](/images/profiles.svg){: caption="Figure 1. Understanding profiles" caption-side="bottom"}



## Working with profiles
{: #profile-types}

When you work with profiles in the {{site.data.keyword.compliance_short}}, you interact with predefined or custom profiles that are used to evaluate a specific set of resources that are known as a scope.

Predefined profiles
:   Predefined profiles contain collections of controls that are curated based on standards for an industry. 

   {{site.data.keyword.compliance_short}} supports over 40 predefined profiles. Within each profile, you can inspect the controls and goals that are required to be fully compliant. For a complete list of supported profiles, go to the Profiles page in the {{site.data.keyword.compliance_short}} UI.

   You can't modify or remove controls from a predefined profile. But, you can [create a new profile](/docs/security-compliance?topic=security-compliance-custom-profiles) from a predefined profile so that you choose only the controls and goals that are relevant for your business.
   {: note}


Custom profiles
:   If you want to ability to customize a profile to include any combination of controls and goals, you can create a custom profile. By using the {{site.data.keyword.compliance_short}} UI, you can build a profile from an existing predefined profile, or you can create a profile with your own controls and guidelines from scratch.


Attachment
:   To start evaluating your resources for compliance by using a specific profile, you must create an attachment between your scope and the profile. To create the attachment, you [schedule a scan](/docs/security-compliance?topic=security-compliance-schedule-scan). 

<customer-updates>

## Monitoring resources
{: #profile-monitor}

You can monitor resources across various {{site.data.keyword.cloud_notm}} services by using the profiles that you select or create. Goals are continuously updated. The following table lists the resources that can be monitored. It also specifies which resources can be evaluated by using the {{site.data.keyword.cloud_notm}} for Financial Services profile. 

| Service | Monitored by Financial Services |
| ------- | ------------------------------- |
| Activity Tracker | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| App ID |  ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Bare Metal Servers |  |
| Certificate Manager |  |
| Cloudant | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Cloud Internet Services (CIS) |      |
| {{site.data.keyword.cloud_notm}} Monitoring | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Cloud Object Storage | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Cloud Shell |      |
| Code Engine |      |
| Container Registry | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| {{site.data.keyword.cloud_notm}} Databases \n Databases for MongoDB* \n Databases for Redis \n Databases for Elasticsearch \n Databases for etcd \n Databases for PostgreSQL \n Databases for Cloudant | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Direct Link | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Event Streams | ![Checkmark icon](../../icons/checkmark-icon.svg) |
|  |        |
| Hyper Protect Crypto Services* \n Hyper Protect DBaaS for MongoDB  | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| IAM | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Key Protect |       |
| Kubernetes Service |          |
| Red Hat OpenShift Kubernetes Service |            |
| Satellite Red Hat OpenShift Kubernetes Service |            |
| Schematics |           |
| Secrets Manager |           |
| Security Insights | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Toolchain |          |
| Transit Gateway | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Virtual Private Cloud \n VPN for VPC* \n File Storage for VPC \n Application Load Balancer for VPC \n Security Groups for VPC* \n Flow Logs for VPC* \n Block Storage for VPC | ![Checkmark icon](../../icons/checkmark-icon.svg) |
{: caption="Table 1. {{site.data.keyword.cloud_notm}} services that can be monitored" caption-side="top"}

## How do I get started?
{: #profile-get-started}

To get started with profiles, you can go to the **Menu icon** ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Configure > Profiles**.

For more information about creating profiles, see [Building custom profiles](/docs/security-compliance?topic=security-compliance-custom-profiles).

