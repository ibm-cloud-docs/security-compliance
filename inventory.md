---

copyright:
  years: 2021
lastupdated: "2021-07-12"

keywords: inventory, security, compliance, discovery, run discovery, discover resources

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



# Inventorying resources
{: #inventory}

With the {{site.data.keyword.compliance_full}}, you can view the full list of available resources that are currently being monitored for security and compliance.
{: shortdesc}

## Before you begin
{: #before-inventory}

Before you get started, be sure that you have the following prerequisites.

- An [installed collector](/docs/security-compliance?topic=security-compliance-collector).
- The required level of access to view and manage inventories. To manage an inventory, you need the editor platform role or higher. For more information, see [IAM access](/docs/security-compliance?topic=security-compliance-access-management).


## Creating an inventory
{: #create-inventory}

To create an inventory, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Inventory**. 
3. Click the **New inventory** icon.
4. Give your inventory a meaningful name and description.
5. Select the collectors that you want to use to discover resources. 

  How you structure your inventory depends on how you prefer to view your available resources. Depending on your use case, you might create inventories to meet the following scenarios:

    * An overarching inventory that contains information for all of your cloud environments.
    * An inventory per cloud provider.
    * An inventory per type of resource. 

6. Click **Create**.


## Viewing an inventory
{: #view-inventory}

To view an inventory, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Inventory**. 
3. In the ***Inventory** table, click the name of the inventory that you want to view. 

  A page opens with high-level information of the resources that are available in that inventory.

4. Optional: From your discovery details page, you can choose to view previous versions of your inventory. This view can help you to see how your inventory changes over time.



## Discovering an inventory
{: #discover-inventory}

To discover new resources in an inventory, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Inventory**.
3. From the actions menu for the inventory that you want to view, click **Discover**.


## Deleting an inventory
{: #delete-inventory}

To discover new resources in an inventory, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Inventory**.
3. From the actions menu for the inventory that you want to delete, select the name of the inventory that you want to delete.
4. Click **Delete**.
5. Confirm that you want to delete the inventory by clicking **Delete** again. 

