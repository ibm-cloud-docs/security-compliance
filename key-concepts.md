---

copyright:
  years: 2020, 2023
lastupdated: "2023-06-28"

keywords: security and compliance, secure development, security strategy

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Key concepts in {{site.data.keyword.compliance_short}}
{: #key-concepts}

When you work with {{site.data.keyword.compliance_full}}, you interact with several different entities. Learn more about the components of {{site.data.keyword.compliance_short}} by reviewing the following definitions.

The collector-based architecture is deprecated. For more information, see the [release notes](/docs/security-compliance?topic=security-compliance-release-notes).
{: deprecated}


## Terminology
{: #terms}

Control
:   A technical, administrative, or physical safeguard that is designed to meet a set of defined security and privacy requirements. Controls exist to prevent, detect, or lessen the ability of a threat to exploit a vulnerability.

Control library
:   A collection of predefined or custom controls. Control libraries show all the controls in your accounts that are available to be evaluated. A library is helpful for organizing and versioning of your controls. A library is structured as follows. 

	![The diagram shows the layout of a control library. The information is conveyed in the surrounding text.](images/control-library.svg){: caption="Figure 1. Understanding control libraries" caption-side="bottom"}

Profile
:   A group of controls that are related to a specific compliance objective.

	Although very similar in structure to a control library, a profile can be attached to a set of resources and be evaluated. When you create the attachment, you can set the parameters that define the way that the evaluation is done.

	![The diagram shows the layout of a profile. The information is conveyed in the surrounding text.](images/kc-profile.svg){: caption="Figure 2. Understanding profiles in the new architecture" caption-side="bottom"}

	In collector-based evaluations, a profile is comprised of goals that you want to achieve. Goal-based profiles are currently used to evaluate hybrid / multi-cloud environments but will be deprecated over time as we move to an API-based architecture.

	![The diagram shows the layout of a goal-based profile. The information is conveyed in the surrounding text.](images/kc-profile-collector.svg){: caption="Figure 3. Understanding profiles that are used for collector-based scanning" caption-side="bottom"}

Specification
:   A statement that defines the specific security and privacy requirements that a control must meet. For example, `Check whether App ID Cloud Directory users aren't able to update their own accounts`. In a collector-based evaluation this concept, when combined with an assessment, is known as a goal.

Assessment
:   The actual evaluation of a configuration for compliance with applicable standards. An assessment can be either automated or manual depending on the control. Currently, the only available type of assessment is an {{site.data.keyword.cloud_notm}} rule. In a collector-based evaluation this concept, when combined with a specification, is known as a goal.

Rule
:   A set of conditional statements that are used to determine whether a resource configuration is in compliance. To evaluate a rule, you must associate it with a profile through an assessment.

Parameter
:   The specific configuration property that is evaluated. Each parameter is assigned a value by default that can be customized when an attachment is created. For example, if a control evaluates which region that a resource exits in, you can specify the region that you want to check for by defining the parameter.

Collector
:   A collector is a software module that has visibility into your resource configurations. It is used in the hybrid or multi-cloud flows to gather the configuration information that is evaluated by {{site.data.keyword.compliance_short}}. 

	**Collectors are required for collector-based evaluations only.*

Credentials
:   A credential provides a collector access to the resources that you want to evaluate. Depending on the resource that you want to evaluate, a credential might be an API key or a username and password combination.

	**Credentials are required for collector-based evaluations only.*

Scope
:   The group of resources that you want to evaluate. In the new API-based architecture, a scope can be an Enterprise, Account group, Account, or Resource group. In the collector-based architecture, a scope is configurable based on your available resources.

Attachment
:   The connection between a profile and scope that defines the way that {{site.data.keyword.compliance_short}} conducts an evaluation. An attachment is formed by selecting the grouping of resources that you want to evaluate and a profile. Then, you specify the parameters that you want to evaluate for. Attachments are evaluated once per day or can be initiated as needed. In collector-based evaluations this concept is known as a scan. Scans can be scheduled or run on-demand.

Results
:   The information that is returned by the evaluation is known as results. For a breakdown of the information that is returned in your results, see [Understanding results](/docs/security-compliance?topic=security-compliance-results).


	Running an evaluation does not ensure regulatory compliance. An evaluation provides a point in time statement of your current posture for a specific resource. It is your responsibility to review and interpret the results to ensure that your organization is adhering to the controls that are required for your industry. 
	{: important}

