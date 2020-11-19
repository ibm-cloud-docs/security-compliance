---

copyright:
  years: 2020
lastupdated: "2020-11-11"

keywords: known limitations, rules, limits, configuration, ibm remediation, ssh key

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


# Known issues and limits
{: #known-issues-limits}

{{site.data.keyword.compliance_full}} includes the following known issues and limits that might impact your experience.
{: shortdesc}


## Known issues
{: #known-issues}

Review the following known issues that you might encounter while working with the service.

| Issue  | Workaround |
|:-------|:-----------|
| Remediation is unavailable for {{site.data.keyword.cloud_notm}}. | If you're working with Amazon Web Services (AWS) or Azure, you can [remediate issues](/docs/security-compliance?topic=security-compliance-remediation) directly from the service UI. If you're working in {{site.data.keyword.cloud_notm}}, you must manually remediate your issues. |
| Results for {{site.data.keyword.cloud_notm}} classic infrastructure are not returned. | It is not possible to scan Gen 1 classic infrastructure as a cloud-based resource. To monitor security and compliance for Gen 1 classic infrastructure, configure an on-prem collector. |
{: caption="Table 1. Known issues and workarounds" caption-side="top"}


## Limits
{: #limits}

When you're working with {{site.data.keyword.compliance_short}}, there are a few limits on profiles and rules that you need to be aware of.

### Rule limits
{: #rule-limits}

Review the following table to see the limits that apply to rules. 

| Rule element   | Limit |
|----------------|-----------|
| Total | 500 rules per enterprise account</br>100 rules per stand alone account |
| Length | 4096 characters |
| Results | Kept for 7 days |
| Name | 32 characters |
| Description | 256 characters |
| Target | 1 per rule |
| Conditions | 16 per rule |
| Properties | 24 per condition |
| Enforcement actions | 2 per rule |
| Labels | 32 per rule </br> **Note**: Commas (,) and slashes (/) cannot be used in labels. |
| Attachments | 10 per rule |
| Excluded scopes | 8 per attachment |
{: caption="Table 2. Rule limits" caption-side="top"}



