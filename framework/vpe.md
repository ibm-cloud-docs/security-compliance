---

copyright:
  years: 2020, 2023
lastupdated: "2023-10-17"

keywords: isolation for {{site.data.keyword.compliance_short}}, service endpoints for {{site.data.keyword.compliance_short}}, private network for {{site.data.keyword.compliance_short}}, network isolation in {{site.data.keyword.compliance_short}}, non-public routes for {{site.data.keyword.compliance_short}}, private connection for {{site.data.keyword.compliance_short}}, private endpoints 

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Using private endpoints to connect to {{site.data.keyword.compliance_short}}
{: #private-endpoints}

You can use private routes to {{site.data.keyword.cloud_notm}} service endpoints to ensure that you have enhanced control and security over your data when you use {{site.data.keyword.compliance_full}}. Private routes are not accessible or reachable over the internet. By using the {{site.data.keyword.cloud_notm}} private service endpoints, you can protect your data from threats from the public network, and logically extend your private network.

## Before you begin
{: #before-vpe}

First, you must enable virtual routing and forwarding in your account before you can enable the use of {{site.data.keyword.cloud_notm}} private service endpoints. For more information about setting up your account to support the private connectivity option, [see Enabling VRF and service endpoints](/docs/account?topic=account-vrf-service-endpoint).

### Setting up private endpoints
{: #setup-vpe}

You must set up {{site.data.keyword.compliance_short}} instances to accept API requests from both public and private endpoints. You don't have the option to set up a {{site.data.keyword.compliance_short}} instance to be accessible through only private endpoints.


## Viewing your endpoint URLs
{: #view-endpoints}

The service endpoint URLs are different for private and public network connections. You can find your service endpoint URLs in the **Endpoints** page of the {{site.data.keyword.compliance_short}} UI. For more information about your service endpoint URLs, [see Regions and endpoints](/docs/security-compliance?topic=security-compliance-endpoints).


