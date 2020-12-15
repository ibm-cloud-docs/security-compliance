---

copyright:
  years: 2020
lastupdated: "2020-12-15"

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


# Managing scopes
{: #scopes}

When you're working with the {{site.data.keyword.compliance_short}}, you can narrow the focus of your scans to a specific environment, region, or even resource. By creating scopes, you can determine your security and compliance score across a specific area of your business. 
{: shortdesc}


## Before you begin
{: #before-scope}

Before you get started, be sure that you have the following prerequisites.

- An [installed collector](/docs/security-compliance?topic=security-compliance-collector).
- The required level of access to view and manage scopes. To manage scopes, you need the editor platform role or higher. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).




## Creating a scope
{: #create-scope}

To narrow the focus of your scans, create a scope by using the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Scopes**.
3. Click **Create**.
4. Give your scope a name and description.

  Be sure to give a descriptive name as you use this field later to configure scans and remediation.

5. Select an environment. Options include AWS, Azure, IBM, GCP, and On-prem.
6. Select the **Collector** that you want to use.
7. Select the **Credentials** that match the collector that you selected in the previous step.
8. Click **Next**.
9. Select the resources that you want to scan.
10. Click **Create**.


If you're working with a scope that requires more than one set of credentials to access the resources within it, be sure to [map your credentials](/docs/security-compliance?topic=security-compliance-credentials)



## Viewing scopes
{: #view-scope}

To view a list of your available scopes, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Scopes**.
3. Click the **Scopes columns** icon to adjust the information that is displayed in the table.
4. To see the details of a specific scope, select a scope and click the **Edit scope** icon. A new page opens that contains the information about the previous scans and events that have occurred for that scope.



## Editing a scope
{: #edit-scope}

If you need to update the resources that are scanned as part of a scope, you can edit an existing scope. However, you cannot update an environment that the scope is associated with. If you want to change an environment, create a new scope.


1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Scopes**.
3. Select the scope that you want to edit in the table.
4. Click the **Edit scope** symbol.
5. Optional: Update the general details of your scope, such as the name or description. 
6. Click **Next**.
7. Optional: Update the resources that you want to scan.
8. Click **Update**.



## Deleting a scope
{: #delete-scope}

If you no longer need to scan a particular scope, you can delete it.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Scopes**.
3. Select the scope that you want to delete.
4. From actions menu in the row of the scope that you want to delete, click **delete scope**.
5. To verify that you understand that any scheduled scans that are associated with that scope are canceled, click **Delete**.

The scope is not fully deleted, but is rendered inactive. You will still be able to access the history of the scans.
{: note}
