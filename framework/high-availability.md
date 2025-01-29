---

copyright:
  years: 2020, 2025
lastupdated: "2025-01-29"

keywords: HA for {{site.data.keyword.compliance_short}}, DR for {{site.data.keyword.compliance_short}}, high availability for {{site.data.keyword.compliance_short}}, disaster recovery for {{site.data.keyword.compliance_short}}, failover for {{site.data.keyword.compliance_short}}, BC for {{site.data.keyword.compliance_short}}, business continuity for {{site.data.keyword.compliance_short}}, disaster recovery for {{site.data.keyword.compliance_short}}

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Understanding high availability for {{site.data.keyword.compliance_short}}
{: #ha}

[High availability](#x2284708){: term} (HA) is a core discipline in an IT infrastructure to keep your apps up and running, even after a partial or full site failure. The main purpose of high availability is to eliminate potential points of failures in an IT infrastructure. 
{: shortdesc}

## Responsibilities
{: #ha-responsibilities}

To find out more about responsibility ownership for using {{site.data.keyword.cloud_notm}} products between {{site.data.keyword.IBM_notm}} and the customer, see [Shared responsibilities for {{site.data.keyword.cloud_notm}} products](/docs/overview?topic=overview-shared-responsibilities).

## What level of availability do I need?
{: #ha-level}

You can achieve high availability on different levels in your IT infrastructure and within different components of your cluster. The level of availability that is ideal for you depends on several factors. These factors include your business requirements, the service level agreements (SLAs) that you have with your customers, and the resources that you want to expend.

## What level of availability does {{site.data.keyword.cloud_notm}} offer?
{: #ha-service}

The level of availability that you set up for your cluster impacts your coverage under the {{site.data.keyword.cloud_notm}} high availability service level agreement terms.

Service level objectives (SLOs) describe the design points that the {{site.data.keyword.cloud_notm}} services are engineered to meet. {{site.data.keyword.compliance_short}} is designed to achieve an availability target of 99.9%.

The SLO is not a warranty and {{site.data.keyword.IBM_notm}} does not issue credits for failure to meet an objective. Refer to the SLAs for commitments and credits that are issued for failure to meet any committed SLAs. For a summary of all SLOs, see [{{site.data.keyword.cloud_notm}} service level objectives](/docs/resiliency?topic=resiliency-slo).


## Locations
{: #ha-locations}

For more information about service availability within regions and data centers, see [Service and infrastructure availability by location](/docs/overview?topic=overview-services_region).
