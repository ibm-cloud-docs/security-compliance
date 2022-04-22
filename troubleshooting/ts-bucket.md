---

copyright:
  years: 2020, 2022
lastupdated: "2022-04-22"

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

# Why can't I connect a bucket to store my insights?
{: #insights-connect}
{: troubleshoot} 

You try to create a new connection with Cloud Object Storage in the {{site.data.keyword.compliance_short}} UI and the button is unable to be clicked.
{: tsSymptoms} 

There are a few reasons that this might happen:
{: tsCauses}

* Your location that is configured on the Data settings page does not match the current location selected on the Activity or Network Insights tables.
* Activity Insights can have only one connection at a time.

To resolve the issue:
{: tsResolve}

* Verify that your locations match.
* Delete your current Activity Insights bucket to connect a new one. 

