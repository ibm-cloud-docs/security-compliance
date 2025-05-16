---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: "isolation for {{site.data.keyword.compliance_short}}, service endpoints for {{site.data.keyword.compliance_short}}, private network for {{site.data.keyword.compliance_short}}, network isolation in {{site.data.keyword.compliance_short}}, non-public routes for {{site.data.keyword.compliance_short}}, private connection for {{site.data.keyword.compliance_short}}, private endpoints "

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Using private endpoints to connect to {{site.data.keyword.compliance_short}}
{: #private-endpoints}


As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


With {{site.data.keyword.compliance_full}}, you can use private routes, that are not accessible or reachable over the internet, to enhance the control and security that you have over your data. By using the {{site.data.keyword.cloud_notm}} private service endpoints, you can protect your data from threats from the public network, and logically extend your private network.

## Before you begin
{: #before-vpe}

First, you must enable virtual routing and forwarding in your account before you can enable the use of {{site.data.keyword.cloud_notm}} private service endpoints. For more information about setting up your account to support the private connectivity option, [see Enabling VRF and service endpoints](/docs/account?topic=account-vrf-service-endpoint).

### Setting up private endpoints
{: #setup-vpe}

You must set up {{site.data.keyword.compliance_short}} instances to accept API requests from both public and private endpoints. You don't have the option to set up a {{site.data.keyword.compliance_short}} instance to be accessible through only private endpoints.


## Viewing your endpoint URLs
{: #view-endpoints}

The service endpoint URLs are different for private and public network connections. You can find your service endpoint URLs in the **Endpoints** page of the {{site.data.keyword.compliance_short}} UI. For more information about your service endpoint URLs, [see Regions and endpoints](/docs/security-compliance?topic=security-compliance-endpoints).
