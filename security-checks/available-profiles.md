---

copyright:
  years: 2023
lastupdated: "2023-06-07"

keywords: best practices, security and compliance, governance, profile, predefined profiles, benchmark, controls, goals, security, compliance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Available predefined profiles 
{: #predefined-profiles}

With the {{site.data.keyword.compliance_full}}, you can take advantage of predefined profiles that contain collections of controls that are curated based on industry standards. You can also [create your own goal-based profiles](/docs/security-compliance?topic=security-compliance-custom-profiles) or [Assessment-based profiles](/docs/security-compliance?topic=security-compliance-build-custom-profiles).  
{: shortdesc}

{{site.data.keyword.compliance_short}} supports more than 40 predefined profiles. Within each profile, you can review the controls and goals that are required to be compliant. You can't modify or remove controls from a predefined profile. But, you can use a predefined profile as a base to create a new profile to choose only the controls and goals that are relevant for your business. 

Then, if needed, you can update the default parameters that are associated with the goals within each predefined profile. To learn more, see [Customizing goals](/docs/security-compliance?topic=security-compliance-custom-goals). 

## Updating predefined profiles
{: #profile-versions}

At times, {{site.data.keyword.compliance_short}} publishes new versions of {{site.data.keyword.cloud_notm}} predefined profiles. Reasons for reversioning include:

* to remove rules that are invalid or are no longer required to meet controls;
* to add new rules and extend the compliance coverage of profiles;
* to fix defective rules. 


### Update levels
{: #profile-update-levels}

Based on specific activities, the updates to the {{site.data.keyword.cloud_notm}}'s predefined profiles can be major, minor, or a simple fix. To understand what each update level includes, review the following table. 

| Activity | Fix | Minor | Major |
| -------- | --- | ----- | ----- |
| Bug fixes \n * Small change to a rule \n * Small change to control guidance  | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Remove controls | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Reduce controls \n * Remove control specifications \n * Remove assessments | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Add controls |   | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Extend controls \n * Add new control specification (for example, new components) |  | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| Major rework of profiles \n * Support for new profile features |  |   |  ![Checkmark icon](../../icons/checkmark-icon.svg) | 
| Reversion \n * Publish a new version of the profile \n * Make the updated profile available for attachments  |   | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) |
{: caption="Table 1. {{site.data.keyword.cloud_notm}} predefined profiles update levels" caption-side="top"}



## {{site.data.keyword.cloud_notm}} 
{: #ibm-cloud-profiles}

Transform your organization with {{site.data.keyword.cloud_notm}} and attain a standardized level of security and compliance by using the {{site.data.keyword.cloud_notm}} profiles.

{{site.data.keyword.cloud_notm}} profiles have been updated to work in the new api-based architecture.
{: note}

| Profile  | Description | Release notes |
| -------- | ----------- | ------------- |
| {{site.data.keyword.cloud_notm}} Control Library | The {{site.data.keyword.cloud_notm}} Control Library is a collection of all the controls and goals that are available for {{site.data.keyword.cloud_notm}}. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-ibm-control-library-change-log) |
| {{site.data.keyword.cloud_notm}} for Financial Services | [{{site.data.keyword.cloud_notm}} for Financial Services™](/docs/framework-financial-services?topic=framework-financial-services-about) is an open platform that brings together independent software vendors (ISVs), Software as a Service (SaaS) providers, and financial services institutions in a single ecosystem. In this secure cloud platform, you can rapidly develop and share innovative applications, APIs, data, and content to meet the unique business needs of your financial institution.  \n \n Through the [{{site.data.keyword.framework-fs_full}}](/docs/framework-financial-services?topic=framework-financial-services-about), you can access a unified set of security and compliance controls, which was built specifically for and with the financial services industry. To address your evolving needs as a financial institution, IBM continuously validates these controls with global Councils of CSOs, CTOs, and CIOs from major banks, insurance providers, and regulatory advisors.  \n \n The {{site.data.keyword.cloud_notm}} for Financial Services profile provides you with a set of pre-configured automated goals that are mapped to the [{{site.data.keyword.framework-fs_full}} control requirements](/docs/framework-financial-services?topic=framework-financial-services-about#framework-control-requirements). The results of these tests help you validate compliance when you are using one of the [references architectures](/docs/framework-financial-services?topic=framework-financial-services-reference-architecture-overview) for the {{site.data.keyword.cloud_notm}} for Financial Services. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-fs-change-log) |
| CIS {{site.data.keyword.cloud_notm}} Foundations Benchmark | Secure your IBM Cloud Foundations resources with CIS Benchmarks.  |  |
| {{site.data.keyword.cloud_notm}} Security Best Practices Controls | Secure your resources to meet industry and {{site.data.keyword.cloud_notm}} best practices. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-ibm-sec-best-practices-change-log) |
{: caption="Table 2. {{site.data.keyword.cloud_notm}} predefined profiles" caption-side="top"}




## Goal-based predefined profiles 
{: #predefined-profiles-collector}

In the collector-based version of {{site.data.keyword.compliance_short}}, you can take advantage of predefined profiles that contain collections of controls that are curated based on industry standards. You can also [create your own profiles](/docs/security-compliance?topic=security-compliance-build-custom-profiles).  
{: shortdesc}

There are more than 40 defined profiles that are available for hybrid cloud evaluations. Within each profile, you can review the controls and goals that are required to be compliant. 



### Best practices
{: #best-practices-profiles}

Use the best practices profiles to securely configure your resources from various product families.

| Profile | Description | 
| -------- | ----------- |
| Best Practices - AWS S3 Controls | Secure Amazon Simple Storage Service infrastructure with Best Practices controls. |
| Best Practices - Firewalls | Secure firewalls with Best Practices controls. |
| Best Practices - Linux Hardening | Secure Linux Hardening with Best Practices controls. |
| Best Practices - MySQL | Secure MySQL server software with Best Practices controls. |
| Best Practices - SQL Server | Secure SQL server software with Best Practices controls. |
| GDPR | Protect your resources according to the GDPR guidelines with Best Practices controls. |
{: caption="Table 6. Best practices predefined profiles" caption-side="top"}


### Benchmarks
{: #benchmarks-profiles}

With the CIS Benchmarks, you have access to a collection of industry best practices for securely configuring IT systems, software, and networks. The benchmarks contain more than 100 configuration guidelines across 25 vendor product families or more. 

| Profile | Description | 
| -------- | ----------- |
| CIS AWS 3-tier Web Architecture Benchmark 1.0 | Secure Amazon Web Services. |
| CIS AWS Foundations Benchmark 1.2 | Secure Amazon Web Services. |
| CIS AZURE Foundations Benchmark 1.1 | Secure Microsoft Azure cloud computing services. |
| CIS Amazon Linux Benchmark 2.1.0 |  Secure Amazon Linux operating systems. | 
| CIS CentOS Linux 7 Benchmark 2.2.0 | Secure CentOS Linux operating systems. | 
| CIS Cisco Firewall Benchmark 4.1 | Secure Cisco Network devices. |
| CIS Debian Linux 8 Benchmark 1.0.1 | Secure Debian Linux operating systems. |
| CIS Debian Linux 9 Benchmark 1.0.1 | Secure Debian Linux operating systems. |
| CIS Docker Benchmark 1.2.0 | Secure Docker server software. | 
| CIS GCP Foundations Benchmark 1.1.0 | Secure Google Cloud Platform services. |
| CIS Juniper OS Benchmark 2.0 | Secure Juniper operating systems. | 
| CIS Kubernetes Benchmark v1.3.0 | Secure Kubernetes server software. |
| CIS Kubernetes Benchmark v1.6.1 | Secure Kubernetes server software. |
| CIS Linux Benchmarks | Secure Linux operating systems.  | 
| CIS MS Windows Server 2008 R2 Benchmark 3.1.0 | Secure Microsoft Windows Server operating systems. |
| CIS MS Windows Server 2012 R2 Benchmark 2.2.1 | Secure Microsoft Windows Server operating systems. |
| CIS MS Windows Server 2016 RTM Benchmark 1.0.0 | Secure Microsoft Windows Server operating systems. | 
| CIS MS Windows Server 2019 RTM Benchmark 1.0.0 | Secure Microsoft Windows Server operating systems. |
| CIS MS Windows10 Enterprise R1909 Benchmark 1.8.0 | Secure Microsoft Windows Desktop operating systems. |
| CIS Microsoft SQL Server 2016 Benchmark 1.0.0 | Secure Microsoft SQL Server software. |
| CIS MongoDB 3.4 Benchmark 1.0.0 | Secure MongoDB server software. |
| CIS MySQL Enterprise Edition 5.7 Benchmark 1.0.0 | Secure Oracle MySQL server software. |
| CIS Oracle Database 11g R2 Benchmark 2.2.0 | Secure Oracle Database server software with CIS Benchmarks. |
| CIS Oracle Linux 6 Benchmark 1.1.0 | Secure Oracle Linux operating systems with CIS Benchmarks. | 
| CIS Oracle Linux 7 Benchmark 2.1.0 | Secure Oracle Linux operating systems with CIS Benchmarks. |
| CIS Red Hat Enterprise Linux 6 Benchmark 2.1.0 | Secure Red Hat Enterprise Linux operating systems with CIS Benchmarks. |
| CIS Red Hat Enterprise Linux 7 Benchmark 2.2.0 | Secure Red Hat Enterprise Linux operating systems with CIS Benchmarks. |
| CIS Red Hat Enterprise Linux 8 Benchmark 1.0.0 | Secure Red Hat Enterprise Linux operating systems with CIS Benchmarks. |
| CIS Red Hat Enterprise Linux Pack | Secure Red Hat Enterprise Linux operating systems with CIS Benchmarks. |
| CIS SUSE Linux Enterprise 12 Benchmark 2.1.0 | Secure SUSE Linux Enterprise Server operating systems with CIS Benchmarks. |
| CIS Ubuntu Linux 18.04 LTS Benchmark 1.0.0 | Secure UBuntu Linux operating systems with CIS Benchmarks. |
| CIS Windows Server Benchmarks | Secure Microsoft Windows server operating systems.  |
{: caption="Table 7. CIS Benchmarks profiles" caption-side="top"}



