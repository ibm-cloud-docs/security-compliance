---

copyright:
  years: 2022
lastupdated: "2022-10-03"

keywords: integrations, integrated services, integrations for rules, rules and goals, cloud services, Business Partners

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

# Available integrations
{: #integrations}

Integrations are connections between the {{site.data.keyword.compliance_full}} and various services. The services that you can integrate with the {{site.data.keyword.compliance_short}} help you manage the security of your account and to connect to your instances of our business partner's services. 
{: shortdesc}


## Business parters
{: #integration-business-partners}

You can integrate Tanium&trade; Comply to view all your compliance data in one location in the same format. To learn more about Tanium Comply, see the product's [documentation](https://docs.tanium.com/comply/comply/index.html){: external}.

### Connecting Tanium
{: #integration-tanium}

When you finish importing the data from your Tanium instance to the {{site.data.keyword.compliance_short}}, a validation scan is run to help you identify any potential issues in your resources. Within the {{site.data.keyword.compliance_short}}, in the format that you choose during setup, you can evaluate the potential issues by control or by resource, view your compliance score, and see a history of scans that were previously run on your data. [Learn more](/docs/security-compliance?topic=security-compliance-setup-tanium).


## Resources
{: #integration-resources}

You can integrate the [{{site.data.keyword.openshiftlong}} Compliance Operator](https://github.com/openshift/compliance-operator){: external} (OSCO) to scan your clusters against defined OSCO profiles.


### Connecting OSCO
{: #integration-osco}

When you deploy the OSCO, you can scan your resources with a bundle of predefined profiles that is automatically installed and available to you. After you integrate the {{site.data.keyword.openshiftlong}} clusters with the {{site.data.keyword.compliance_short}}, you can see the details of your scan, including any potential issues and your compliance score. You can also view a history of previous scans. [Learn more](/docs/security-compliance?topic=security-compliance-setup-osco).




## Integrated {{site.data.keyword.cloud_notm}} services for enhancing data security
{: #integration-ibm-cloud}

You can integrate the capabilities of various IBM Cloud services with the {{site.data.keyword.compliance_short}} to enhance the security of your data. By managing the connection between the following services and the {{site.data.keyword.compliance_short}}, you can assign required access policies to the users in your account, notify users of critical events, and encrypt your data with customer-managed keys. After you complete the integration, you can take these actions by using the UI of your service instance.

| Service | Description | 
| -------- | ---------- |
| [Event Notifications](/docs/security-compliance?topic=security-compliance-event-notifications) | Send notifications of Posture Management and Admin events in the {{site.data.keyword.compliance_short}} to other users or human destinations by using email, SMS, or other supported delivery channels. |
| [Hyper Protect Crypto services](/docs/security-compliance?topic=security-compliance-mng-data&interface=ui#data-encryption) | Encrypt your data by using Hyper Protect Crypto Services, which is a single-tenant key management service that is backed by a FIPS140-2 level 4 certified Hardware Security Model (HSM). |
| [IAM](/docs/security-compliance?topic=security-compliance-access-management) | Assign access policies with a defined platform IAM role to every user that accesses the {{site.data.keyword.compliance_short}} in your account. |
| [{{site.data.keyword.keymanagementserviceshort}}](/docs/security-compliance?topic=security-compliance-mng-data) |  Encrypt your data by using customer-managed keys that are supported by using {{site.data.keyword.keymanagementserviceshort}}. |
{: caption="Table 1. Integrated services for enhancing data security" caption-side="top"}

