---

copyright:
  years: 2020, 2023
lastupdated: "2023-10-10"

keywords: public isolation for {[scc]}, compute isolation for {[scc]}, {[scc]} architecture, workload isolation in {[scc]} 

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Learning about {[scc]} architecture and workload isolation
{: #compute-isolation}

Review the following architecture for {[scc-full]}, and learn more about different isolation levels, so that you can choose the solution that best meets the requirements of the workloads that you want to run in the cloud.
{: shortdesc}


## {[scc]} architecture
{: #architecture}

{[scc]} is a multi-tenant, regional service that is fully integrated with the {[cloud]} platform. The IBM-managed components of the {[scc]} are organized to provide compute isolation between workloads. 

Check out the following image to see how the service workloads are isolated and managed.

![This image shows the workload isolation for the {[scc]} service.](../images/architecture.svg){: caption="Figure 1. Workload isolation" caption-side="bottom"}

| Component | Description |
|:----------|:------------|
| Control plane | The microservices that make up the individual components of the service run in the control plane, where they are isolated from the other components. Additionally, internal dependencies are run and isolated as part of the control plane. |
| Data plane |  |
{: caption="Table 1. IBM-managed components of the {[scc]}" caption-side="top"}
{: #ibm-managed}
{: tab-title="IBM"}
{: tab-group="arch-manage"}
{: class="simple-tab-table"}

| Component | Description |
|:----------|:------------|
| {[cloud]} services | As you interact with {[scc]}, you are responsible for the instances of the other services that you chose to interact with through the service. |
| {[at]} | As you interact with the service, a log of the events that are generated can be found in your instance of {[at]}. |
{: caption="Table 1. Customer-managed components of the {[scc]}" caption-side="top"}
{: #customer-managed}
{: tab-title="Customer"}
{: tab-group="arch-manage"}
{: class="simple-tab-table"}



## {[scc]} workload isolation
{: #workload-isolation}

Each regional deployment of the {[scc]} serves multiple tenants and can be accessed through public endpoints. By default, all data at rest is encrypted by IBM keys. Data in transit is encrypted by using TLS. Your data is isolated from other customer's data but does share physical resources such as CPU, memory, and I/O devices. 

