---

copyright:
  years: 2020
lastupdated: "2020-08-31"

keywords: mapping tags, compliance, security, tiered architecture, 

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


# Mapping tags
{: #tags}

Tags are platform level labels used by the Security and Compliance Center to guide which Goals are applied to which resources. In some standards, for example, CIS AWS 3-tier Web Architecture Benchmark, different Goals are applicable to different tiers. The Benchmark uses the keyword Web, App and DB. But within your company you may use different naming conventions. By creating the mapping, you can ensure that the service is aware of the terms that you use for the Web, App, Database, and Data architecture tiers.
{: shortdesc}


1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Settings > Tags**.
3. Click the **New tag** icon.
4. Add the tag that you use in the **Name** field.
5. Optional: Give your tag a description.
6. Select the tag that aligns with your architecture tier.

  <table>
    <caption>Table 1. Understanding tag mapping</caption>
    <tr>
      <th>Tier mapping</th>
      <th>Definition</th>
      <th>Commonly used terms</th>
    </tr>
    <tr>
      <td>Web tier</td>
      <td>The web tier of your deployment architecture is generally written in HTML, CSS, or JavaScript and is presented to a user through a web browser or application.</td>
      <td>Front end, web, browser, client, or presentation.</td>
    </tr>
    <tr>
      <td>App tier</td>
      <td>The app tier of your deployment architecture is written in a programming language, such as Java or Go, and contains the business logic that supports your application's core function.</td>
      <td>Logic, core, application, backend, or APIs.</td>
    </tr>
    <tr>
      <td>DB tier</td>
      <td>The database tier of your deployment architecture consists of a database and the system that is used to manage it, such as MySQL or MongoDB.</td>
      <td>Server, storage, or database.</td>
    </tr>
    <tr>
      <td>Data tier</td>
      <td>The data tier of your deployment architecture consists of application storage that might not be specific to a database or communication port.</td>
      <td>Storage or log files.</td>
    </tr>
  </table>
7. Click **Save**.


