---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: "public isolation for {{site.data.keyword.compliance_short}}, compute isolation for {{site.data.keyword.compliance_short}}, {{site.data.keyword.compliance_short}} architecture, workload isolation in {{site.data.keyword.compliance_short}} "

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Learning about {{site.data.keyword.compliance_short}} architecture and workload isolation
{: #compute-isolation}

As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the replacement service {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}

Review the following architecture for {{site.data.keyword.compliance_full}} and learn more about different isolation levels, so that you can choose the solution that best meets the requirements of the workloads that you want to run in the cloud.
{: shortdesc}


## {{site.data.keyword.compliance_short}} architecture
{: #architecture}

{{site.data.keyword.compliance_short}} is a multi-tenant, regional service that is fully integrated with the {{site.data.keyword.cloud_notm}} platform. The IBM-managed components of the {{site.data.keyword.compliance_short}} are organized to provide compute isolation between workloads.

Check out the following image to see how the service workloads are isolated and managed.

![This image shows the workload isolation for the {{site.data.keyword.compliance_short}} service.](../images/architecture.svg){: caption="Workload isolation" caption-side="bottom"}

| Component | Description |
|:----------|:------------|
| Control plane | The microservices that make up the individual components of the service run in the control plane, where they are isolated from the other components. Additionally, internal dependencies are run and isolated as part of the control plane. |
| Data plane |  |
{: caption="IBM-managed components of the {{site.data.keyword.compliance_short}}" caption-side="top"}
{: #ibm-managed}
{: tab-title="IBM"}
{: tab-group="arch-manage"}
{: class="simple-tab-table"}

| Component | Description |
|:----------|:------------|
| {{site.data.keyword.cloud_notm}} services | As you interact with {{site.data.keyword.compliance_short}}, you are responsible for the instances of the other services that you chose to interact with through the service. |
| {{site.data.keyword.at_short}} | As you interact with the service, a log of the events that are generated can be found in your instance of {{site.data.keyword.at_short}}. |
{: caption="Customer-managed components of the {{site.data.keyword.compliance_short}}" caption-side="top"}
{: #customer-managed}
{: tab-title="Customer"}
{: tab-group="arch-manage"}
{: class="simple-tab-table"}



## {{site.data.keyword.compliance_short}} workload isolation
{: #workload-isolation}

Each regional deployment of the {{site.data.keyword.compliance_short}} serves multiple tenants and can be accessed through public endpoints. By default, all data at rest is encrypted by IBM keys. Data in transit is encrypted by using TLS. Your data is isolated from other customers' data, but it does share physical resources such as CPU, memory, and I/O devices.
