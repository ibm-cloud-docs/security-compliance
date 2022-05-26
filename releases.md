---

copyright:
  years: 2020, 2022
lastupdated: "2022-05-26"

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



## 26 May 2022
{: #security-compliance-may2622}
{: release-note}

In addition to small bug fixes and general updates, version 0.3.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is updated with the following changes.

| Goal ID   | Associated controls | Update |
|:----------|:--------------------|:-------|
| `3000025` |  | Goal is removed. |
| `3000039` |  | Goal is removed. |
| `3000410` |  | Goal is removed. |
| `3000411` |  | Goal is removed. |
| `3000013` |  | Goal is removed. |
| `3000014` |  | Goal is removed. |
| `3000603` | `AC-11(a)` | Goal is removed. |
| `3000049` | `SC-10` | Goal is added. |
| `3000233` | `SC-36` | Goal is added. |
| `3000470` | `AC-17(2)`, `SC-8`, `SC-8(1)`, and `SC-13` | Goal is added. |
| `3000473` | `CP-7(a)`, `CP-7(1)`, `CP-10`, and `SC-6` | Goal is added. |
| `3000474` | `CP-7(a)`, `CP-7(1)`, `CP-10`, and `SC-6` | Goal is added. |
| `3000475` | `AC-4`, `CM-2`, `SC-7`, and `SC-7(5)` | Goal is added. |
| `3000476` | `AC-4`, `CM-2`, `SC-7`, and `SC-7(5)` | Goal is added. |
| `3000462` | `SA-3(a)` | Goal is partially removed. |
| `3000907` | `SA-3(a)` | Goal is partially removed. |
| `3000711` | `AC-3` and `AC-6-0` | Goal is partially removed. |
| `3000712` | `AC-3` and `AC-6-0` | Goal is partially removed. |
| `3000047` | `SA-9`, `AC-20`, and `CA-3` | Goal is partially removed. |
| `3000711` | `AC-8` | Goal is partially added. |
| `3000712` | `AC-8` | Goal is partially added. |
| `3000047` | `SA-9(a)`, `AC-20(a)`, and `CA-3(a)` | Goal is partially added. |
| `3000282` |  | Goal logic is updated. |
| `3000455` |  | Goal logic is updated. |
{: caption="Table. Summary of {{site.data.keyword.cloud_notm}} for Financial Services profile changes for 26 May 2022" caption-side="top"}





## 13 May 2022
{: #security-compliance-may1322}
{: release-note}

New pricing plans available
:    The Posture Management component of the {{site.data.keyword.compliance_short}} is now a paid component. For more information about how pricing works and the available plans, see [How does {{site.data.keyword.compliance_short}} calculate pricing?](/docs/security-compliance?topic=security-compliance-scc-pricing).

For the most up-to-date pricing information, you can create a cost estimate by clicking **Add to estimate** from either the [provisioning](/security-compliance/catalog) or [plan page](/security-compliance/plan).



## 5 May 2022
{: #security-compliance-may0522}
{: release-note}

In addition to small bug fixes and general updates, version 0.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is updated with the following changes as of 4 May 2022.

| Goal ID   | Associated controls | Update made |
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





New versions of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Versions 0.1.4 and 0.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Serviices profile are now available with new goals and controls.

   Goals that were removed:

   * Goal ID: `3000104`
   * Goal ID: `3000040`
   * Goal ID: `3000021`
   * Goal ID: `3000029`
   * Goal ID: `3000032`
   * Goal ID: `3000038`
   * Goal ID: `3000529`
   * Goal ID: `3000537`
   * Goal ID: `3000623`
   * Goal ID: `3000538`
   * Goal ID: `3000628`
   * Goal ID: `3000533`
   * Goal ID: `3000541`
   * Goal ID: `3000639`
   * Goal ID: `3000414`
   * Goal ID: `3000415`
   * Goal ID: `3000416`
   * Goal ID: `3000417`
   * Goal ID: `3000012`
   * Goal ID: `3000018`

   Goals that were removed from specific controls:

   * Goal ID: `3000015` removed from the control AC-2(i)
   * Goal ID: `3000016` removed from the control AC-2(i)
   * Goal ID: `3000035` removed from the controls AC-2(i) and SC-2
   * Goal ID: `3000430` removed from the controls SI-4(a), SI-4(b) and SI-4(c)
   * Goal ID: `3000707` removed from the controls AC-2(i) and SC-2
   * Goal ID: `3000708` removed from the controls AC-2(i) and SC-2
   * Goal ID: `3000709` removed from the controls AC-2(i) and SC-2
   * Goal ID: `3000711` removed from the controls AC-2(i) and SC-2
   * Goal ID: `3000712` removed from the controls AC-2(i) and SC-2

   Goal mappings that were updated:

   * Goal ID: `3000001` mapped to the controls AC-2(1), AC-2(f), AC-2(j), IA-2, IA-5(c), IA-5(1) and IA-5(4)
   * Goal ID: `3000002` mapped to the controls AC-2(1), AC-2(f), AC-2(j), IA-2, IA-5(c), IA-5(1) and IA-5(4)
   * Goal ID: `3000003` mapped to the controls AC-2(1), AC-2(f), AC-2(j), IA-2, IA-5(c), IA-5(1) and IA-5(4)
   * Goal ID: `3000004` mapped to the controls AC-2(1), AC-2(f), AC-2(j), IA-2, IA-5(c), IA-5(1) and IA-5(4)
   * Goal ID: `3000005` mapped to the controls AC-2(1), AC-2(f), AC-2(j), IA-2, IA-5(c), IA-5(1) and IA-5(4)
   * Goal ID: `3000006` mapped to the controls AC-2(1), AC-2(f), AC-2(j), IA-2, IA-5(c), IA-5(1) and IA-5(4)
   * Goal ID: `3000007` mapped to the controls AC-2(1), AC-2(f), AC-2(j), IA-2, IA-5(c), IA-5(1) and IA-5(4)
   * Goal ID: `3000008` mapped to the controls AC-2(1), AC-2(f), AC-2(j), IA-2, IA-5(1) and IA-5(4)
   * Goal ID: `3000625` mapped to the controls AC-4, CM-2, SC-7, SC-7(3) and SC-7(5)
   * Goal ID: `3000601` mapped to the controls SI-2(2) and SI-2(a)
   * Goal ID: `3000602` mapped to the controls SI-2(2) and SI-2(a)
   * Goal ID: `3000603` mapped to the controls SI-2(2) and SI-2(a)
   * Goal ID: `3000430` mapped to the controls CA-7(a) and CA-7(b)
   * Goal ID: `3000022` mapped to the control AC-14(a)
   * Goal ID: `3000716` mapped to the control AC-7(a)
   * Goal ID: `3000717` mapped to the control AC-7(b)
   * Goal ID: `3000712` mapped to the control AC-14(a)
   * Goal ID: `3000015` mapped to the control AC-2(j)
   * Goal ID: `3000016` mapped to the control AC-2(j)
   * Goal ID: `3000035` mapped to the control AC-2(j)
   * Goal ID: `3000446` mapped to the control SC-7(3)
   * Goal ID: `3000707` mapped to the control SC-7(3)
   * Goal ID: `3000708` mapped to the control SC-7(3)
   * Goal ID: `3000709` mapped to the control SC-7(3)
   * Goal ID: `3000711` mapped to the control SC-7(3)
   * Goal ID: `3000712` mapped to the control SC-7(3)

   Goals that were added to version 0.2.0:

   * Goal ID: `3000418` mapped to the controls AC-4, CM-2, SC-7, SC-7(3) and SC-7(5)
   * Goal ID: `3000047` mapped to the controls SA-4(a), SA-4(b), SA-4(c), SA-9, AC-20, ESA-3, ESA-5 and CA-3
   * Goal ID: `3000282` mapped to the controls AU-4 and AU-11
   * Goal ID: `3000283` mapped to the controls AU-4, AU-11, SC-6 and SI-12
   * Goal ID: `3000322` mapped to the controls SC-13 and SC-28
   * Goal ID: `3000323` mapped to the controls SC-13 and SC-28
   * Goal ID: `3000471` mapped to the controls AC-4, SC-2 and SC-3
   * Goal ID: `3000472` mapped to the controls AC-4, SC-2 and SC-3
   * Goal ID: `3000915` mapped to the controls CP-7(a), CP-7(1), CP-10 and SC-6



## 23 March 2022
{: #security-compliance-mar2322}
{: release-note}

New goals
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. New goals have been added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000046` - `3000048` and `3000473` - `3000474`.


## 10 March 2022
{: #security-compliance-mar1022}
{: release-note}

Create rule flow updates
:   When you create a rule by using the console, the flow now includes the attachment of a scope. To try out the new flow, see [the {{site.data.keyword.compliance_short}} UI](/security-compliance/rules){: external}.

Quick start: Posture Management
:   The {{site.data.keyword.compliance_short}} UI has been updated to include more information in the overview page as well as a new Quick Start wizard for the Posture Management component of the service. To try it out, see [the {{site.data.keyword.compliance_short}} UI](/security-compliance/overview){: external}.


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
:   When resources such as an instance of {{site.data.keyword.containershort}} clusters are scanned, additional parameters must be provided in order for the collector to access all their configuration data. If this is the case, additional fields are displayed in the {{site.data.keyword.compliance_short}} UI when you are mapping credentials. For more information, see [Mapping additional credentials](/docs/security-compliance?topic=security-compliance-map-credentials).





New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.1.3 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. 

   Goals that were removed:
   * Goal ID: `3000019`
   * Goal ID: `3000030`
   * Goal ID: `3000031`
   * Goal ID: `3000033`
   * Goal ID: `3000034`
   * Goal ID: `3000101`
   * Goal ID: `3000418`
   * Goal ID: `3000635`
   * Goal ID: `3000636`

   Goal mappings that were updated:
   * Goal ID: `3000510` mapped to the controls AC-4, CM-2, SC-7 and SC-7(5)
   * Goal ID: `3000526` mapped to the controls AC-4, CM-2, SC-7 and SC-7(5)
   * Goal ID: `3000528` mapped to the controls SC-13 and SC-28
   * Goal ID: `3000529` mapped to the controls AC-2(i), AC-5(b), AC-18 and AC-21
   * Goal ID: `3000533` mapped to the controls AC-2(1), AC-2(c), AC-2(i), AC-3, AC-5(b), AC-6 and SC-2
   * Goal ID: `3000534` mapped to the controls AC-4, CM-2, SC-7 and SC-7(5)
   * Goal ID: `3000536` mapped to the controls SC-13 and SC-28
   * Goal ID: `3000537` mapped to the controls AC-2(i), AC-5(b), AC-18 and AC-21
   * Goal ID: `3000538` mapped to the controls AC-2(i), AC-5(b), AC-18 and AC-21
   * Goal ID: `3000541` mapped to the controls AC-2(1), AC-2(c), AC-2(i), AC-3, AC-5(b), AC-6 and SC-2
   * Goal ID: `3000611` mapped to the controls CM-8(3)(a), RA-5(a) and SI-2(2)
   * Goal ID: `3000108` mapped to the controls SC-13 and SC-28



## 21 January 2022
{: #security-compliance-jan2122}
{: release-note}

New service available in Configuration Governance
:   {{site.data.keyword.cloud_notm}} App ID is now available as part of the Configuration Governance component. You can create guardrails for App ID such as enforcing whether monitoring of runtime activity made by application users is tracked. For more information about the integration, see [the App ID docs](/docs/appid?topic=appid-manage-security-compliance).


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
:   {{site.data.keyword.cloud_notm}} Container Registry is now available as part of the Configuration Governance component. You can create guardrails for Container Registry such as restricting an account so that it can only push and pull images over private connections. For more information about the integration and the other available properties, see [the Container Registry docs](/docs/Registry?topic=Registry-manage-security-compliance#govern-container-registry).


## 22 November 2021
{: #security-compliance-nov2221}
{: release-note}

New goals
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. New goals have been added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

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
:   Version 0.1.2 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. Check out the following list of goals to see how they're mapped to specific controls.

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



## 2 September 2021
{: #security-compliance-sept0221}
{: release-note}

New goals
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. New goals have been added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000526` - `3000533`


## 18 August 2021
{: #security-compliance-aug1821}
{: release-note}

New goals
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. New goals have been added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000510` - `3000525` and `3000640`.

## 22 July 2021
{: #security-compliance-jul2221}
{: release-note}

New Posture Management API endpoints
:   With this release there are 9 new API endpoints available for the Posture Management API. To get started, see the [Posture Management API documentation](/apidocs/security-compliance/posture){: external}.

Consolidated SDK package
:   To make it easier to programmatically access the API from your code, {{site.data.keyword.compliance_short}} SDK packages are now available. The SDKs implement best practices for using the API and reduces the amount of code that you need to write. For more information, see the documentation for the following APIs:

* [Admin](/apidocs/security-compliance-admin){: external}
* [Configuration Governance](/apidocs/security-compliance-config){: external}
* [Posture Management](/apidocs/security-compliance/posture){: external}


New goals
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. New goals have been added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000509`

## 24 June 2021
{: #security-compliance-june242021}
{: release-note}





New version of the {{site.data.keyword.cloud_notm}} for Financial Services profile
:   Version 0.1.1 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls.

   Controls that were changed:

   * The control IDs `AC-2:(c)(j)`, `AC-2:(f)(j)`, and `AC-2:(j)` are changed to `AC-2(c)`, `AC-2(f)`, and `AC-2(j)`
   * The control ID `AC-2:(f)(j)` is changed to `AC-2(f)` and `AC-2(j)`
   * The control ID `AU-12(a)(d)` is changed to `AU-12(a) and AU-12(d)`
   * The control ID `CA-7:(a)(b)` is changed to `CA-7(a) and CA-7(b)`
   * The control ID `SI-4(a)(b)(c)` is changed to `SI-4(a)`, `SI-4(b)` and `SI-4(c)`


   Goals that were removed:

   * Goal ID: `3000011`
   * Goal ID: `3000204`
   * Goal ID: `3000303`
   * Goal ID: `3000450`
   * Goal ID: `3000301`


   Goals that were removed from specific controls:

   * Goal ID: `3000014` removed from the control `AC-2(1)`
   * Goal ID: `3000114` removed from the control `AU-12`


   Goal mappings that were updated:

   * Goal ID: `3000425` mapped to the controls `AC-2(1)` and `AC-2(j)`
   * Goal ID: `3000015` mapped to the controls `SC-2` and `AC-2(j)`
   * Goal ID: `3000462` mapped to the control `SA-3(a)`
   * Goal ID: `3000030` mapped to the control `SC-3`
   * Goal ID: `3000701` mapped to the controls `SC-8-0` and `SC-8(1)`
   * Goal ID: `3000466` mapped to the controls `SI-4(a)`, `SI-4(b)` and `SI-4(c)`
   * Goal IDs: `3000009`, `3000010`, `3000023`, `3000027`, `3000038`, `3000713`, `3000714`, `3000715`, `3000716`, `3000717`, `3000718`, `3000719`, `3000720`, `3000724` mapped to the control `AC-2(j)`
   * Goal IDs: `3000016`, `3000035`, `3000639`, `3000707`, `3000708`, `3000709`, `3000711`, `3000712` mapped to the controls `AC-2(1)`, `AC-2(j)` and `SC-2`
   * Goal IDs: `3000101`, `3000102`, `3000103` mapped to the control `SC-13`
   * Goal IDs: `3000458`, `3000460` mapped to the controls `SC-13` and `SC-23`


   Goals that were added:

   * Goal ID: `3000038` mapped to the control `AC-2(j))`



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
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. N goals have been added to the {{site.data.keyword.compliance_short}} profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the `IBM Best Practices Controls 1.0` profile. All the goals with ID's in the following ranges are new.

* Goal ID's: `3000901` - `3000907`

## 5 April 2021
{: #security-compliance-april0521}

Initial Posture Management API support
:   As part of this release, the Posture Management component of the service provides three external APIs that you can use as part of your security and compliance automation. For more information, see the [Posture Management API docs](/apidocs/security-compliance/posture).

Proxy support for discovery and fact collection
:   With this release, you can configure your collector to use a proxy to access the public endpoints to enhance the security of your scans. For more information, see [Which endpoints does a collector access?](/docs/security-compliance?topic=security-compliance-collector-manual#collector-proxy).

New goal mapping
:   The goal `3000045` is now mapped to CM-2 NIST 800 and has been added to an additional profile.

{{site.data.keyword.cloud_notm}} for Financial Services profile
:   Released today, the {{site.data.keyword.cloud_notm}} for Financial Services profile is a collection of curated goals that can help organizations make a large jump on the path to meeting the NIST 800-53 security controls that are required for financial institutions. By validating your resources against the {{site.data.keyword.cloud_notm}} for Financial Services profile, you can be more confident that your {{site.data.keyword.cloud_notm}} resources are following best practices for security and compliance.

   *Important*: The {{site.data.keyword.cloud_notm}} for Financial Services profile will be constantly expanding and is not an exhaustive list of all the controls that might be required for every organization. Users should validate the available goals and determine where there is a need to supplement their workloads with other security measures.



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
:   You might notice that your compliance score has changed even though you haven't updated any of your configurations. 51 new goals have been added to the IBM profiles that your resources are automatically scanned for. For detailed descriptions of the new goals, you can review the IBM Best Practices Controls 1.0 profile. All the goals with ID's in the following ranges are new.

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
:   An improved experience is now available for protecting the credentials that you use in the {{site.data.keyword.compliance_short}}. For more information, see [Creating a passphrase](/docs/security-compliance?topic=security-compliance-passphrase).

## 1 September 2020
{: #security-compliance-sept0120}
{: release-note}

General availability of the {{site.data.keyword.compliance_short}}
:   The {{site.data.keyword.compliance_short}} is now generally available on {{site.data.keyword.cloud_notm}}!

   In this release, the {{site.data.keyword.compliance_short}} offers support for profiles that you can use to monitor your accounts for compliance and config rules for governing the use of resources across your accounts. For more information, check out the [announcement blog](https://www.ibm.com/cloud/blog/announcements/ibm-cloud-security-and-compliance-center){: external}.

