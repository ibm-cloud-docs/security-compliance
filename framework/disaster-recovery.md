---

copyright:
  years: 2020, 2023
lastupdated: "2023-10-10"

keywords: HA for {[scc]}, DR for {[scc]}, high availability for {[scc]}, disaster recovery for {[scc]}, failover for {[scc]}, BC for {[scc]}, business continuity for {[scc]}, disaster recovery for {[scc]}

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Understanding business continuity and disaster recovery for {[scc]}
{: #bc-dr}

[Disaster recovery](#x2113280){: term} involves a set of policies, tools, and procedures for returning a system, an application, or an entire data center to full operation after a catastrophic interruption. It includes procedures for copying and storing an installed system's essential data in a secure location, and for recovering that data to restore normalcy of operation. {: shortdesc}

In case of failure, a failover design is established to keep your resources running without needing you to act. See [How {[cloud]} ensures high availability and disaster recovery](/docs/overview?topic=overview-zero-downtime#zero-downtime) to learn more about the high availability and disaster recovery standards in {[cloud]}.

## Responsibilities
{: #bc-dr-responsibilities}

To find out more about responsibility ownership for using {[cloud]} products between {{site.data.keyword.IBM_notm}} and customer, see [Shared responsibilities for {[cloud]} products](/docs/overview?topic=overview-shared-responsibilities).

## Disaster recovery strategy
{: #bc-dr-strategy}

{[cloud]} has [business continuity](#x3026801){: term} plans in place to provide for the recovery of services within hours if a disaster occurs. You are responsible for your data backup and associated recovery of your content.

{[scc]} provides mechanisms to protect your data and restore service functions. Business continuity plans are in place to achieve targeted [recovery point objective](#x3429911){: term} (RPO) and [recovery time objective](#x3167918){: term} (RTO) for the service. The following table outlines the targets for {[scc]}.

| Disaster recovery objective | Target value |
| --------------------------- | ------------ |
| RPO | 12 hours |
| RTO | 4 hours |
{: caption="Table 1. RPO and RTO for {[scc]}" caption-side="bottom"}


