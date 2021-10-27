---

copyright:
  years: 2021
lastupdated: "2021-10-13"

keywords: credentials, security and compliance, collector access, collector communication, resource scan, configuration scanning, credentials stored

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
{:release-note: data-hd-content-type='release-note'}

# Mapping additional credentials
{: #map-credentials}

You can map additional credentials to your scope if you need the {{site.data.keyword.compliance_short}} collector to use multiple credentials to complete a scan.
{: shortdesc}

## Understanding scenarios for mapping additional credentials 
{: #why-map-credentials}

You might encounter various scenarios within which you need to map additional credentials to your scope. 
{: shortdesc}

Occasionally, you might have a scope that requires the collector use more than one set of credentials to complete a scan. Collectors use multiple credentials when users have credentials that are used for individual databases or servers that need to be scanned. Those scenarios include the use of Activity Tracker, Virtual Private Cloud, and a proxy server that uses an IP address.

### Scenario 1 - Activity Tracker
{: #map-at}

If you enable a control that measures a specific number of days, it is monitored by using Activity Tracker. To enable Activity Tracker, you must create a new credential and map it to your scope. To [create a new credential](/docs/security-compliance?topic=security-compliance-credentials), you must use Activity Tracker's GUID and `Service_key` as the username and password. 

### Scenario 2 - Virtual Private Cloud (VPC)
{: #map-vpc}

In this scenario, you are a developer and you want to validate your IBM cloud resources against defined best practices. The security requirements of your organization specify that you must install the collector on infrastructure that is owned by your organization. To meet your organizational requirements, you decide to use [IBM Cloud Virtual Private Cloud](/docs/security-compliance?topic=security-compliance-ibm-customer-collector). 

If you install the collector on your Virtual Private Cloud, in order to scan your IBM Cloud resources, you need to map additional credentials to your scope. You must provide the credentials with `read` access that are associated with your resources on IBM Cloud. Additionally, you must provide the credentials to access the VPC. 

### Scenario 3 - Proxy IP 
{: #map-ip}

In this scenario, you are a developer. As an additional protection, your organization wants you to use an intermediary between the collector and your resources. To meet the requirement, you choose to [configure a proxy server by using an IP address](/docs/security-compliance?topic=security-compliance-collector-manual#collector-proxy). To scan your resources with {{site.data.keyword.compliance_short}}, you need to provide the credentials with `read` access that are associated with your resources. You must also provide the credentials that are associated with your proxy. 



## Before you begin
{: #before-map-credentials}

Before you get started, be sure that you have the required level of access to view and manage credentials. To map a credential, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).


## Adding credentials to a scope
{: #howto-map-credentials}

To map a credential, it must exist in the service. To map credentials to your scope, complete the following steps. 

You can also choose to edit or delete an existing entry if you made a mistake or no longer need to use that credential with that scope.
{: tip}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the **Manage posture** section of the navigation, click **Configure > Scopes**.
3. Select the scope that you want to map credentials for.
4. In the **Credentials** section of the navigation, click **Add**. A side panel appears. 
5. Select the credential that you want to add from the list under **Credential**.
6. Select the **Remediation Credential**, if applicable. 
7. Provide a path to an IP address, machine, or resource that you want to access with your selected credential in the **Resource** field. If you are using Activity Tracker, Virtual Private Cloud, or a proxy server that uses an IP address, complete the steps in the following table, based on the appropriate scenario.

   | Scenario | Resource specification |
   |:-------|:---------|
   | Activity Tracker | `AT=service_key` |
   | Virtual Private Cloud (VPC) | `VPC=testing-vpc` |
   | Proxy IP | `IP=123.45.67.89` |
   {: caption="Table 1. Resource specific path inputs" caption-side="top"}

8. Select a **Proxy**, if applicable.
9. Click **Add**.

