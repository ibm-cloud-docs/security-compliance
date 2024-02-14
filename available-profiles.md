---

copyright:
  years: 2024
lastupdated: "2024-02-14"

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

| Profile  | Description | Environment | Release notes |
|:---------|:------------|:------------|:--------------|
| AI ICT Guardrails | Ensure that your resource configurations meet the baseline requirements surrounding AI and generative AI workloads. | {{site.data.keyword.cloud_notm}} | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-ai-ict-change-log) |
| Amazon Web Services CIS Foundations Benchmark* | Validate that your resource configurations meet the baseline requirements that are identified by the Center for Internet Security. | Amazon Web Services | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-cis-amazon-benchmark) |
| Amazon Web Services CIS Kubernetes Service Benchmark* | Validate that your Kubernetes Service resource configurations meet the baseline requirements that are identified by the Center for Internet Security. | Amazon Web Services | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-cis-amazon-eks-benchmark) |
| Caveonix Security Baselines for VMWare* | Validate that your VMWare resource configurations that run on {{site.data.keyword.cloud_notm}} meet the baselines requirements that have been identified by Caveonix. | {{site.data.keyword.cloud_notm}} | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-caveonix-vmware) |
| CIS Amazon Web Services Foundational Security Best Practices* | Validate that your resource configurations meet the baseline requirements that are identified by the Center for Internet Security.  | Amazon Web Services | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-aws-fs-benchmark) |
| CIS {{site.data.keyword.cloud_notm}} Foundations Benchmark | Validate that your resource configurations meet the baseline requirements that are identified by the Center for Internet Security. | {{site.data.keyword.cloud_notm}} | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-cis-benchmark-profile) |
| CIS Amazon Web Services Well-architected Framework*  | Validate that your resource configurations meet the baseline requirements that are identified by the Center for Internet Security. | Amazon Web Services | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-aws-waf-benchmark) |
| CIS Microsoft Azure Foundations Benchmark* | Validate that your resource configurations meet the baseline requirements that are identified by the Center for Internet Security. | Microsoft Azure | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-cis-azure-benchmark) |
| CIS Microsoft Azure Kubernetes Service Benchmark* | Validate that your Kubernetes Service resource configurations meet the baseline requirements that are identified by the Center for Internet Security. | Microsoft Azure | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-cis-azure-ks-benchmark) |
| {{site.data.keyword.cloud_notm}} Framework for Financial Services | [{{site.data.keyword.cloud_notm}} for Financial Services™](/docs/framework-financial-services?topic=framework-financial-services-about) is an open platform that brings together independent software vendors (ISVs), Software as a Service (SaaS) providers, and financial services institutions in a single ecosystem. In this secure cloud platform, you can rapidly develop and share innovative applications, APIs, data, and content to meet the unique business needs of your financial institution.  \n \n Through the [{{site.data.keyword.framework-fs_full}}](/docs/framework-financial-services?topic=framework-financial-services-about), you can access a unified set of security and compliance controls, which was built specifically for and with the financial services industry. To address your evolving needs as a financial institution, IBM continuously validates these controls with global Councils of CSOs, CTOs, and CIOs from major banks, insurance providers, and regulatory advisors.  \n \n The {{site.data.keyword.cloud_notm}} for Financial Services profile provides you with a set of pre-configured automated goals that are mapped to the [{{site.data.keyword.framework-fs_full}} control requirements](/docs/framework-financial-services?topic=framework-financial-services-about#framework-control-requirements). The results of these tests help you validate compliance when you are using one of the [references architectures](/docs/framework-financial-services?topic=framework-financial-services-reference-architecture-overview) for the {{site.data.keyword.cloud_notm}} for Financial Services. | {{site.data.keyword.cloud_notm}} | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-fs-change-log) |
| {{site.data.keyword.cloud_notm}} Kubernetes Service Benchmark | Validate that your Kubernetes Service resource configurations meet the baseline requirements that are identified by {{site.data.keyword.cloud_notm}}.  | {{site.data.keyword.cloud_notm}} | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-iks-profile) |
| {{site.data.keyword.cloud_notm}} Red Hat OpenShift Kubernetes OCP4 | Validate that your Red Hat OpenShift Kubernetes Service resource configurations meet the baseline requirements that are identified by {{site.data.keyword.cloud_notm}}. | {{site.data.keyword.cloud_notm}} | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-openshift-profile) |
| C5:2020 | Validate that your resource configurations meet the baselines requirements that are identified in the Cloud Computing Compliance Controls Catalog by the Gernam Federal Office for Information Security. | {{site.data.keyword.cloud_notm}} | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-bsi-c5-change-log) |
| ENS High | Validate that your resource configurations meet the baseline requirements that are identified in the National Security Scheme for Spanish agencies and organizations. | Multi-environment | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-ens-high-change-log) |
| NIST SP 800-53 | Validate that your resource configurations meet the baselines requirements that are identified by the National Institute of Standards and Technology | Multi-environment | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-nist-800-53-change-log) |
| PCI | Validate that your resource configurations meet the baseline requirements that are identified by the Payment Card Industry Data Security Standard. | Multi-environment | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-pci-dss-change-log) |
| SOC 2 | Validate that your resource configurations meet the baselines requirements that are identified in the Service Organization Control reports issued by the American Institute of Certified Public Accountants. | {{site.data.keyword.cloud_notm}} | [![Note icon](../../icons/note_icon.svg)](/docs/security-compliance?topic=security-compliance-soc2-change-log) |
{: caption="Table 2. Available predefined profiles" caption-side="top"}

**Integration required*
