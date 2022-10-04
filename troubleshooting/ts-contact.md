---

copyright:
  years: 2020, 2022
lastupdated: "2022-10-04"

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

You encounter an issue that you cannot fix and you want to contact the support team.
{: shortdesc}

If you encounter an issue that you cannot fix while you work with the {{site.data.keyword.compliance_short}} dashboard, contact the [IBM Cloud support team](https://www.ibm.com/cloud/support){: external}.

If you're opening a support ticket for the security and compliance posture monitoring portion of the service, be sure that you include your cluster logs. To obtain your cluster logs, you can use the following steps:

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

