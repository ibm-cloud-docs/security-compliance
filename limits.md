---

copyright:
  years: 2020
lastupdated: "2020-10-01"

keywords: known limitations, rules, limits, configuration

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


# Known issues and limitations
{: #known-issues}

{{site.data.keyword.compliance_full}} includes the following known issues and limits that might impact your experience.
{: shortdesc}



## Limits
{: #limits}

When you're working with {{site.data.keyword.compliance_short}}, there are a few limits on profiles and rules that you need to be aware of.

### Rule limits
{: #rule-limits}

Review the following table to see the limits that apply to rules. 

| Rule element   | Limit |
|----------------|-----------|
| Length | 4096 characters including all elements |
| Total number | 500 per enterprise account</br>100 per stand alone account |
| Results | Kept for 7 days |
| Name | 32 characters |
| Description | 256 characters |
| Target | 1 per rule |
| Conditions | 16 per rule |
| Properties | 24 per condition |
| Enforcement actions | 2 per rule |
| Labels | 32 per rule |
| Attachments | 10 per rule |
| Excluded scopes | 8 per attachment |
{: caption="Table 1. Rule limits" caption-side="top"}



