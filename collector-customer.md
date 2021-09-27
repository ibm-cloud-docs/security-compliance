---

copyright:
  years: 2021
lastupdated: "2021-09-27"

keywords: collector, security and compliance, security, compliance, install, resource monitoring, configuration monitoring, security, approve collector, register collector, use credentials

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
 

# Manually administering collectors
{: #collector-manual}

For the {{site.data.keyword.compliance_full}} to gather and validate information about your resource configurations, you must create a collector. A customer managed collector is installed, approved, and maintained by you. To learn more about how collectors work, how your data is handled, and your responsibilities, see [What is a collector?](/docs/security-compliance?topic=security-compliance-collector).
{: shortdesc}



## Before you begin
{: #before-collector}

Before you get started, be sure that you have the required level of access to view and manage collectors. To administer collectors, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).


### Verifying installation requirements
{: #before-collector-verify}

To manually install a collector, you must have access to a server. That server must have the following minimum configuration requirements depending on the type of machine that you are using.

| Machine type | Minimum requirement | 
|:-------------|:--------------------|
| Virtual | **Image:** Red Hat Enterprise Linux, CentOS, or Ubuntu 18.x </br>**Profile:** <code>cx2-2x4</code> (2 vCPUs, 4 GB RAM, and 4GBPS </br>**Boot volume:** 50 GB disk space |
| Physical | **Image:** Red Hat Enterprise Linux, CentOS, or Ubuntu 18.x </br>**Processor:** Intel Server Class QuadCore processor </br>**Profile:** 8 GB RAM </br>**Boot volume:** 50 GB Disk Space |
{: caption="Table 1. Minimum machine requirements to install a collector" caption-side="top"}

### Configuring your ACL
{: #before-collector-acl}

By default, most access control lists (ACLs) block outgoing communication. To circumvent this setting without configuring an `Allow_all` policy, add the following hostnames to an allow list.

* `accounts.cloud.ibm.com`
* `api.cis.cloud.ibm.com`
* `api.softlayer.com`
* `api.*.softlayer.com`
* `api.*.logging.cloud.ibm.com`
* `api.shell.cloud.ibm.com`
* `api.*.databases.cloud.ibm.com`
* `config.cloud-object-storage.cloud.ibm.com`
* `config.private.cloud-object-storage.cloud.ibm.com`
* `config.public.cloud-object-storage.cloud.ibm.com`
* `containers.cloud.ibm.com`
* `directlink.cloud.ibm.com`
* `iam.cloud.ibm.com`
* `iam.bluemix.net`
* `otc-api.*.devops.cloud.ibm.com`
* `private.*.certificate-manager.cloud.ibm.com`
* `private.*.kms.cloud.ibm.com`
* `resource-controller.cloud.ibm.com`
* `schematics.cloud.ibm.com`
* `s3.*.cloud-object-storage.appdomain.cloud`
* `s3.private.*.cloud-object-storage.appdomain.cloud`
* `s3.direct.*.cloud-object-storage.appdomain.cloud`
* `transit.cloud.ibm.com`
* `user-management.cloud.ibm.com`
* `*.appid.cloud.ibm.com`
* `*.certificate-manager.cloud.ibm.com`
* `*.iaas.cloud.ibm.com`
* `*.icr.io`
* `*.kms.cloud.ibm.com`
* `*.mybluemix.net`
* `*.secadvisor.cloud.ibm.com`
* `*.*.secrets-manager.appdomain.cloud`

Working with VPC? Get help [Setting up your Network ACLs](/docs/vpc?topic=vpc-using-acls).
{: tip}

## Creating a collector with the console
{: #create-collector-ui}
{: ui}

You can use the {{site.data.keyword.compliance_short}} UI to create a collector by completing the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Manage posture > Configure > Collectors**.
3. Click **Create**.
4. Give your collector a name and description.

   It is helpful to ensure that the name is unique across your organization so that its intended purpose is clear to other members of your team.

5. Choose an endpoint option for your collector.

   By default, your collector connects to resources in your account by using a public endpoint. To allow the collector to use a private IP that is accessible only through the IBM Cloud private network, choose **Private endpoint**.

6. Click **Create**.
  
When the collector is created successfully, the status updates to **Ready to install**.



## Installing a collector
{: #install-collector}

Now that you have a collector, you can install it by completing the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Manage posture > Configure > Collectors**.
3. In the **Collectors** table, click the name of the collector that you want to register. The table row expands to provide more information.
4. Download the `initiate_collector.sh` file.
5. In terminal, log in to your virtual machine by using SSH.

   ```sh
   ssh root@<hostname_or_IP_address>
   ```
   {: codeblock}

6. Be sure that you have the required software on your VSI and that it is up to date. If you're working with Ubuntu, you can use the following commands.
   1. Verify that your OS image is up to date. In Ubuntu, you can run the following command: 

      ```sh
      sudo apt-get update
      ```
      {: codeblock}
  
   2. If you don't have it already, install [Docker Compose](https://docs.docker.com/compose/install/){: external} by using the command for your OS.

      ```sh
      sudo apt-get install docker-compose
      ```
      {: codeblock}

   3. If you plan to use your collector to run on-premises resource scans, install [Nmap version 7.6 or higher](https://nmap.org/download.html){: external} by using the command for your OS. If you're working with Ubuntu, you can use the following command.

      ```sh
      sudo apt-get install nmap
      ```
      {: codeblock}

7. Transfer the collector installation file to your VSI. If you are using VIM in your command line, you can use the following steps as an example.
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

8. Change the permissions of the `initiate_collector.sh` file to allow it to run.

   ```sh
   chmod +x initiate_collector.sh
   ```
   {: codeblock}

9. Install the collector by running the following command and then answering the following prompts as they are asked. 

   ```sh
   ./initiate_collector.sh
   ```
   {: codeblock}

   | Prompt | Response |
   |:-------|:---------|
   | Data Path | Provide the data path to your host machine. For example, `/root/compliance/`. |
   | Nmap validation | No - This tutorial is designed to focus on cloud resources. You only need to run an Nmap validation if your resources exist behind a firewall. |
   | Registration key | Provide the registration key. This can be found in the table on the **Collectors** page of the {{site.data.keyword.compliance_short}} UI. Expand the details for the collector that you want to register and copy the key. |
   {: caption="Table 3. Collector installation prompts" caption-side="top"}

   The registration key is active for 24 hours. Installation must be complete and the collector activated within that timeframe.
   {: important}

9. Confirm that everything is installed.

   ```sh
   docker ps
   ```
   {: codeblock}

   Your output looks similar to the following example.

   ```xml
   CONTAINER ID      IMAGE                                                 COMMAND                   CREATED           STATUS             PORTS               NAMES
   d7884888ec15      us.icr.io/posture-management/compliance-collector:8495ece54142      "sh -c '/usr/local/b_"    10 seconds ago    Up 9 seconds     ASAP-vjdemoibmcloud
   6f76237c39c8      us.icr.io/posture-management/compliance-watchtower:8495ece54142     "/watchtower --clean_"    10 seconds ago    Up 1 seconds     watch-collectors
   ```
   {: screen}

10. Approve your collector.
   1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
   2. In the navigation, click **Manage posture > Configure > Collectors**.
   3. In the **Collectors** table, click **Approval required** in the row that corresponds to the collector that you're working with. When the collector is approved, it switches to an **Active** status. It can take a few minutes for the approval to take effect and the status to change.
   4. If a passphrase is enabled, click **Passphrase** and enter the phrase. Be sure to enter your passphrase exactly.


### Using a proxy with your collector
{: #collector-proxy}

As an additional protection, your organization might want to configure a proxy to use as an intermediary between the collector and your resources. To install a collector to use a proxy, you can use the same steps that are detailed in [Installing a collector](#install-collector), and provide the following additional information.

1. In step 8 of the [Installing a collector](#install-collector) instructions, you are asked whether you would like to add a proxy. To use a proxy, enter `y` (yes). Then, when prompted provide the following information:

   * The IP address that you want to use as the proxy.
   * The port of your proxy server.
   * The username and password for your proxy.

2. Add your IP Addresses and ports to your ACL.

   | IP address | Port |
   |:-------|:---------|
   | DNS | `161.26.0.6` <br /> `53` |
   | Service endpoints | `166.8.0.0` <br /> `443` |
   {: caption="Table 5. Collector installation prompts" caption-side="top"}
