---

copyright:
  years: 2020, 2023
lastupdated: "2023-04-12"

keywords: collector, security and compliance, security, compliance, install, resource monitoring, configuration monitoring, security, approve collector, register collector, use credentials

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Managing collectors
{: #collector}

In {{site.data.keyword.compliance_full}}, a collector is used to gather the configuration information of your resources and then validate it against your specified requirements. 
{: shortdesc}


The collector-based architecture is deprecated. For more information, see the [release notes](/docs/security-compliance?topic=security-compliance-release-notes).
{: deprecated}


## Before you begin
{: #before-collector}

Before you get started, be sure that you have the level of access that is necessary to view and manage collectors. To administer collectors, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).

Additionally, you must configure your access control list (ACL) to ensure that communication can take place without configuring an `allow_all` policy. Add the following hostnames to an allowlist.

```
accounts.cloud.ibm.com, api.cis.cloud.ibm.com, api.softlayer.com, api.*.softlayer.com, api.*.logging.cloud.ibm.com, api.shell.cloud.ibm.com, api.*.databases.cloud.ibm.com, config.cloud-object-storage.cloud.ibm.com, config.private.cloud-object-storage.cloud.ibm.com, config.public.cloud-object-storage.cloud.ibm.com, containers.cloud.ibm.com, directlink.cloud.ibm.com, iam.cloud.ibm.com, iam.bluemix.net, otc-api.*.devops.cloud.ibm.com, private.*.certificate-manager.cloud.ibm.com, private.*.kms.cloud.ibm.com, resource-controller.cloud.ibm.com, schematics.cloud.ibm.com, s3.*.cloud-object-storage.appdomain.cloud, s3.private.*.cloud-object-storage.appdomain.cloud, s3.direct.*.cloud-object-storage.appdomain.cloud, transit.cloud.ibm.com, user-management.cloud.ibm.com, *.appid.cloud.ibm.com, *.certificate-manager.cloud.ibm.com, *.iaas.cloud.ibm.com, *.icr.io, *.kms.cloud.ibm.com, *.mybluemix.net, *.secadvisor.cloud.ibm.com, *.*.secrets-manager.appdomain.cloud
```
{: codeblock}

Working with VPC? Get help [Setting up your Network ACLs](/docs/vpc?topic=vpc-using-acls).
{: tip}


## Understanding collectors
{: #understand-collector}

A collector is a software module that is packaged as a container image. It is deployed on infrastructure that has access to the resources in your account. You can choose to have IBM manage your collector, or you can choose to deploy it and manage it yourself.

IBM-managed collectors
:   When you choose to have IBM manage your collector, it is installed on IBM infrastructure as a Universal Base Image (UBI). IBM is responsible for the installation and management for the lifecycle of the collector. This option gives you the ability to focus on just the health and security of your resources. Before you get started, be sure that you understand [the limitations](/docs/security-compliance?topic=security-compliance-service-limits).

Customer-managed collectors
:  In some situations, an IBM-managed collector might not be possible. If your organization has policies about the ownership of infrastructure or specific security constraints, you can always continue to manage your own collector. With a customer-owned collector, you own the infrastructure and you have total control over where the collector is installed. You can install the collector as a UBI or Ubuntu container image. The Ubuntu image is not compliant with the Federal Information Processing Standards (FIPS).

If you choose to work with a customer-managed collector, you are responsible for the stability of the virtual machine on which you deploy the collector. Your responsibilities include processing power, disk space, log clean up, access control, and port management. You are also responsible for ensuring that your copy of the Watchtower image remains stable and up to date. When you install a collector, you install both the collector image and the Watchtower image. The Watchtower image continuously monitors the container registry where the collector image is stored to detect updates to the image. If an update is detected, the Watchtower image forces an update to the collector. For more information about Watchtower, see the [open source docs](https://github.com/containrrr/watchtower){: external}.

### Understanding collector statuses
{: #collector-status}

When you are looking at the UI, you might see the following collector statuses. You can monitor the status changes of your collectors. Additionally, you can filter your list of collectors in the UI by selecting the statuses that you want to observe.

| Status | Description |
| ------ | ----------- |
| Activating collector | Your collector is being activated. | 
| Active | Your collector is now active. |
| Approval required | You must approve the activation of your collector. |
| Deleted | Your collector was deleted. |
| Download in progress | Your collector is downloading. |
| Expired | Your collector expired. |
| Inactive | Your collector is not active. |
| Install in progress | Your collector is being installed. |
| Installation failed | Your collector failed to install. |
| Ready to install | Your collector is ready to be installed. |
| Waiting for upgrade | Your collector is waiting to be upgraded. | 
{: caption="Table 1. Description of collector statuses" caption-side="top"}


### Working with multiple collectors
{: #collector-multiple}

If you're working with more than one cloud provider or an on-premises environment, you might need to install more than one collector. A collector is only able to access the subnets that it has appropriate access for. For example, the collector might need to have `icmp ping` access to run an Nmap scan, `SSH` access for accessing VMs or `winrm` access to access a windows machine. One collector is able to access multiple subnets, but you must be sure that it is correctly sized to scan a specified environment.

If your collector needs to access multiple subnets, you must add them to the subnet list for the collector. The file name that you need to update is `<collector_dir_path>/config/discovery_subnet_list.cfg`.



## Creating an IBM-managed collector
{: #collector-create-ibm-ui}
{: ui}

You can create a collector by using the {{site.data.keyword.compliance_short}} UI.


1. Ensure that your account allows traffic to all the following [IP addresses](/docs/account?topic=account-ips#ips_account).

	| Location | IP addresses |
	| --- | --- |
	| United States | `150.239.179.224/27`, `52.116.28.0/27`, `169.62.230.48/28`, `52.116.224.64/28`, `169.46.94.0/28`, `150.238.252.224/27` |
	| European Union | `158.177.77.112/28`, `159.122.112.96/27`, `161.156.11.32/27`, `161.156.18.0/28`, `149.81.148.224/28`, `149.81.181.224/27`, `149.81.131.192/28`, `158.177.244.192/28`, `161.156.178.96/28` |
	{: caption="Table 2. IP addresses for IBM managed collectors" caption-side="top"}

2. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access {{site.data.keyword.compliance_short}}.
3. In the navigation, click **Hybrid cloud configurations > Collectors > Create**.
4. Give your collector a name and optionally provide a description. Then, click **Next**.
5. Select **IBM** as your **Managed by** choice.
6. Click **Create**.

When it's time for your scan to run, the status updates to **Active**. To learn more, see [Understanding collector statuses](#collector-status).



## Creating a managed collector with the API
{: #create-collector-managed-api}
{: api}

You can use the {{site.data.keyword.compliance_short}} Posture Management API to create a collector.

1. Ensure that your account allows traffic to all the following [IP addresses](/docs/account?topic=account-ips#ips_account).

	| Location | IP addresses |
	| --- | --- |
	| United States | `150.239.179.224/27`, `52.116.28.0/27`, `169.62.230.48/28`, `52.116.224.64/28`, `169.46.94.0/28`, `150.238.252.224/27` |
	| European Union | `158.177.77.112/28`, `159.122.112.96/27`, `161.156.11.32/27`, `161.156.18.0/28`, `149.81.148.224/28`, `149.81.181.224/27`, `149.81.131.192/28`, `158.177.244.192/28`, `161.156.178.96/28` |
	{: caption="Table 2. IP addresses for IBM managed collectors" caption-side="top"}

2. Make the following POST request.

	```sh
	curl POST 'https://<region>.compliance.cloud.ibm.com/posture/v2/collectors?account_id=<accountID>' \
	-H 'Authorization: <IAMToken>' \
	-H 'Content-Type: application/json' \
	-d '{
			"name":"my_collector",
			"is_public":true,    
			"description": "This is my description.",
			"managed_by":"ibm",
			"is_ubi_image":true
			}'
	```
	{: codeblock}

	| Variable   | Description |
	|:-----------|:------------|
	| `region` | The region in which you want to create a collector. Be sure that your region matches the location that is configured for {{site.data.keyword.compliance_short}}. You can view your account settings by making a POST request to the [Admin API](/apidocs/security-compliance-admin#getsettings). For example, `eu`.|
	| `accountID` | The ID of the account that manages the {{site.data.keyword.compliance_short}}. If you are the owner of the managing account, can find this ID in the {{site.data.keyword.cloud_notm}} console by clicking **Manage > Account > Account Settings**.| 
	| `IAMToken` | For help with creating your IAM token, see [Generating an {{site.data.keyword.cloud_notm}} IAM token by using an API key](/docs/account?topic=account-iamtoken_from_apikey).|
	| `name` | The name that you want your collector to have. It must be unique to the {{site.data.keyword.compliance_short}} instance that you're working with.|
	| `is_public` | The type of endpoint that your collector is able to use to connect to your resources. This value must be set to `false`, which means that a private IP address that is accessible only through the {{site.data.keyword.cloud_notm}} private network is used.|
	| `description`| Optional: A detailed description of how you intend to use your collector.|
	| `managed_by` | The entity responsible for managing the collector. This value must be set to `ibm`.|
	| `is_ubi_image` | The parameter `is_ubi_image` determines whether the collector has a UBI image. Universal Base Images (UBI) are OCI-compliant container-based operating system images. They cannot be used with Windows OS. |
	{: caption="Table 3. Understanding the variables used to create a collector with the API" caption-side="top"}

	If your collector is successfully created, you receive the following response.

	```json
	{
		"id": "1",
		"display_name": "my_collector",
		"name": "my_collector",
		"status": "install_in_progress",
		"description": "This is my description.",
		"created_at": "1970-01-01T00:00:00.000Z",
		"updated_at": "1970-01-01T00:00:00.000Z",
		"enabled": false,
		"registration_code": "400000a-0000-00f5-9d00-000000c3cb79",
		"type": "unrestricted",
		"failure_count": 0,
		"use_private_endpoint": false,
		"managed_by": "ibm",
		"status_description": "Install In Progress",
		"is_fips_compliant": false,
		"collector_enable": true,
		"is_public": true
	}
	```
	{: screen}


## Creating a customer-managed collector
{: #create-collector-customer-ui}
{: ui}

You can use the {{site.data.keyword.compliance_short}} UI to create a collector.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Hybrid cloud configurations > Collectors > Create**.
3. Give your collector a name and optionally provide a description. Then, click **Next**.
4. Select **Customer** as your **Managed by** choice.
5. Select the type of image that you want your collector to be from the following choices.

	* Universal Base Image (UBI): A UBI image is OCI-compliant but cannot be used on Windows OS.
	* Ubuntu Image: An Ubuntu image is not compliant with the Federal Information Processing Standards (FIPS), but can be used with Windows OS.

   If you select UBI, you must have the latest version of Docker installed.
   {: note}

6. Select whether you want your collector to use **Private** or **Public** endpoints to communicate with the resources in your account.
7. Click **Create**. A download panel opens.
8. Select the type of installation file that you want to use to install your collector and click **Download**. 

	If you are deploying on a virtual machine, select the **Shell script**. If you are working with Kubernetes, select the **YAML file**.

	If you select the shell script, be sure to make a note of your registration key.
	{: tip}


## Creating a customer-managed collector by using the API
{: #create-collector-customer-api}
{: api}

You can use the {{site.data.keyword.compliance_short}} Posture Management API to create a collector by making the following POST request.

```sh
curl POST 'https://<region>.compliance.cloud.ibm.com/posture/v2/collectors?account_id=<accountID>' \
   -H 'Authorization: <IAMToken>}' \
   -H 'Content-Type: application/json' \
   -d '{
         "name":"my_collector",
         "is_public":true,
         "managed_by":"customer",
         "description": "This is my description.",
         "is_ubi_image":true
         }'
```
{: codeblock}

| Variable   | Description |
|:-----------|:------------|
| `region` | The region in which you want to create a collector. Be sure that your region matches the location that is configured for {{site.data.keyword.compliance_short}}. You can view your account settings by making a POST request to the [Admin API](/apidocs/security-compliance-admin#getsettings). For example, `eu`.|
| `accountID` | The ID of the account that manages the {{site.data.keyword.compliance_short}}. If you are the owner of the managing account, can find this ID in the {{site.data.keyword.cloud_notm}} console by clicking **Manage > Account > Account Settings**.| 
| `IAMToken` | For help with creating your IAM token, see [Generating an {{site.data.keyword.cloud_notm}} IAM token by using an API key](/docs/account?topic=account-iamtoken_from_apikey). Be sure to configure your API key and permissions for a service ID. |
| `name` | The name that you want your collector to have. It must be unique to the {{site.data.keyword.compliance_short}} instance that you're working with.|
| `is_public` | The type of endpoint that your collector is able to use to connect to your resources. If set to `false`, a private IP address that is accessible only through the {{site.data.keyword.cloud_notm}} private network is used. If set to `true`, the collector can access your resources over a public network. |
| `managed_by` | The entity responsible for managing the collector. This value must be set to `customer`.|
| `description`| Optional: A detailed description of how your collector is used.|
| `is_ubi_image` | The parameter `is_ubi_image` determines whether the collector has a UBI image. Universal Base Images (UBI) are OCI-compliant container-based operating system images. They cannot be used with Windows OS. |
{: caption="Table 4. Understanding the variables used to create a collector with the API" caption-side="top"}

If your collector is successfully created, you receive the following response.

```json
{
  "id": "1",
  "display_name": "my-collector-azure",
  "name": "my-collector-azure",
  "status": "ready_to_install",
  "description": "This collector is used with my Azure resources.",
  "created_by": "IBMid-1200007EV9",
  "created_at": "2021-06-20T03:51:09.131Z",
  "updated_by": "IBMid-1200007EV9",
  "updated_at": "2021-06-20T03:51:09.131Z",
  "enabled": true,
  "registration_code": "400000a-0000-00f5-9d00-000000c3cb79",
  "type": "unrestricted",
  "failure_count": 0,
  "use_private_endpoint": false,
  "managed_by": "customer",
  "status_description": "Ready to install",
  "is_public": true
}
```
{: screen}

To download your installation file, go to the **Hybrid cloud configurations > Collectors** page of the {{site.data.keyword.compliance_short}} UI.

## Installing your collector
{: #collector-install}

You can choose to install a collector on a {{site.data.keyword.containershort}} or {{site.data.keyword.openshiftshort}} on {{site.data.keyword.cloud_notm}} cluster or on a virtual machine. 

### Installing a collector on a cluster
{: #install-collector-cluster}

You can install a collector an {{site.data.keyword.cloud_notm}} {{site.data.keyword.containershort}} or {{site.data.keyword.openshiftshort}} cluster.

1. Optional: Customize the YAML file that you downloaded when you created your collector.

   | Property | Note |
   | -------- | ---- |
   | `namespace` | If you choose to customize `namespace`, both occurrences must match. |
   | `resources` | You can edit only the values of `cpu` and `memory`. |
   {: caption="Table 4. The properties that you can edit in the YAML file" caption-side="top"}

2. Log in to the {{site.data.keyword.cloud_notm}} CLI by running the following command and then following the prompts. If you have a federated ID, append the `--sso` option to the end of the command. 

   ```sh
   ibmcloud login
   ```
   {: codeblock}

3. Set the context for your cluster. 

   * If you are using a {{site.data.keyword.containershort}} cluster, run the following command.

      ```sh
      ibmcloud ks cluster config --cluster <CLUSTER_NAME_OR_ID>
      ```
      {: codeblock}

   * If you are using an {{site.data.keyword.openshiftshort}} cluster, run the following command.

      ```sh
      ibmcloud oc cluster config --cluster <CLUSTER_NAME_OR_ID> --admin
      ```
      {: codeblock}

7. Deploy your collector. 

   * If you are using a {{site.data.keyword.containershort}} cluster, run the following command.

      ```sh
      kubectl apply -f <deployment-testdocumentation>.yaml
      ```
      {: codeblock}

   * If you are using an {{site.data.keyword.openshiftshort}} cluster, run the following command.

      ```sh
      OC apply -f <deployment-testdocumentation>.yaml
      ```
      {: codeblock}

Be sure to **Approve** your collector on the **Hybrid cloud configurations > Collectors** page of the {{site.data.keyword.compliance_short}} UI.
{: note}



### Installing a collector on a virtual machine
{: #install-collector-vm}

You can install a collector on any VM that has access to your resource configurations.

1. Verify the installation requirements.

	| Machine type | Minimum requirement | 
	|:-------------|:--------------------|
	| Virtual | **Image:** Red Hat Enterprise Linux, CentOS, or Ubuntu 18.x  \n **Profile:** `cx2-2x4` (2 vCPUs, 4 GB RAM, and 4GBPS)  \n **Boot volume:** 50 GB disk space |
	| Physical | **Image:** Red Hat Enterprise Linux, CentOS, or Ubuntu 18.x  \n **Processor:** Intel Server Class QuadCore processor  \n **Profile:** 8 GB RAM  \n **Boot volume:** 50 GB Disk Space |
	{: caption="Table 5. Minimum machine requirements to install a collector" caption-side="top"}

2. Log in to your virtual machine by using SSH in your terminal.

   ```sh
   ssh root@<HOSTNAME_OR_IP_ADDRESS>
   ```
   {: codeblock}

3. Be sure that you have the required software on your VSI and that it is up to date. If you're working with Ubuntu, you can use the following commands.

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

      Depending on the version of Docker that you use, you might be charged for the use of Docker Compose. Be sure that you understand the [subscription model](https://www.docker.com/blog/updating-product-subscriptions/){: external}.
      {: note}

   3. If you plan to use your collector to run on-premises resource scans, install [Nmap version 7.6 or higher](https://nmap.org/download.html){: external} by using the command for your OS. If you're working with Ubuntu, you can use the following command.

      ```sh
      sudo apt-get install nmap
      ```
      {: codeblock}

4. Transfer the collector installation file to your VSI. If you are using VIM in your command line, you can use the following steps as an example.

   1. Locally, open the **initiate_collector.sh** file that you downloaded and copy its contents.
   2. From your command line, open the VIM editor.

      ```sh
      vi initiate_collector.sh
      ```
      {: codeblock}

   3. Press **i** to insert content.
   4. Paste the content that you previously copied.
   5. Press the **Escape** key to exist edit mode.
   6. Type `:wq` and push enter to save and exit VIM.
   7. To confirm that the file was created, run the `ls` command.

5. Change the permissions of the `initiate_collector.sh` file to allow it to run.

   ```sh
   chmod +x initiate_collector.sh
   ```
   {: codeblock}

6. Install the collector by running the following command and then answering the following prompts as they are asked. 

   ```sh
   ./initiate_collector.sh
   ```
   {: codeblock}

   | Prompt | Response |
   |:-------|:---------|
   | Data Path | Provide the data path to your host machine. For example, `/root/compliance/`. |
   | Nmap validation | You need to run an Nmap validation only if your resources exist behind a firewall. |
	| Proxy | As extra protection, your organization might want to configure a proxy to use as an intermediary between the collector and your resources. If you select yes, be sure to provide the IP address that you want to use as the proxy, the port of your servicer, and the credentials that are needed. Then, be sure to add the following IP addresses and ports to your ACL. DNS: `161.26.0.6` and `53`. Service endpoints: `166.8.0.0` and `443`.
   | Registration key | Provide the registration key. This registration key can be found in the table on the **Collectors** page of the {{site.data.keyword.compliance_short}} UI. Expand the details for the collector that you want to register and copy the key. |
   {: caption="Table 6. Collector installation prompts" caption-side="top"}

   The registration key is active for 24 hours. Installation must be complete and the collector must be activated within that timeframe.
   {: important}

7. Confirm that everything is installed.

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

Be sure to **Approve** your collector on the **Hybrid cloud configurations > Collectors** page of the {{site.data.keyword.compliance_short}} UI.
{: note}


