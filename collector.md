---

copyright:
  years: 2021
lastupdated: "2021-06-07"

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


# Managing collectors
{: #collector}

A collector is used to enable communication between the service and your IT resources. To enable the service to monitor your resource configurations for potential issues, you must create, install, and approve a collector.
{: shortdesc}

## Understanding collectors
{: #understand-collector}

A collector is a software module that is packaged as a Docker image. It is installed within sight of your environment where it has network access to your IT resources. Collectors are used to fetch the configuration information from your environment and perform a validation.


### How is the collector deployment managed?
{: #collector-deployment}

Each instance of the collector is managed by you and only applicable where you configure it to have access. The data that is collected and analyzed is specific to your account and the results of the scans are available only to you and the users that you authorize to use your account. It is your responsibility to manage the security of the deployment.

If you're working with more than one cloud provider or an on-premises environment, you might need to install more than one collector. Each collector operates only within the subnets to which it belongs, so if your IT network is segmented, you might need a collector for each subnet.

### How does the collector communicate with the service?
{: #collector-comm-service}

All communication between the collector and the service is TLS 1.2+ encrypted and signed with the collector's public key. All traffic is transported over the public internet by using Cloud Internet Services with TLS termination, DDoS protection, and a Web Application Firewall (WAF). Although the transportation takes place through a trusted intermediary, be sure that you consider this as part of your security and risk assessment when you deploy collectors.

The collector sends a regular heartbeat every minute to notify the service that it is active and ready to run commands. As a response to that heartbeat, the service might send a command for the cluster to run, such as running a discovery scan.

### How does the collector communicate with my resources?
{: #collector-comm-resource}

To gather information about your resources, the collector must be able to connect to them by using a combination of methods, including API calls, SSH, Shell commands, and Windows PowerShell. The communication is able to occur only because the collector uses credentials that you associate with it through the {{site.data.keyword.compliance_short}} UI. To communicate with them, the collector needs to use credentials that have read access to your resources. 

Collectors that run in an on-premises environment use Nmap to scan and discover resources. The collector uses SSH or the equivalent to connect to and query the resources for the configurations. The network and ports on the VMs must allow for the connectivity.

For more information about granting the authorization between a collector and your resources, see [Managing credentials](/docs/security-compliance?topic=security-compliance-credentials).
{: tip}


### What happens with the data that the collector gathers?
{: #collector-data}

The collector uses the data that is collected to validate the controls before it sends the results to the {{site.data.keyword.compliance_short}} for storage and reporting. The data that is collected varies depending on the environment that you're working with and the type of credentials that you provide. For cloud environments, a significant portion of the data is available as metadata. If you're working with an on-premises environment, some of the data is typically stored in configuration management databases. Collected data includes the properties and configurations for supported services, network objects, hosts, databases, Kubernetes platforms, and virtual machines. 


### Which endpoints does a collector access?
{: #collector-proxy}

A collector uses the following endpoints to access your resource configurations. To use a proxy with your collector, be sure to add the following hostnames to an allowlist.

`accounts.cloud.ibm.com`, `api.cis.cloud.ibm.com`, `api.softlayer.com`, `api.*.softlayer.com`, `api.*.logging.cloud.ibm.com`, `api.shell.cloud.ibm.com``api.*.databases.cloud.ibm.com`, `config.cloud-object-storage.cloud.ibm.com`, `config.private.cloud-object-storage.cloud.ibm.com`, `config.public.cloud-object-storage.cloud.ibm.com`, `containers.cloud.ibm.com`, `directlink.cloud.ibm.com`, `iam.cloud.ibm.com`, `iam.bluemix.net`, `otc-api.*.devops.cloud.ibm.com`, `private.*.certificate-manager.cloud.ibm.com`, `private.*.kms.cloud.ibm.com`, `resource-controller.cloud.ibm.com`, `schematics.cloud.ibm.com`, `s3.*.cloud-object-storage.appdomain.cloud`, `s3.private.*.cloud-object-storage.appdomain.cloud`, `s3.direct.*.cloud-object-storage.appdomain.cloud`, `transit.cloud.ibm.com`, `user-management.cloud.ibm.com`, `*.appid.cloud.ibm.com`, `*.certificate-manager.cloud.ibm.com`, `*.iaas.cloud.ibm.com`, `*.icr.io`, `*.kms.cloud.ibm.com`, `*.mybluemix.net`, `*.secadvisor.cloud.ibm.com`, and `*.*.secrets-manager.appdomain.cloud`.


## Before you begin
{: #before-collector}

Before you begin, be sure that you're using a Pay-As-You-Go or Subscription [{{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started) where you are the owner or have [full administrator access](/docs/account?topic=account-assign-access-resources).

Be sure that you also have the following requirements:

- Access to the [Credentials](/docs/security-compliance?topic=security-compliance-credentials) needed to communicate with resources.
- Access to a server on which you can install the collector. Check out the following table to learn about the minimum configuration requirements.

| Machine type | Minimum requirement | 
|:-------------|:--------------------|
| Virtual | <strong>Image:</strong> Red Hat Enterprise Linux, CentOS, or Ubuntu 18.x </br><strong>Profile:</strong> <code>cx2-2x4</code> (2 vCPUs, 4 GB RAM, and 4GBPS </br><strong>Boot volume:</strong> 50 GB disk space |
| Physical | <strong>Image:</strong> Red Hat Enterprise Linux, CentOS, or Ubuntu 18.x </br><strong>Processor:</strong> Intel Server Class QuadCore processor </br><strong>Profile:</strong> 8 GB RAM </br><strong>Boot volume:</strong> 50 GB Disk Space |
{: caption="Table 1. Minimum requirements for installing the collector" caption-side="top"}


## Creating a collector
{: #create-collector}

You can use the {{site.data.keyword.compliance_short}} UI to create a collector by completing the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Manage posture > Configure > Settings > Collectors**.
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
2. In the navigation, click **Manage posture > Configure > Settings > Collectors**.
3. In the **Collectors** table, click the name of the collector that you want to register. The table row expands to provide more information.
4. Download the `initiate_collector.sh` file.
5. In terminal, log in to your virtual machine by using SSH.

  ```
  ssh <username>@<hostname_or_IP_address>
  ```
  {: codeblock}

  If you do not log in as the root user, you must prefix the following commands with `sudo`.
  {: tip}

6. Be sure that you have the required software on your VM and that it is up to date. If you're working with Ubuntu, you can use the following commands.
  1. Verify that your OS image is up to date. In Ubuntu, you can run the following command: 

    ```
    [sudo] apt-get update
    ```
    {: codeblock}
  
  2. If you don't have it already, install [Docker Compose](https://docs.docker.com/compose/install/){: external} by using the command for your OS.

    ```
    [sudo] apt-get install docker-compose
    ```
    {: codeblock}

  3. If you plan to use your collector to run on-premises resource scans, install [Nmap version 7.6 or higher](https://nmap.org/download.html){: external} by using the command for your OS. If you're working with Ubuntu, you can use the following command.

    ```
    [sudo] apt-get install nmap
    ```
    {: codeblock}

7. Transfer the downloaded `initiate_collector.sh` file onto your virtual machine and change the permissions to allow it to run.

  ```
  chmod +x initiate_collector.sh
  ```
  {: codeblock}

8. Install the collector by running the following command and then answering the following prompts as they are asked. 

  ```
  ./initiate_collector.sh
  ```
  {: codeblock}

  <table>
    <caption>Table 1. Collector installation prompts and responses</caption>
    <tr>
      <th>Prompt</th>
      <th>Desciption and example</th>
    </tr>
    <tr>
      <td>Data path</td>
      <td>The path to your host machine. For example, <code>/root/folder_name/</code>.</td>
    </tr>
    <tr>
      <td>Nmap validation</td>
      <td>Nmap scans are done on resources that are behind a firewall such as on-premesis resources. Enter <code>y</code> (yes) or <code>n</code> (no)</td>
    </tr>
    <tr>
      <td>Proxy</td>
      <td>Your organization might want to use a proxy to allow communication between the collector and your resources. For more information about using a proxy, see [Intalling a collector by using a proxy](#collector-proxy).</td>
    </tr>
    <tr>
      <td>Registration key</td>
      <td>You can get this value by going to the **Manage posture > Configure > Settings > Collectors** page of the {{site.data.keyword.compliance_short}} UI and viewing more details about the collector that you want to install.</td>
    </tr>
  </table>

  The registration key is active for 24 hours. Installation must be complete and the collector activated within that timeframe.
  {: important}

9. Confirm that everything is installed.

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

10. Approve your collector.
  1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
  2. In the navigation, click **Manage posture > Configure > Settings > Collectors**.
  3. In the **Collectors** table, click **Approve** in the row that corresponds to the collector that you're working with. When the collector is approved, it switches to an **Active** status. It can take a few minutes for the approval to take effect and the status to change.
  4. If a passphrase is enabled, click **Passphrase** and enter the phrase. Be sure to enter your passphrase exactly.


## Installing a collector through a Proxy
{: #collector-proxy}



A collector uses the following endpoints to access your resource configurations. To use a proxy with your collector, be sure to add the following hostnames to an allowlist.

`accounts.cloud.ibm.com`, `api.cis.cloud.ibm.com`, `api.softlayer.com`, `api.*.softlayer.com`, `api.*.logging.cloud.ibm.com`, `api.shell.cloud.ibm.com``api.*.databases.cloud.ibm.com`, `config.cloud-object-storage.cloud.ibm.com`, `config.private.cloud-object-storage.cloud.ibm.com`, `config.public.cloud-object-storage.cloud.ibm.com`, `containers.cloud.ibm.com`, `directlink.cloud.ibm.com`, `iam.cloud.ibm.com`, `iam.bluemix.net`, `otc-api.*.devops.cloud.ibm.com`, `private.*.certificate-manager.cloud.ibm.com`, `private.*.kms.cloud.ibm.com`, `resource-controller.cloud.ibm.com`, `schematics.cloud.ibm.com`, `s3.*.cloud-object-storage.appdomain.cloud`, `s3.private.*.cloud-object-storage.appdomain.cloud`, `s3.direct.*.cloud-object-storage.appdomain.cloud`, `transit.cloud.ibm.com`, `user-management.cloud.ibm.com`, `*.appid.cloud.ibm.com`, `*.certificate-manager.cloud.ibm.com`, `*.iaas.cloud.ibm.com`, `*.icr.io`, `*.kms.cloud.ibm.com`, `*.mybluemix.net`, `*.secadvisor.cloud.ibm.com`, and `*.*.secrets-manager.appdomain.cloud`.


