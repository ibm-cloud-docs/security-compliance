---

copyright:
  years: 2020, 2023
lastupdated: "2023-02-15"

keywords: security and compliance, secure development, security strategy

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

# Key concepts in {{site.data.keyword.compliance_short}}
{: #posture-management}

When you work with {{site.data.keyword.compliance_full}}, you interact with several different entities and can take multiple user paths through the service. Learn more about each entity by reviewing the following definitions and user flows.

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
:   A set of conditional statements that are used to determine whether a resource configuration is in compliance. To evaluate a rule, it is associated with a profile through an assessment.

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


## Understanding user flows
{: #user-flows}

Now that you have an understanding of each entity individually, how do they work together? As part of some recent architectural changes in {{site.data.keyword.compliance_short}}, you have the option to use either an API or collector-based approach when you are working with the service. The following diagram details the two different user flows that you might take when you are working with {{site.data.keyword.compliance_short}}. Currently, if you're working with {{site.data.keyword.cloud_notm}} resources, the evaluation process integrated with the platform and conducted through API calls. Permissions are granted through IAM. If you're working in an environment other than {{site.data.keyword.cloud_notm}}, such as Amazon Web Services or Microsoft Azure, or if you're working with the OSCO profile you must use the collector-based flow.

![A diagram that shows the relationship between the entities that you work with in the service.](images/SCC-flow.svg){: caption="Figure 1. Understanding the user flows in {{site.data.keyword.compliance_short}}" caption-side="bottom"}

| User flow A |
|:--------------|
| 1. As a security or compliance focal, choose a predefined profile that is most suitable for your organization. Optionally you can customize the profile by creating custom rules, adding or removing rules, or building your own profile based on the catalog of controls.  \n 2. To start scanning your resources, create an attachment of the profile to the scope of resources you want to scan. You can optionally customize parameters of the controls when you create the attachment.  \n 3. After the attachment is created, your resources are evaluated one time per day by {{site.data.keyword.compliance_short}}.  \n 4. As results are returned, they are forwarded to a Cloud Object Storage bucket that you own.  \n 5. Results are shown in the {{site.data.keyword.compliance_short}} dashboard. |
{: caption="Table 1. Understanding user flows" caption-side="top"}
{: #scc-user-flows-api}
{: tab-title="IBM Cloud"}
{: tab-group="user-flows"}
{: class="simple-tab-table"}

| User flow B |
|:--------------|
| 1. To get started as a security or compliance focal, you create and deploy a collector to infrastructure that has network connectivity to your resources.  \n 2. For the collector to read your resource configuration data, you must provide credentials that have the appropriate level of access.  \n 3. When you're ready to start evaluating, you target a set of resources by defining a scope and then scheduling your scan.  \n 4. The collector watches to see when it is time to scan.  \n 5. The collector evaluates your resources.  \n 6. When the scan is complete, results are forwarded to a database that is owned by {{site.data.keyword.compliance_short}} and are kept for 180 days.  \n 7. Results are visible in the {{site.data.keyword.compliance_short}} console on the **Hybrid cloud results** page. |
{: caption="Table 1. Understanding user flows" caption-side="top"}
{: #scc-user-flows-collector}
{: tab-title="Hybrid cloud"}
{: tab-group="user-flows"}
{: class="simple-tab-table"}


### How does the functionality differ?
{: #functionality}
{: support}

Depending on the evaluation flow that you're working in, your experience with the service differs. Review the following table to see how the functionality that is offered in each flow differs. As more functionality is released in the new architecture, this table will be updated.

|            | {{site.data.keyword.cloud_notm}} | Collector-based |
|------------|-----------|-----------------|
| Availability | {{site.data.keyword.cloud_notm}} | {{site.data.keyword.cloud_notm}}, Amazon Web Services, Google Cloud Platform, Microsoft Azure, and On-premises |
| Integrations | | Tanium and OSCO |
| Enterprise account support | Available by default | Requires setup |
| Setup | Integrated with {{site.data.keyword.cloud_notm}} - Create an attachment to start evaluating | Requires setup of collectors and credentials |
| Results storage | Customer-owned | IBM-owned |
| Control parameters | Customizable by attachment | Customizable by account |
| Custom assessments | Write simple declarative rules | |
| Versioning | Supported for controls and profiles | |
| Search | Ability to search and filter controls and results by component, scope, category, and status | Searchable by control name |
{: row-headers}
{: caption="Table 2. Functionality comparison" caption-side="top"}


