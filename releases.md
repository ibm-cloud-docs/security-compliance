---

copyright:
  years: 2020, 2022
lastupdated: "2022-10-04"

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

# Release notes for {{site.data.keyword.compliance_short}}
{: #release-notes}





## 21 September 2022
{: #security-compliance-sept2022}
{: release-note}

Now available: New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.6.0  of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-profile-change-log).




## 1 September 2022
{: #security-compliance-sept0122}
{: release-note}

New properties available for Virtual Private Cloud
:   {{site.data.keyword.cloud_notm}} Virtual Private Cloud now has additional properties available as part of the Configuration Governance component. You can create guardrails for virtual servers such as restricting the use of floating IPs and service metadata. For more information about the integration and view other available properties, see the [VPC documentation](/docs/vpc?topic=vpc-manage-security-compliance).

Removed: Credential passphrase
:   As of today, 1 September 2022, the ability to use a passphrase to manage the security of your credentials is deprecated in favor of Bring Your Own Key (BYOK) functionality. If you did not disable your passphrase and return to IBM-managed, you must recreate all of your credentials to continue to scan your resources. For help enabling BYOK or to learn more about how your credentials are protected, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).



## 11 August 2022
{: #security-compliance-aug1222}
{: release-note}

Now available: New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.5.0  of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-profile-change-log).


## 9 August 2022
{: #security-compliance-aug0922}
{: release-note}

New available: Longer default storage
:   The data that is generated during a scan is now stored for 180 days. This is an increase from 30 days. For more information about how your data is stored, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).


## 3 August 2022
{: #security-compliance-aug-0322}

Change to permission requirements for integrations
:   As of today, Security and Compliance Integrations permissions for viewing, creating, updating, and deleting integrations in {{site.data.keyword.compliance_short}} are no longer supported. To work with integrations use the following action to role mappings:

   * `compliance.posture-management.integrations-read`: View an integration in {{site.data.keyword.compliance_short}}.
   * `compliance.posture-management.integrations-create`: Create an integration in {{site.data.keyword.compliance_short}}.
   * `compliance.posture-management.integrations-update`: Update an integration in {{site.data.keyword.compliance_short}}.
   * `compliance.posture-management.integrations-delete`: Delete an integration in {{site.data.keyword.compliance_short}}.

   For more information about required permissions, view [Managing IAM access for {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-access-management).
   

## 2 August 2022
{: #security-compliance-aug-0222}

Deprecated: Credential passphrase
:   As of today, the ability to create a passphrase to manage the security of your credentials is deprecated in favor of the Bring Your Own Key (BYOK) functionality. If you are currently using a passphrase to protect your credentials, you must disable the passphrase by returning to IBM-managed encryption prior to 1 September 2022. Then, you can enable BYOK on the **Settings** page of the {{site.data.keyword.compliance_short}} UI. For more information about how your credentials are protected, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).

## 25 July 2022
{: #security-compliance-july2522}
{: release-note}

Now available: Profile updates
:   Goal updates are now available to the {{site.data.keyword.cloud_notm}} Control Library and {{site.data.keyword.cloud_notm}} Security Best Practices Profiles. For more information see the [{{site.data.keyword.cloud_notm}} Control Library change log](/docs/security-compliance?topic=security-compliance-ibm-control-library-change-log) or the [{{site.data.keyword.cloud_notm}} Security Best Practices change log](/docs/security-compliance?topic=security-compliance-ibm-sec-best-practices-change-log).


## 12 July 2022
{: #security-compliance-july1222}
{: release-note}

Now available: New region - WDC
:   {{site.data.keyword.compliance_short}} is now configured to use the Washington DC region as a back up should a disaster scenario occur. 


## 23 June 2022
{: #security-compliance-june2322}
{: release-note}

Now available: New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.4.0  of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-profile-change-log).


## 1 June 2022
{: #security-compliance-June0122}
{: release-note}

As of 1 June 2022, the Security Insights component of {{site.data.keyword.compliance_short}} is deprecated and support was removed. A replacement has not yet been found. Please note, this discontinuation does not affect the other features in {{site.data.keyword.compliance_short}}. If you have comments, questions, or concerns, please reach out to Jessica Doherty by email at `jpbonner@us.ibm.com`.


## 27 May 2022
{: #security-compliance-may2722}
{: release-note}

Profiles are constantly expanding and are not an exhaustive list of all the controls that might be required for every organization. Users can validate the available goals and determine where a need to supplement their workloads with other security and compliance measures exists.
{: note}

Now available: {{site.data.keyword.cloud_notm}} Security Best Practices Controls profile
:    Released today, the {{site.data.keyword.cloud_notm}} Security Best Practices profile is a collection of goals that can help an organization to ensure that they are adhering to best practices as defined by {{site.data.keyword.cloud_notm}} security.

Now available: The {{site.data.keyword.cloud_notm}} Control Library profile
:    As part of this release the {{site.data.keyword.cloud_notm}} Best Practices Controls 1.0 profile was renamed to the {{site.data.keyword.cloud_notm}} Control Library. The {{site.data.keyword.cloud_notm}} Control Library is a profile that contains all the available controls and goals that are available for {{site.data.keyword.cloud_notm}}. The library cannot be used to scan your resources directly, but you are able to create a custom profile from the library. 

Now available: New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.3.0  of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-profile-change-log).


## 13 May 2022
{: #security-compliance-may1322}
{: release-note}

New pricing plans available
:    The Posture Management component of the {{site.data.keyword.compliance_short}} is now a paid component. For more information about how pricing works and the available plans, see [How does {{site.data.keyword.compliance_short}} calculate pricing?](/docs/security-compliance?topic=security-compliance-scc-pricing)

For the most up-to-date pricing information, you can create a cost estimate by clicking **Add to estimate** from either the [provisioning](/security-compliance/catalog) or [plan page](/security-compliance/plan).



## 5 May 2022
{: #security-compliance-may0522}
{: release-note}

In addition to small bug fixes and general updates, version 0.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is updated with the following changes as of 4 May 2022.

| Goal ID   | Associated controls | Update |
|:----------|:-------------|:------------|
| `3000906` | `SC-8-0`, `SC-8(1)`, `SC-13`, and `SC-23` | Updated goal and fact collection logic. |
| `3000601` | `CM-8(3)(a)`, `RA-5(a)`, `SI-2(2)`, and `SI-2(a)` | Updated goal logic to consider whether the status is either unscanned or incomplete. |
| `3000601` | `CM-8(3)(a)`, `RA-5(a)`, `SI-2(2)`, and `SI-2(a)` | Updated messaging. |
| `3000407` | `SC-8-0`, `SC-8(1)`, `SC-13`, and `SC-23` | Updated goal and fact collection logic. |
| `3000462` | `CM-2`, `CM-7(a)`, `CM-8(3)(a)`, and `SA-3(a)` | Updated goal and fact collection logic. |
| `3000029`* | `AC-3`, `AC-5(b)`, `AC-6-0`, and `AC-2(i)` | Goal is removed. |
{: caption="Table. Summary of {{site.data.keyword.cloud_notm}} for Financial Services profile changes for 4 May 2022" caption-side="top"}

*This goal is also removed from version 0.1.4.


## 5 April 2022
{: #security-compliance-apr0522}
{: release-note}

New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.1.4 and Version 0.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile are now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-profile-change-log).


## 23 March 2022
{: #security-compliance-mar2322}
{: release-note}

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000046` - `3000048` and `3000473` - `3000474`.


## 10 March 2022
{: #security-compliance-mar1022}
{: release-note}

Create rule flow updates
:   When you create a rule by using the console, the flow now includes the attachment of a scope. To try out the new flow, see [the {{site.data.keyword.compliance_short}} UI](/security-compliance/rules){: external}.

Quick start: Posture Management
:   The {{site.data.keyword.compliance_short}} UI was updated to include more information in the overview page and a new Quick Start wizard for the Posture Management component of the service. To try it out, see [the {{site.data.keyword.compliance_short}} UI](/security-compliance/overview){: external}.


## 1 March 2022
{: #security-compliance-mar0122}
{: release-note}

Create scope flow updates
:   The create scope flow is now updated in the GUI to include the scheduling of scans as part of the creation of a scope. To try out the new flow, see [the {{site.data.keyword.compliance_short}} UI](/security-compliance/scopes){: external}. 


## 17 February 2022
{: #security-compliance-feb1722}
{: release-note}

New service available in Configuration Governance
:   VPN for Virtual Private Cloud is now available as part of the Configuration Governance component. You can create guardrails for VPN for VPC such as enforcing specific IPsec and IKE policies for authentication and encryption. For more information about the integration, see [the VPC docs](/docs/vpc?topic=vpc-manage-security-compliance).



## 27 January 2022
{: #security-compliance-jan2722}
{: release-note}

Add parameters during credential mapping
:   When resources such as an instance of {{site.data.keyword.containershort}} clusters are scanned, additional parameters must be provided in order for the collector to access all their configuration data. If so, additional fields are displayed in the {{site.data.keyword.compliance_short}} UI when you are mapping credentials. For more information, see [Mapping additional credentials](/docs/security-compliance?topic=security-compliance-map-credentials).



Now available: New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.1.3 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-profile-change-log).

## 21 January 2022
{: #security-compliance-jan2122}
{: release-note}

New service available in Configuration Governance
:   {{site.data.keyword.cloud_notm}} App ID is now available as part of the Configuration Governance component. You can create guardrails for App ID such as enforcing whether monitoring of runtime activity that is made by application users is tracked. For more information about the integration, see [the App ID docs](/docs/appid?topic=appid-manage-security-compliance).


## 11 January 2022
{: #security-compliance-jan1122}
{: release-note}

New service available in Configuration Governance
:   {{site.data.keyword.cloud_notm}} Code Engine is now available as part of the Configuration Governance component. You can create guardrails for Code Engine such as ensuring that projects can be created only within specific regions. For more information about the integration, see [the Code Engine docs](/docs/codeengine?topic=codeengine-manage-security-compliance).


## 13 December 2021
{: #security-compliance-dec1321}
{: release-note}

{{site.data.keyword.en_short}} integration
:   You can now integrate with [{{site.data.keyword.en_full_notm}}](/catalog/services/event-notifications){: external} so that you can view and manage all your {{site.data.keyword.compliance_short}} alerts in a single location. With a fast alert time, you're able to immediately start an investigation into any reported issue and fix the vulnerability before it becomes a larger problem in your application.

   To connect the {{site.data.keyword.compliance_short}} with the {{site.data.keyword.en_short}} service, see [Enabling event notifications](/docs/security-compliance?topic=security-compliance-event-notifications). For more information, check out the [announcement blog](https://www.ibm.com/cloud/blog/announcements/ibm-cloud-security-and-compliance-center-is-now-integrated-with-event-notifications){: external}.

Deprecation of the alerts capability
:   As of 13 December 2021, alerts are deprecated in favor of [{{site.data.keyword.en_short}}](/docs/security-compliance?topic=security-compliance-event-notifications). The ability to create alerts within the {{site.data.keyword.compliance_short}} is no longer supported. You can continue to view, enable, disable, or delete your existing alerts until 15 March 2021. After this date, any existing alerts will be deleted, and the feature will be removed from the UI.

   To enable the new notifications capability, you can go to the **Global settings > Event Notifications** section of the {{site.data.keyword.compliance_short}} UI. For more information, see [Enabling event notifications](/docs/security-compliance?topic=security-compliance-event-notifications).


## 9 December 2021
{: #security-compliance-dec921}
{: release-note}

Customer-managed collectors can now be installed on a cluster
:   You can now install your customer-managed collector on to an {{site.data.keyword.cloud_notm}} Kubernetes Service or OpenShift cluster. For more information or help getting started, see [the tutorial](/docs/security-compliance?topic=security-compliance-ibm-customer-collector-cluster).

New service available in Configuration Governance
:   {{site.data.keyword.cloud_notm}} Container Registry is now available as part of the Configuration Governance component. You can create guardrails for Container Registry such as restricting an account so that it can push and pull images only over private connections. For more information about the integration and the other available properties, see [the Container Registry docs](/docs/Registry?topic=Registry-manage-security-compliance#govern-container-registry).


## 22 November 2021
{: #security-compliance-nov2221}
{: release-note}

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000542` - `3000544` and `3000321`.

## 1 November 2021
{: #security-compliance-nov012021}
{: release-note}

Scan your OpenShift clusters
:   The ability to scan your OpenShift clusters is now available through the OpenShift Compliance Operator(OSCO) integration. To get started, see [Integrating OSCO](/docs/security-compliance?topic=security-compliance-setup-osco).

## 27 October 2021
{: #security-compliance-oct272021}
{: release-note}

Deprecation of the bookmarks capability
:   The ability to create bookmarks or direct connections within the {{site.data.keyword.compliance_short}} will be deprecated on 30 November 2021, when the feature will be removed from the UI. Be sure to save any bookmarked URLs that you need to before the deprecation date.

## 16 September 2021
{: #security-compliance-sept152021}
{: release-note}



New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.1.2 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-profile-change-log).



## 2 September 2021
{: #security-compliance-sept0221}
{: release-note}

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000526` - `3000533`


## 18 August 2021
{: #security-compliance-aug1821}
{: release-note}

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000510` - `3000525` and `3000640`.

## 22 July 2021
{: #security-compliance-jul2221}
{: release-note}

New Posture Management API endpoints
:   With this release, 9 new API endpoints for the Posture Management API are available. To get started, see the [Posture Management API documentation](/apidocs/security-compliance/posture){: external}.

Consolidated SDK package
:   To make it easier to programmatically access the API from your code, {{site.data.keyword.compliance_short}} SDK packages are now available. The SDKs implement best practices for using the API and reduces the amount of code that you need to write. For more information, see the documentation for the following APIs:

* [Admin](/apidocs/security-compliance-admin){: external}
* [Configuration Governance](/apidocs/security-compliance-config){: external}
* [Posture Management](/apidocs/security-compliance/posture){: external}


New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000509`

## 24 June 2021
{: #security-compliance-june242021}
{: release-note}


New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.1.1 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. For more information, see the [{{site.data.keyword.cloud_notm}} for Financial Services profile change log](/docs/security-compliance?topic=security-compliance-fs-profile-change-log).


## 22 June 2021
{: #security-compliance-jun2221}
{: release-note}

Tanium integration
:   Now, you can configure [Tanium Comply](https://docs.tanium.com/comply/comply/index.html){: external} to forward your compliance data. With Tanium Comply, you can evaluate your organizations endpoints for potential vulnerabilities and misconfigurations against industry security standards, vulnerability definitions, and custom compliance checks. When you integrate Tanium with the {{site.data.keyword.compliance_short}}, you can view all your compliance data in one location in the same format. For more information, see [Connecting Tanium](/docs/security-compliance?topic=security-compliance-setup-tanium).


## 14 June 2021
{: #security-compliance-jun1421}
{: release-note}

IBM-managed collector
:   A collector is used to gather the configuration information about your resources and then validate it against a specified standard. Previously, you were responsible for the installation and lifecycle management of the collector. Now, you can get a proof of concept up and running quickly by configuring an IBM-managed collector. For more information, see [Configuring managed collectors](/docs/security-compliance?topic=security-compliance-ibm-collector) or [What is a collector?](/docs/security-compliance?topic=security-compliance-collector).

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. New goals were added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000901` - `3000907`

## 5 April 2021
{: #security-compliance-april0521}

Initial Posture Management API support
:   As part of this release, the Posture Management component of the service provides three external APIs that you can use as part of your security and compliance automation. For more information, see the [Posture Management API docs](/apidocs/security-compliance/posture).

Proxy support for discovery and fact collection
:   With this release, you can configure your collector to use a proxy to access the public endpoints to enhance the security of your scans. For more information, see [Which endpoints does a collector access?](/docs/security-compliance?topic=security-compliance-collector-manual#collector-proxy)

New goal mapping
:   The goal `3000045` is now mapped to CM-2 NIST 800 and were added to an additional profile.

{{site.data.keyword.cloud_notm}} for Financial Services profile
:   Released today, the {{site.data.keyword.cloud_notm}} for Financial Services profile is a collection of curated goals. These goals can help organizations make a large jump on the path to meeting the NIST 800-53 security controls that are required for financial institutions. By validating your resources against the {{site.data.keyword.cloud_notm}} for Financial Services profile, you can be more confident that your {{site.data.keyword.cloud_notm}} resources are following best practices for security and compliance.

   *Important*: The {{site.data.keyword.cloud_notm}} for Financial Services profile are constantly expanding and is not an exhaustive list of all the controls that might be required for every organization. Users can validate the available goals and determine where a need to supplement their workloads with other security measures exists.



## 23 March 2021
{: #security-compliance-march0321}
{: release-note}

Manage the location in which your data is stored
:   Have specific regulations around where your data is stored and processed? With {{site.data.keyword.compliance_short}}, you can now choose the location in which the data that is generated by the service is managed. To set your location preferences, you can go to the **Menu icon** ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Data Settings**.

   For more information, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).


## 15 March 2021
{: #security-compliance-march1521}
{: release-note}

Customize default values for your resources
:   Looking for more options to help you govern {{site.data.keyword.cloud_notm}} resources? With {{site.data.keyword.compliance_short}}, you can now create templates that define your preferred property values for target resources in your selected {{site.data.keyword.cloud_notm}} accounts. After you create a template and attach it to a scope, your customized defaults override the default values that are provided by IBM.

   To get started with templates, you can go to the **Menu icon** ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Govern resources > Configure > Templates**, or check out the [API reference](/apidocs/security-compliance-config) to learn more about creating templates programmatically.

   For more information, see [What is Configuration Governance?](/docs/security-compliance?topic=security-compliance-what-is-governance)

## 17 February 2021
{: #security-compliance-feb1721}
{: release-note}

Manage your own encryption
:   If you're using {{site.data.keyword.compliance_short}} to monitor your current posture, you can now manage your encryption settings in the **Data settings** tab of the service UI.

   By default, the data that is generated by the {{site.data.keyword.compliance_short}} is encrypted at rest by IBM. To control the encryption of your data, you can enable a key management service and select your own key. For more information, see [Protecting your sensitive data](/docs/security-compliance?topic=security-compliance-mng-data#data-encryption).

New goals
:   You might notice that your compliance score changed even though you didn't update any of your configurations. 51 new goals were added to the IBM profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the IBM Best Practices Controls 1.0 profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000110` - `3000117`
* Goal ID's: `3000256` - `3000279`
* Goal ID's: `3000311` - `3000320`
* Goal ID's: `3000631` - `3000639`



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
:   An improved experience is now available for protecting the credentials that you use in the {{site.data.keyword.compliance_short}}.

## 1 September 2020
{: #security-compliance-sept0120}
{: release-note}

General availability of the {{site.data.keyword.compliance_short}}
:   The {{site.data.keyword.compliance_short}} is now generally available on {{site.data.keyword.cloud_notm}}!

   In this release, the {{site.data.keyword.compliance_short}} offers support for profiles that you can use to monitor your accounts for compliance and config rules for governing the use of resources across your accounts. For more information, check out the [announcement blog](https://www.ibm.com/cloud/blog/announcements/ibm-cloud-security-and-compliance-center){: external}.

