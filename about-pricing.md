---

copyright:
  years: 2020, 2022
lastupdated: "2022-08-09"

keywords: best practices security and compliance, secure development, security strategy, governance

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

# How does {{site.data.keyword.compliance_short}} calculate pricing?
{: #scc-pricing}

{{site.data.keyword.compliance_short}} consists of two parts - Posture Management and Configuration Governance. When you work with the service, you are charged for each evaluation of your compliance posture.


For the most up-to-date pricing information, you can create a cost estimate by clicking **Add to estimate** from either the [provisioning](/security-compliance/catalog) or [plan page](/security-compliance/plan).
{: important}


## Plan types
{: #plan-types}

The service offers two pricing plans.

Trial
:   To try out the service, you can enroll in a Trial period that allows you to access the full capabilities of the Posture Management component for a 30-day period at no charge. You can create profiles, set up credentials, and configure your account to evaluate your resources, among other things. The data that is generated is maintained for 180 days before it is automatically deleted by IBM. 


Standard
:   With a Standard plan, you are able to access the full capabilities of the service without the 30-day limitation, but you are charged per evaluation.


## What is an evaluation?
{: #evaluation-definition}

An evaluation is the check of one goal against one resource. When an evaluation passes - the resource is considered to be compliant with the goal at the time of the scan. If the scan fails, then the resource is non-compliant and you should begin remediation.

## When am I charged?
{: #evaluation-charge}

You are charged if the evaluation produces a result of pass or fail. You are not charged for the evaluation if the result is unable to perform or not applicable. You are also not charged for the evaluation of built-in goals that are met by default.


## How do I stop getting charged for {{site.data.keyword.compliance_short}}?
{: #pricing-stop}

You are charged when an evaluation takes place. If you no longer want to be charged for a specific evaluation, stop the scan or scans that you do not want to be charged for from running. 

