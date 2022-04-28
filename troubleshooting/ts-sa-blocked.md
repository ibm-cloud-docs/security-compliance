---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-10"

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

# Why am I blocked from accessing the API?
{: #sa-blocked}
{: troubleshoot}

You are blocked from accessing the API endpoint: `secadvisor.cloud.ibm.com`.
{: shortdesc}

When you create a new card by specifying it as a note type, you encounter the following error.
{: tsSymptoms}

```txt
You have been blocked. You are unable to access secadvisor.cloud.ibm.com.
```
{: screen}

This error can occur when the value that is provided for `badge_image` is the wrong type.
{: tsCauses}

To resolve the issue, provide an optimized and compressed SVG value for `badge_image`.
{: tsResolve}

