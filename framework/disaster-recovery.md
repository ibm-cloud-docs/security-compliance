---

copyright:
  years: 2020, 2024
lastupdated: "2024-01-03"

keywords: HA for {{site.data.keyword.compliance_short}}, DR for {{site.data.keyword.compliance_short}}, high availability for {{site.data.keyword.compliance_short}}, disaster recovery for {{site.data.keyword.compliance_short}}, failover for {{site.data.keyword.compliance_short}}, BC for {{site.data.keyword.compliance_short}}, business continuity for {{site.data.keyword.compliance_short}}, disaster recovery for {{site.data.keyword.compliance_short}}

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Understanding business continuity and disaster recovery for {{site.data.keyword.compliance_short}}
{: #bc-dr}

[Disaster recovery](#x2113280){: term} involves a set of policies, tools, and procedures for returning a system, an application, or an entire data center to full operation after a catastrophic interruption. It includes procedures for copying and storing an installed system's essential data in a secure location, and for recovering that data to restore normalcy of operation. {: shortdesc}

In case of failure, a failover design is established to keep your resources running without needing you to act. See [How {{site.data.keyword.cloud_notm}} ensures high availability and disaster recovery](/docs/overview?topic=overview-zero-downtime#zero-downtime) to learn more about the high availability and disaster recovery standards in {{site.data.keyword.cloud_notm}}. You can also learn more about [Service Level Agreements](/docs/overview?topic=overview-slas).

## Responsibilities
{: #bc-dr-responsibilities}

To find out more about responsibility ownership for using {{site.data.keyword.cloud_notm}} products between {{site.data.keyword.IBM_notm}} and customer, see [Shared responsibilities for {{site.data.keyword.cloud_notm}} products](/docs/overview?topic=overview-shared-responsibilities).

## Disaster recovery strategy
{: #bc-dr-strategy}



{{site.data.keyword.cloud_notm}} has [business continuity](#x3026801){: term} plans in place to provide for the recovery of services within hours if a disaster occurs. You are responsible for your data backup and associated recovery of your content.

{{site.data.keyword.compliance_short}} provides mechanisms to protect your data and restore service functions. Business continuity plans are in place to achieve targeted [recovery point objective](#x3429911){: term} (RPO) and [recovery time objective](#x3167918){: term} (RTO) for the service. The following table outlines the targets for {{site.data.keyword.compliance_short}}.

| Disaster recovery objective | Target value |
| --------------------------- | ------------ |
| RPO | 12 hours |
| RTO | 4 hours |
{: caption="Table 1. RPO and RTO for {{site.data.keyword.compliance_short}}" caption-side="bottom"}


