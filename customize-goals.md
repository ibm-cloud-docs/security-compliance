---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-10"

keywords: goals, parameters, customize parameters, customize goals, security and compliance,

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

# Customizing goals
{: #custom-goals}

With the {{site.data.keyword.compliance_full}}, you can update the default parameters that are associated with the goals within each predefined profile. When you change a parameter, it affects all of the goals in that profile.
{: shortdesc}


## Before you begin
{: #before-custom-goals}

Before you get started, be sure that you have the required level of access to customize goal parameters. To edit parameters, you need the editor platform role or higher for the {{site.data.keyword.compliance_short}}. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).



## Editing goal parameters
{: #edit-goals}

To update the default parameters for the goals that you use, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Settings > Goal parameters**.
3. In the **Goal parameters** table, select **Input config parameters**. 
4. Click the **Edit parameters** icon.
5. From the list of profiles, click the name of the profile that you want to update.

   Each table row expands so that you can review the configuration information of each profile. 
6. To save your changes, click **Update**.

If you make an accidental change, you can click **Revert** to return all of the profiles back to default.
{: tip}







