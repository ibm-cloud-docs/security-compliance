---

copyright:
  years: 2020
lastupdated: "2020-06-18"

keywords: controls, nist, audit log, internal audit, compliance rules, compliance

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


# Available controls
{: #available-controls}

When you create [profiles](/docs/security-compliance?topic=security-compliance-profiles), you can choose from the following [NIST 800-53 controls](https://nvd.nist.gov/800-53/Rev4/){: external} and IBM implementations to secure your accounts.
{: shortdesc}


## App and container security
{: #app-container}

With risk assessment controls in place, you can ensure that you are monitoring for any potential security issues in your applications and images. When an issue is detected, you can fix the issue immediately. Then, when you prove compliance, you can show that the vulnerability was detected but fixed within the allotted time.

| Control       | Implementation   | Description  | 
|:--------------|:-----------------|:-------------|
| `RA-5` Vulnerability scanning | Configuration rule | Vulnerability Advisor is used to validate the images that exist within your {{site.data.keyword.registrylong_notm}} are passing your vulnerability scans. | 
{: caption="Table 1. Available app and container security controls" caption-side="bottom"}


## Audit logging and monitoring
{: #au}

With audit logging and monitoring controls in place, you can ensure that there is sufficient evidence for key system interactions and that the evidence is available for a specific amount of time.

| Control       | Implementation   | Description  | 
|:--------------|:-----------------|:-------------|
| `AU-2` Audit Events | Built-in | An audit system supports the coordination of a security audit with other organizational entities. | 
| `AU-3` Content of Audit Records | Built-in | {{site.data.keyword.at_short}} provides the who, what, where, and when of each action that is taken within your accounts. |
| `AU-7` Audit reduction and Report Generation | Configuration rule | {{site.data.keyword.at_short}} supports processing of audit records for events of interest. With this control enabled, you must have an instance of {{site.data.keyword.at_short}} that is configured to process your audit records to be considered compliant. | 
| `AU-7(1)` Automatic processing | Configuration rule | {{site.data.keyword.at_short}} supports processing of audit records for events of interest. With this control enabled, you must have an instance of {{site.data.keyword.at_short}} that is configured to process your audit records to be considered compliant. | 
| `AU-9` Protection of Audit Information | Configuration rule | {{site.data.keyword.at_short}} protects audit information and tools by requiring access permissions to access, modify, or delete any data. | 
| `AU-12` Audit Generation | Configuration rule | {{site.data.keyword.at_short}} is used to validate that all of the accounts in a given scope have audit logging enabled. With this control enabled, your instance of {{site.data.keyword.at_short}} must be configured to retain data. | 
{: caption="Table 2. Available audit logging and monitoring controls" caption-side="bottom"}


## Identity and access
{: #id-access}

With identification and authentication controls in place, you can ensure that the users of your accounts are verified. 

| Control       | Implementation   | Description  | 
|:--------------|:-----------------|:-------------|
| `IA-2` Organizational Users | Configuration rule | {{site.data.keyword.cloud_notm}} supports the ability to enable Multifactor authentication for all of your accounts. |
| `AC-6` Least Privilege | Built-in | {{site.data.keyword.cloud_notm}} supports the ability to limit user access to only those permissions that are required to accomplish a task. |
| `AC-6(10)` Prohibit Non-privileged Users from Executing Privileged Fuctions | Built-in | {{site.data.keyword.cloud_notm}} supports the ability to prevent non-priviliged users from executing privileged functions such as disabling, circumventing, or altering implemented security safeguards. |
{: caption="Table 3. Available identity and access controls" caption-side="bottom"}



## Network security
{: #network}

With network protections in place, you can ensure that your network traffic communication is limited to only those connections that are essential and are approved. You can also ensure that your audit information is handled in a secure manner.

| Control       | Implementation   | Description  | 
|:--------------|:-----------------|:-------------|
| `SC-7` Boundary Protection | Configuration rule | {{site.data.keyword.cis_full_notm}} is used to configure your web application firewall. With this control enabled, you must have your Web Application Firewall (WAF) enabled for all of your defined zones. |
| `SC-7(5)` Deny by Default / Allow by Exception | Configuration rule | {{site.data.keyword.cis_full_notm}} is used to configure your web application firewall. With this control enabled, you must have your Web Application Firewall (WAF) enabled for all of your defined zones. | 
| `SC-28` Protection of Information at Rest | Built-in | {{site.data.keyword.at_short}} encrypts the audit information that it stores while the data is at rest by using AES 256. | 
{: caption="Table 4. Available Network security controls" caption-side="bottom"}


