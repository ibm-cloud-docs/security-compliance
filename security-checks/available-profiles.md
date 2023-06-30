---

copyright:
  years: 2023
lastupdated: "2023-06-30"

keywords: best practices, security and compliance, governance, profile, predefined profiles, benchmark, controls, goals, security, compliance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Available predefined profiles 
{: #predefined-profiles}

With the {{site.data.keyword.compliance_full}}, you can take advantage of predefined profiles that contain collections of controls that are curated based on industry standards. You can also create your own [Assessment-based profiles](/docs/security-compliance?topic=security-compliance-build-custom-profiles).  
{: shortdesc}

{{site.data.keyword.compliance_short}} supports predefined profiles. Within each profile, you can review the controls that are required to be compliant. You can't modify or remove controls from a predefined profile. But, you can use a predefined profile as a base to create a new profile to choose only the controls and goals that are relevant for your business. 

Then, if needed, you can update the default parameters that are associated with the goals within each predefined profile. 

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


