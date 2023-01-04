---

copyright:
  years: 2020, 2023
lastupdated: "2023-01-04"

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

# What information do I need to provide to the support team?
{: #contact-support}
{: troubleshoot}

If you encounter an issue that you cannot fix while you work with {{site.data.keyword.compliance_short}}, contact the [{{site.data.keyword.cloud_notm}} support team](https://www.ibm.com/cloud/support){: external}.
{: shortdesc}

When you open a support ticket, be sure to provide the following information that is relevant to your case:

* The ID of the entity that you have a question about - Attachment, Profile, Specification, or Rule.
* The scope.
* A detailed description of the issue.
* Any other information that can help process your ticket quickly.

If you're opening a ticket for collector-based evaluations, then be sure to include your collector logs. To obtain your logs:

1. Log in to the collector.
2. Run the following command to package your logs.

   ```sh
   docker ps
   docker exec -it <COLLECTOR_NAME> bash
   zip /opt/data/collector_log.zip /var/log/*.log
   ```
   {: codeblock}

3. Navigate to the installation path on your host machine to find the `collector_log.zip` file.

   ```sh
   ls /home/ubuntu/<COLLECTOR_FOLDER>/collector_log.zip
   ```
   {: codeblock}

