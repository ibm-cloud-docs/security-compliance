---

copyright:
  years: 2020
lastupdated: "2020-08-31"

keywords: HA for {{site.data.keyword.compliance_short}}, DR for {{site.data.keyword.compliance_short}}, high availability for {{site.data.keyword.compliance_short}}, disaster recovery for {{site.data.keyword.compliance_short}}, failover for {{site.data.keyword.compliance_short}}

subcollection: security-compliance

---

{:codeblock: .codeblock}
{:screen: .screen}
{:download: .download}
{:external: target="_blank" .external}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}
{:gif: data-image-type='gif'}
{:term: .term}
{:important: .important}
{:note: .note}
{:pre: .pre}
{:tip: .tip}
{:preview: .preview}
{:deprecated: .deprecated}
{:shortdesc: .shortdesc}
{:support: data-reuse='support'}
{:script: data-hd-video='script'}
{:table: .aria-labeledby="caption"}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:help: data-hd-content-type='help'}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tsSymptoms: .tsSymptoms}
{:beta: .beta}


# Understanding high availability and disaster recovery for {{site.data.keyword.compliance_short}}
{: #ha-dr}

As an {{site.data.keyword.cloud}} platform service, {{site.data.keyword.compliance_short}} follows the practices that are described in [How {{site.data.keyword.cloud_notm}} ensures high availability and disaster recovery](/docs/overview?topic=overview-zero-downtime) with the exceptions listed in the following topic.
{: shortdesc}

## Security and compliance posture management HA/DR
{: #posture-management-ha-dr}

The posture management capability of the {{site.data.keyword.compliance_short}} is a highly-available regional service that runs in the `us-south` region only. In the supported region, the service runs in several availablity zones with three in-region replicas. 

Your data is stored securely and backed up to IBM Cloud Databases. If a regional disaster occurs, the available data is restored by the {{site.data.keyword.compliance_short}} without any action from you.

## Configuration governance HA/DR
{: #config-governance-ha-dr}

The configuration governance capability of the {{site.data.keyword.compliance_short}} is a highly-available regional service that runs in the Dallas (`us-south`) and Washington DC (`us-east`) regions. In each region, a highly available Cloudant cluster contains three copies of the data. The data is backed-up daily to Cloud Object Storage.

If all of the availability zones in a region fail, {{site.data.keyword.compliance_short}} becomes unavailable in that location and all of the network traffic is routed to the other location. When the region is shown to be available again by health check APIs, traffic is automatically redirected back to the previously unavailable region without any need for action from you.

