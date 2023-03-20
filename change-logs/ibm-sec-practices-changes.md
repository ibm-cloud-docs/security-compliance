---

copyright:
  years: 2020, 2023
lastupdated: "2023-03-20"

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

# Change log: {{site.data.keyword.cloud_notm}} Security Best Practices
{: #ibm-sec-best-practices-change-log}

The {{site.data.keyword.cloud_notm}} Security Best Practices library is a collection of controls and goals that meet {{site.data.keyword.cloud_notm}} and industry best practices. The library is consistently updated and can change at any time, which can cause your compliance score to change without any update to your configuration. When new controls or specifications are edited or removed from the library in a way that is not compatible with the current version, a new version is released.


If you're working with this library, new goals are automatically added to your current scans. If you want more control over when new goals are added, you can create a custom profile that contains all or a subset of the goals that are currently available. For more information, see [Building custom profiles](/docs/security-compliance?topic=security-compliance-custom-profiles).
{: note}

## Version 1.1.0
{: #sec-best-v1.1.0}

The following new controls have been added to the {{site.data.keyword.cloud_notm}} Security Best Practices library and profile. 


| Control ID | Control Description |
|:-----------|:--------------------|
| 6.1 | Ensure Toolchain scans during continuous integration the source code to identify vulnerabilities |
| 6.2 | Ensure Toolchain has unit tests that are continuously run to validate source code changes |
| 6.3 | Ensure Toolchain has Code Risk Analyzer configured that collects a bill of materials for pipeline run  |
| 6.4 | Ensure Toolchain is configured with image signing |
| 6.5 | Ensure Toolchain source code meets Center for Internet Security Docker benchmarks |
| 6.6 | Ensure Toolchain has branch protection rules enabled |
| 6.7 | Ensure Toolchain has secret detection scans enabled for source code |
| 6.8 | Ensure Toolchain production change request exists and is approved |
| 6.9 | Ensure Toolchain Container Registry Vulnerability Advisor scans images for OS vulnerability detection |
| 6.12 | Ensure Toolchain acceptance tests exist and have passed |
| 6.16 | Ensure that only the tool integrations within the toolchain are included in the allow list parameter array |
| 6.17 | Ensure a Toolchain static scan exists and has passed |
| 6.18 | Ensure a Toolchain dynamic scan exists and has passed |
{: caption="Table. Summary of {{site.data.keyword.cloud_notm}} Security Best Practices profile changes for Version 1.1.0" caption-side="top"}

The Toolchain controls that are listed in the table are configured to check DevSecOps Continuous Delivery (CD) and DevSecOps Continuous Compliance (CC) toolchains only, except for control 6.16, which is relevant to all toolchains. If you run an evaluation on a DevSecOps Continous Integration (CI) toolchain, or on any other toolchain that is not a DevSecOps toolchain, the result is returned as *Unable to perform*.
{: note}

## Version 1.0.0
{: #sec-best-v1.0.0}

The format of the {{site.data.keyword.cloud_notm}} Security Best Practices profile has been updated with the following changes. Review your configuration closely to ensure that the profile still meets your needs.
- The profile is noq available on the **Profiles** page of the **Manage** section of the updated infrastructure.
- The format changed from being goal-based to assessment-based.

## Goal-based architecture
{: #sec-goals}

### 25 July 2022
{: #sec-best-jul2522}

In addition to small bug fixes and general updates, the {{site.data.keyword.cloud_notm}} Security Best Practices profile has now been updated with the following changes as of 25 July 2022.

This update adds goals that are based on functionality that helps you to maintain compliance that is built-in to {{site.data.keyword.cloud_notm}}.
{: note}


| Goal ID   | Description | Associated controls | Update |
|-----------|-------------|---------------------|--------|
| `3000053` | IBMid enforces a limit of 5 consecutive unsuccessful sign in attempts | `1.47` | The goal was added. |
| `3000054` | IBMid automatically locks an account for 30 minutes after 5 consecutive unsuccessful sign in attempts | `1.48` | The goal was added. |
| `3000055` | IBM Cloud console conceals information previously visible on the display when the user has been signed out due to inactivity | `1.49` | The goal was added. |
| `3000056` | IBM Cloud retains the session lock until access is reestablished by signing in | `1.50` | The goal was added. |
| `3000057` | IBM Cloud provides the means to associate a customer-defined security identifier and attributes with IBM Cloud resources (for example, tags) | `1.51` | The goal was added. |
| `3000058` | IBM Cloud provides the ability to immediately terminate a user session for an account | `1.52` | The goal was added. |
| `3000060` | IBMid uniquely identifies and authenticates organizational users or processes that act on behalf of organizational users | `1.53` | The goal was added. |
| `3000061` | IBM Cloud IAM uniquely identifies and authenticates organizational users or processes that act on behalf of organizational users | `1.54` | The goal was added. |
| `3000062` | IBMid selects and assigns identifiers that identify individuals | `1.55` | The goal was added. |
| `3000063` | IBM Cloud assigns identifiers that identify individuals, groups, roles, and devices | `1.56` | The goal was added. |
| `3000064` | IBM Cloud prevents reuse of identifiers | `1.57` | The goal was added. |
| `3000065` | IBMid ensures that passwords have sufficient strength for their intended use | `1.58` | The goal was added. |
| `3000066` | IBM Cloud IAM ensures that authenticators, such as API keys, have sufficient strength for their intended use | `1.59` | The goal was added. |
| `3000067` | IBMid establishes minimum and maximum lifetime restrictions and reuse conditions for authenticators | `1.60` | The goal was added. |
| `3000068` | IBM Cloud IAM establishes minimum and maximum lifetime restrictions and reuse conditions for authenticators, such as API keys | `1.61` | The goal was added. |
| `3000069` | IBMid does not allow changed or reset passwords to be the same as any of the 24 previously used passwords | `1.62` | The goal was added. |
| `3000070` | IBMid stores and transmits only encrypted representations of passwords | `1.63` | The goal was added. |
| `3000071` | IBMid enforces password expiry after 90 days | `1.64` | The goal was added. |
| `3000073` | IBMid employs automated tools to determine if password authenticators satisfy IBMid password requirements | `1.65` | The goal was added. |
| `3000074` | IBMid protects user information during the authentication process from possible exploitation by unauthorized individuals by obscuring it  | `1.66` | The goal was added. |
| `3000075` | IBM Cloud IAM establishes initial authenticator content for authenticators that are defined by the organization (for example, API keys) | `1.67` | The goal was added. |
| `3000076` | IBM Cloud VPC uniquely identifies all physical devices before accepting a network connection | `1.74` | The goal was added. |
{: caption="Table. Summary of {{site.data.keyword.cloud_notm}} Security Best Practices profile changes for 25 July 2022" caption-side="top"}


### 27 May 2022
{: #sec-best-may2722}

Profiles are constantly expanding and are not an exhaustive list of all the controls that might be required for every organization. Users can validate the available goals and determine where a need to supplement their workloads with other security and compliance measures exists.
{: note}

Now available: {{site.data.keyword.cloud_notm}} Security Best Practices profile
:    Released today, the {{site.data.keyword.cloud_notm}} Security Best Practices profile is a collection of goals that can help an organization to ensure that they are adhering to best practices as defined by {{site.data.keyword.cloud_notm}} security.

