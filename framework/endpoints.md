---

copyright:
  years: "2024"
lastupdated: "2024-10-15"

keywords: security compliance developer tools, integrate with application, API, SDK, CLI

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Regions and endpoints
{: #endpoints}

Review region and connectivity options for interacting with {{site.data.keyword.compliance_full}}.
{: shortdesc}

## Supported regions
{: #supported-regions}

You can create {{site.data.keyword.compliance_short}} resources in one of the supported {{site.data.keyword.cloud_notm}} regions, which represents the geographic area where your {{site.data.keyword.compliance_short}} requests are handled and processed.

- Dallas (`us-south`)
- Frankfurt (`eu-de`)
- Toronto (`ca-tor`)
- Madrid (`eu-es`)

## Service endpoints
{: #service-endpoints}

You can use the {{site.data.keyword.compliance_short}} APIs to manage your resources programmatically. You can connect to resources in your account over the {{site.data.keyword.cloud_notm}} public network. Your data is encrypted in transit by using the Transport Security Layer (TLS) 1.2 protocol.

Review the following table to determine the API endpoints to use when you connect to the {{site.data.keyword.compliance_short}} API.

| Region        | Endpoint URL             |
| ------------- | ---------------------------- |
| Dallas        | **Public:** `https://us-south.compliance.cloud.ibm.com/instances/{instance_id}/v3`  \n  \n  **Private:** `https://private.us-south.compliance.cloud.ibm.com/instances/{instance_id}/v3` | 
| Frankfurt     | **Public:** `https://eu-de.compliance.cloud.ibm.com/instances/{instance_id}/v3`  \n  \n  **Private:** `https://private.eu-de.compliance.cloud.ibm.com/instances/{instance_id}/v3` |
| Toronto       |  **Public:** `https://ca-tor.compliance.cloud.ibm.com/instances/{instance_id}/v3`  \n  \n  **Private:** `https://private.ca-tor.compliance.cloud.ibm.com/instances/{instance_id}/v3` |
| Madrid       | **Public:** `https://eu-es.compliance.cloud.ibm.com/instances/{instance_id}/v3`  \n  \n  **Private:** `https://private.eu-es.compliance.cloud.ibm.com/instances/{instance_id}/v3` |
{: caption="Endpoints for interacting with {{site.data.keyword.compliance_short}}" caption-side="top"}




### Viewing your endpoint URLs
{: #view-endpoint-urls}

You can find your service endpoint URLs in the **Settings** page of the {{site.data.keyword.compliance_short}} UI. If you need to retrieve your service endpoint URLs programmatically, you can also call the following API to retrieve the values that are specific to your {{site.data.keyword.compliance_short}} instance.


```sh
curl -X GET  
    -H "Accept: application/json" \
    -H "Authorization: Bearer <IAMToken>"
https://us-south.compliance.cloud.ibm.com/instances/<instanceId>/v3/{urlEncodedInstanceCRN}/endpoints"
```
{: pre}


Replace the variables in the example request according to the following table.

| Parameter | Description |
| --- | --- |
| `region` | The region abbreviation that represents the geographic area where your {{site.data.keyword.compliance_short}} is located. For example, `us-south` or `eu-de`. |
| `url_encoded_instance_CRN` | The Cloud Resource Name (CRN) that uniquely identifies your {{site.data.keyword.compliance_short}} service instance. The value must be URL encoded. |
| `IAM_token` | Your {{site.data.keyword.cloud_notm}} IAM access token. |
{: caption="Required parameters for retrieving service endpoints with the API" caption-side="top"}

A successful request returns the endpoint URLs that are associated with the region and service instance CRN that you specify. 
