---

copyright:
  years: 2020, 2023
lastupdated: "2023-03-29"

keywords: collector install, vpc collector, monitor resources, security, compliance

subcollection: security-compliance

content-type: tutorial
services: security-compliance, vpc
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

# Install a customer-managed collector on VPC
{: #collector-vpc}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, vpc"}
{: toc-completion-time="20m"}

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
   ssh root@FLOATING_IP
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
6. For **Endpoint type**, select **Public**.  To allow the collector to use a private IP that is accessible only through the {{site.data.keyword.cloud_notm}} private network, choose **Private**. 
7. Click **Create**.
8. On the **Download collector** panel that appears after you create a collector, select **Download shell script**, and then click **Download**. The registration key is required.


## Installing a collector
{: #customer-collector-install-vm}
{: step}

To install your collector onto your VM, you can use the following steps.


1. Transfer the collector installation file that you downloaded in the previous step to your VSI. If you are using VIM in your terminal, you can use the following steps as an example.

   1. Locally, open the **initiate_collector.sh** file that you downloaded and copy its contents.
   2. From your terminal, open the VIM editor.

      ```sh
      vi initiate_collector.sh
      ```
      {: codeblock}

   3. Press **i** to insert content.
   4. Paste the content that you previously copied.
   5. Press the **Escape** key to exist edit mode.
   6. Type `:wq` and click **Enter** to save and exit VIM.
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


## Next steps
{: #ibm-customer-collector-scan}

Now that your collector is installed and active, you're ready to [schedule a scan](/docs/security-compliance?topic=security-compliance-schedule-scan). When your scan completes, you can return to the UI to view your results.

