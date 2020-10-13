<staging>---

copyright:
  years: 2020
lastupdated: "2020-10-13"

keywords: documenting security and compliance, get started, integrated services

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

# Overview
{: #internal-onboard-monitoring}


The {{site.data.keyword.compliance_full}} unifies all {{site.data.keyword.cloud_notm}} security and compliance capabilities into a "secure by default" experience for end users of {{site.data.keyword.cloud_notm}}. By integrating security and compliance monitoring directly into the platform, our customers can embed checks into their everyday workflows to help monitor their security and compliance posture. By monitoring for risks, customers can identify security vulnerabilities, quickly work to mitigate the impact, and fix the issue.
{: shortdesc}

This phase of onboarding typically does NOT require any development work from service teams - it is an excercise in documenting APIs so that the {{site.data.keyword.compliance_short}} team can implement goals to perform montoring for your service. A potential exception to that statement would be if your service has configurable parameters that are relevant to the controls but currently have no API that can be used to retrieve the state of those parameters. In this case, the service team should implement an API that allow's retrieval of the parameter.


## Hamilton wave 1
{: #internal-hamilton}

Security and compliance posture enablement is required for all Hamilton wave 1 services in 4Q2020. Although configuration governance onboarding is requried for all services in 1Q2021, services that have committed to onboarding in 4Q2020 or have work underway to do so, should still plan to complete both stages in 4Q2020.



## Prerequistes
{: #internal-monitor-prereq}

Before your service can onboard to the {{site.data.keyword.compliance_short}}, you must be onboarded to IAM.


## Step 1: Determine applicable controls
{: #internal-determine-controls}

The first stage of onboarding to the {{site.data.keyword.compliance_short}} is to enable your service to be monitored by the Posture Management component. To do this, you must first determine the controls that are applicable to your service and define goals related to that control. To help you get started, we've provided a [list of controls](https://ibm.ent.box.com/s/77xq7e0r7mtpel7irn5zfd7keb9bk6gj){: external} that you can use to determine whether there is something in your service that a user could configure to affect whether the control is met in their account. 

Please note: A control is not applicable to your service if your internal service operations team has to meet the control but users don't meet this control by configuring your service. For example, if the IAM Access Groups team is assessing wehther the control "All data must be encrypted at rest" applies to their services, they would note that there is nothing that a user could configure in the Access Groups services that would validate the control. This is true even though the Access Groups service stores data in a Cloudant database that their operations team is responsible for ensuring is encrypted. Because, in order to check whether that control is met, a Cloudant API would be called, not an Access Groups API. 

For each control that is applicable to your service, you must provide the APIs that are called to determine whether your service's resources in a customer account are compliant to the control. Along with the APIs, please explain any non-trivial logic that would be needed to check the API results to see if the control is met.


## Step 2: Define your goals
{: #internal-define-goals}


Using a copy of the spreadsheet that is linked in the previous section, provide the needed information - including APIs and postman collections. When it's ready, create a box folder that you name to match your service and upload your filled out spreadsheet and postman collections. Note: Before you can upload documents, you might need to click **Join Folder**.

**Goal writing tips**

* Start goals with "Check whether...", "Ensure...", "Continuously...", "Indicates...", or "Specifies".
* Do not use abbreviations that are not legally approved. For example: COS, BSS, and IKS.
* Take advantage of your service's content team and have them review your goals for any typo's or potential IBM style conflicts.


## Next steps
{: #internal-monitor-next}

With your goals written, there are two next steps.

* After your information is uploaded, post in the #fortress-adopters channel that you're ready for review. The adopters team will reach out with any questions. 
* At the same time, share your spreadsheet with your content team so that they can prepare the end-user documentation.
