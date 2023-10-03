---

copyright:
  years: 2023
lastupdated: "2023-10-03"

keywords: terraform, {{site.data.keyword.compliance_short}}, terraform setup, create instance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Setting up Terraform for {{site.data.keyword.compliance_short}}
{: #terraform-setup}

Terraform on {{site.data.keyword.cloud_notm}} enables predictable and consistent creation of {{site.data.keyword.cloud_notm}} services, so that you can rapidly build complex, multitier cloud environments that follow Infrastructure as Code (IaC) principles. Similar to using the {{site.data.keyword.cloud_notm}} CLI or API and SDKs, you can automate the creation, update, and deletion of your {{site.data.keyword.compliance_short}} instances by using HashiCorp Configuration Language (HCL).
{: shortdesc}

Looking for a managed Terraform on {{site.data.keyword.cloud_notm}} solution? Try out [{{site.data.keyword.bplong}}](/docs/schematics?topic=schematics-getting-started). With {{site.data.keyword.bpshort}}, you can use the Terraform scripting language that you are familiar with. But you don't need to worry about setting up and maintaining the Terraform command line and the {{site.data.keyword.cloud_notm}} Provider plug-in. {{site.data.keyword.bpshort}} also provides pre-defined Terraform templates that you can easily install from the {{site.data.keyword.cloud_notm}} catalog.
{: tip}

## Installing Terraform and configuring resources for {{site.data.keyword.compliance_short}}
{: #install-terraform}

Before you can create an authorization by using Terraform, make sure that you completed the following steps:

* Make sure that you have the [required access](/docs/security-compliance?topic=security-compliance-assign-roles) to create and work with {{site.data.keyword.compliance_short}} resources.
* Install the Terraform CLI and configure the {{site.data.keyword.cloud_notm}} Provider plug-in for Terraform. For more information, see the tutorial for [Getting started with Terraform on {{site.data.keyword.cloud_notm}}](/docs/ibm-cloud-provider-for-terraform?topic=ibm-cloud-provider-for-terraform-getting-started). The plug-in abstracts the {{site.data.keyword.cloud_notm}} APIs that are used to complete this task.
* Create a Terraform configuration file that is named `main.tf`. In this file, you define resources by using HashiCorp Configuration Language. For more information, see the [Terraform documentation](https://developer.hashicorp.com/terraform/language){: external}.


1. After you finish building your configuration file, initialize the Terraform CLI. For more information, see [Initializing Working Directories](https://developer.hashicorp.com/terraform/cli/init){: external}.

   ```terraform
   terraform init
   ```
   {: pre}

2. Create a {{site.data.keyword.compliance_short}} instance by using the the [UI](/docs/security-compliance?topic=security-compliance-getting-started), API, or CLI.

    * Optionally, you can create a data source to retrieve information about an existing {{site.data.keyword.compliance_short}} instance from {{site.data.keyword.cloud_notm}}, by running the following command. 

        ```terraform
        "ibm_scc_instance_settings" "scc_instance_settings_tf" {
            instance_id              = "data-source-security-compliance-instance"
        }
        ```
        {: codeblock}

   For a complete list of the supported attributes, see [`ibm_resource_instance`](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/data-sources/resource_instance){: external}.

3. Provision the resources from the `main.tf` file. For more information, see [Provisioning Infrastructure with Terraform](https://developer.hashicorp.com/terraform/cli/run){: external}.

   1. Run `terraform plan` to generate a Terraform execution plan to preview the proposed actions.

        ```terraform
        terraform plan
        ```
        {: pre}

   2. Run `terraform apply` to create the resources that are defined in the plan.

    ```terraform
    terraform apply
    ```
    {: pre}

4. Define local values for your {{site.data.keyword.compliance_short}} instance to be used when you are creating resources.

    ```terraform
        locals {
            instance_id = data.ibm_resource_instance.scc_resource_instance.guid
            region = data.ibm_resource_instance.scc_resource_instance.location
        }
    ```
   {: pre}

5. From the {{site.data.keyword.cloud_notm}} resource list in the UI, select the {{site.data.keyword.compliance_short}} instance that you created and note the instance ID.
6. Verify that the access policy is successfully assigned. For more information, see [Reviewing assigned access in the console](/docs/account?topic=account-assign-access-resources#review-your-access-console).


## What's next?
{: #terraform-setup-next}

Now that you successfully created your first {{site.data.keyword.compliance_short}} service instance with Terraform on {{site.data.keyword.cloud_notm}}, you can review the {{site.data.keyword.compliance_short}} resources and data sources in the [Terraform registry](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/scc_rule){: external}. You can also review how to manage your {{site.data.keyword.compliance_short}} resources by following the Terraform steps that are included in the How to section. For example, you can follow the directions on how to create [custom libraries](/docs/security-compliance?topic=security-compliance-custom-library&interface=api&code=curl) by using Terraform.

