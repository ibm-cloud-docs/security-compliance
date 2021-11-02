---

copyright:
  years: 2021
lastupdated: "2021-11-02"

keywords: support, help, stack overflow, slack, no results, scan error

subcollection: security-compliance

content-type: troubleshoot

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

# Why aren't my OpenShift clusters being scanned?
{: #ts-osco-results}
{: troubleshoot} 

You created a connection between the OpenShift Compliance Operator and the {{site.data.keyword.compliance_short}}, but your clusters are not being scanned.
{: tsSymptoms} 

There are a few reasons that this might happen:
{: tsCauses}

* Your scope does not contain any OpenShift clusters.
* The integration might not be enabled in your scan settings.
* Discovery might not have completed.

To resolve the issue:
{: tsResolve}

* Verify that your scope contains OpenShift clusters.
* Verify that the integration is enabled in your scan settings.
* Run a discovery scan on your scope. When it's complete, run another validation scan.