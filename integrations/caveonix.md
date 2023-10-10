---

copyright:
  years: 2023
lastupdated: "2023-10-10"

keywords: Centralized security, workload protection, compliance monitoring, compliance, scan, sysdig, multicloud, multi-cloud, azure, amazon, aws

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Connecting Caveonix Cloud Platform
{: #setup-caveonix}

Short description here


## Before you begin
{: #caveonix-before}

Before you get started, be sure that you have the following prerequisites:

* An {{site.data.keyword.cloud_notm}} account. For more information, see [Setting up your {{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started).
* An instance of the {{site.data.keyword.compliance_short}} service. For more information, see [Create an instance](/docs/security-compliance?topic=security-compliance-getting-started#gs-instance).
* A {{site.data.keyword.cos_short}} bucket to store results. For more information, see [Setting up data storage and processing for {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-storage).
* An instance of
* API keys

### Create an API key
{: #create-api}

API key is required for Caveonix to send the data. To generate an API key, you must create a Service ID. The generated api key is required for the [Configure the Caveonix to send results](##configure-caveonix-value).

1. In the IBM Cloud console, go to **Manage** > **Access (IAM)**, and select **Service IDs**.
1. Click **Create**.
1. Follow the process to create a name and description for your service ID.
1. Click **Create**.
1. Select the newly created Service ID from the list of Service IDs.
1. In the Service ID page, click **Assign Access** to configure your Service ID.

To ensure that the API key is generated successfully for Caveonix integration, Select **{{site.data.keyword.compliance_short}}** as your **Service** option and **Data Provider** under **Roles and actions**.
 {: note}

1. Click on **Assign**.
1. On your Service ID page, go to the API tab and create your API.
1. Note the API key generated.

## Creating a connection
{: #caveonix-create-connection}

To create a successful Caveonix connection with the {{site.data.keyword.compliance_short}}, you must:
1. Add Caveonix to the integration with the {{site.data.keyword.compliance_short}}.
1. Creating the attachment
1. Configure Caveonix to send results to the dashboard.

### Adding Caveonix to the integration
{: #add-caveonix-integration}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) > **Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
1. In the navigation, click **Integrations**.
1. In the **Caveonix** tile, click **Connect**.
1. On the **Connect your Caveonix RiskForesight account** panel, provide a name for your connection and click **Connect**.

If you want to open the Caveonix instance dashboard, click **Open dashboard**.

### Creating the attachment
{: #caveonix-attachment}

To evaluate your resources, you create an attachment. An attachment is the association between the set of resources that you want to evaluate and a profile that contains the specific controls that you want to evaluate. An attachment is how you target a specific grouping of your resources to evaluate against a specific profile.

You must have already have a {{site.data.keyword.cos_short}} bucket available. Be sure to use a bucket that's located in the same region that your data is processed.

To create an attachment, see [Scanning your resources](docs/security-compliance?topic=security-compliance-scan-resources&interface=ui).

 Copy or download the attachment ID.
 {: tip}

### Configure Caveonix to send results
{: #configure-caveonix}

Caveonix profile configuration must be done in Caveonix to successfully create the Caveonix connection. Before you configure you Caveonix profile, you must have the following details:

1. Provider type instance id, and Endpoint for pushing results- To view the details, go to the newly created connection in the **Intergation** section, click the **Actions** icon ![Actions icon](../icons/action-menu-icon.svg) > **View details**
1. Attachment IDs
1. API keys
1. SCC instance ID

See <link> to configure your Caveonix profile.

## Viewing the results
{: #caveonix-results}

To view the results of your scan, go to the dashboard in the UI of the {{site.data.keyword.compliance_short}} instance that you are working with. For more information about the details in your results, see [Viewing results](/docs/security-compliance?topic=security-compliance-results).
