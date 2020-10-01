---

copyright:
  years: 2020
lastupdated: "2020-10-01"

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


# Managing collectors
{: #collector}

A collector is used to enable communication between the service and your IT resources. To enable the service to monitor your resource configurations for potential issues, you must create, install, and approve a collector.
{: shortdesc}

## Understanding collectors
{: #understand-collector}

A collector is a software module that is packaged as a Docker image. It is installed within sight of your environment where it has network access to your IT resources. Collectors are used to fetch the configuration information from your environment and perform a validation.


**How is the collector deployment managed?**

Each instance of the collector is managed by you and only applicable where you configure it to have access. The data that is collected and analyzed is specific to your account and the results of the scans are available only to you and the users that you authorize to use your account. It is your responsibility to manage the security of the deployment.

If you're working with more than one cloud provider or an on-premises environment, you might need to install more than one collector. Each collector operates only within the subnets to which it belongs, so if your IT network is segmented, you might need a collector for each subnet.

**How does the collector communicate with the service?**

All communication between the collector and the service is TLS 1.2+ encrypted and signed with the collector's public key. All traffic is transported over the public internet by using Cloud Internet Services with TLS termination, DDoS protection, and a Web Application Firewall (WAF). Although the transportation takes place through a trusted intermediary, be sure that you consider this as part of your security and risk assessment when you deploy collectors.

The collector sends a regular heartbeat every minute to notify the service that it is active and ready to run commands. As a response to that heartbeat, the service might send a command for the cluster to run, such as running a discovery scan.

**How does the collector communicate with my resources?**

To gather information about your resources, the collector must be able to connect to them by using a combination of methods, including API calls, SSH, Shell commands, and Windows PowerShell. The communication is able to occur only because the collector uses credentials that you associate with it through the {{site.data.keyword.compliance_short}} UI. To communicate with them, the collector needs to use credentials that have read access to your resources. 

For more information about granting that authorization, see [Managing credentials](/docs/security-compliance?topic=security-compliance-credentials).
{: tip}


**What happens with the data that the collector gathers?**

The collector uses the data that is collected to validate the controls before it sends the results to the {{site.data.keyword.compliance_short}} for storage and reporting. The data that is collected varies depending on the environment that you're working with and the type of credentials that you provide. For cloud environments, a significant portion of the data is available as metadata. If you're working with an on-premises environment, some of the data is typically stored in configuration management databases. Collected data includes the properties and configurations for supported services, network objects, hosts, databases, Kubernetes platforms, and virtual machines. 



## Before you begin
{: #before-collector}

Before you begin, be sure that you're using a Pay-As-You-Go or Subscription [{{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started) where you are the owner or have [full administrator access](/docs/account?topic=account-assign-access-resources).

Be sure that you also have the following requirements:

- Access to the [Credentials](/docs/security-compliance?topic=security-compliance-credentials) needed to communicate with resources.
- Access to a server on which you can install the collector. Check out the following table to learn about the minimum configuration requirements.

| Machine type | Minimum requirement | 
|:-------------|:--------------------|
| Virtual | <strong>Image:</strong> Red Hat Enterprise Linux, CentOS, or Ubuntu </br><strong>Profile:</strong> <code>cx2-2x4</code> (2 vCPUs, 4 GB RAM, and 4GBPS </br><strong>Boot volume:</strong> 50 GB disk space |
| Physical | <strong>Image:</strong> Red Hat Enterprise Linux, CentOS, or Ubuntu 18.x </br><strong>Processor:</strong> Intel Server Class QuadCore processor </br><strong>Profile:</strong> 8 GB RAM </br><strong>Boot volume:</strong> 50 GB Disk Space |
{: caption="Table 1. Minimum requirements for installing the collector" caption-side="top"}


## Creating a collector
{: #create-collector}

You can use the {{site.data.keyword.compliance_short}} UI to create a collector by completing the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Collectors**.
3. Click the **New collector** icon.
4. Give your collector a name and description. It is helpful to ensure that the name is unique across your organization so that its intended purpose is clear to other members of your team.
5. Select a **Type**. Options include **Restricted** and **Unrestricted**.

  **Restricted**: A restricted collector is used most often for on-premises resources that exist behind a firewall and is not needed to access resources from public cloud environment. To scan resources from on-premises or private cloud environment, the collector must install the Nmap package to be able to run an Nmap network scan.

  **Unrestricted**: An unrestricted collector is installed in a way in which it might have access to all of the environments that you want to scan including on-premises or private clouds and other public clouds. Depending on how you plan to use your collector, it might have access to a public cloud environment and it might not need to run Nmap scans.
  
When the collector is created successfully, the status updates to **Ready to install**.


## Installing a collector
{: #install-collector}

Now that you have a collector, you can install it by completing the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Collectors**.
3. In the **Collectors** table, click the name of the collector that you want to register. The table row expands to provide more information.
4. Download the `initiate_collector.sh` file.
5. In terminal, log in to your virtual machine by using SSH.

  ```
  ssh <username>@<hostname_or_IP_address>
  ```
  {: codeblock}

  If you do not log in as the root user, you must prefix the following commands with `sudo`.
  {: tip}

6. Ensure that your OS image is up to date. In Ubuntu, you can run the following command: 

  ```
  [sudo] apt-get update
  ```
  {: codeblock}

7. Install [Docker Compose](https://docs.docker.com/compose/install/){: external} by using the command for your OS. If you're working with Ubuntu, you can use the following command.

  ```
  [sudo] apt-get install docker-compose
  ```
  {: codeblock}

8. If you plan to use your collector to run on-premises resource scans, install Nmap version 7.6 by using the command for your OS. If you're working with Ubuntu, you can use the following command.

  ```
  [sudo] apt-get install nmap
  ```
  {: codeblock}

9.  Transfer the downloaded `initiate_collector.sh` file onto your virtual machine.

10. Change the permissions of the `initiate_collector.sh` file to allow it run.

  ```
  chmod +x initiate_collector.sh
  ```
  {: codeblock}

11. Install the collector by running the following command.

  ```
  ./initiate_collector.sh
  ```
  {: codeblock}

12. When prompted, enter the data path from your host machine. For example, `/root/folder_name/`.
13. When prompted about whether to do an Nmap validation, enter `y` (yes) or `n` (no).

  Nmap scans are done on resources that are behind a firewall. If you're working with an unrestricted collector, your answer would be no. If you're working with a restricted collector for on-premises resources, your answer would be yes.

14. When prompted, enter your collector registration key.

  You can get this value by going to the **Collectors** page of the {{site.data.keyword.compliance_short}} UI and viewing more details about the collector that you want to install.

15. Confirm that everything is installed.

  ```
  docker ps
  ```
  {: codeblock}

  Your output looks similar to the following example.

  ```
  CONTAINER ID      IMAGE                                                 COMMAND                   CREATED           STATUS             PORTS               NAMES
  d7884888ec15      us.icr.io/posture-management/compliance-collector:8495ece54142      "sh -c '/usr/local/b_"    10 seconds ago    Up 9 seconds     ASAP-vjdemoibmcloud
  6f76237c39c8      us.icr.io/posture-management/compliance-watchtower:8495ece54142     "/watchtower --clean_"    10 seconds ago    Up 1 seconds     watch-collectors
  ```
  {: screen}

If you're working with a scope that requires multiple credentials to complete a scan, be sure to [map your credentials](/docs/security-compliance?topic=security-compliance-credentials-map-credentials)


## Approving a collector
{: #approve-collector}

Now that your collector is installed, you must approve it before it can start collecting information on your resources.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Collectors**.
3. In the **Collectors** table, click **Approve** in the row that corresponds to the collector that you're working with.

  When the collector is approved, it switches to an **Active** status. It can take a few minutes for the approval to take effect and the status to change.
4. If a passphrase is enabled, click **Passphrase** and enter the phrase.



