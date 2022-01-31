---

copyright:
  years: 2022
lastupdated: "2022-01-31"

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


## Understanding credential mapping
{: #why-map-credentials}

Your scope might require that the collector use more than one set of credentials to complete a scan. For example, you might have a collector that gathers facts from both databases and servers that require different credentials to access. In those scenarios, you need to map additional permissions to the credentials that are associated with your scope. 
{: shortdesc}


### Scenario 1 - Mapping credentials to resources
{: #map-resource}

When resources such as an instance of {{site.data.keyword.at_short}} or Virtual Private Cloud are scanned, additional permissions must be provided in order for the collector to access their configuration data. The additional permissions are mapped to an existing credential that is already attached to your scope. To see which resources require additional permissions and how to provide them, see the following table.

| Resource | Mapping |
|:---------|:-------------------|
| {{site.data.keyword.at_short}} | `AT=service_key` |
| Virtual Private Cloud (VPC) | `VPC=testing-vpc` |
| Server | `IP=123.45.67.89` |
| {{site.data.keyword.cloud_notm}} {{site.data.keyword.containershort}} Cluster | `cluster=cluster_id` |
{: caption="Table 1. Resource specific path inputs" caption-side="top"}


### Scenario 2 - Providing additional parameters
{: #map-nested-resource}

Occasionally, there is additional information that is required for a resource. In some cases, additional configuration data must be gathered from resources that are contained within a larger resource. If this is the case, additional fields are displayed in the {{site.data.keyword.compliance_short}} UI when you are mapping credentials. To understand which resources give you the option to provide additional details and the format in which to provide them, see the following table. 

| Resource | Parameter | Mapping |
|:---------|:-------------|:-------------------|
| {{site.data.keyword.containershort}} Cluster | Storage class | `cluster_storage_class_string` |
| {{site.data.keyword.containershort}} Cluster | Namespace | `cluster_namespace_string` |
{: caption="Table 2. Sub resource specific path inputs" caption-side="top"}


## Before you begin
{: #before-map-credentials}

Before you get started, be sure that you have the required level of access to view and manage credentials. To map a credential, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).


## Mapping credentials
{: #howto-map-credentials}

To map additional permissions, the credential must already added to the service. If you haven't yet added a credential, start with [Managing credentials](/docs/security-compliance?topic=security-compliance-credentials) and then return to the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the **Manage posture** section of the navigation, click [**Configure > Scopes**](https://{DomainName}/security-compliance/scopes).
3. Select the scope that you want to map credentials for.
4. In the **Credentials** section of the navigation, click **Add**. A side panel appears. 
5. Select the credential that you want to add from the list under **Credential**.
6. Select the **Remediation Credential**, if applicable. 
7. Provide a path to an IP address, machine, or resource that you want to access with your selected credential in the **Resource** field. For help with formatting the additional credentials, see the scenarios in [Understanding credential mapping](#why-map-credentials).

   When additional parameters are required for a resources, an input box is displayed for you to provide the details.
   {: note}

8. Provide a **Proxy**, if applicable.
9. Click **Add**.


You can also choose to edit or delete an existing entry if you made a mistake or no longer need to use that credential with that scope.
{: tip}
