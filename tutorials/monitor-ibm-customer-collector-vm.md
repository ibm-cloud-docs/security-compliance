<tutorial-prod>---

copyright:
  years: 2020, 2022
lastupdated: "2022-05-16"

keywords: collector install, vpc collector, monitor resources, security, compliance

subcollection: security-compliance

content-type: tutorial
services: security-compliance, vpc
completion-time: 30m

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

# Monitor {{site.data.keyword.cloud_notm}} resources with a customer-managed collector on a VM
{: #ibm-customer-collector}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, vpc"}
{: toc-completion-time="30m"}

In this tutorial, you learn how to use {{site.data.keyword.compliance_full}} to automate the checks that your organization must complete to prove compliance.
{: shortdesc}

To scan and validate your resource configurations, a [collector](/docs/security-compliance?topic=security-compliance-collector) is used. Collectors act as an intermediary between your resources and the {{site.data.keyword.compliance_short}}, where the gathering and validation of your configurations is done. In this scenario, you are a developer who wants to validate your {{site.data.keyword.cloud_notm}} resources against defined best practices. Due to the security requirements of your organization, you are required to install the collector on infrastructure that is owned by your organization. You decide to use {{site.data.keyword.cloud_notm}} Virtual Private Cloud. 

This tutorial must be completed within 24 hours or the collector registration key expires.
{: note}


## Before you begin
{: #ibm-customer-collector-before}

To complete this tutorial, be sure that you have the following requirements:

* A Pay-As-You-Go or Subscription [{{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started) where you are the owner or have [full **Administrator** access](/docs/account?topic=account-assign-access-resources)
* Docker
* Resources in your {{site.data.keyword.cloud_notm}} account
* An instance of VPC in your {{site.data.keyword.cloud_notm}} account



## Set up your Virtual Private Cloud (VPC) Infrastructure
{: #ibm-customer-collector-vpc}
{: step}

Virtual Private Cloud gives you the ability to establish your own private cloud-like computing environment on shared public cloud infrastructure. You define and control a virtual network that is logically isolated from all other public cloud tenants. 

If you already have a VPC that is configured with an SSH key, a VSI, and a floating IP, you can skip to step 2.
{: note}

1. Create a VPC.

   1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> VPC Infrastructure > Network > [VPCs](https://{DomainName}/vpc-ext/network/vpcs){: external}**.
   2. Click **Create**.
   3. Give your VPC a meaningful name. For example, `compliance-vpc`. Then, ensure that the VPC settings are configured the way that you want them.
   4. Optional: Click the **Edit** icon to rename your automatically generated subnets to give them a meaningful name. For example, `compliance-vpc-subnet-1`.
   5. Review your total estimated cost and click **Create Virtual Private Cloud**. If you don't immediately see your new VPC in the table, refresh the page.

2. Create an SSH key.

   1. In the VPC navigation, click **Compute > [SSH keys](https://{DomainName}/vpc-ext/compute/sshKeys) > Create**.
   2. Give your SSH key a meaningful name. For example, `compliance-vpc-ssh-key`.
   3. Paste your public key into the **Public key** field and then click **Add SSH key**.

      Can't find or don't have a public key? For help, see [Locating or generating your SSH key](/docs/vpc?topic=vpc-ssh-keys#locating-ssh-keys).
      {: tip}

3. Create a VSI.

   1. In the navigation, click **Compute > [Virtual server instances](https://{DomainName}/vpc-ext/compute/vs) > Create**.
   2. Give your VSI a meaningful name. For example, `compliance-vpc-vsi`. Then, ensure that the settings are configured the way that you want them.
   3. For **Operating System**, select **Ubuntu Linux**.
   4. Select the **Profile** size that you want to work with. The recommended size is `bx2-2x8` (2 vCPUs, 8 GB RAM, and 4GBPS).
   5. Select the **SSH key** that you created in the previous step.
   6. Select the VPC that you previously created.
   7. Click **Create Virtual Server Instance**. If you don't immediately see your new VSI in the table with a status of **Running**, refresh the page.

4. Reserve a Floating IP.

   1. Click **Network > [Floating IPs](https://{DomainName}/vpc-ext/network/floatingIPs) > Create**.
   2. Give your Floating IP a meaningful name. For example, `compliance-vpc-floating-ip`.
   3. From the **Resource to bind** dropdown, select the VSI that you created in the previous step.
   4. Click **Reserve IP**.

5. By using the Floating IP that you created, SSH into your VSI. When prompted, type yes and click **Enter** to create the connection.

   ```sh
   ssh root@Floating_IP
   ```
   {: codeblock}

6. Get your latest configuration information.
  
   ```sh
   sudo apt-get update
   ```
   {: codeblock}

7. Install Docker Compose.

   ```sh
   sudo apt-get install docker-compose
   ```
   {: codeblock}


## Creating a collector
{: #ibm-customer-collector-create}
{: step}

A collector is a container image that you install on your Virtual Private Cloud. The collector image is responsible for gathering your configuration information and validating it.

1. Go to the [**Manage posture > Configure > Collectors**](https://{DomainName}/security-compliance/collectors) tab and click **Create**.
2. Give your collector a meaningful name and description. For example, `ibm-cloud-collector`. 
3. Click **Next**.
4. Select **Customer** to install the collector on your organization's infrastructure.
5. **UBI** is selected as the default container **image type**. Alternatively, you can choose **Ubuntu**.

   Universal Base Images (UBI) are OCI-compliant container-based operating system images. They cannot be used with Windows OS. Ubuntu images are disk-images that are designed to run on the Ubuntu OS. Ubuntu images are not compliant with the Federal Information Processing Standards (FIPS).
6. For **Endpoint type**, select **Public**.  To allow the collector to use a private IP that is accessible only through the IBM Cloud private network, choose **Private**. 
7. Click **Create**.
8. On the **Download collector** panel that appears after you create a collector, select **Download shell script**, and then click **Download**. The registration key is required.


## Installing a collector
{: #customer-collector-install-vm}
{: step}


1. Transfer the collector installation file that you downloaded in the previous step to your VSI. If you are using VIM in your command line, you can use the following steps as an example.

   1. Locally, open the **initiate_collector.sh** file that you downloaded and copy its contents.
   2. From your command line, open the VIM editor.

      ```sh
      vi initiate_collector.sh
      ```
      {: codeblock}

   3. Press **i** to insert content.
   4. Paste the content that you previously copied.
   5. Press the **Escape** key to exist edit mode.
   6. Type `:wq` and click **Enter**. to save and exist VIM.
   7. To confirm that the file was created, run the `ls` command.

2. Change the permissions of the `initiate_collector.sh` file to allow it to run.

   ```sh
   chmod +x initiate_collector.sh
   ```
   {: codeblock}

3. Install the collector by running the following command. When prompted, use the table as a guide for answering the questions.

   ```sh
   ./initiate_collector.sh
   ```
   {: codeblock}

   | Prompt | Response |
   |:-------|:---------|
   | Data Path | Provide the data path to your host machine. For example, `/root/compliance/`. |
   | Nmap validation | No - This tutorial is designed to focus on cloud resources. You only need to run an Nmap validation if your resources exist behind a firewall. |
   | Registration key | Provide the registration key. This can be found in the table on the **Collectors** page of the {{site.data.keyword.compliance_short}} UI. Expand the details for the collector that you want to register and copy the key. |
   {: caption="Table 1. Collector installation prompts" caption-side="top"}

4. On the **Collectors** page of the {{site.data.keyword.compliance_short}} UI, click **Approval required** to approve the collector for use. Wait a few minutes and refresh the page. The collector status updates to **Active**.

## Grant your collector access to your resources
{: #ibm-customer-collectors-access}
{: step}

To run the scan, the collector must have *read* access to the resources that you want to scan. This access is granted through an {{site.data.keyword.cloud_notm}} API key. For more information about the security of your credentials, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).

1. Create an {{site.data.keyword.cloud_notm}} API key for a service ID.

   1. Go to [**Manage > Access (IAM) > Service IDs**](https://{DomainName}/iam/serviceids/). If you don't already have a service ID that you want to use, click **Create** and provide a name and description. Click **Create** again.
   2. Select the service ID that you want to use and click **API keys**.
   3. Click **Create** and give your API key a meaningful name and description. For example, `compliance-api-key` and this key is used by the collector to validate my resource configurations. Click **Create**.
   4. Click **Copy** or **Download** to save your key.

2. Add the API key to the {{site.data.keyword.compliance_short}} as a credential.

   1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and compliance** to return to the {{site.data.keyword.compliance_short}}.
   2. In the navigation, click [**Manage posture > Configure > Credentials**](https://{DomainName}/security-compliance/credentials).
   3. Click **Create**.
   4. Give your credential a meaningful name. For example, `ibm-cloud-compliance`.
   5. Select **Discovery / fact collection** as the purpose of the credential and then click **Next**.
   6. Select **{{site.data.keyword.cloud_notm}}** as the type of credential.
   7. Paste the API key that you created in the previous step and click **Create**.

## Target your resources and validate your configurations
{: #ibm-customer-collector-scope}
{: step}

Target the resources that you want to validate by creating a scope and scheduling a scan. To create a scope, select an environment, select your collector, and select the credentials that are required to access your targeted resources. Then, you can schedule a scan to discover and validate your resource configurations.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In **Manage Posture > Configure > Scopes**, click **Create**.
3. Give your scope a name and description and then click **Next**.

   Be sure to give a detailed name as you use this field later to configure scans and remediation.
4. Select an **Environment** from the drop-down list.

   If you choose On-premises, you can select from multiple options to discover your resources. For example, you can [schedule a discovery scan](/docs/security-compliance?topic=security-compliance-schedule-scan), import resources from a file, or connect to a third party. Supported format for imported files is  `.json`. The maximum file size is 30 MB.
5. From the **Credentials** drop-down, select a credential that you previously added to the service and then click **Next**.

   If you have not yet added a credential, you can use the following steps to add one and then select it from the drop-down.

   1. Click **Create**. A side panel opens.
   2. Provide a name and description.
   3. Select a **Purpose** and then click **Next**.
   4. Select a **Credential type**.
   5. Provide the information that is requested. For more information about each type of secret, see [Understanding credentials](/docs/security-compliance?topic=security-compliance-permissions#understand-credentials).
   6. Click **Create** and repeat as necessary.

6. From the table, select the [collector](/docs/security-compliance?topic=security-compliance-collector) or collectors that you want to use to gather configuration data and then click **Next**.
7. Create an attachment between your scope and profile by scheduling a scan. 

   1. Give your scan a name and description.
   2. Select a **Scan type**.
   3. From the **Profile** drop-down, select the profile that you want to use to evaluate your configuration.
   4. **Enable** or **Disable** the profiles that are associated with your integrated resources. For more information about integrations see the [integrations tab of the UI](/security-compliance/integrations){: external}.

      If you are working with any {{site.data.keyword.openshiftshort}} resources, you must enable the [OSCO integration](/security-compliance/integrations){: external}  and then enable profiles during this step in order for your resources to be evaluated.
      {: note}

   5. If applicable: Select a remediation type.

      Only some environments are configured to provide automatic remediation. For more information, see [Remediating issues](/docs/security-compliance?topic=security-compliance-remediation).

   6. The scan will automatically occur when the scope is created. To schedule additional scans select the **Frequency** at which you want them to be run and the date when you want the scan to **End**.

8. Click **Next** and review your selections.
9. Click **Create**. 


## Next steps
{: #ibm-customer-collector-scan}

When a scan completes, you can view the results as an overview in your dashboard, or in more detail by resource or by control. In all three options, you are presented with a compliance score so that you can view your compliance posture at a glance. To learn more about your score, see [Understanding your compliance score](/docs/security-compliance?topic=security-compliance-view-posture#understand-scores).

</tutorial-prod>