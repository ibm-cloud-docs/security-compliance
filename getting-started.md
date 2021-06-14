---

copyright:
  years: 2021
lastupdated: "2021-06-14"

keywords: getting started with the security and compliance center, get started, security, compliance

subcollection: security-compliance

content-type: tutorial
services: security-compliance, vpc
completion-time: 20m

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


# Getting started with {{site.data.keyword.compliance_short}}
{: #getting-started}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, vpc"}
{: toc-completion-time="15m"}

With {{site.data.keyword.compliance_full}}, you can embed security checks into your every day workflows to help monitor for security and compliance. By monitoring for risks, you can identify security vulnerabilities and quickly work to mitigate the impact and fix the issue.
{: shortdesc}



## Objective
{: #objective}

This tutorial focuses on the steps that are required to start scanning your cloud-based resources with the {{site.data.keyword.compliance_short}} in {{site.data.keyword.cloud_notm}}. 

If you don't need to monitor your {{site.data.keyword.cloud_notm}} resources for external regulations, try configuring resource monitoring for another environment, defining a config rule to govern the way that your resources can be used, or enabling built-in insights to help detect incoming threats.

[![This image is a visual link to the instructions for installing a collector on another cloud provider.](images/gs-environment.svg)](/docs/security-compliance?topic=security-compliance-collector)     [![This image is a visual link to the conceptual information about defining config rules.](images/gs-rules.svg)](/docs/security-compliance?topic=security-compliance-rules)     [![This image is a visual link to the conceptual information about built-in insights.](images/gs-insights.svg)](/docs/security-advisor?topic=security-advisor-integrations#integrate-insights)



## Before you begin
{: #before-start}

To complete the getting started tutorial, use a [Pay-As-You-Go or Subscription](/docs/account?topic=account-accounts) {{site.data.keyword.cloud_notm}} account where you are the owner or have [full Administrator access](/docs/account?topic=account-assign-access-resources).

Be sure that you also have the following requirements:

- A [service ID API key](/docs/account?topic=account-serviceidapikeys) with **Read** access permissions for the resources that you want to scan.


## Create credentials
{: #gs-credentials}
{: step}


To gather information about your resources, you must create a [collector](#gs-collector). Credentials are used to allow the collector to gather information about your resources, assess your configurations, and initiate any required remediation.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Settings > Credentials**.
3. Click the **New Credential** icon.
4. Give your credential a meaningful name and description.
5. Select **{{site.data.keyword.cloud_notm}}**.
6. Select **Discovery/Collection**.
7. Paste your API key into the **IBM API key** field. For help with creating an API key, see [Understanding API keys](/docs/account?topic=account-manapikey).

  Your API key must have reader access permissions to the resources that you want to scan.
  {: note}

8. Verify your updates and click **Save**. The credential is added to a list of available credentials. 


## Install a collector
{: #gs-collector}
{: step}

A collector is a software module that is packaged as a Docker image. It is installed "within sight" of your environment where it can have network access to your IT resources. After you create your credentials, you can create and install a managed collector that you can use to complete the tutorial. To learn more about collectors and how the communication takes place, see [What is a collector?](/docs/security-compliance?topic=security-compliance-collector).

IBM managed collectors are created on IBM owned infrastructure and are maintained by the {{site.data.keyword.compliance_short}}. If your organization doesn't allow managed collectors, you can always create and install your own. For more information, see [Manually administering collectors](/docs/security-compliance?topic=security-compliance-collector-manual).
{: note}

1. On the **Configure > Settings > Collectors** page of the {{site.data.keyword.compliance_short}}, click **Create**.
2. Give your collector a name and description.

  It is helpful to ensure that the name is unique across your organization so that its intended purpose is clear to other members of your team.

3. If you have a passphrase enabled, the **Existing passphrase** field displays. Enter your passphrase. If you do not have a passphrase enabled, the field will not display.
4. Click **Next**.
5. In the **Managed by** field, select **IBM**.
6. By default, the **Private** endpoint type is selected.

  A collector requires constant communication with the service to validate your current posture. By default, a private endpoint is used for communication in all IBM managed collectors.

7. Click **Create**. When the collector is created successfully, the status updates to **Installing**.

When your collector is ready, the status updates to **Active**.


## Create a scope
{: #gs-scope}
{: step}

When you're working with the {{site.data.keyword.compliance_short}}, you can narrow the focus of your scans to a specific environment, region, or even resource. By creating scopes, you can determine your security and compliance score across a specific area of your business. 

1. On the **Scopes** page of the {{site.data.keyword.compliance_short}}, click the **New scope** icon.
2. Give your scope a meaningful name and description.
3. Select an environment.
4. Select the **Collector** that you want to use.
5. Select the **Credentials** that provide access to the resources that you want to scan.
6. Click **Next**.
7. Select the resource groups that you want to scan and click **Create**.



## Schedule a scan
{: #gs-scan}
{: step}

To discover resources, assess their configuration, and validate their compliance against a predefined profile, you can schedule a validation scan.

1. On the **Scans > Scheduled scans** page of the {{site.data.keyword.compliance_short}}, click **Schedule**. A side panel opens.
2. Give your scan a meaningful name and description.
3. Select **Validation**.
4. Select the scope that you created in the previous step.
5. Select one of the predefined profiles and click **Next**.
6. Select the frequency at which you want the scan to run.
7. Select when you want the scan to stop. Options include never, a specific number of scans, or on a set date.
8. Click **Create**.


## Next steps
{: #gs-next}

You did it! Now you can choose to map more credentials to your collector so that you can scan more resources or you can learn more about the way that security and compliance score is calculated to better understand your results. 

[![This image is a visual link to the instructions for mapping credentials.](images/gs-map-credentials.svg)](/docs/security-compliance?topic=security-compliance-credentials#map-credentials)     [![This image is a visual link to the conceptual information about compliance scores.](images/gs-learn-scores.svg)](/docs/security-compliance?topic=security-compliance-view-posture)


