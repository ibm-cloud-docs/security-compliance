---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-10"

keywords: mapping tags, compliance, security, tiered architecture

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


# Mapping tags
{: #tags}

Tags are platform level labels used by the Security and Compliance Center to guide which Goals are applied to which resources. In some standards, for example, CIS AWS 3-tier Web Architecture Benchmark, different Goals are applicable to different tiers. The Benchmark uses the keyword Web, App and DB. But within your company you may use different naming conventions. By creating the mapping, you can ensure that the service is aware of the terms that you use for the Web, App, Database, and Data architecture tiers.
{: shortdesc}


1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Settings > Tags**.
3. Click the **New tag** icon.
4. Add the tag that you use in the **Name** field.
5. Optional: Give your tag a description.
6. Select the tag that aligns with your architecture tier.

   | Tier mapping | Definition | Commonly used terms |
   | --------- | ----------- | --------|
   | Web tier | The web tier of your deployment architecture is generally written in HTML, CSS, or JavaScript and is presented to a user through a web browser or application. | Front end, web, browser, client, or presentation. |
   | App tier | The app tier of your deployment architecture is written in a programming language, such as Java or Go, and contains the business logic that supports your application's core function. | Logic, core, application, backend, or APIs. |
   | DB tier | The database tier of your deployment architecture consists of a database and the system that is used to manage it, such as MySQL or MongoDB. | Server, storage, or database. |
   | Data tier | The data tier of your deployment architecture consists of application storage that might not be specific to a database or communication port. | Storage or log files. |
   {: caption="Table 1. Understanding tag mapping" caption-side="top"}

7. Click **Save**.


