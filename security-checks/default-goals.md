---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-10"

keywords: goals, secure by default, secure, secure platform, default goals, available goals

subcollection: security-compliance

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

# Available default goals
{: #default-goals}

{{site.data.keyword.cloud_notm}} is secure-by-design. Just by working with {{site.data.keyword.cloud_notm}} platform, you are compliant with several goals. Because they are always compliant, default goals are not validated as part of a scan. To learn more about goals in general and how they are used in the {{site.data.keyword.compliance_short}}, see [Understanding profiles](/docs/security-compliance?topic=security-compliance-profiles#understand-profiles). 
{: shortdesc}

To see which goals are met by default, check out the following table.

| Goal ID | Goal |
|:--------|:-----|
| 3000001 | Check whether IBMid password policy requires at least one uppercase letter |
| 3000002 | Check whether IBMid password policy requires at least one lowercase letter |
| 3000003 | Check whether IBMid password policy requires at least one number |
| 3000004 | Check whether IBMid password policy requires minimum length of 12 characters |
| 3000005 | Check whether IBMid password policy prevents password reuse before a minimum of # |
| 3000006 | Check whether IBMid password may contain only printable ASCII characters (in the range 33 - 126) |
| 3000007 | Check whether IBMid password policy contains spaces or any of the following characters: \;:(""?)<> |
| 3000008 | Check whether IBMid uses a password meter that coaches users to create strong passwords that exceed the minimum requirements |
| 3000009 | Check whether IAM roles are used to create IAM policies for IBM resources |
| 3000010 | Check whether a support role has been assigned in IAM to manage cases in the IBM Cloud Support Center |
| 3000011 | Check whether API keys are not created in IAM during the initial setup of IAM users |
| 3000101 | Check whether Cloud Object Storage is enabled with encryption |
| 3000203 | Check whether Databases for MongoDB is accessible only through HTTPS |
| 3000208 | Check whether Databases for Redis is accessible only through HTTPS |
| 3000213 | Check whether Databases for ElasticSearch is accessible only through HTTPS |
| 3000218 | Check whether Databases for etcd is accessible only through HTTPS |
| 3000223 | Check whether Databases for PostgreSQL is accessible only through HTTPS |
| 3000231 | Check whether Key Protect has high availability |
| 3000302 | Check whether IBM Activity Tracker trails are integrated with LogDNA logs |
| 3000303 | Check whether IBM Activity Tracker logs are encrypted at rest |
| 3000706 | Check whether App ID user data is encrypted |
{: caption="Table 1. Default goals met by working with {{site.data.keyword.cloud_notm}}" caption-side="bottom"}
