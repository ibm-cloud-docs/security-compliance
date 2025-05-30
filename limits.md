---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: known limitations, rules, limits, configuration, ibm remediation, ssh key

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Limits
{: #service-limits}


As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}

{{site.data.keyword.compliance_full}} has the following known limits that might impact your experience.
{: shortdesc}

| Attachment entities | Limit |
|:--------|:-------|
| Attachments | 50 per account |
| Scans | 1 per attachment at a time |
| Exclusions | 1000 per attachment |
{: caption="{{site.data.keyword.compliance_short}} Limits" caption-side="top"}
{: #attachment-limits}
{: tab-title="Attachments"}
{: tab-group="limits"}
{: class="simple-tab-table"}

| Scope entities | Limit |
|:--------|:-------|
| Scopes | 1000 per instance  /n 300 per attachment |
| Subscopes | 300 per scope |
{: caption="{{site.data.keyword.compliance_short}} Limits" caption-side="top"}
{: #scope-limits}
{: tab-title="Scopes"}
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
{: caption="{{site.data.keyword.compliance_short}} Limits" caption-side="top"}
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
{: caption="{{site.data.keyword.compliance_short}} Limits" caption-side="top"}
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
{: caption="{{site.data.keyword.compliance_short}} Limits" caption-side="top"}
{: #rule-limits}
{: tab-title="Rules"}
{: tab-group="limits"}
{: class="simple-tab-table"}
