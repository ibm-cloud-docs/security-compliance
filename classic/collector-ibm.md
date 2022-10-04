---

copyright:
  years: 2020, 2022
lastupdated: "2022-10-04"

keywords: collector, security and compliance, security, compliance, install, resource monitoring, configuration monitoring, security, approve collector, register collector, use credentials, ibm managed collector, ibm managed

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
{:release-note: data-hd-content-type='release-note'}


# Configuring managed collectors
{: #ibm-collector}

For the {{site.data.keyword.compliance_full}} to gather and validate information about your resource configurations, you must create a collector. An IBM managed collector is created on IBM owned infrastructure and is maintained by the {{site.data.keyword.compliance_short}}. To learn more about how collectors work, how your data is handled, and your responsibilities, see [What is a collector?](/docs/security-compliance?topic=security-compliance-collector).
{: shortdesc}


## Before you begin
{: #before-collector-ibm}

Before you get started, be sure that you have the required level of access to view and manage collectors. To administer collectors, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).


Before you get started, be sure that you understand [the limitations](/docs/security-compliance?topic=security-compliance-known-issues-limits#ibm-collector-limits).
{: important}


### Updating your IP address restrictions
{: #before-collector-ip-address}

If the account in which you want to install your collector restricts access to some IP addresses, you must allow access to the following list of addresses along with your own in order for the managed collector to gather data in that location. 


| Location | IP addresses |
| --- | --- |
| United States | `150.239.179.224/27`, `52.116.28.0/27`, `169.62.230.48/28`, `52.116.224.64/28`, `169.46.94.0/28`, `150.238.252.224/27` |
| European Union | `158.177.77.112/28`, `159.122.112.96/27`, `161.156.11.32/27`, `161.156.18.0/28`, `149.81.148.224/28`, `149.81.181.224/27`, `149.81.131.192/28`, `158.177.244.192/28`, `161.156.178.96/28` |
{: caption="Table 1. IP addresses for IBM managed collectors" caption-side="top"}

To learn more about updating your IP address settings, see [Allowing specific IP addresses for an account](/docs/account?topic=account-ips#ips_account).


## Creating a managed collector with the console
{: #create-managed-collector-ui}
{: ui}

You can use the {{site.data.keyword.compliance_short}} UI to create a collector by completing the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Manage posture > Configure > Collectors**.
3. Click **Create**.
4. Give your collector a name and description.

   It is helpful to ensure that the name is unique across your organization so that its intended purpose is clear to other members of your team.

5. Click **Next**.
6. In the **Managed by** field, select **IBM**.
7. **UBI** is selected as the default container **image type**.

   Universal Base Images (UBI) are OCI-compliant container-based operating system images. They cannot be used with Windows OS.

8. By default, the **Private** endpoint type is selected.

   A collector requires constant communication with the service to validate your current posture. By default, a private endpoint is used for communication in all IBM managed collectors.

9. Click **Create**. When the collector is created successfully, the status updates to **Installing**.

When it's time for your scan to run, the status updates to **Active**.

## Creating a managed collector with the API
{: #create-managed-collector-api}
{: api}

You can use the {{site.data.keyword.compliance_short}} Posture Management API to create a collector by making the following POST request.

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
{: caption="Table 1. Understanding the variables used to create a collector with the API" caption-side="top"}

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

