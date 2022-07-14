---

copyright:
  years: 2020, 2022
lastupdated: "2022-07-14"

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

# Change log: {{site.data.keyword.cloud_notm}} for Financial Services
{: #fs-profile-change-log}

In this change log, you can learn about the latest changes, improvements, and updates for the {{site.data.keyword.cloud_notm}} for Financial Services profile. The change log lists changes that were made, ordered by the version number.

## Profile versioning
{: #fs-profile-versioning}

When goals or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new minor version is released. To take advantage of the changes in a new version, update your scans to use the newest profile version. 

The {{site.data.keyword.cloud_notm}} for Financial Services profile is consistently updated and is not an exhaustive list of all of the controls that might be required for every organization. Users can validate the available goals and determine where a need to supplement their workloads with other security measures exists.
{: important}


### Active versions
{: #fs-active-versions}

The following table shows the service behavior changes for each version date. Switching to a later version date activates all changes that are introduced in earlier versions.

| Version number | Release date |
|:---------------|:-------------|
| Version 0.4.0 | `2022-06-23` |
| Version 0.3.0 | `2022-04-27` |
| Version 0.2.0 | `2022-04-05` |
| Version 0.1.4 | `2022-04-05` |
| Version 0.1.3 | `2022-01-27` |
| Version 0.1.2 | `2021-09-16` |
| Version 0.1.1 | `2021-06-24` |
| Version 0.1.0 | `2021-04-05` |
{: caption="Table 1. Active versions of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}


## Version 0.4.0
{: #fs-cloud-v030}

In addition to small bug fixes and general updates, version 0.4.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available has been updated with the following changes as of 23 June 2022.

| Goal ID | Associated controls | Update |
|--------|---------------------|---------|
| `3000431` |  | The goal was removed. |
| `3000404` |  | The goal was removed. |
| `3000405` |  | The goal was removed. |
| `3000051` | `CP-6(a)`, `CP-6(b)` and `SC-6AC-17(2)` | The goal was added. |
| `3000052` | `AC-14` | The goal was added. |
| `3000117` | `AU-19` | The goal was added. |
| `3000118` | `AU-2(a)`, `AU-2(d)`, `SI-4(a)`, `SI-4(b)`, `SI-4(c)`, `AC-2(4)`, `AC-2(7)(b)`, `AC-2(g)`, `AC-6(9)`, `AU-12(a)`, `AU-12(b)`, `AU-12(c)`, `AU-3`, `AU-8(a)`, `AU-8(b)`, `AU-8(1)(a)`, `AU-8(1)(b)` and `CA-7(d)` | The goal was added. |
| `3000447` | `SC-8` | The goal was added. |
| `3000461` | `AC-13` and `SC-28`| The goal was added. |
| `3000049` | `AC-11(a)` | Goal logic is updated to include all of the locations for IAM account settings that are supported by IBM Cloud. |
| `3000050` | `SC-10` | Goal logic is updated to include all of the locations for IAM account settings that are supported by IBM Cloud. |
| `3000020` | `AC-3`, `AC-6-0`, `SC-7-0`, and `SC-7(5)` | The goal text is updated. |
{: caption="Table. Summary of {{site.data.keyword.cloud_notm}} for Financial Services profile changes for 23 June 2022" caption-side="top"}



## Version 0.3.0
{: #fs-cloud-v030}

In addition to small bug fixes and general updates, version 0.3.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available has been updated with the following changes as of 27 May 2022.

| Goal ID   | Associated controls | Update |
|:----------|:--------------------|:-------|
| `3000013` |  | Goal is removed from the profile. |
| `3000014` |  | Goal is removed from the profile. |
| `3000025` |  | Goal is removed from the profile. |
| `3000039` |  | Goal is removed from the profile. |
| `3000047` | `SA-9`, `AC-20`, and `CA-3` </br></br>`SA-9(a)`, `AC-20(a)`, and `CA-3(a)`| Goal is removed from the listed associated controls. </br></br>Goal mapping is updated and it is now associated with the listed control.|
| `3000049` | `AC-11(a)` | Goal mapping is updated and it is now associated with the listed control. |
| `3000050` | `SC-10` | Goal mapping is updated and it is now associated with the listed control. |
| `3000233` | `SC-36` | Goal mapping is updated and it is now associated with the listed control. |
| `3000282` |  | Goal logic is updated. |
| `3000410` |  | Goal is removed from the profile. |
| `3000411` |  | Goal is removed from the profile. |
| `3000455` |  | Goal logic is updated. |
| `3000462` | `SA-3(a)` | Goal is removed from the listed associated control. |
| `3000470` | `AC-17(2)`, `SC-8`, `SC-8(1)`, and `SC-13` | Goal mapping is updated to be added to the listed associated controls. |
| `3000473` | `CP-7(a)`, `CP-7(1)`, `CP-10`, and `SC-6` | Goal mapping is updated to be added to the listed associated controls. |
| `3000474` | `CP-7(a)`, `CP-7(1)`, `CP-10`, and `SC-6` | Goal mapping is updated to be added to the listed associated controls. |
| `3000475` | `AC-4`, `CM-2`, `SC-7`, and `SC-7(5)` | Goal mapping is updated to be added to the listed associated controls. |
| `3000476` | `AC-4`, `CM-2`, `SC-7`, and `SC-7(5)` | Goal mapping is updated to be added to the listed associated controls. |
| `3000510` | `AC-4`, `CM-2`, `SC-7`, and `SC-7(5)` | Goal logic was updated to include all of the locations for Hyper Protect Crypto Services that are supported by IBM Cloud. |
| `3000603` |  | Goal is removed from the profile. |
| `3000711` | `AC-3` and `AC-6-0`</br></br> `AC-8` | Goal is removed from the listed associated controls. </br></br>Goal mapping is updated and it is now associated with the listed control. |
| `3000712` | `AC-3` and `AC-6-0`</br></br> `AC-8` | Goal is removed from the listed associated controls. </br></br>Goal mapping is updated and it is now associated with the listed control. |
| `3000907` | `SA-3(a)` | Goal is removed from the listed associated control. |
{: caption="Table. Summary of {{site.data.keyword.cloud_notm}} for Financial Services profile changes for 26 May 2022" caption-side="top"}


## Version 0.2.0
{: #fs-cloud-v020}

In addition to small bug fixes and general updates, version 0.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is updated with the following changes as of 4 May 2022.

| Goal ID | Associated controls | Update made |
|:----------|:-------------|:------------|
| `3000906` | `SC-8-0`, `SC-8(1)`, `SC-13`, and `SC-23` | Updated goal and fact collection logic. |
| `3000601` | `CM-8(3)(a)`, `RA-5(a)`, `SI-2(2)`, and `SI-2(a)` | Updated goal logic to consider whether the status is either unscanned or incomplete. |
| `3000601` | `CM-8(3)(a)`, `RA-5(a)`, `SI-2(2)`, and `SI-2(a)` | Updated messaging. |
| `3000407` | `SC-8-0`, `SC-8(1)`, `SC-13`, and `SC-23` | Updated goal and fact collection logic. |
| `3000462` | `CM-2`, `CM-7(a)`, `CM-8(3)(a)`, and `SA-3(a)` | Updated goal and fact collection logic. |
| `3000029`* | `AC-3`, `AC-5(b)`, `AC-6-0`, and `AC-2(i)` | Goal is removed. |
{: caption="Table 1. Summary of {{site.data.keyword.cloud_notm}} for Financial Services profile changes for 4 May 2022" caption-side="top"}

*This goal is also removed from version 0.1.4.


As of 5 April 2022, version 0.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls.

Goals that were added:

* Goal ID: `3000418` mapped to the controls `AC-4`, `CM-2`, `SC-7`, `SC-7(3)`, and `SC-7(5)`
* Goal ID: `3000047` mapped to the controls `SA-4(a)`, `SA-4(b)`, `SA-4(c)`, `SA-9`, `AC-20`, `ESA-3`, `ESA-5`, and `CA-3`
* Goal ID: `3000282` mapped to the controls `AU-4` and `AU-11`
* Goal ID: `3000283` mapped to the controls `AU-4`, `AU-11`, `SC-6`, and `SI-12`
* Goal ID: `3000322` mapped to the controls `SC-13` and `SC-28`
* Goal ID: `3000323` mapped to the controls `SC-13` and `SC-28`
* Goal ID: `3000471` mapped to the controls `AC-4`, `SC-2`, and `SC-3`
* Goal ID: `3000472` mapped to the controls `AC-4`, `SC-2`, and `SC-3`
* Goal ID: `3000915` mapped to the controls `CP-7(a)`, `CP-7(1)`, `CP-10`, and `SC-6`


## Version 0.1.4
{: #fs-cloud-v014}

As of 5 April 2022, version 0.1.4 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls.

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

* Goal ID: `3000015` removed from the control `AC-2(i)`
* Goal ID: `3000016` removed from the control `AC-2(i)`
* Goal ID: `3000035` removed from the controls `AC-2(i)` and `SC-2`
* Goal ID: `3000430` removed from the controls `SI-4(a)`, `SI-4(b)`, and `SI-4(c)`
* Goal ID: `3000707` removed from the controls `AC-2(i)` and `SC-2`
* Goal ID: `3000708` removed from the controls `AC-2(i)` and `SC-2`
* Goal ID: `3000709` removed from the controls `AC-2(i)` and `SC-2`
* Goal ID: `3000711` removed from the controls `AC-2(i)` and `SC-2`
* Goal ID: `3000712` removed from the controls `AC-2(i)` and `SC-2`

Goal mappings that were updated:

* Goal ID: `3000001` mapped to the controls `AC-2(1)`, `AC-2(f)`, AC-2(j)`, IA-2`, `IA-5(c)`, `IA-5(1)`, and `IA-5(4)`
* Goal ID: `3000002` mapped to the controls `AC-2(1)`, `AC-2(f)`, AC-2(j)`, IA-2`, `IA-5(c)`, `IA-5(1)`, and `IA-5(4)`
* Goal ID: `3000003` mapped to the controls `AC-2(1)`, `AC-2(f)`, AC-2(j)`, IA-2`, `IA-5(c)`, `IA-5(1)`, and `IA-5(4)`
* Goal ID: `3000004` mapped to the controls `AC-2(1)`, `AC-2(f)`, AC-2(j)`, IA-2`, `IA-5(c)`, `IA-5(1)`, and `IA-5(4)`
* Goal ID: `3000005` mapped to the controls `AC-2(1)`, `AC-2(f)`, AC-2(j)`, IA-2`, `IA-5(c)`, `IA-5(1)`, and `IA-5(4)`
* Goal ID: `3000006` mapped to the controls `AC-2(1)`, `AC-2(f)`, AC-2(j)`, IA-2`, `IA-5(c)`, `IA-5(1)`, and `IA-5(4)`
* Goal ID: `3000007` mapped to the controls `AC-2(1)`, `AC-2(f)`, AC-2(j)`, IA-2`, `IA-5(c)`, `IA-5(1)`, and `IA-5(4)`
* Goal ID: `3000008` mapped to the controls `AC-2(1)`, `AC-2(f)`, `AC-2(j)`, `IA-2`, `IA-5(1)`, and `IA-5(4)`
* Goal ID: `3000625` mapped to the controls `AC-4`, `CM-2`, `SC-7`, `SC-7(3)`, and `SC-7(5)`
* Goal ID: `3000601` mapped to the controls `SI-2(2)` and `SI-2(a)`
* Goal ID: `3000602` mapped to the controls `SI-2(2)` and `SI-2(a)`
* Goal ID: `3000603` mapped to the controls `SI-2(2)` and `SI-2(a)`
* Goal ID: `3000430` mapped to the controls `CA-7(a)` and `CA-7(b)`
* Goal ID: `3000022` mapped to the control `AC-14(a)`
* Goal ID: `3000716` mapped to the control `AC-7(a)`
* Goal ID: `3000717` mapped to the control `AC-7(b)`
* Goal ID: `3000712` mapped to the control `AC-14(a)`
* Goal ID: `3000015` mapped to the control `AC-2(j)`
* Goal ID: `3000016` mapped to the control `AC-2(j)`
* Goal ID: `3000035` mapped to the control `AC-2(j)`
* Goal ID: `3000446` mapped to the control `SC-7(3)`
* Goal ID: `3000707` mapped to the control `SC-7(3)`
* Goal ID: `3000708` mapped to the control `SC-7(3)`
* Goal ID: `3000709` mapped to the control `SC-7(3)`
* Goal ID: `3000711` mapped to the control `SC-7(3)`
* Goal ID: `3000712` mapped to the control `SC-7(3)`



## Version 0.1.3
{: #fs-cloud-v013}

As of 27 January 2022, version 0.1.3 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls. 

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
* Goal ID: `3000510` mapped to the controls `AC-4`, `CM-2`, `SC-7`, and `SC-7(5)`
* Goal ID: `3000526` mapped to the controls `AC-4`, `CM-2`, `SC-7`, and `SC-7(5)`
* Goal ID: `3000528` mapped to the controls `SC-13` and `SC-28`
* Goal ID: `3000529` mapped to the controls `AC-2(i)`, `AC-5(b)`, `AC-18`, and `AC-21`
* Goal ID: `3000533` mapped to the controls `AC-2(1)`, `AC-2(c)`, `AC-2(i)`, `AC-3`, `AC-5(b)`, `AC-6`, and `SC-2`
* Goal ID: `3000534` mapped to the controls `AC-4`, `CM-2,` `SC-7`, and `SC-7(5)`
* Goal ID: `3000536` mapped to the controls `SC-13` and `SC-28`
* Goal ID: `3000537` mapped to the controls `AC-2(i)`, `AC-5(b)`, `AC-18` and `AC-21`
* Goal ID: `3000538` mapped to the controls `AC-2(i)`, `AC-5(b)`, `AC-18` and `AC-21`
* Goal ID: `3000541` mapped to the controls `AC-2(1)`, `AC-2(c)`, `AC-2(i)`, `AC-3`, `AC-5(b)`, `AC-6`, and `SC-2`
* Goal ID: `3000611` mapped to the controls `CM-8(3)(a)`, `RA-5(a)`, and `SI-2(2)`
* Goal ID: `3000108` mapped to the controls `SC-13` and `SC-28`


## Version 0.1.2
{: #fs-cloud-v012}

As of 16 September 2021, version 0.1.2 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls.

* Goal ID: `3000039` mapped to the controls `AC-2(i)` and `AC-2(1)`
* Goal ID: `3000040` mapped to the control `AC-2(3)`
* Goal ID: `3000045` mapped to the control `CM-6(a)`
* Goal ID: `3000438` mapped to the controls `SC-13` and `SC-28`
* Goal ID: `3000439` mapped to the controls `SC-13` and `SC-28`
* Goal ID: `3000440` mapped to the controls `SC-13` and `SC-28`
* Goal ID: `3000901` mapped to the controls `CM-8(3)(a)`, `RA-5(a)`, `SI-2(2)`, and `SI-7(1)`
* Goal ID: `3000902` mapped to the controls `AC-4`, `CM-2`, `SC-7`, `SC-7(3)` and `SC-7(5)`
* Goal ID: `3000903` mapped to the controls `AC-4` and `SC-12`
* Goal ID: `3000906` mapped to the controls `AC-17(2)`, `SC-8`, `SC-8(1)`, `SC-13`, and `SC-23`
* Goal ID: `3000907` mapped to the controls `CM-2`, `CM-7(a)`, `CM-8(1)`, `CM-8(3)(a)`, `SA-3(a)`, and `SI-2(2)`


## Version 0.1.1
{: #fs-cloud-v011}

As of 24 June 2021, version 0.1.1 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available with new goals and controls.

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



## Version 0.1.0
{: #fs-cloud-v010}

Released today, 5 April 2021, the {{site.data.keyword.cloud_notm}} for Financial Services profile is a collection of curated goals. These goals can help organizations make a large jump on the path to meeting the NIST 800-53 security controls that are required for financial institutions. By validating your resources against the {{site.data.keyword.cloud_notm}} for Financial Services profile, you can be more confident that your {{site.data.keyword.cloud_notm}} resources are following best practices for security and compliance.

