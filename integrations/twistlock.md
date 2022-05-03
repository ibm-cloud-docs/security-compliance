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

# Connecting Twistlock
{: #setup-twistlock}

You can prevent risk by stopping the deployment of vulnerable images in your environment. With automated and custom policy enforcement, [Twistlock](https://www.paloaltonetworks.com){: external} offers complete control at every stage of the application lifecycle.
{: shortdesc}

When you connect Twistlock, two insights cards are created in the {{site.data.keyword.compliance_short}} that summarize the findings that are identified.


| Card                      | Description of findings   |
|:--------------------------|:--------------------------|
| Twistlock runtime         | Total incidents and audits: Findings that are related to incidents or audits on your cloud-native workloads.  \n Total firewall audits: Findings that are related to issues with your firewall. |
| Twistlock vulnerabilities | Total images with new vulnerabilities: Findings that are related to vulnerabilities found in your container images. |
{: caption="Table 1. Summary of cards that are generated when you connect your Twistlock account" caption-side="top"}


## Before you begin
{: #twistlock-before}

Before you start integrating business partners, be sure that you have the following prerequisites:

* An account with the business partner that you want to integrate.
* The required permissions to obtain the registration URL from the business partner.
* The IAM role `administrator` for the Security and Compliance Integrations and {{site.data.keyword.compliance_short}} services.


## Registering Twistlock
{: #registering-twistlock}

You can use the {{site.data.keyword.compliance_short}} UI to create a connection to Twistlock. When the connection is created, you establish trust and associate your accounts, which shares the required information such as credentials and URLs.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. Navigate to **Gain insight > Configure > Business partners**.
3. On the **Twistlock** tile, click **Connect**.
4. Provide a name for your connection.
5. Input the registration URL provided by Twistlock. If you don't know the URL, click **Get URL from Twistlock** to go to your Twistlock account and use the following steps to retrieve the URL.
   1. In the Twistlock dashboard, navigate to **Manage > Alerts > Add profile**.
   2. Select {{site.data.keyword.compliance_short}} from the **Provider** drop down.
   3. Copy the available URL.
6. Click **Connect**.


## Verifying the connection
{: #twistlock-verify}

1. In the Insights overview, check to see whether the Twistlock cards are displaying as expected.
2. In the Twistlock dashboard, refresh the **Alerts** tab. The {{site.data.keyword.compliance_short}} connection shows. Open the connection.
3. Verify that the alert types that you want to be notified of are checked and then click **Verify**.
