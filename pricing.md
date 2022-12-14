---

copyright:
  years: 2020, 2022
lastupdated: "2022-12-14"

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

Pricing for {{site.data.keyword.compliance_full}} is based on the number of evaluations performed. An evaluation is the check of one assessment against one resource.


For the most up-to-date pricing information, you can create a cost estimate by clicking **Add to estimate** from either the [provisioning](/security-compliance/catalog) or [plan page](/security-compliance/plan).
{: important}


## Plan types
{: #plan-types}

The service offers two pricing plans.

Trial
:   To try out the service, you can enroll in a Trial period where you have access the full capabilities of the Posture Management component for 30 days at no charge. You can create profiles, set up credentials, and configure your account to evaluate your resources, among other things. The data that is generated is maintained for 180 days before it is automatically deleted. 

Standard
:   With a Standard plan, you are able to access the full capabilities of the service without limitations. However, you are charged per evaluation.


## When am I charged?
{: #evaluation-charge}

You are charged if an evaluation produces a result of pass or fail. You are not charged for the evaluation if the check cannot be performed or is not applicable. Each scan that is run provides you with the number of billable evaluations in the results UI.

## How do I stop getting charged for {{site.data.keyword.compliance_short}}?
{: #pricing-stop}

You are charged when an evaluation takes place. If you no longer want to be charged for a specific evaluation, stop the scan or scans that you do not want to be charged for from running by deleting your attachment. This does not remove your historical results, but it does stop future scans from being run.

