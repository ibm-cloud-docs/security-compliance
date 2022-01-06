---

copyright:
  years: 2022
lastupdated: "2022-01-06"

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

In this tutorial, you learn how to use {{site.data.keyword.compliance_full}} to automate the compliance checks that your organization must complete.
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


## Set up your Virtual Private Cloud (VPC) Infrastructure
{: #ibm-customer-collector-vpc}
{: step}

Virtual Private Cloud gives you the ability to establish your own private cloud-like computing environment on shared public cloud infrastructure. You define and control a virtual network that is logically isolated from all other public cloud tenants. 

If you already have a VPC that is configured with an SSH key, a VSI, and a floating IP, be sure that you know that information that then skip to step 2.
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

1. Go to the **Manage posture > Configure > Collectors** tab and click **Create**.
2. Give your collector a meaningful name and description. For example, `ibm-cloud-collector`. 
3. Click **Next**.
4. Select **Customer** to install the collector on your organization's infrastructure.
5. **UBI** is selected as the default container **image type**. Alternatively, you can choose **Ubuntu**.

   Universal Base Images (UBI) are OCI-compliant container-based operating system images. They cannot be used with Windows OS. Ubuntu images are disk-images that are designed to run on the Ubuntu OS. Ubuntu images are not compliant with the Federal Information Processing Standards (FIPS).
7. For **Endpoint type**, select **Public**.  To allow the collector to use a private IP that is accessible only through the IBM Cloud private network, choose **Private**. 
8. Click **Create**.
9. On the **Download collector** panel that appears after you create a collector, select **Download shell script**, and then click **Download**. The registration key is required.


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

1. Change the permissions of the `initiate_collector.sh` file to allow it to run.

   ```sh
   chmod +x initiate_collector.sh
   ```
   {: codeblock}

1. Install the collector by running the following command. When prompted, use the table as a guide for answering the questions.

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

1. On the **Collectors** page of the {{site.data.keyword.compliance_short}} UI, click **Approval required** to approve the collector for use. Wait a few minutes and refresh the page. The collector status updates to **Active**.

## Grant your collector access to your resources
{: #ibm-customer-collector-access}
{: step}

To run the scan, the collector must have *read* access to the resources that you want to scan. This access is granted through an {{site.data.keyword.cloud_notm}} API key. For more information about the security of your credentials, see [Storing and encrypting data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).

1. Create an {{site.data.keyword.cloud_notm}} API key.

   1. Go to **Manage > Access (IAM) > API keys**.
   2. Click **Create an {{site.data.keyword.cloud_notm}} API key**.
   3. Give your API key a meaningful name and description. For example, `compliance-api-key` and this key is used by the collector to validate my resource configurations.
   4. Click **Create**.
   5. Click **Copy** or **Download** to save your key.

2. Add the API key to the {{site.data.keyword.compliance_short}} as a credential.

   1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and compliance** to return to the {{site.data.keyword.compliance_short}}.
   2. In the navigation, click **Manage posture > Configure > Credentials**.
   3. Click **Create**.
   4. Give your credential a meaningful name. For example, `ibm-cloud-compliance`.
   5. Select **Discovery / fact collection** as the purpose of the credential and then click **Next**.
   6. Select **{{site.data.keyword.cloud_notm}}** as the type of credential.
   7. Paste the API key that you created in the previous step and click **Create**.

## Target your resources
{: #ibm-customer-collector-scope}
{: step}

To target the resources that you want your collector to validate, you create a scope. To do so, you select an environment, a collector, and a set of credentials. The collector uses the credentials to gather information from the resources that are available in the environment that you selected. 


1. Go to the **Manage posture > Configure > Scopes** tab and click **Create**.
2. Give your scope a meaningful name. For example, `ibm-cloud-compliance`.
3. Click **Next**.
4. From the **Environment** dropdown, select **{{site.data.keyword.cloud_notm}}**.
5. From the **Credentials** dropdown, select the credential that you previously added. Then, click **Next**.
6. From the table, select the **Collector** that you previously installed. Then, click **Next**.
7. Review your choices and click **Create**.

After you create the scope, a discovery scan is run to inventory your available resources.


## Validate your configurations
{: #ibm-customer-collector-scan}
{: step}

When your resources and their configurations are discovered, you're ready to validate the configurations. To validate your configurations, you schedule a scan. To do so, you select the scope that you created and choose a profile to validate it against. A profile is a collection of compliance goals and best practices are predefined by {{site.data.keyword.cloud_notm}} or external regulators.


1. Go to the **Manage posture > Assess > Scans > Scheduled scans** tab and click **Schedule**.
2. Give your scan a meaningful name. For example, `ibm-cloud-scan-daily`.
3. For **Scan type**, select **Validation**.
4. From the **Scope** dropdown, select the scope that you previously created.
5. From the **Profile** dropdown, select the **{{site.data.keyword.cloud_notm}} Best Practices Controls 1.0**.
6. Click **Next**.
7. Select the frequency that you want your scan to run. It is automatically set to 2 days.
8. Specify when you want the scan end. The scan can run daily indefinitely, a specific number of times, or it can stop on a specific date.
9. Click **Create**.


## Next steps
{: #ibm-customer-collector-next}

When a scan completes, you can view the results as an overview in your dashboard, or in more detail by resource or by control. In all three options, you are presented with a compliance score so that you can view your compliance posture at a glance. To learn more about your score, see [Understanding your compliance score](/docs/security-compliance?topic=security-compliance-view-posture#understand-scores).

