---

copyright:
  years: 2020, 2024
lastupdated: "2024-08-13"

keywords: known limitations, rules, limits, configuration, ibm remediation, ssh key

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Limits
{: #service-limits}

{{site.data.keyword.compliance_full}} has the following known limits that might impact your experience.
{: shortdesc}

| Attachment entities | Limit |
|:--------|:-------|
| Attachments | 50 per account |
| Scans | 1 per attachment at a time |
| Exclusions | 1000 per attachment |
{: caption="Table 1. {{site.data.keyword.compliance_short}} Limits" caption-side="top"}
{: #attachment-limits}
{: tab-title="Attachments"}
{: tab-group="limits"}
{: class="simple-tab-table"}



| Profile entities | Limit |
|:--------|:-------|
| Custom profiles | 50 per account |
| Size | Less than 1 MB |
| Version | 128 characters |
| Controls | 1200 per profile |
| Specifications | 100 per control |
| Assessments | 10 per specification |
{: caption="Table 1. {{site.data.keyword.compliance_short}} Limits" caption-side="top"}
{: #profile-limits}
{: tab-title="Profiles"}
{: tab-group="limits"}
{: class="simple-tab-table"}

| Control library entities | Limit |
|:--------|:-------|
| Custom libraries | 50 per account |
| Size | Less than 1 MB |
| Version | 128 characters |
| Library name | 128 characters |
| Library description | 512 characters |
| Controls | 1200 per library |
| Control name | 64 characters |
| Control description | 1024 characters |
| Specifications | 100 per control |
| Specification description | 1024 characters |
| Assessments | 10 per specification |
{: caption="Table 1. {{site.data.keyword.compliance_short}} Limits" caption-side="top"}
{: #library-limits}
{: tab-title="Control Libraries"}
{: tab-group="limits"}
{: class="simple-tab-table"}

| Rule entities | Limit |
|:--------|:---------|
| Custom rules | 500 per enterprise account  \n 100 per account |
| Size | 4096 characters |
| Description | 512 characters |
| Targets | 1 per rule |
| Conditions | 16 per rule |
| Properties | 24 per condition |
| Labels | 32 per rule |
{: caption="Table 1. {{site.data.keyword.compliance_short}} Limits" caption-side="top"}
{: #rule-limits}
{: tab-title="Rules"}
{: tab-group="limits"}
{: class="simple-tab-table"}





