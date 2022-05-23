---

copyright:
  years: 2020, 2022
lastupdated: "2022-05-23"

keywords: public isolation for {{site.data.keyword.compliance_short}}, compute isolation for {{site.data.keyword.compliance_short}}, {{site.data.keyword.compliance_short}} architecture, workload isolation in {{site.data.keyword.compliance_short}} 

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


# Learning about {{site.data.keyword.compliance_short}} architecture and workload isolation
{: #compute-isolation}

Review the following sample architecture for {{site.data.keyword.compliance_full}}, and learn more about different isolation levels so that you can choose the solution that best meets the requirements of the workloads that you want to run in the cloud.
{: shortdesc}

## {{site.data.keyword.compliance_short}} architecture
{: #architecture}

{{site.data.keyword.compliance_short}} is a multi-tenant, regional service that is fully integrated with the {{site.data.keyword.cloud_notm}} platform. The IBM-managed components of the {{site.data.keyword.compliance_short}} are organized to provide compute isolation between workloads. 



## {{site.data.keyword.compliance_short}} workload isolation
{: #workload-isolation}

Each regional deployment of the {{site.data.keyword.compliance_short}} serves multiple tenants and can be accessed through public endpoints. By default, all data at rest is encrypted by IBM keys, but you can [bring your own keys](/docs/security-compliance?topic=security-compliance-mng-data). Data in transit is encrypted by using TLS. Your data is isolated from other customer's data but does share the same physical resources such as CPU, memory, and I/O devices. 

