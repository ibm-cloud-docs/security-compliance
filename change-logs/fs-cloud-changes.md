---

copyright:
  years: 2020, 2023
lastupdated: "2023-04-14"

keywords: release notes for {{site.data.keyword.compliance_short}}, what's new, enhancements, fixes, improvements

subcollection: security-compliance
content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}

# Change log: {{site.data.keyword.cloud_notm}} for Financial Services
{: #fs-change-log}

In this change log, you can learn about the latest changes, improvements, and updates for the {{site.data.keyword.cloud_notm}} for Financial Services profile. The change log lists changes that were made, ordered by the version number.

## Profile versioning
{: #fs-profile-versioning}

When goals or controls are edited, removed from, or added to a profile in a way that is not compatible with the current version, a new minor version is released. To take advantage of the changes in a new version, update your scans to use the newest profile version. 

The {{site.data.keyword.cloud_notm}} for Financial Services profile is consistently updated and is not an exhaustive list of all the controls that might be required for every organization. Users can validate the available goals and determine where a need to supplement their workloads with other security measures exists.
{: important}


### Active versions
{: #fs-active-versions}

The following table shows the service behavior changes for each version date. Switching to a later version date activates all changes that are introduced in earlier versions.

| Version number | Release date |
|:---------------|:-------------|
| Version 1.1.0 | `2023-03-02` |
| Version 1.0.0 | `2022-14-21` |
| Version 0.6.0 | `2022-09-21` |
| Version 0.5.0 | `2022-08-11` |
| Version 0.4.0 | `2022-06-23` |
| Version 0.3.0 | `2022-04-27` |
| Version 0.2.0 | `2022-04-05` |
| Version 0.1.4 | `2022-04-05` |
| Version 0.1.3 | `2022-01-27` |
| Version 0.1.2 | `2021-09-16` |
| Version 0.1.1 | `2021-06-24` |
| Version 0.1.0 | `2021-04-05` |
{: caption="Table. Active versions of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}




## Version 1.1.0
{: #fs-cloud-v110}

Version 1.1.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile has been updated to include all 565 controls that have been identified as required to ensure that you are compliant with the {{site.data.keyword.cloud_notm}} for Financial Services reference architecture. As part of that update we've introduced the concept of "Manual assessments". When results are returned, you will see a new status: `user_evaluation_required` - this indicates that the control must be evaluated manually by your organization as the control check is either not yet or cannot be automated.

Additionally, the phrasing of 42 controls was updated for grammar purposes. For example, controls that use the Activity Tracker Event Tracking service were updated to include the correct capitalization.




## Version 1.0.0
{: #fs-cloud-v100}

The format of the {{site.data.keyword.cloud_notm}} for Financial Services profile has been updated with the following changes. Review your configuration closely to ensure that the profile still meets your needs.
- The profile is available only on the **Profiles** page of the **Manage** section of the updated infrastructure.
- The format changed from being goal-based to assessment-based.

Starting with version 1.0.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile, all new versions of the profile that become available will be compatible only with the updated service architecture. To upgrade your profile version, you must move to the new evaluation format. For more information, see [Getting started](/docs/security-compliance?topic=security-compliance-getting-started).
{: important}


## Version 0.6.0
{: #fs-cloud-v060}

Version 0.6.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available has been updated with the following changes as of 21 September 2022.

| Goal ID   | Associated controls | Update |
|:----------|:--------------------|:-------|
| `3000023` | `AC-2(d)`, `AC-3`, `AC-5(c)`, and `AC-6-0` | The goal is removed. |
| `3000024` | `IA-5(g)` | The goal was removed. |
| `3000041`[^g-1] | `AU-14`, `AC-17`, and `IA-2(1)` | The goal was added and the goal logic was changed. Previously the goal evaluated whether Cloud Shell was disabled in your account, now the logic evaluates whether it is enabled. |
| `3000045` | `AC-20(a)` and `CA-3(a)`  \n  \n `AC-20` and `CA-3` | The goal was added.  \n  \n The goal was removed. |
| `3000078` | `SC-13`, `SC-28`, and `SC-28(1)` | The goal was added. |
| `3000324` | `SI-2(a)` and `SI-5(a)` | The goal was added. |
| `3000478` | `AC-4`, `CM-2`, `SC-7`, and `SC-7(5)` | The goal was added. |
| `3000479` | `CP-7(a)`, `CP-7(1)`, `CP-8`, and `CP-8(2)` | The goal was added. |
{: caption="Table. Summary of the changes for version 0.6.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}

[^g-1]: This goal is also changed in all previous profile versions as of the 21 September 2022.



## Version 0.5.0
{: #fs-cloud-v050}

Version 0.5.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available and has been updated with the following changes as of 11 August 2022.

Control SC-28 is renamed to SC-28-0 and control SC-12 is renamed to SC-12-0.
{: note}

| Goal ID | Associated controls | Update |
|--------|---------------------|---------|
| `3000001` | `IA-5(1)(a)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(j)`, `IA-2-0`, `IA-5(1)`, and `IA-5(c)` | The goal was added.  \n  \n The goal was removed. |
| `3000002` | `IA-5(1)(a)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(j)`, `IA-2-0`, `IA-5(1)`, `IA-5(4)`, and `IA-5(c)` | The goal was added.  \n  \n The goal was removed. |
| `3000003` | `IA-5(1)(a)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(j)`, `IA-2-0`, `IA-5(1)`, `IA-5(4)`, and `IA-5(c)` | The goal was added.  \n  \n The goal was removed. |
| `3000004` | `IA-5(1)(a)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(j)`, `IA-2-0`, `IA-5(1)`, `IA-5(4)`, and `IA-5(c)` | The goal was added.  \n  \n The goal was removed. |
| `3000005` | `IA-5(1)(e)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(j)`, `IA-2-0`, `IA-5(1)`, `IA-5(4)`, and `IA-5(c)` | The goal was added.  \n  \n The goal was removed. |
| `3000006` | `IA-5(1)(a)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(j)`, `IA-2-0`, `IA-5(1)`, and `IA-5(c)` | The goal was added.  \n  \n The goal was removed. |
| `3000007` | `IA-5(1)(a)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(j)`, `IA-2-0`, `IA-5(1)`, and `IA-5(c)` | The goal was added.  \n  \n The goal was removed. |
| `3000008` | `IA-5(1)(a)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(j)`, `IA-2-0`, and `IA-5(1)` | The goal was added.  \n  \n The goal was removed. |
| `3000009` | `AC-2(d)`, `AC-3`, `AC-5(c)`, `AC-6-0`, and `IA-7`  \n  \n `AC-2(c)` and `AC-2(i)` | The goal was added.  \n  \n The goal was removed. |
| `3000010` | `AC-2(7)`, `AC-2(c)`, and `AC-2(i)` | The goal was removed. |
| `3000015` | `AC-2(d)`, `AC-5(c)`, and `IA-7`  \n  \n `AC-2(d)`, `AC-2(c)`, `AC-2(j)`, and `AC-5(b)` | The goal was added.  \n  \n The goal was removed. |
| `3000016` | `AC-2(d)`, `AC-5(c)`, and `IA-7`  \n  \n `AC-2(d)`, `AC-2(c)`, `AC-2(j)`, and `AC-5(b)` | The goal was added.  \n  \n The goal was removed. |
| `3000017` | `IA-7`  \n  \n `AC-2(i)`, and `IA-2(11)` | The goal was added.  \n  \n The goal was removed. |
| `3000020` | `IA-3`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `AC-3`, `AC-6-0`, and `SC-7-0` | The goal was added.  \n  \n  The goal was removed. |
| `3000022` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000023` | `AC-2(d)` and `AC-5(c)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(i)`, and `AC-6(10)` | The goal was added.  \n  \n The goal was removed. |
| `3000024` | `IA-5(g)`  \n  \n `AC-2(1)` and `AC-2(i)` | The goal was added.  \n  \n The goal was removed. |
| `3000026` | `AC-3`  \n  \n `AC-2(1)` | The goal was added.  \n  \n The goal was removed. |
| `3000027` | `AC-2(d)` and `AC-5(c)`  \n  \n `AC-2(f)`, `AC-2(i)`, `AC-6(10)`, and `SC-12` | The goal was added.  \n  \n The goal was removed. |
| `3000028` | `AC-3`| The goal was added. |
| `3000035` | `AC-5(c)`  \n  \n `AC-2(1)`, `AC-2(c)`, `AC-2(j)`, `AC-5(b)` | The goal was added.  \n  \n The goal was removed. |
| `3000045` | `AC-20-0`, `CA-3-0`, `ESA-3`, `ESA-5`, `SA-4(a)`, and `SA-9(a)`  \n  \n `CM-6(a)` | The goal was added.  \n  \n The goal was removed. |
| `3000047` | `SA-4(d)`, `SA-4(e)`, `SA-4(f)`, and `SA-4(g)` | The goal was added. |
| `3000051` | `CP-6(1)`, `CP-7(a)`, `CP-7(b)`, `CP-7(c)`, `CP-7(1)`, `CP-9(b)`, `CP-9(d)`, and `CP-10` | The goal was added. |
| `3000053` | `AC-7(a)` | The goal was added. |
| `3000054` | `AC-7(b)` | The goal was added. |
| `3000055` | `AC-11(1)` | The goal was added. |
| `3000056` | `AC-11(b)` | The goal was added. |
| `3000057` | `AC-16(a)` | The goal was added. |
| `3000058` | `AC-17(9)` | The goal was added. |
| `3000059` | `AC-2(a)` | The goal was added. |
| `3000060` | `IA-2-0` | The goal was added. |
| `3000061` | `IA-2-0` | The goal was added. |
| `3000062` | `IA-4(b)` and `IA-4(c)` | The goal was added. |
| `3000063` | `IA-4(b)` and `IA-4(c)` | The goal was added. |
| `3000064` | `IA-4(d)` | The goal was added. |
| `3000065` | `IA-5(c)` | The goal was added. |
| `3000066` | `IA-5(c)` | The goal was added. |
| `3000067` | `IA-5(f)` | The goal was added. |
| `3000068` | `IA-5(f)` | The goal was added. |
| `3000070` | `IA-5(1)(c)` | The goal was added. |
| `3000071` | `IA-5(1)(d)` | The goal was added. |
| `3000073` | `IA-5(4)` | The goal was added. |
| `3000074` | `IA-6` | The goal was added. |
| `3000075` | `IA-5(b)` | The goal was added. |
| `3000076` | `IA-3` | The goal was added. |
| `3000103` | `CM-7(a)`, `CM-7(b)`, `SC-7(4)(c)`, and `SC-11` | The goal was added. |
| `3000105` | `CM-7(a), CM-7(b), SC-7(a), SC-7(b), and SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000106` | `AC-5(c)`  \n  \n `AC-2(i)` and `AC-5(b)` | The goal was added.  \n  \n The goal was removed. |
| `3000107` | `SC-7(a), SC-7(b), and SC-7(4)(a)`  \n  \n `CM-2, and SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000108` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal is removed. |
| `3000116` | `CP-6(a)`, `CP-6(b)`, and `CP-10`  \n  \n `CP-6-0` | The goal was added.  \n  \n The goal was removed. |
| `3000117` | `CP-6(a)`, `CP-6(b)`, `CP-6(1)`, `CP-7(a)`, `CP-7(b)`, `CP-7(c)`, `CP-7(1)`, `CP-9(b)`, `CP-9(d)`, `CP-10`, and `SC-6` | The goal was added. |
| `3000233` | `CP-7(a)`, `CP-7(b)`, `CP-7(c)`, `CP-7(1)`, `CP-10`, and `SC-6`  \n  \n `SC-36` | The goal was added.  \n  \n The goal was removed. |
| `3000234` | `IA-7`, `SC-12-0`, `SC-12(2)`, and `SC-12(3)`  \n  \n `SC-12` | The goal was added.  \n  \n The goal is removed. |
| `3000235` | `IA-5(g)`, `SC-12-0`, `SC-12(2)`, and `SC-12(3)`  \n  \n `AC-2(1)` and `SC-12` | The goal was added.  \n  \n The goal is removed. |
| `3000283` | `SI-12`  \n  \n `AU-11` | The goal was added.  \n  \n The goal was removed. |
| `3000306` | `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000307` | `SC-7(a), SC-7(b), and SC-7(4)(a)`  \n  \n `CM-2 and SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000322` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000323` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000406` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(c)`, `SC-7(4)(a)`, and `SC-7(10)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000407` | `CM-7(a)`, `CM-7(b)`, `IA-5(1)(c)`, `SC-7(4)(c)`, and `SC-11` | The goal was added. |
| `3000408` | `SC-7(a)`  \n  \n `AU-2(a)`, `AU-2(d)`, and `AU-12` | The goal was added.  \n  \n The goal was removed. |
| `3000412` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(c)`, `SC-7(4)(a)`, and `SC-7(10)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000413` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(c)`, `SC-7(4)(a)`, and `SC-7(10)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000418` | `SC-7(a)`, `SC-7(b)`, `SC-7(c)`, `SC-7(4)(a)`, `SC-7(10)` and `SC-11`  \n  \n `CM-2`, `SC-7-0`, and `SC-7(3)` | The goal was added.  \n  \n The goal was removed. |
| `3000425` | `AC-2(1)`, `AC-2(f)`, `AC-2(i)`, `IA-2-0`, and `IA-5(1)` | The goal was removed. |
| `3000427` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000428` | `CP-10` and `SC-6`  \n  \n `AC-4`, `CM-2`, `SC-7-0`, and `SC-7(5)` | The goal was added.  \n  \n The goal was removed. |
| `3000429` | `CP-10` and `SC-6`  \n  \n `AC-4`, `CM-2`, `SC-7-0`, and `SC-7(5)` | The goal was added.  \n  \n The goal was removed. |
| `3000430` | `CP-10` and `SC-6`  \n  \n `CA-7(a)` and `CA-7(b)` | The goal was added.  \n  \n The goal was removed. |
| `3000432` | `CM-7(a), CM-7(b), IA-5(1)(c), SC-7(4)(c), and SC-11` | The goal was added. |
| `3000433` | `CM-7(a), CM-7(b), IA-5(1)(c), SC-7(4)(c), and SC-11` | The goal was added. |
| `3000434` | `CM-7(a), CM-7(b), IA-5(1)(c), SC-7(4)(c), and SC-11` | The goal was added. |
| `3000437` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000438` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000439` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000440` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000441` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2`, `SC-7-0`, and `SC-7(5)` | The goal was added.  \n  \n The goal was removed. |
| `3000442` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2`, and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000444` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(4)(a)` and `SC-7(10)`  \n  \n `CM-2`, and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000445` | `AC-4`, `CM-2`, `SC-7-0`, and `SC-7(5)` | The goal was removed. |
| `3000446` | `AC-4`, `CM-2`, `SC-7-0`, `SC-7(5)`, and `SC-7(3)` | The goal was removed. |
| `3000447` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(c)`, `SC-7(4)(a)`, and `SC-7(10)`  \n  \n `CM-2`, `SC-7-0`, and `SC-8-0` | The goal was added.  \n  \n The goal was removed. |
| `3000463` | `IA-4(b)` and `IA-4(c)`  \n  \n `IA-4` | The goal was added.  \n  \n The goal was removed. |
| `3000464` | `IA-4(b)` and `IA-4(c)`  \n  \n `IA-4` | The goal was added.  \n  \n The goal was removed. |
| `3000465` | `IA-4(b)` and `IA-4(c)`  \n  \n `IA-4` | The goal was added.  \n  \n The goal was removed. |
| `3000448` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(c)`, `SC-7(4)(a)`, and `SC-7(10)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000449` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(c)`, `SC-7(4)(a)`, and `SC-7(10)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000451` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000452` | `CM-7(a), CM-7(b), SC-7(a), SC-7(c), SC-7(4)(a), and SC-7(10)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000453` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, `SC-7(c)`, and `SC-7(10)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000454` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000455` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000456` | `AC-4`, `CM-2`, `SC-7-0`, and `SC-7(5)` | The goal was removed. |
| `3000458` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000460` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000461` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000462` | `CM-2` and `CM-7(a)` | The goal was removed. |
| `3000463` | `IA-4` | The goal was removed. |
| `3000464` | `IA-4` | The goal was removed. |
| `3000465` | `IA-4` | The goal was removed. |
| `3000466` | `CP-10` and `SC-6`  \n  \n `CA-7(a)`, `CA-7(b)`, `SI-4(a)`, `SI-4(b)`, and `SI-4(c)` | The goal was added.  \n  \n The goal was removed. |
| `3000467` | `SC-7(a)`, `SC-7(c)`, `SC-7(4)(a)`, and `SC-7(10),`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000468` | `SC-7(a)`, `SC-7(c)`, `SC-7(4)(a)`, and `SC-7(10),`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000469` | `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000470` | `CM-7(a)`, `CM-7(b)`, `SC-7(4)(c)`, and `SC-11` | The goal was added. |
| `3000473` | `CP-7(b)` and `CP-7(c)` | The goal was added. |
| `3000474` | `CP-7(b)` and `CP-7(c)` | The goal was added. |
| `3000475` | `CM-7(a)`, `SC-7(a)`, `SC-7(c)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000476` | `CM-7(a)`, `SC-7(a)`, `SC-7(c)`, `SC-7(4)(a)`, and `SC-7(10)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000510` | `IA-7`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000526` | `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000528` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000534` | `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000536` | `SC-28-0` and `SC-28(1)`  \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000538` |    \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000601` | `CA-2(2)`, `CA-7(d)`, `RA-5(1)`, `RA-5(2)`, `SA-10(1)`, and `SI-3(a)` | The goal was added. |
| `3000611` | `CA-2(2)`, `CA-7(d)`, `RA-5(1)`, `RA-5(2)`, `SA-3(a)`, `SA-3(d)`, `SA-10(1)`, `SI-2(2)`, and `SI-3(a)` | The goal was added. |
| `3000625` | `SA-3(a)`, `SA-3(d)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000701` | `CM-7(a)`, `CM-7(b)`, `IA-5(1)(c)`, `SC-7(4)(c)`, and `SC-11` | The goal was added. |
| `3000702` | `CM-7(a)`, `CM-7(b)`, `IA-5(1)(c)`, `SC-7(4)(c)`, and `SC-11` | The goal was added. |
| `3000703` | `CM-7(a)`, `CM-7(b)`, `IA-5(1)(c)`, `SC-7(4)(c)`, and `SC-11` | The goal was added. |
| `3000704` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000705` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000706` |    \n  \n `SC-28` | The goal was added.  \n  \n The goal was removed. |
| `3000707` | `AC-5(c)`, `CM-7(a)`, and `CM-7(b)`  \n  \n `AC-2(1)`, `AC-2(c)`, `AC-2(j)`, `AC-3`, `AC-5(b)`, and `AC-6-0` | The goal was added.  \n  \n The goal was removed. |
| `3000708` | `AC-5(c)`, `CM-7(a)`, and `CM-7(b)`  \n  \n `AC-2(1)`, `AC-2(c)`, `AC-2(j)`, `AC-3`, and `AC-5(b)` | The goal was added.  \n  \n The goal was removed. |
| `3000709` | `AC-5(c)`, `CM-7(a)`, and `CM-7(b)`  \n  \n `AC-2(1)`, `AC-2(c)`, `AC-2(j)`, `AC-3`, `AC-5(b)`, and `AC-6-0` | The goal was added.  \n  \n The goal was removed. |
| `3000711` | `CM-7(a)`  \n  \n `AC-2(1)`, `AC-2(c)`, `AC-2(j)`, `AC-5(b)`, and `AC-8` | The goal was added.  \n  \n The goal was removed. |
| `3000712` | `CM-7(a)` and `CM-7(b)`  \n  \n `AC-2(1)`, `AC-2(c)`, `AC-2(j)`, `AC-5(b)`, and `AC-8` | The goal was added.  \n  \n The goal was removed. |
| `3000713` | `IA-5(1)(a)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(i)`, `IA-2-0`, and `IA-5(1)` | The goal was added.  \n  \n The goal was removed. |
| `3000714` | `IA-5(1)(a)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(i)`, `IA-2-0`, and `IA-5(1)` | The goal was added.  \n  \n The goal was removed. |
| `3000715` | `CM-7(a)`, `CM-7(b)`, and `IA-5(1)(e)`  \n  \n `AC-2(1)`, `AC-2(f)`, `AC-2(i)`, `IA-2-0`, `IA-5(1)`, `IA-5(4)`, and `IA-5(c)` | The goal was added.  \n  \n The goal was removed. |
| `3000716` | `AC-2(1)`, `AC-2(f)`, `AC-2(i)`, `IA-2-0`, `IA-5(1)`, `IA-5(4)`, and `IA-5(c)` | The goal was removed. |
| `3000717` | `AC-2(1)`, `AC-2(f)`, `AC-2(i)`, `IA-2-0`, `IA-5(1)`, `IA-5(4)`, and `IA-5(c)` | The goal was removed. |
| `3000718` | `AC-2(1)`, `AC-2(f)`, `AC-2(i)`, `IA-2-0`, `IA-5(1)`, `IA-5(4)`, and `IA-5(c)` | The goal was removed. |
| `3000719` | `AC-2(1)`, `AC-2(f)`, `AC-2(i)`, `IA-2-0`, `IA-5(1)`, `IA-5(4)`, and `IA-5(c)` | The goal was removed. |
| `3000720` | `AC-2(1)`, `AC-2(f)`, `AC-2(i)`, `IA-2-0`, `IA-5(1)`, `IA-5(4)`, and `IA-5(c)` | The goal was removed. |
| `3000721` | `CM-6(a)` | The goal was added. |
| `3000722` | `CM-6(a)` | The goal was added. |
| `3000723` | `AC-2(i)` and `IA-2(11)` | The goal was removed. |
| `3000724` | `SC-10`  \n  \n `AC-2(f)`, `AC-2(i)`, `AC-3`, `AC-6-0`, and `AC-6(10)` | The goal was added.  \n  \n The goal was removed. |
| `3000901` | `RA-5(a)` | The goal was removed. |
| `3000902` | `CM-7(a)`, `CM-7(b)`, `SC-7(a)`, `SC-7(b)`, and `SC-7(4)(a)`  \n  \n `CM-2` and `SC-7-0` | The goal was added.  \n  \n The goal was removed. |
| `3000903` | `IA-2-0` and `IA-5(c)`  \n  \n `AC-4` and `SC-12` | The goal was added.  \n  \n The goal was removed. |
| `3000906` | `CM-7(a)`, `CM-7(b)`, `SC-7(4)(c)`, and `SC-11` | The goal was added. |
| `3000915` | `CP-7(a)`, `CP-7(b)`, and `CP-7(c)`  \n  \n `CA-7(a)` | The goal was added.  \n  \n The goal was removed. |
{: caption="Table. Summary of the changes for version 0.5.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}


## Version 0.4.0
{: #fs-cloud-v040}

In addition to small bug fixes and general updates, version 0.4.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is now available and has been updated with the following changes as of 23 June 2022.

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
| `3000049` | `AC-11(a)` | Goal logic is updated to include all the locations for IAM account settings that are supported by IBM Cloud. |
| `3000050` | `SC-10` | Goal logic is updated to include all the locations for IAM account settings that are supported by IBM Cloud. |
| `3000020` | `AC-3`, `AC-6-0`, `SC-7-0`, and `SC-7(5)` | The goal text is updated. |
{: caption="Table. Summary of the changes for version 0.4.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}



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
| `3000510` | `AC-4`, `CM-2`, `SC-7`, and `SC-7(5)` | Goal logic was updated to include all the locations for Hyper Protect Crypto Services that are supported by IBM Cloud. |
| `3000603` |  | Goal is removed from the profile. |
| `3000711` | `AC-3` and `AC-6-0`</br></br> `AC-8` | Goal is removed from the listed associated controls. </br></br>Goal mapping is updated and it is now associated with the listed control. |
| `3000712` | `AC-3` and `AC-6-0`</br></br> `AC-8` | Goal is removed from the listed associated controls. </br></br>Goal mapping is updated and it is now associated with the listed control. |
| `3000907` | `SA-3(a)` | Goal is removed from the listed associated control. |
{: caption="Table. Summary of the changes for version 0.3.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}


## Version 0.2.0
{: #fs-cloud-v020}

Version 0.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile is updated with the following changes as of 4 May 2022.

| Goal ID | Associated controls | Update made |
|:----------|:-------------|:------------|
| `3000906` | `SC-8-0`, `SC-8(1)`, `SC-13`, and `SC-23` | Updated goal and fact collection logic. |
| `3000601` | `CM-8(3)(a)`, `RA-5(a)`, `SI-2(2)`, and `SI-2(a)` | Updated goal logic to consider whether the status is either unscanned or incomplete. |
| `3000601` | `CM-8(3)(a)`, `RA-5(a)`, `SI-2(2)`, and `SI-2(a)` | Updated messaging. |
| `3000407` | `SC-8-0`, `SC-8(1)`, `SC-13`, and `SC-23` | Updated goal and fact collection logic. |
| `3000462` | `CM-2`, `CM-7(a)`, `CM-8(3)(a)`, and `SA-3(a)` | Updated goal and fact collection logic. |
| `3000029` | `AC-3`, `AC-5(b)`, `AC-6-0`, and `AC-2(i)` | Goal is removed. |
| `3000418` | `AC-4`, `CM-2`, `SC-7`, `SC-7(3)`, and `SC-7(5)` | Goal is added. |
| `3000047` | `SA-4(a)`, `SA-4(b)`, `SA-4(c)`, `SA-9`, `AC-20`, `ESA-3`, `ESA-5`, and `CA-3` | Goal is added. |
| `3000282` | `AU-4` and `AU-11` | Goal is added. |
| `3000283` | `AU-4`, `AU-11`, `SC-6`, and `SI-12` | Goal is added. |
| `3000322` | `SC-13` and `SC-28` | Goal is added. |
| `3000323` | `SC-13` and `SC-28` | Goal is added. |
| `3000471` | `AC-4`, `SC-2`, and `SC-3` | Goal is added. |
| `3000472` | `AC-4`, `SC-2`, and `SC-3` | Goal is added. |
| `3000915` | `CP-7(a)`, `CP-7(1)`, `CP-10`, and `SC-6` | Goal is added. |
{: caption="Summary of the changes for version 0.2.0 of the {{site.data.keyword.cloud_notm}} for Financial Services profile" caption-side="top"}

*This goal is also removed from version 0.1.4.


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

