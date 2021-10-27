---

copyright:
  years: 2017, 2021
lastupdated: "2021-10-13"

keywords: Centralized security, security management, alerts, security risk, insights, threat detection, vpc, flow logs, flow log alerts, findings, network insights

subcollection: security-compliance

content-type: tutorial
services: security-compliance, vpc, cloud-object-storage
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

# Generate alerts for potential issues found in your VPC Flow Logs
{: #ni-vpc-alerts}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, vpc, cloud-object-storage"}
{: toc-completion-time="10m"}

With Security Insights, formerly known as {{site.data.keyword.compliance_full}}, you can continuously analyze your Virtual Private Cloud (VPC) network interface Flow Logs to detect any suspicious activity by using learned patterns and threat intelligence. By walking through this tutorial, you can learn about each of the steps that you must take to set up alerts for potential issues that are found in your Flow Logs.
{: shortdesc}

![The Network Insights Alert flow. The graphics in this image are explained fully in the surrounding text.](../images/ni-alert-flow.svg){: caption="Figure 1. Network Insights alerts flow" caption-side="bottom"}

1. A user configures a Flow Logs collector for their VPC.
2. The collector interfaces with Cloud Object Storage and writes the logs to a bucket.
3. The Security Insights component of the {{site.data.keyword.compliance_short}} analyzes the logs that are stored in the bucket.
4. When a finding is flagged, an alert is triggered.


## Before you begin
{: #ni-before}

To complete this tutorial, be sure that you have the following prerequisites and permissions.

* A Virtual Private Cloud that is able to send network information.
* A Cloud Object Storage bucket that you are able to store your logs in.
* An *Editor* IAM permissions policy for VPC.
* A *Manager* IAM permissions policy for {{site.data.keyword.security-advisor_short}}
* Service-to-service authorization policies for the bucket that stores your logs. {{site.data.keyword.security-advisor_short}} must be able to *read* the information that is in the Cloud Object Storage bucket. VPC must be able to *write* your Flow Logs to the Cloud Object Storage bucket.


## Collect your Flow Logs
{: #collect-logs}
{: step}

To start analyzing your Flow Logs, you must first collect them.

1. In the {{site.data.keyword.cloud_notm}} console, navigate to **VPC Infrastructure > Flow logs**.
2. Click **Create**.
3. Give your flow logs a name.
4. Select a resource group.
5. Optionally, add tags.
6. Select **Interface** for **Attach flow log connector to**.
7. Select your VPC, virtual server instance, and network interface.
8. Select an instance of Cloud Object Storage and a bucket.
9. Click **Create flow log**.


## Enable analysis with Security Insights
{: #enable-analysis}
{: step}

Now that you've started collecting your Flow Logs to Cloud Object Storage, you can enable Network Insights to start analyzing them.

1. In the {{site.data.keyword.cloud_notm}} console, navigate to **Security and compliance > Integrations > Built-in insights**.
2. Toggle Network Insights to **On**.
3. Click **Connect**.
4. Select a resource group, an instance of Cloud Object Storage, and a bucket.
5. Optionally, provide a description.
6. Click **Connect**.


## Configure alerts
{: #ni-alerts}
{: step}

To start receiving alerts for potential issues related to your VPC FLow Logs, you can configure an alert channel by using the GUI. If you prefer to work with the API, see [Configuring alerts](/docs/security-compliance?topic=security-compliance-notifications).

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Alerts**.
3. Click **Create**.
4. Provide a name and meaningful description for your channel.
5. To configure the threshold for alerts, select the severity of the notifications that you want to be alerted for. Severity choices include *critical*, *high*, *medium*, and *low*. For more information about the types of findings that are returned for each severity, see [Available Network Insights finding types](/docs/security-compliance?topic=security-compliance-network-insights-finding-types).
6. Select Network Insights as your source.
7. Click **Next**.
8. Enter the callback endpoint where you want to receive the alerts.
9. Click **Create**. You channel is listed in the **Alerts** table. 


To verify that your channel is configured correctly by selecting **Test connection** in the overflow menu. A test alert is sent to your endpoint. Be sure to remove any alerts that are sent by *{{site.data.keyword.compliance_short}} Notification Test* after you've completed your testing.

