---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-10"

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
{:release-note: data-hd-content-type='release-note'}

# Connecting NeuVector
{: #setup-neuvector}

With [NeuVector](https://neuvector.com/){: external}, you can detect network threats and violations to prevent attacks of your container-based applications. Through monitoring, you can prevent exploits and breakouts by detecting root privilege escalations, port scans, reverse shells, and suspicious file system activity in your containers and hosts.
{: shortdesc}

When you configure the business partner connection, a card is created in your dashboard that summarizes the findings that are flagged by NeuVector. The NeuVector security report introduces one key performance indicator (KPIs) and a chart that represents findings data as it is updated daily. The chart contains the:

* *Security events*: Daily details of findings that are related to network threats and violations in your containers and hosts.
* *Security events count*: The total amount of findings that are related to network threats and violations in your containers and hosts.



## Before you begin
{: #NeuVector-before}

Before you start integrating business partners, be sure that you have the following prerequisites:

* An account with the business partner that you want to integrate.
* The required permissions to obtain the registration URL from the business partner.
* The IAM role `administrator` for the Security and Compliance Integrations and {{site.data.keyword.compliance_short}} services.



## Registering NeuVector
{: #registering-neuvector}

You can use the {{site.data.keyword.compliance_short}} UI to create a connection to NeuVector. When the connection is created, you establish trust and associate your accounts, which shares the required information such as credentials and URLs.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. Navigate to **Integrations**.
3. On the **NeuVector** tile, click **Connect**.
4. Provide a name for your connection.
5. Input the registration URL provided by NeuVector. This is the URL of your NeuVector dashboard. If you don't know the URL, click **Get URL from NeuVector** to go to your NeuVector account. If you need help obtaining the URL, see [Getting a setup URL](https://docs.neuvector.com/integration/ibmsa){: external} in the NeuVector documentation.
6. Click **Next**.
7. Click **Connect**.


## Verifying the connection
{: #neuvector-verify}

1. In the Security Insights overview, check whether the NeuVector card displays as expected.
2. Log in to NeuVector and [verify the connection](https://docs.neuvector.com/integration/ibmsa){: external}.

