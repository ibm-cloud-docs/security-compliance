---

copyright:
  years: 2020, 2021
lastupdated: "2021-11-23"

keywords: getting started with the security and compliance center, get started, security, compliance

subcollection: security-compliance

content-type: tutorial
completion-time: 10m

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


# Monitor resources with an IBM-managed collector
{: #monitor-ibm-collector}
{: toc-content-type="tutorial"}
{: toc-completion-time="10m"}

With {{site.data.keyword.compliance_full}}, you can embed security checks into your every day workflows to help monitor for security and compliance. By monitoring for risks, you can identify security vulnerabilities and quickly work to mitigate the impact. This tutorial focuses on the steps that are required to start scanning your cloud-based resources with the {{site.data.keyword.compliance_short}} in {{site.data.keyword.cloud_notm}} by using an IBM-managed collector. 
{: shortdesc}


## Before you begin
{: #monitor-ibm-before}

To complete the getting started tutorial, use a [Pay-As-You-Go or Subscription](/docs/account?topic=account-accounts) {{site.data.keyword.cloud_notm}} account where you are the owner or have [full Administrator access](/docs/account?topic=account-assign-access-resources).

Be sure that you also have the following requirements:

- A [service ID API key](/docs/account?topic=account-serviceidapikeys) with **Read** access permissions for the resources that you want to scan.



## Create a collector
{: #create-ibm-collector}
{: step}

A collector is a software module that is packaged as a container image that scans your resources and validates their configurations. To learn more about collectors and how the communication takes place, see [What is a collector?](/docs/security-compliance?topic=security-compliance-collector).

IBM-managed collectors are created on IBM-owned infrastructure and are maintained by the {{site.data.keyword.compliance_short}}. If your organization doesn't allow managed collectors, you can always create and install your own. For more information, see [Manually administering collectors](/docs/security-compliance?topic=security-compliance-collector-manual).
{: note}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. On the **Configure > Collectors** page of the {{site.data.keyword.compliance_short}}, click **Create**.
3. Give your collector a name and description.

   It is helpful to ensure that the name is unique across your organization so that its intended purpose is clear to other members of your team.

4. If you have a passphrase enabled, the **Existing passphrase** field displays. Enter your passphrase. If you do not have a passphrase enabled, the field will not display.
5. Click **Next**.
6. In the **Managed by** field, select **IBM**. 

8. By default, the **Private** endpoint type is selected.

   A collector requires constant communication with the service to validate your current posture. By default, a private endpoint is used for communication in all IBM managed collectors.

9. Click **Create**. When the collector is created successfully, the status updates to **Installing**.

When your collector is ready, the status updates to **Active**.

## Add credentials
{: #monitor-ibm-credentials}
{: step}

The credentials that you add to the service must allow the collector to read your resource configurations.

1. In the navigation, click **Configure > Credentials**.
2. Click **Create**.
3. Give your credential a meaningful name and description.
4. Select **Discovery/Collection**.
5. Click **Next**.
6. Select **{{site.data.keyword.cloud_notm}}**.
7. Paste your API key into the **IBM API key** field. For help with creating an API key, see [Understanding API keys](/docs/account?topic=account-manapikey).

  Your API key must have reader access permissions to the resources that you want to scan.
  {: note}

8. Verify your updates and click **Create**. The credential is added to a list of available credentials. 


## Create a scope
{: #monitor-ibm-scope}
{: step}

When you're working with the {{site.data.keyword.compliance_short}}, you can narrow the focus of your scans to a specific environment, region, or even resource. By creating scopes, you can determine your security and compliance score across a specific area of your business. 

1. On the **Configure > Scopes** page of the {{site.data.keyword.compliance_short}}, click **Create**.
2. Give your scope a meaningful name and description.
3. Click **Next**. 
4. Select an environment.
5. Select the **Credentials** that provide access to the resources that you want to scan.
6. Click **Next**.
7. Select the **Collector** that you want to use.
8. Click **Next**.
9. Review the details of your scope and click **Create**.



## Schedule a scan
{: #monitor-ibm-scan}
{: step}

To discover resources, assess their configuration, and validate their compliance against a predefined profile, you can schedule a validation scan.

1. On the **Assess > Scans > Scheduled scans** page of the {{site.data.keyword.compliance_short}}, click **Schedule**. A side panel opens.
2. Give your scan a meaningful name and description.
3. Select **Validation**.
4. Select the scope that you created in the previous step.
5. Select one of the predefined profiles and click **Next**.
6. Select the remediation preference. Options include automatic, approved, and none.
7. Select the frequency at which you want the scan to run.
8. Select when you want the scan to stop. Options include never, a specific number of scans, or on a set date.
9. Click **Create**.


## Next steps
{: #monitor-ibm-next}

You did it! Now you can choose to map more credentials to your collector so that you can scan more resources or you can learn more about the way that security and compliance score is calculated to better understand your results. 

[![This image is a visual link to the instructions for mapping credentials.](../images/gs-map-credentials.svg)](/docs/security-compliance?topic=security-compliance-map-credentials)     [![This image is a visual link to the conceptual information about compliance scores.](../images/gs-score.svg)](/docs/security-compliance?topic=security-compliance-view-posture)


