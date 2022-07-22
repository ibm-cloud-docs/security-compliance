---

copyright:
  years: 2022
lastupdated: "2022-07-22"

keywords: integration, integrated services, integrations for rules, rules and goals, cloud services, Business Partners

subcollection: security-compliance
content-type: release-note

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

# Environments and services that are supported by {{site.data.keyword.compliance_short}}
{: #supported}

Integrations are connections between the {{site.data.keyword.compliance_full}} and various services. The services that are integrated with {{site.data.keyword.compliance_short}} help you manage the compliance of your account by standardizing and validating the configuration of your resources.
{: shortdesc}


## Environments that can be evaluated
{: #available-environments}

You can monitor the current security and compliance posture across all of the following environments by using the {{site.data.keyword.compliance_short}}. 
 
 - {{site.data.keyword.cloud_notm}}
 - Amazon Web Services
 - Google Cloud Platform
 - Microsoft Azure
 - On-premises

For more information, see [What is Posture Management?](/docs/security-compliance?topic=security-compliance-posture-management).



## {{site.data.keyword.cloud_notm}} services that can be evaluated
{: #evaluate-services}

You can evaluate your organization’s current security and compliance posture by [governing](/docs/security-compliance?topic=security-compliance-formatting-rules-templates) and [validating](/docs/security-compliance?topic=security-compliance-profiles#understand-profiles) the configuration of your resources in the following services.


| Service | Rules[^rule] | Template[^temp] | Goal[^goal] | Description |
| ------- | ------------ | ----------------| ------------| ----------- |
| [{{site.data.keyword.at_short}}](/docs/activity-tracker?topic=activity-tracker-getting-started#getting-started) |       |    | ![Checkmark icon](../../icons/checkmark-icon.svg) | Validate that {{site.data.keyword.at_short}} is tracking how your users and applications interact. |
| [{{site.data.keyword.appid_short_notm}}](/docs/appid?topic=appid-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg) |    | ![Checkmark icon](../../icons/checkmark-icon.svg) | Monitor {{site.data.keyword.appid_short_notm}} for the configurations that you have defined for your applications. |
| [Bare Metal Servers](/docs/security-compliance?topic=security-compliance-ibm-control-library#tpm-bare-metal-txt-modules-goals) |      |     | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of TPM/TXT modules, secure passwords, SSH keys, remote administration, workload protection, and hardware firewalls. |
| [{{site.data.keyword.cloudcerts_short}}](/docs/certificate-manager?topic=certificate-manager-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg) |   | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of private access and the number of days until expiration of a {{site.data.keyword.cloudcerts_short}} instance. |
| [Cloudant](/docs/Cloudant?topic=Cloudant-manage-security-compliance) |    |   | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of your Cloudant instances. |
| [Cloud Databases](/docs/cloud-databases?topic=cloud-databases-manage-security-compliance) \n * Elasticsearch \n * etcd \n * MongoDB \n * PostgreSQL \n * Redis  |     |   | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of the {{site.data.keyword.cloud_notm}} Databases in your account. |   
| [Cloud Internet Services (CIS)](/docs/cis?topic=cis-manage-security-compliance) |      |      | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of inbound traffic, web application firewall, and DDoS protection in {{site.data.keyword.cloud_notm}} Internet Services (CIS). |
| [Cloud Monitoring](/docs/security-compliance?topic=security-compliance-ibm-security-library#cloud-object-storage-buckets-sec-monitoring-goals) |     |     | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of Cloud Monitoring's connection to Cloud Object Storage buckets. |
| [{{site.data.keyword.cloud_notm}} Platform](/docs/overview?topic=overview-manage-security-compliance) \n * Billing \n * Catalog Management \n * IAM Access Groups \n * IAM Identity Service | ![Checkmark icon](../../icons/checkmark-icon.svg) |   | ![Checkmark icon](../../icons/checkmark-icon.svg) | Validate or enforce account settings or permission configurations. |
| [Cloud Shell](/docs/cloud-shell?topic=cloud-shell-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg) |    |	![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of Cloud Shell's location, file upload and download features, and web preview features. |
| [Cloud Object Storage](/docs/cloud-object-storage?topic=cloud-object-storage-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg)| ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of IBM Cloud Object Storage encryption.|
| [Code Engine](/docs/codeengine?topic=codeengine-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg) |	![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of the location of the Code Engine project. | 
| [{{site.data.keyword.registryshort}}](/docs/Registry?topic=Registry-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of {{site.data.keyword.registryshort}}'s credentials, access, and monitoring. |
| [Continuous Delivery](/docs/ContinuousDelivery?topic=ContinuousDelivery-cd-manage-security-compliance) |      |    | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of Continuous Delivery's credentials and access. |
| [Direct Link](/docs/dl?topic=dl-manage-security-compliance) |  ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of {{site.data.keyword.cloud_notm}} Direct Link's connection requests and approvals. |
| [Event Streams](/docs/EventStreams?topic=EventStreams-manage-security-compliance)	| ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of Event Streams' access and encryption. |
| [Hyper Protect Crypto Services](/docs/hs-crypto?topic=hs-crypto-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of Hyper Protect Crypto Services' encryption, access, and policies. |
| [Hyper Protect DBaaS for MongoDB](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg) |		 | ![Checkmark icon](../../icons/checkmark-icon.svg)| Evaluate the configuration of Hyper Protect DBaaS for MongoDB's access and encryption. |
| [Hyper Protect DBaaS for PostgreSQL](/docs/hyper-protect-dbaas-for-postgresql?topic=hyper-protect-dbaas-for-postgresql-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg) |	| ![Checkmark icon](../../icons/checkmark-icon.svg)   | Evaluate the configuration of Hyper Protect DBaaS for PostgreSQL's access and encryption. |
| [{{site.data.keyword.keymanagementserviceshort}}](/docs/key-protect?topic=key-protect-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of {{site.data.keyword.keymanagementserviceshort}}'s access, monitoring, and high availability. |
| [{{site.data.keyword.containershort}}](/docs/containers?topic=containers-security) |      |        | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of {{site.data.keyword.containershort}} Service's policies. |
| [Log Analysis](/docs/log-analysis?topic=log-analysis-adoption#adoption_acc_settings) |       |      | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of Log Analysis's HIPAA and EU supported policies. |
| [{{site.data.keyword.openshiftlong}}](/docs/openshift?topic=openshift-security) |    |    | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of {{site.data.keyword.openshiftshort}}'s policies. |
| [{{site.data.keyword.satelliteshort}}](/docs/security-compliance?topic=security-compliance-ibm-control-library#openshift-sattelite-kubernetes-goals) |      |     | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of {{site.data.keyword.satelliteshort}}'s policies.  |
| [Schematics](/docs/schematics?topic=schematics-access) |     |   | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of Schematics's access, encryption, and monitoring. |
| [{{site.data.keyword.secrets-manager_short}}](/docs/secrets-manager?topic=secrets-manager-manage-security-compliance) |    |     | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of {{site.data.keyword.secrets-manager_short}}'s secret rotation and IAM policies. |
| [Transit Gateway](/docs/transit-gateway?topic=transit-gateway-manage-security-compliance) | ![Checkmark icon](../../icons/checkmark-icon.svg) |      | ![Checkmark icon](../../icons/checkmark-icon.svg) | Evaluate the configuration of Transit Gateway's connection requests and approvals. |
| [Virtual Private Cloud (VPC)](/docs/vpc?topic=vpc-manage-security-compliance) \n * Application Load Balancer for VPC \n * Auto Scale for VPC \n * Block Storage for VPC \n * Security Groups for VPC \n * VPN for VPC |      |      | ![Checkmark icon](../../icons/checkmark-icon.svg)  | Evaluate the configuration of IBM Cloud Virtual Private Cloud's traffic. |
{: caption="Table 1. {{site.data.keyword.cloud_notm}} that can be evaluated by {{site.data.keyword.compliance_short}} " caption-side="top"}

[^rule]: Rules are used to help enforce or monitor the configuration of specific resources.
[^temp]: Templates are used to override the default values that are provided by IBM Cloud during resource configuration.
[^goal]: Goals are used to evaluate a resource configuration against a defined compliance standard.


