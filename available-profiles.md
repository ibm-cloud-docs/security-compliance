---

copyright:
  years: 2023
lastupdated: "2023-12-07"

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

	

	New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
	{: important}

	

## Available pre-defined profiles
{: #available-predefined-profiles}

The following profiles are available for you to use in {{site.data.keyword.compliance_short}}.

| Profile  | Description | Release notes |
| -------- | ----------- | ------------- |
| CIS {{site.data.keyword.cloud_notm}} Foundations Benchmark | Secure your IBM Cloud Foundations resources with CIS Benchmarks.  | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-cis-benchmark-profile) |
| CIS Amazon Elastic Kubernetes Service (EKS) Benchmark | View the results of the Amazon Elastic Kubernetes Service evaluations done in Workload Protection in {{site.data.keyword.compliance_short}}. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-cis-amazon-eks-benchmark) |
| CIS Azure Kubernetes Service (AKS) Benchmark | View the results of the Azure Kubernetes Service evaluations done in Workload Protection in {{site.data.keyword.compliance_short}}. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-cis-azure-ks-benchmark) |
| Amazon Web Services Foundations Benchmark | View the results of the Amazon evaluations done in Workload Protection in {{site.data.keyword.compliance_short}}. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-cis-amazon-benchmark) |
| CIS Microsoft Azure Foundations Benchmark | View the results of the Azure evaluations done in Workload Protection in {{site.data.keyword.compliance_short}}. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-cis-azure-benchmark) |
| {{site.data.keyword.cloud_notm}} for Financial Services | [{{site.data.keyword.cloud_notm}} for Financial Services™](/docs/framework-financial-services?topic=framework-financial-services-about) is an open platform that brings together independent software vendors (ISVs), Software as a Service (SaaS) providers, and financial services institutions in a single ecosystem. In this secure cloud platform, you can rapidly develop and share innovative applications, APIs, data, and content to meet the unique business needs of your financial institution.  \n \n Through the [{{site.data.keyword.framework-fs_full}}](/docs/framework-financial-services?topic=framework-financial-services-about), you can access a unified set of security and compliance controls, which was built specifically for and with the financial services industry. To address your evolving needs as a financial institution, IBM continuously validates these controls with global Councils of CSOs, CTOs, and CIOs from major banks, insurance providers, and regulatory advisors.  \n \n The {{site.data.keyword.cloud_notm}} for Financial Services profile provides you with a set of pre-configured automated goals that are mapped to the [{{site.data.keyword.framework-fs_full}} control requirements](/docs/framework-financial-services?topic=framework-financial-services-about#framework-control-requirements). The results of these tests help you validate compliance when you are using one of the [references architectures](/docs/framework-financial-services?topic=framework-financial-services-reference-architecture-overview) for the {{site.data.keyword.cloud_notm}} for Financial Services. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-fs-change-log) |
| {{site.data.keyword.cloud_notm}} Kubernetes Service Benchmark | Validate the configuration of your {{site.data.keyword.cloud_notm}} Red Hat OpenShift clusters. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-iks-profile) |
| [Deprecated]{: tag-deprecated} {{site.data.keyword.cloud_notm}} Security Best Practices Controls | Secure your resources to meet industry and {{site.data.keyword.cloud_notm}} best practices. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-ibm-sec-best-practices-change-log) |
| PCI DSS | Validate the configuration of your {{site.data.keyword.cloud_notm}} resources. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-pci-dss-change-log) |
| SOC 2 | Validate  the internal controls configuration of your {{site.data.keyword.cloud_notm}} resources. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-soc2-change-log) |
| Red Hat OpenShift Kubernetes OCP4 | Validate the configuration of your {{site.data.keyword.cloud_notm}} Red Hat OpenShift clusters. | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-openshift-profile) |
{: caption="Table 2. {{site.data.keyword.cloud_notm}} predefined profiles" caption-side="top"}
