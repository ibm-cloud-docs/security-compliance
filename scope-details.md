---

copyright:
  years: 2021
lastupdated: "2021-10-13"

keywords: scopes, accounts, resources, environments

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

# Viewing scope details
{: #view-scope}

You can view the details of your existing scopes and create a new mapping by using the {{site.data.keyword.compliance_short}} UI.
{: shortdesc}

##  Seeing scopes in more detail
{: #detail-scope}

To view the details of the scopes that you create, you can complete the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, under **Manage Posture**, click **Configure > Scopes**.
3. From the **Scopes** table, select the scope that you want to see in more detail. A new page opens that displays which credentials and collectors are used in the scope, as well as an inventory of the resources that are available in the scope.
4. Click **Event history** to see the historical archive of each scan that has been run on the scope. If there are additional details available for the scan, the event time is clickable.

You can run a one-time on-demand scan from the **Actions > Scan** drop down on the scope details page.
{: tip}


## Creating a new resource mapping
{: #resource-mapping}

When an Nmap scan is run on on-premises resources, occasionally a resource is misidentified. In order to override the mapping that is made by the scan, you can create a new mapping in the UI. 

1. From the scope details page, select **Resource mapping** from the **Actions** drop-down.
2. Click **Create**.
3. Create a mapping for a virtual machine by selecting a **Virtual machine**, **Object**, **Operating system**, and **Vendor** for your resource. The VM and object are required fields.
