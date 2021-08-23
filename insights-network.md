---

copyright:
  years: 2017, 2021
lastupdated: "2021-08-23"

keywords: Centralized security, security management, alerts, security risk, insights, threat detection

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

# Enabling Network Insights
{: #setup-network}

With Security Insights, formerly known as {{site.data.keyword.security-advisor_long}}, you can continuously analyze your Virtual Private Cloud (VPC) network interface flow logs to detect any suspicious activity by using learned patterns and threat intelligence.
{: shortdesc}



## Before you begin
{: #before-network}


Before you get started, be sure that you have the required level of access to view and manage Activity Insights. To manage Activity Insights, you must have the Writer service role or higher for {{site.data.keyword.security-advisor_short}} and Virtual Private Cloud. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management). You must also have [an instance of VPC](https://{DomainName}/vpc-ext/provision/vpc).


## Connecting to Cloud Object Storage
{: #network-store-data}

Before you can analyze your network communication, {{site.data.keyword.security-advisor_short}} must have access to your network flow logs that are stored in Cloud Object Storage. To create the connection between the services, you must store the logs in a Cloud Object Storage bucket and then grant the service access to the bucket. 

1. In the {{site.data.keyword.cloud_notm}} console, navigate to **Security and compliance > Gain insight > Configure > Built-in Insights**.
2. Click **Connect**.
3. Select a resource group, an instance of Cloud Object Storage, and a bucket.
4. Optionally, provide a description.
5. Click **Connect bucket**.
6. Create a *reader* [service-to-service authorization policy](https://{DomainName}/iam/authorizations) between Cloud Object Storage and {{site.data.keyword.security-advisor_short}}.



## Collecting your flow logs
{: #collecting your flow logs}

Before it can be analyzed, you must collect your data. To do so, you can create a flow log that collects your network interface logs and funnels them into a Cloud Object Storage bucket.

You must have a service-to-service authorization policy between VPC and the same Cloud Object Storage bucket that you connected to {{site.data.keyword.security-advisor_short}} in order to ensure that the data can be analyzed.
{: note}

1. In the {{site.data.keyword.cloud_notm}} console, navigate to **VPC Infrastructure > Flow logs**.
2. Click **Create**.
3. Give your flow logs a name.
4. Select a resource group.
5. Optionally, add tags.
6. Select **Interface** for **Attach flow log connector to**.
7. Select your VPC, virtual server instance, and network interface.
8. Select the instance of Cloud Object Storage and the bucket that you connected to {{site.data.keyword.security-advisor_short}}.
9. Click **Create flow log**.



## Enabling analysis
{: #enable-analysis-network}

Now that you've connected your Cloud Object Storage bucket and verified that your flow logs are being stored correctly, you can enable Network Insights to start analyzing them.


1. In the {{site.data.keyword.cloud_notm}} console, navigate to **Security Compliance > Gain insight > Configure > Built-in insights**.
2. Toggle Network Insights to **On**.

As results come in, you can see any flagged issues on the **Insights** or **Findings** pages of the UI.


Now that you've configured Network Insights to analyze your flow logs, set up alerts so that you can be notified if an issue is found. [Learn more](/docs/security-compliance?topic=security-compliance-notifications).
{: tip}

