---

copyright:
  years: 2020, 2022
lastupdated: "2022-12-06"

keywords: scan ibm resources, compliance scan, evaluation, evaluate compliance

subcollection: security-compliance

content-type: tutorial
services: security-compliance
completion-time: 20m

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


# Step 2: Discover your available resources
{: #ibm-discover}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance"}
{: toc-completion-time="20m"}

This tutorial is part 2 of a 4-part tutorial series that guides you through configuring the {{site.data.keyword.compliance_short}} to scan your {{site.data.keyword.cloud_notm}} resources for compliance.

Target the resources that you want to validate by creating a scope and scheduling a scan. To create a scope, select an environment, select your collector, and select the credentials that are required to access your targeted resources. Then, you can schedule a scan to discover and validate your resource configurations.

![The image shows the flow of user actions for this tutorial series](../images/credentials-tutorial.svg){: caption="Figure 1. Tutorial parts" caption-side="bottom"}


## Before you begin
{: #ibm-discover-before}

To complete this tutorial, you must complete [part 1](/docs/security-compliance?topic=security-compliance-ibm-credential) first. 


## Create a collector
{: #ibm-discover-collector}
{: step}

A collector is a software module that is packaged as a container image that scans your resources and validates their configurations. To learn more about collectors and how the communication takes place, see [What is a collector?](/docs/security-compliance?topic=security-compliance-collector).


1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and compliance** to access {{site.data.keyword.compliance_short}}.
2. On the [**Manage Posture > Configure > Collectors** page](/security-compliance/collectors) of the {{site.data.keyword.compliance_short}}, click **Create**.
3. Give your collector a name and description. Click **Next**.
4. For **Managed by**, select **IBM**.

   IBM-managed collectors are created on IBM-owned infrastructure and are maintained by the {{site.data.keyword.compliance_short}}. If your organization doesn't allow managed collectors, you can always create and install your own. For more information, see [Manually administering collectors](/docs/security-compliance?topic=security-compliance-collector-manual). Or, see the tutorials on how to install your collector on [{{site.data.keyword.containershort}}](/docs/security-compliance?topic=security-compliance-collector-iks) or [Virtual Private Cloud](/docs/security-compliance?topic=security-compliance-collector-vpc).
   {: tip}


## Discover your resources
{: #ibm-discover-scan}
{: step}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In **Manage Posture > Configure > Scopes**, click **Create**.
3. Give your scope a name and description. Then, click **Next**.
4. Select **{{site.data.keyword.cloud_notm}}** from the **Environment** menu.
5. From the **Credentials** menu, select the credential that you previously added to the service in part 1. Then, click **Next**.
6. From the table, select the [collector](/docs/security-compliance?topic=security-compliance-collector) that you created in the previous step. Then, click **Next**.
7. Create an attachment between your scope and profile by scheduling a scan. 

   1. Give your scan a name and description.
   2. Select **Validation** as a **Scan type**.
   3. From the **Profile** menu, select the profile that you want to use to evaluate your configuration.

      If your scope includes a deployment of either the [{{site.data.keyword.vpc_full}} reference architecture](/docs/framework-financial-services?topic=framework-financial-services-vpc-architecture-about) for the {{site.data.keyword.cloud_notm}} for Financial Services™, then select the latest version of the {{site.data.keyword.cloud_notm}} for Financial Services profile. This profile maps a tailored set of SCC goals to the [control requirements](/docs/framework-financial-services#framework-control-requirements) in the {{site.data.keyword.framework-fs_full}}. You can also choose to create a [custom profile](/docs/security-compliance?topic=security-compliance-custom-profiles) that contains the specific subset of goals from a profile that you want to evaluate your resources for. 
      {: note}

   4. **Enable** or **Disable** the profiles that are associated with your integrated resources. To see this option, you must have the [OSCO integration enabled](/security-compliance/integrations){: external}.

      If you are working with any {{site.data.keyword.openshiftshort}} resources, you must enable the [OSCO integration](/security-compliance/integrations){: external} and then enable profiles during this step in order for those resources to be evaluated.
      {: note}

   5. The scan automatically occurs once when the scope is created. To schedule additional scans, select the **Frequency** at which you want them to be run and the date when you want the scan to **End**.

8. Click **Next** and review your selections. Then, click **Create**.


## Next steps
{: #next-2}

Next, you're ready to [complete part 3](/docs/security-compliance?topic=security-compliance-ibm-credential-map) by mapping additional permissions that are required to access your resources configuration data.

