---

copyright:
  years: 2020, 2023
lastupdated: "2023-03-31"

keywords: scopes, accounts, resources, environments

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Managing scopes
{: #scopes}

When you're working with {{site.data.keyword.compliance_short}}, you can narrow the focus of your scans to a specific environment, region, or resource. By creating a scope, you can determine your security and compliance score across a specific area of your business. 
{: shortdesc}

The collector-based architecture is deprecated. For more information, see the [release notes](/docs/security-compliance?topic=security-compliance-releases).
{: deprecated}



## Before you begin
{: #before-scope}

Before you get started, be sure that you have the required level of access to view and manage scopes. To manage scopes, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).

Before you create a scope, you must have an [active collector](/docs/security-compliance?topic=security-compliance-collector).
{: note}

## Creating a scope
{: #create-scope}

To narrow the focus of your scans, create a scope by using the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In **Hybrid cloud configurations > Scopes**, click **Create**.
3. Give your scope a name and optionally provide a description. Then, click **Next**.

   Be sure to give a detailed name as you use this field later to configure scans and remediation.
   
4. Target a group of resources by selecting an **Environment** from the drop-down list.

   If you choose On-premises, you can select from multiple options to discover your resources. For example, you can [schedule a discovery scan](/docs/security-compliance?topic=security-compliance-schedule-scan), import resources from a file, or connect to a third party. Supported format for imported files is  `.json`. Max file size is 30 MB.

5. From the **Credentials** drop-down, select a credential that you previously added to the service and then click **Next**.

   If you have not yet added a credential, you can use the following steps to add one, and then select it from the drop-down.

   1. Click **Create**. A side panel opens.
   2. Provide a name and description.
   3. Select a **Purpose** and then click **Next**.
   4. Select a **Credential type**.
   5. Provide the information that is requested. For more information about each type of secret, see [Understanding credentials](/docs/security-compliance?topic=security-compliance-credentials).
   6. Click **Create**.

6. From the table, select the [collector](/docs/security-compliance?topic=security-compliance-collector) or collectors that you want to use to gather configuration data and then click **Next**.
7. Create an attachment between your scope and profile by scheduling a scan.

   1. Give your scan a name and description.
   2. Select a **Scan type**.
   3. From the **Profile** drop-down, select the profile that you want to use to evaluate your configuration.

      If your scope includes a deployment of either the [{{site.data.keyword.vpc_full}} reference architecture](/docs/framework-financial-services?topic=framework-financial-services-vpc-architecture-about) for the {{site.data.keyword.cloud_notm}} for Financial Services™, then select the latest version of the {{site.data.keyword.cloud_notm}} for Financial Services profile. This profile maps a tailored set of Security and Compliance Center goals to the control requirements in the {{site.data.keyword.framework-fs_full}}. You can also choose to create a [custom profile](/docs/security-compliance?topic=security-compliance-custom-profiles) that contains the specific subset of goals from a profile that you want to evaluate your resources for. 
      {: note}

   4. **Enable** or **Disable** the profiles that are associated with your integrated resources. For more information about integrations, see the [integrations tab of the UI](/security-compliance/integrations){: external}.

      If you are working with any {{site.data.keyword.openshiftshort}} resources, you must enable the [OSCO integration](/security-compliance/integrations){: external}, and then enable profiles during this step in order for those resources to be evaluated.
      {: note}

   5. If applicable: Select a remediation type.

      Only some environments are configured to provide automatic remediation. For more information, see [Remediating issues](/docs/security-compliance?topic=security-compliance-remediation).

   6. Select the **Frequency** at which you want your scans to run and click **Next**.

      The scan automatically begins when the scope is created. To change your frequency or stop your scans, you can update the scan on the **Scans** page.

8. Review your selections and click **Create**.

If you're working with a scope that requires more than one set of credentials to access the resources within it, be sure to [map your credentials](/docs/security-compliance?topic=security-compliance-credentials).
{: tip}


## Updating a scope
{: #update-scope}

If you need to update the resources that are scanned as part of a scope, you can edit an existing scope. However, you cannot update an environment that the scope is associated with. If you want to change an environment, create a new scope.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the **Manage Posture** section of the navigation, click **Configure > Scopes**.
3. Select the scope that you want to edit in the table.
4. Click **Details**. A side panel appears.
5. Click **Edit**.
6. Optional: Update the general details of your scope, such as the name or description. 
7. Click **Next**.
8. Optional: Update the resources that you want to scan.
9. Click **Save**.

## Deleting a scope
{: #delete-scope}

If you no longer need to evaluate a particular group of resources, you can delete the scope.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Hybrid cloud configurations  > Scopes**.
3. Click the **Actions** icon ![Actions icon](../icons/actions-icon-vertical.svg) in the row of the scope that you want to delete, then click **Delete**.
4. To verify that you understand that any scheduled scans that are associated with that scope are canceled, click **Delete**.

The scope is not fully deleted, but is rendered inactive. You can still access the history of the scans.
{: note}



## Viewing scope details
{: #view-scope}

You can view the details of your existing scopes and create a new mapping by using the {{site.data.keyword.compliance_short}} UI.
{: shortdesc}

### Viewing scope details
{: #detail-scope}

To view the details of the scopes that you create, you can complete the following steps.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Hybrid cloud configurations > Scopes**.
3. From the **Scopes** table, select the scope that you want to see in more detail. A new page opens that displays which credentials and collectors are used in the scope, as well as an inventory of the resources that are available in the scope.
4. Click **Event history** to see the historical archive of each scan that has been run on the scope. If there are more details available for the scan, the event time is clickable.
5. Click **Attachments** to see which profiles are currently being used to validate the resources in your selected scope.

You can run a one-time on demand scan from the **Actions > Scan** drop down on the scope details page.
{: tip}


## Creating a new resource mapping
{: #resource-mapping}

When an Nmap scan is run on on-premises resources, occasionally a resource is misidentified. To override the mapping that is made by the scan, you can create a new mapping in the UI.

![This image is a visual representation of how to apply your credentials to specific resources in the GUI. The information that is shown in the image is detailed in the surrounding text.](images/cluster-credential-map.svg){: caption="Figure 2. Mapping credentials through the UI" caption-side="bottom"}

To update a resource mapping:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Hybrid cloud configurations > Scopes**. Select the scope that you want to update.
3. From the scope details page, select **Resource mapping** from the **Actions** drop-down.
4. Click **Create**.
5. Create a mapping for a virtual machine by selecting a **Virtual machine**, **Object**, **Operating system**, and **Vendor** for your resource. The VM and object are required fields.

