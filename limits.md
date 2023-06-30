---

copyright:
  years: 2020, 2023
lastupdated: "2023-06-30"

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
| Custom rules | 500 per enterprise account</br>100 per stand-alone account |
| Rule description | 256 characters |
| Rule size | 4096 characters |
| Target | 1 per rule |
| Condition | 16 per rule |
| Property | 24 per condition |
| Label | 32 per rule |
| Custom libraries | 10 per enterprise account  \n 5 per stand-alone account |
| Library name | 64 Characters |
| Library description | 256 characters |
| Library size | Less than 1 MB |
| Profile name | 64 characters |
| Profile description | 256 Characters |
| Profile size | Less than 1 MB |
| Custom profiles | 20 per enterprise account  \n 5 per stand-alone account |
| Control | 1200 per library  \n 600 per profile |
| Control name | 64 characters |
| Control description | 256 characters |
| Specification | 100 per control per library  \n 400 per control per profile |
| Specification description | 256 characters |
| Assessment | 10 per specification per library or profile |
| Attachment | 50 per account |
| Exclusion | 8 per attachment |
| Scan | 1 per attachment - at any time |
{: row-headers}
{: caption="Table 1. {{site.data.keyword.compliance_short}} limits" caption-side="top"}

