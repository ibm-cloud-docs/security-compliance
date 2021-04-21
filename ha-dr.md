---

copyright:
  years: 2021
lastupdated: "2021-04-21"

keywords: HA for {{site.data.keyword.compliance_short}}, DR for {{site.data.keyword.compliance_short}}, high availability for {{site.data.keyword.compliance_short}}, disaster recovery for {{site.data.keyword.compliance_short}}, failover for {{site.data.keyword.compliance_short}}

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

# Understanding high availability and disaster recovery for {{site.data.keyword.compliance_short}}
{: #ha-dr}

As an {{site.data.keyword.cloud_notm}} platform service, {{site.data.keyword.compliance_short}} follows the practices that are described in [How {{site.data.keyword.cloud_notm}} ensures high availability and disaster recovery](/docs/overview?topic=overview-zero-downtime) with the exceptions listed in the following topic.
{: shortdesc}

## Posture Management HA/DR
{: #posture-ha-dr}

The Posture Management capability of the {{site.data.keyword.compliance_short}} is a highly-available regional service that runs in the Dallas (`us-south`) and Frankfurt (`fra`). In the supported region, the service runs in several availability zones with three in-region replicas. 

Your data is stored securely and backed up to IBM Cloud Databases. If a regional disaster occurs, the available data is restored by the {{site.data.keyword.compliance_short}} without any action from you.

## Configuration Governance HA/DR
{: #config-ha-dr}

The Configuration Governance capability of the {{site.data.keyword.compliance_short}} is a highly-available regional service that runs in the Dallas (`us-south`), Frankfurt (`fra`), and Washington DC (`us-east`) regions. In each region, a highly available Cloudant cluster contains three copies of the data. The data is backed-up daily to Cloud Object Storage.

If all of the availability zones in a region fail, {{site.data.keyword.compliance_short}} becomes unavailable in that location and all of the network traffic is routed to the other location. When the region is shown to be available again by health check APIs, traffic is automatically redirected back to the previously unavailable region without any need for action from you.

## Security Insights HA/DR
{: #insights-ha-dr}

Security Insights is a highly available, regional service that runs in the Dallas (`us-south`), Frankfurt (`fra`), and London (`eu-gb`) regions.

In each supported region, the service runs in several availability zones. The service supports manual cross-regional failover from `us-south` to `us-east` and from `eu-gb` to `us-south`. There is no cross-regional failover for the `eu-de` region, but data is backed up to a secondary account that also resides in `eu-de` region. A daily backup of data to Cloud Object Storage is done and the backup is kept for 7 days.

If a regional disaster occurs, the available data is restored by Security Insights without any action from you. 

