---

copyright:
  years: 2020, 2023
lastupdated: "2023-06-12"

keywords: security and compliance, secure development, security strategy

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# How does {{site.data.keyword.compliance_short}} work?
{: #posture-management}

When you work with {{site.data.keyword.compliance_full}}, you interact with several different entities and can take multiple user paths through the service. Learn more about each entity by reviewing the following definitions and user flows.





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

| [deprecated]{: tag-deprecated} User flow B |
|:--------------|
| 1. To get started as a security or compliance focal, you create and deploy a collector to infrastructure that has network connectivity to your resources.  \n 2. For the collector to read your resource configuration data, you must provide credentials that have the appropriate level of access.  \n 3. When you're ready to start evaluating, you target a set of resources by defining a scope and then scheduling your scan.  \n 4. The collector watches to see when it is time to scan.  \n 5. The collector evaluates your resources.  \n 6. When the scan is complete, results are forwarded to a database that is owned by {{site.data.keyword.compliance_short}} and are kept for 180 days.  \n 7. Results are visible in the {{site.data.keyword.compliance_short}} console on the **Hybrid cloud results** page. |
{: caption="Table 1. Understanding user flows" caption-side="top"}
{: #scc-user-flows-collector}
{: tab-title="Hybrid cloud"}
{: tab-group="user-flows"}
{: class="simple-tab-table"}


## How does the functionality differ between flows?
{: #functionality}
{: support}

Depending on the evaluation flow that you're working in, your experience with the service differs. Review the following table to see how the functionality that is offered in each flow differs. As more functionality is released in the new architecture, this table will be updated.

|            | {{site.data.keyword.cloud_notm}} | [deprecated]{: tag-deprecated} Collector-based |
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


