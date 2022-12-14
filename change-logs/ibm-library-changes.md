---

copyright:
  years: 2020, 2022
lastupdated: "2022-12-14"

keywords: release notes for {{site.data.keyword.compliance_short}}, ibm security best practices, profile changes, enhancements, fixes, improvements

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

# Change log: {{site.data.keyword.cloud_notm}} Control Library
{: #ibm-control-library-change-log}

In this change log, you can learn about the changes, improvements, and updates for the {{site.data.keyword.cloud_notm}} Control Library. The change log lists changes that were made, ordered by the date that they were released.

As of 27 May 2022, the {{site.data.keyword.cloud_notm}} Best Practices Controls profile was rebranded to become the {{site.data.keyword.cloud_notm}} Control Library.
{: note}

## Profile versioning
{: #cl-profile-versioning}

The {{site.data.keyword.cloud_notm}} Control Library profile is an exhaustive list of all the controls and goals that are available for {{site.data.keyword.cloud_notm}}. The profile is consistently updated and can change at any time, which can cause your compliance score to change without any update to your configuration. When new goals or controls are edited or removed from the profile in a way that is not compatible with the current version, a new version is released.

## 14 December 2022
{: #ibmcl-dec1422}

The format of the {{site.data.keyword.cloud_notm}} Control Library profile has been updated with the following changes. Review your configuration closely to ensure that the profile still meets your needs.
- The profile is available only on the **Profiles** page of the **Manage** section of the updated infrastructure.
- The format changed from being goal-based to assessment-based.



## 25 July 2022
{: #ibmcl-jul2522}

In addition to small bug fixes and general updates, the {{site.data.keyword.cloud_notm}} Control Library profile has been updated with the following changes as of 25 July 2022.

This update adds goals that are based on functionality that helps you to maintain compliance that is built-in to {{site.data.keyword.cloud_notm}}.
{: note}

| Goal ID   | Description | Associated controls | Update |
|-----------|-------------|---------------------|--------|
| `3000053` | IBMid enforces a limit of 5 consecutive unsuccessful sign in attempts | `1.52` | The goal was added. |
| `3000054` | IBMid automatically locks an account for 30 minutes after 5 consecutive unsuccessful sign in attempts | `1.53` | The goal was added. |
| `3000055` | IBM Cloud console conceals information previously visible on the display when the user has been signed out due to inactivity | `1.54` | The goal was added. |
| `3000056` | IBM Cloud retains the session lock until access is reestablished by signing in | `1.55` | The goal was added. |
| `3000057` | IBM Cloud provides the means to associate a customer-defined security identifier and attributes with IBM Cloud resources (for example, tags) | `1.56` | The goal was added. |
| `3000058` | IBM Cloud provides the ability to immediately terminate a user session for an account | `1.57` | The goal was added. |
| `3000059` | IBM Cloud accounts are one of the account types used to support your applications | `1.58` | The goal was added. |
| `3000060` | IBMid uniquely identifies and authenticates organizational users or processes that act on behalf of organizational users | `1.59` | The goal was added. |
| `3000061` | IBM Cloud IAM uniquely identifies and authenticates organizational users or processes that act on behalf of organizational users | `1.60` | The goal was added. |
| `3000062` | IBMid selects and assigns identifiers that identify individuals | `1.61` | The goal was added. |
| `3000063` | IBM Cloud assigns identifiers that identify individuals, groups, roles, and devices | `1.62` | The goal was added. |
| `3000064` | IBM Cloud prevents reuse of identifiers | `1.63` | The goal was added. |
| `3000065` | IBMid ensures that passwords have sufficient strength for their intended use | `1.64` | The goal was added. |
| `3000066` | IBM Cloud IAM ensures that authenticators, such as API keys, have sufficient strength for their intended use | `1.65` | The goal was added. |
| `3000067` | IBMid establishes minimum and maximum lifetime restrictions and reuse conditions for authenticators | `1.66` | The goal was added. |
| `3000068` | IBM Cloud IAM establishes minimum and maximum lifetime restrictions and reuse conditions for authenticators, such as API keys | `1.67` | The goal was added. |
| `3000069` | IBMid does not allow changed or reset passwords to be the same as any of the 24 previously used passwords | `1.68` | The goal was added. |
| `3000070` | IBMid stores and transmits only encrypted representations of passwords | `1.69` | The goal was added. |
| `3000071` | IBMid enforces password expiry after 90 days | `1.70` | The goal was added. |
| `3000073` | IBMid employs automated tools to determine if password authenticators satisfy IBMid password requirements | `1.71` | The goal was added. |
| `3000074` | IBMid protects user information during the authentication process from possible exploitation by unauthorized individuals by obscuring it  | `1.72` | The goal was added. |
| `3000075` | IBM Cloud IAM establishes initial authenticator content for authenticators that are defined by the organization (for example, API keys) | `1.73` | The goal was added. |
| `3000076` | IBM Cloud VPC uniquely identifies all physical devices before accepting a network connection | `1.74` | The goal was added. |
{: caption="Table. Summary of {{site.data.keyword.cloud_notm}} Control Library profile changes for 25 July 2022" caption-side="top"}


## 27 May 2022
{: #ibmcl-may2722}


Profiles are constantly expanding and are not an exhaustive list of all the controls that might be required for every organization. Users can validate the available goals and determine where a need to supplement their workloads with other security and compliance measures exists.
{: note}

Now available: The {{site.data.keyword.cloud_notm}} Control Library profile
:    As part of this release the {{site.data.keyword.cloud_notm}} Control Library 1.0 profile was renamed to the {{site.data.keyword.cloud_notm}} Control Library. The {{site.data.keyword.cloud_notm}} Control Library is a profile that contains all the available controls and goals that are available for {{site.data.keyword.cloud_notm}}. The library cannot be used to scan your resources directly, but you are able to create a custom profile from the library. 


## 23 March 2022
{: #ibmcl-mar2322}

Five new goals were added to the Best Practices Controls profile. The following goals are new:

* Goal IDs: `3000046` - `3000048` and `3000473` - `3000474`.


## 22 November 2021
{: #ibmcl-nov2221}

Four new goals that were added to the Best Practices Controls profile. The following goals are new:

* Goal IDs: `3000542` - `3000544` and `3000321`.


## 2 September 2021
{: #ibmcl-sept0221}

Seven new goals were added to the Best Practices Controls profile. The following goals are new:

* Goal IDs: `3000526` - `3000533`


## 18 August 2021
{: #ibmcl-aug1821}

16 new goals were added to the Best Practices Controls profile. The following goals are new:

* Goal IDs: `3000510` - `3000525` and `3000640`.

## 22 July 2021
{: #ibmcl-jul2221}

One new goal that was added to the Best Practices Controls profile. The following goal is new:

* Goal IDs: `3000509`


## 14 June 2021
{: #ibmcl-jun1421}

Seven new goals were added to the Best Practices Controls profile. The following goals are new:

* Goal IDs: `3000901` - `3000907`


## 17 February 2021
{: #ibmcl-feb1721}

51 new goals were added to the Best Practices Controls profile. The following goals are new:

* Goal IDs: `3000110` - `3000117`
* Goal IDs: `3000256` - `3000279`
* Goal IDs: `3000311` - `3000320`
* Goal IDs: `3000631` - `3000639`


## 1 September 2020
{: #ibmcl-sept0120}

With the release of the {{site.data.keyword.compliance_short}}, the Best Practices Controls profile is now available.

