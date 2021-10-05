---

copyright:
  years: 2021
lastupdated: "2021-10-05"

keywords: Terraform for {{site.data.keyword.compliance_short}}

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


# Setting up Terraform for {{site.data.keyword.compliance_short}}
{: #terraform-setup} 

Terraform on {{site.data.keyword.cloud_notm}} enables predictable and consistent provisioning of {{site.data.keyword.cloud_notm}} services so that you can rapidly build complex, multi-tier cloud environments following Infrastructure as Code (IaC) principles. Similar to using the {{site.data.keyword.cloud_notm}} CLI or API and SDKs, you can automate the creation, update, and deletion of {{site.data.keyword.compliance_short}} resources by using HashiCorp Configuration Language (HCL).
{: shortdesc}

Looking for a managed Terraform on {{site.data.keyword.cloud_notm}} solution? Try out [{{site.data.keyword.bplong}}](/docs/schematics?topic=schematics-getting-started). With {{site.data.keyword.bpshort}}, you can use the Terraform scripting language that you are familiar with, but you don't have to worry about setting up and maintaining the Terraform command line and the {{site.data.keyword.cloud_notm}} Provider plug-in. {{site.data.keyword.bpshort}} also provides pre-defined Terraform templates that you can easily install from the {{site.data.keyword.cloud_notm}} catalog.
{: tip}

## Before you begin
{: #before-terraform}


Before you get started, be sure that you have the [required access](/docs/security-compliance?topic=security-compliance-access-management) to create and work with {{site.data.keyword.compliance_short}} resources. If you have not yet worked with Terraform, you can follow the [Terraform on {{site.data.keyword.cloud_notm}} getting started tutorial](/docs/ibm-cloud-provider-for-terraform?topic=ibm-cloud-provider-for-terraform-getting-started) to install the Terraform CLI and configure the {{site.data.keyword.cloud_notm}} Provider plug-in.

## Creating a configuration file
{: #create-file}

When you work with Terraform, you create a file that is used to define the configuration for the resources that you want to work with. For more information, see the [Terraform documentation](https://www.terraform.io/docs/language/index.html){: external}.


To get started, create a Terraform configuration file that is named, `main.tf`. In this file, you add the configuration to view all of the scopes that are available in your account by using HashiCorp Configuration Language (HCL). 
   
```terraform
data "ibm_scc_posture_scopes" "list_scopes" {
  scope_id = "1"
}
```
{: codeblock}


## Viewing your resource
{: #view-resource}

After you've defined your configuration file, you're ready to apply the configuration to view your resources.

1. Initialize the Terraform CLI.

   ```terraform
   terraform init
   ```
   {: pre}

2. Create a Terraform execution plan. The Terraform execution plan summarizes all the actions that need to be run to create the resource in your account.

   ```terraform
   terraform plan
   ```
   {: pre}

3. View the scopes that are available in your profile.

   ```terraform
   terraform apply
   ```
   {: pre}


## What's next?
{: #terraform-setup-next}

Now that you successfully viewed the scopes that are available in your account with Terraform on {{site.data.keyword.cloud_notm}}, you can visit the [{{site.data.keyword.compliance_short}} Terraform registry](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/scc){: external} to perform additional tasks using Terraform.
