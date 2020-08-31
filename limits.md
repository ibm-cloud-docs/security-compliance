---

copyright:
  years: 2020
lastupdated: "2020-08-31"

keywords: known limitations, rules, limits, configuration

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

| Limit | Description |
|---------|-------|
| Rule length | 4096 characters including all elements |
| Total rules | 500 per enterprise account |
| Rule results | Kept for 7 days.|
{: caption="Table 1. Rule limits" caption-side="top"}

Review the following table to see the limits that apply to each element within a rule.

| Element | Limit |
|---------|-------|
| Name | 32 characters |
| Description | 256 characters |
| Target | 1 per rule |
| Conditions | 16 per rule |
| Properties | 24 per condition |
| Enforcement actions | 2 per rule |
| Labels | 32 per rule |
| Attachments | 10 per rule |
| Excluded scopes | 8 per attachment |
{: caption="Table 2. Rule element limits" caption-side="top"}



