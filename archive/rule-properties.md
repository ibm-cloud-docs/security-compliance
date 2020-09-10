---

copyright:
  years: 2020
lastupdated: "2020-08-19"

keywords: rules, resource kind, service, access, mfa, waf, properties

subcollection: security-compliance

---

{:codeblock: .codeblock}
{:screen: .screen}
{:download: .download}
{:external: target="_blank" .external}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}
{:gif: data-image-type='gif'}
{:term: .term}
{:important: .important}
{:note: .note}
{:pre: .pre}
{:tip: .tip}
{:preview: .preview}
{:deprecated: .deprecated}
{:shortdesc: .shortdesc}
{:support: data-reuse='support'}
{:script: data-hd-video='script'}
{:table: .aria-labeledby="caption"}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:help: data-hd-content-type='help'}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tsSymptoms: .tsSymptoms}
{:beta: .beta}



# Available rule properties
{: #available-rules}

To define guardrails for the way that your accounts and resources can be used, you can choose from the following options to create configuration rules by using {{site.data.keyword.compliance_full}}.
{: shortdesc}

For help with structuring your JSON snippet, see [Working with config rules](/docs/security-compliance?topic=security-compliance-rules).
{: tip} 

## Platform
{: #platform-rules}

{{site.data.keyword.cloud}} platform services are used to manage your accounts and platform security. [Learn more](/docs/account?topic=account-overview).


| Service name         | Resource kind | Property   | Operator type  | Value     |
|---------------------|--------------|-----------|-----------|-----------|
| `billing` | `account-traits` | `MFA` | String | Indicates whether multifactor authentication is enabled for an account. Valid values include: `TOTP` and `TOTP4ALL`.  |
| `iam-groups` | `service` | `public_access_enabled` | Boolean | N/A |
{: caption="Table 1. Available platform rules configurations" caption-side="bottom"} 


## {{site.data.keyword.at_short}}
{: #at-rules}

The {{site.data.keyword.at_full_notm}} service monitors the activity of your {{site.data.keyword.cloud_notm}} account for and alerts you to abnormal activity and critical actions. [Learn more](/docs/Activity-Tracker-with-LogDNA?topic=Activity-Tracker-with-LogDNA-getting-started).


| Service name         | Resource kind | Property   | Operator type   | Value     |
|:---------------------|:--------------|:-----------|:-----------|-----------|
| `logdnaat` | `service` | `instance_count` | Numeric | The number of activity tracker instances that you want in an account. |
| `logdnaat` | `instance` | `retention_period_days` | Numeric | Indicates the number of days that an instance is configured to store data. Valid values include: `0`, `7`, `14`, and `30`. |
{: caption="Table 2. Available {{site.data.keyword.at_short}} rules configurations" caption-side="bottom"}

## {{site.data.keyword.cis_full_notm}}
{: #cis-rules}

{{site.data.keyword.cis_full_notm}} ({{site.data.keyword.cis_short_notm}}), powered with Cloudflare, offers three main capabilities to enhance your workflow: security, reliability, and performance. [Learn more](/docs/cis?topic=cis-getting-started).


| Service name         | Resource kind | Property   | Operator type   | Value     |
|:---------------------|:--------------|:-----------|:-----------|-----------|
| `internet-svcs` | `zone` | `waf_toggle` | Boolean | N/A | 
| `internet-svcs` | `zone` | `proxy_toggle` | Boolean | N/A |
| `internet-svcs` | `zone` | `domain` | String | The domain that you want to check. |
{: caption="Table 3. Available {{site.data.keyword.cis_short_notm}} rule configurations" caption-side="bottom"} 




## {{site.data.keyword.registrylong_notm}}
{: #cr-rules}

Vulnerability Advisor provides security management for {{site.data.keyword.registrylong_notm}}, by generating a security status report that includes suggested fixes and best practices. [Learn more](/docs/va?topic=va-va_index).

| Service name         | Resource kind | Property   | Operator type   | Value     |
|:---------------------|:--------------|:-----------|:-----------|-----------|
| `container-registry` | `image` | `name` | String | The name of the image. |
| `container-registry` | `image` | `issue_count` | Numeric |The number of issues found in an image. | 
| `container-registry` | `image` | `exempt_issue_count` | Numeric | The number of exempt issues. |
{: caption="Table 4. Available {{site.data.keyword.registrylong_notm}} rule configurations" caption-side="bottom"} 
