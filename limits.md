---

copyright:
  years: 2020, 2023
lastupdated: "2023-03-31"

keywords: known limitations, rules, limits, configuration, ibm remediation, ssh key

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Limits
{: #service-limits}

{{site.data.keyword.compliance_full}} has the following known limits that might impact your experience.
{: shortdesc}


|  | Limit |
|----------------|-----------|
| Number of custom rules | 500 per enterprise account</br>100 per stand-alone account |
| Rule description | 256 characters |
| Targets | 1 per rule |
| Conditions | 16 per rule |
| Properties | 24 per condition |
| Labels | 32 per rule |
| Rule size | 4096 characters |
| Number of custom libraries | 10 per enterprise account</br>5 per stand-alone account |
| Library name | 64 Characters |
| Library description | 256 characters |
| Controls | 1200 per library |
| Specifications | 100 per control per library |
| Assessments | 10 per specification per library |
| Control name | 64 characters |
| Control description | 256 characters |
| Specification description | 256 characters |
| Library size | Less than 1 MB |
| Profile name | 64 characters |
| Profile description | 256 Characters |
| Custom profiles | 20 per enterprise account</br>5 per stand-alone account |
| Controls | 600 per profile |
| Specifications | 400 per control per profile |
| Assessments | 10 per specification per profile |
| Attachments | 50 per account |
| Exclusions | 8 per attachment |
| Scans | 1 per attachment - at any time |
| Profile size | Less than 1 MB |
| Number of managed collectors | 1 per account |
| Number of scannable resources | 900 resources per managed-collector |
| Scannable environments | If you're working with an environment that is not {{site.data.keyword.cloud_notm}}, you must use a customer-managed collector. |
{: row-headers}
{: caption="Table 1. {{site.data.keyword.compliance_short}} limits" caption-side="top"}

