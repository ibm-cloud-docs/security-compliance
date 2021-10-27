---

copyright:
  years: 2021
lastupdated: "2021-10-13"

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

# Why did my compliance score change without any updates to my resources?
{: #score-change}
{: troubleshoot} 

Your compliance score changed but you did not make any changes to your resources.
{: shortdesc}

You notice that your compliance score has changed, but you haven't made any changes to your resource configurations or your posture management configurations.
{: tsSymptoms} 

Base profiles are continuously updated by the {{site.data.keyword.compliance_short}} service team. If you are using a base profile to scan your resources, the goals that are added are automatically included in the next scans that are run. 
{: tsCauses}

If you don't want new goals automatically included in your scans, you can build or create a profile that includes only the controls and goals that you want to scan for. [Learn more](/docs/security-compliance?topic=security-compliance-profiles). 
{: tsResolve}
