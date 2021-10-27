---

copyright:
  years: 2020, 2021
lastupdated: "2021-10-15"

keywords: release notes for {{site.data.keyword.compliance_short}}, what's new, enhancements, fixes, improvements

subcollection: security-compliance
content-type: release-note

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

# Release notes for {{site.data.keyword.compliance_full}}
{: #release-notes}



## 15 September 2021
{: #security-compliance-sept2021}
{: release-note}

Next version (v0.1.2) of IBM Cloud for Financial Services profile
:   Released today, the next version (v0.1.2) of IBM Cloud for Financial Services profile is added with new goals and new controls. The goals and controls mapping are given below:
   * Goal ID: `3000039` mapped to the controls AC-2(i) and AC-2(1)
   * Goal ID: `3000040` mapped to the control AC-2(3)
   * Goal ID: `3000045` mapped to the control CM-6(a)
   * Goal ID: `3000438` mapped to the controls SC-13 and SC-28
   * Goal ID: `3000439` mapped to the controls SC-13 and SC-28
   * Goal ID: `3000440` mapped to the controls SC-13 and SC-28
   * Goal ID: `3000901` mapped to the controls CM-8(3)(a), RA-5(a), SI-2(2) and SI-7(1)
   * Goal ID: `3000902` mapped to the controls AC-4, CM-2, SC-7, SC-7(3) and SC-7(5)
   * Goal ID: `3000903` mapped to the controls AC-4 and SC-12
   * Goal ID: `3000906` mapped to the controls AC-17(2), SC-8, SC-8(1), SC-13 and SC-23
   * Goal ID: `3000907` mapped to the controls CM-2, CM-7(a), CM-8(1), CM-8(3)(a), SA-3(a) and SI-2(2)

## 02 September 2021
{: #security-compliance-sept0221}
{: release-note}

New goals
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. 1 new goal has been added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All of the goals with ID's in the following ranges are new.
   * Goal ID's: `3000526` - `3000533`


## 18 August 2021
{: #security-compliance-aug1821}
{: release-note}

New goals
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. 1 new goal has been added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All of the goals with ID's in the following ranges are new.
   * Goal ID's: `3000510` - `3000525` and `3000640`.

## 22 July 2021
{: #security-compliance-jul2221}
{: release-note}

New Posture Management API endpoints
:   With this release there are 9 new API endpoints available for the Posture Management API. To get started, see the [Posture Management API documentation](https://{DomainName}/apidocs/security-compliance/posture).

Consolidated SDK package
:   To make it easier to programmatically access the API from your code, {{site.data.keyword.compliance_short}} SDK packages are now available. The SDKs implement best practices for using the API and reduces the amount of code that you need to write. For more information, see the documentation for the following APIs:
   * [Admin](https://{DomainName}/apidocs/security-compliance/admin)
   * [Configuration Governance](https://{DomainName}/apidocs/security-compliance/config)
   * [Posture Management](https://{DomainName}/apidocs/security-compliance/posture)
   * [Findings](https://{DomainName}/apidocs/security-compliance/findings)
   * [Notifications](https://{DomainName}/apidocs/security-compliance/si-notifications)

Documentation update
:   With this release we've completed the integration of the Security Insights, formerly known as {{site.data.keyword.security-advisor_short}}, documentation into the {{site.data.keyword.compliance_short}} docs. You can now find the documentation for all three components in the {{site.data.keyword.compliance_short}} documentation.

New goals
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. 1 new goal has been added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All of the goals with ID's in the following ranges are new.
   * Goal ID's: `3000509`

## 22 June 2021
{: #security-compliance-jun2221}
{: release-note}

Tanium integration
:   Now, you can configure [Tanium Comply](https://docs.tanium.com/comply/comply/index.html){: external} to forward your compliance data. With Tanium Comply, you can evaluate your organizations endpoints for potential vulnerabilities and misconfigurations against industry security standards, vulnerability definitions, and custom compliance checks. When you integrate Tanium with the {{site.data.keyword.compliance_short}}, you can view all of your compliance data in one location in the same format. For more information, see [Connecting Tanium](/docs/security-compliance?topic=security-compliance-setup-tanium).


## 14 June 2021
{: #security-compliance-jun1421}
{: release-note}

IBM-managed collector
:   A collector is used to gather the configuration information about your resources and then validate it against a specified standard. Previously, you were responsible for the installation and lifecycle management of the collector. Now, you can get a proof of concept up and running quickly by configuring an IBM-managed collector. For more information, see [Configuring managed collectors](/docs/security-compliance?topic=security-compliance-ibm-collector) or [What is a collector?](/docs/security-compliance?topic=security-compliance-collector).

New goals
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. 7 new goals have been added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All of the goals with ID's in the following ranges are new.
   * Goal ID's: `3000901` - `3000907`

## 05 April 2021
{: #security-compliance-april0521}

Initial Posture Management API support
:   As part of this release, the Posture Management component of the service provides three external APIs that you can use as part of your security and compliance automation. For more information, see the [Posture Management API docs](/apidocs/security-compliance/posture).

Proxy support for discovery and fact collection
:   With this release, you can configure your collector to use a proxy to access the public endpoints to enhance the security of your scans. For more information, see [Which endpoints does a collector access?](/docs/security-compliance?topic=security-compliance-collector-manual#collector-proxy).

New goal mapping
:   The goal `3000045` is now mapped to CM-2 NIST 800 and has been added to an additional profile.

IBM Cloud for Financial Services profile
:   Released today, the IBM Cloud for Financial Services profile is a collection of curated goals that can help organizations make a large jump on the path to meeting the NIST 800-53 security controls that are required for financial institutions. By validating your resources against the IBM Cloud for Financial Services profile, you can be more confident that your IBM Cloud resources are following best practices for security and compliance.

   *Important*: The IBM Cloud for Financial Services profile will be constantly expanding and is not an exhaustive list of all of the controls that might be required for every organization. Users should validate the available goals and determine where there is a need to supplement their workloads with other security measures.

## 23 March 2021
{: #security-compliance-march0321}
{: release-note}

Manage the location in which your data is stored
:   Have specific regulations around where your data is stored and processed? With {{site.data.keyword.compliance_short}}, you can now choose the location in which the data that is generated by the service is managed. To set your location preferences, you can go to the **Menu icon** ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Data Settings**.

   For more information, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).

The full integration of the Security Insights UI
:   With this release we've completed the integration of the Security Insights, formerly known as {{site.data.keyword.security-advisor_short}}, UI into the {{site.data.keyword.compliance_short}}. You can now view your findings, enable Built-in Insights, set up alerts, and integrate with our existing business partners without ever leaving the {{site.data.keyword.compliance_short}} UI.

   To see the updates, check out the [{{site.data.keyword.compliance_short}} UI](https://cloud.ibm.com/security-compliance).

An update to the Security Insights notifications API
:   With this release we've dropped camel-case support for parameters. The parameters `publicKey` and `alertSource` have been updated to `public_key` and `alert_source`.

   To work with the updated notifications API, see the [API docs](/apidocs/security-advisor/notifications).

## 15 March 2021
{: #security-compliance-march1521}
{: release-note}

Customize default values for your resources
:   Looking for more options to help you govern {{site.data.keyword.cloud_notm}} resources? With {{site.data.keyword.compliance_short}}, you can now create templates that define your preferred property values for target resources in your selected {{site.data.keyword.cloud_notm}} accounts. After you create a template and attach it to a scope, your customized defaults override the default values that are provided by IBM.

   To get started with templates, you can go to the **Menu icon** ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Govern resources > Configure > Templates**, or check out the [API reference](/apidocs/security-compliance/config) to learn more about creating templates programmatically.

   For more information, see [What is Configuration Governance?](/docs/security-compliance?topic=security-compliance-what-is-governance)

## 17 February 2021
{: #security-compliance-feb1721}
{: release-note}

Manage your own encryption
:   If you're using {{site.data.keyword.compliance_short}} to monitor your current posture, you can now manage your encryption settings in the **Data settings** tab of the service UI.

   By default, the data that is generated by the {{site.data.keyword.compliance_short}} is encrypted at rest by IBM. To control the encryption of your data, you can enable a key management service and select your own key. For more information, see [Protecting your sensitive data](/docs/security-compliance?topic=security-compliance-mng-data#data-encryption).

New goals
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. 51 new goals have been added to the IBM profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the IBM Best Practices Controls 1.0 profile. All of the goals with ID's in the following ranges are new.
   * Goal ID's: `3000110` - `3000117`
   * Goal ID's: `3000256` - `3000279`
   * Goal ID's: `3000311` - `3000320`
   * Goal ID's: `3000631` - `3000639`

## 13 January 2021
{: #security-compliance-jan1321}
{: release-note}

General availability of Security Insights
:   You can now enable Security Insights (formerly known as Security Advisor) in the {{site.data.keyword.compliance_short}} so that you can analyze activity and identify suspicious behavior in your {{site.data.keyword.cloud_notm}} resources and applications. For more information, check out the [announcement blog](https://www.ibm.com/cloud/blog/announcements/security-insights-now-generally-available-in-the-security-and-compliance-center){: external}.

End of support for Network Insights
:   The beta version of Network Insights is deprecated and will no longer be supported as of 12 February 2021. To fully remove the beta version of Network Insights, delete the service components from your cluster and [delete your stored data from Cloud Object Storage](/docs/cloud-object-storage/info?topic=cloud-object-storage-security).

## 15 December 2020
{: #security-compliance-dec1520}
{: release-note}

Updated Scopes page
:   An improved experience is now available for viewing, creating, and deleting scopes. For more information, see [Managing scopes](/docs/security-compliance?topic=security-compliance-scopes).

Updated Inventory page
:   You can now delete inventories that you no longer require. For more information, see [Deleting an inventory](/docs/security-compliance?topic=security-compliance-inventory#delete-inventory)

New dashboard widget
:   Monitor your overall security and compliance at a glance by adding a {{site.data.keyword.compliance_short}} widget to your dashboard in the {{site.data.keyword.cloud_notm}} console. To learn more about customizing your dashboard, check out [Working with scoped dashboards](/docs/account?topic=account-custom-dashboard).

## 8 December 2020
{: #security-compliance-dec0820}
{: release-note}

Updated Goals page
:   An improved experience is now available for viewing and customizing goals. For more information, see [Customizing goals](/docs/security-compliance?topic=security-compliance-custom-goals).

Updated Profiles page
:   An improved experience is now available for viewing and managing profiles. For more information, see [Working with profiles](/docs/security-compliance?topic=security-compliance-profiles).

## 19 November 2020
{: #security-compliance-dec1920}
{: release-note}

Updated Settings page
:   An improved experience is now available for protecting the credentials that you use in the {{site.data.keyword.compliance_short}}. For more information, see [Creating a passphrase](/docs/security-compliance?topic=security-compliance-passphrase).

## 1 September 2020
{: #security-compliance-sept0120}
{: release-note}

General availability of the {{site.data.keyword.compliance_short}}
:   The {{site.data.keyword.compliance_short}} is now generally available on {{site.data.keyword.cloud_notm}}!

   In this release, the {{site.data.keyword.compliance_short}} offers support for profiles that you can use to monitor your accounts for compliance, config rules for governing the use of resources, and Security Insights for gaining insight into potential risks to your environments. For more information, check out the [announcement blog](https://www.ibm.com/cloud/blog/announcements/ibm-cloud-security-and-compliance-center){: external}.

## 1 September 2020
{: #security-compliance-sept0120}
{: release-note}

Introducing {{site.data.keyword.compliance_short}}
:   Manage security and compliance controls directly within the IBM Cloud® platform. With the IBM Security and Compliance Center, you view your security and compliance postures from a unified dashboard. 
   * Automate security and compliance postures
   * Enable configuration governance
   * Detect vulnerabilities and threats
