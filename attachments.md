---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: attachment, scan resources, scc, run evaluation

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Creating an attachment
{: #attachments}

As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}

To start evaluating your resources, you must create an attachment by specifying which profile you want to evaluate against which scope. To learn more about scopes and profiles, see [How does {{site.data.keyword.compliance_short}} work](/docs/security-compliance?topic=security-compliance-posture-management).
{: shortdesc}

Running an evaluation does not ensure regulatory compliance. An evaluation provides a point in time statement of your current posture for a specific resource. It is your responsibility to review and interpret the results to ensure that your organization is adhering to the controls that are required for your industry. 
{: important}

## Before you begin
{: #before-attachment}

Before you get started be sure that you have the following prerequisites.

* [A scope](/docs/security-compliance?topic=security-compliance-scopes).
* [A profile](/docs/security-compliance?topic=security-compliance-predefined-profiles).
* [A storage configuration](/docs/security-compliance?topic=security-compliance-storage).
* The required level of access to create and manage attachments. To create attachments, you must have [the **Writer** service role or higher](/docs/security-compliance?topic=security-compliance-access-management).


## Creating an attachment
{: #create-attachment}

To create an attachment, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, go to the **Resource list** page and select your instance of {{site.data.keyword.compliance_short}}.
2. In your instance of {{site.data.keyword.compliance_short}}, go to the **Attachments** page and click **Create**.
3. Provide a name and description for your attachment. Then, click **Next**.
   
   Be sure that this is as descriptive as possible so that other members of your team can quickly find the information that they're looking for.

4. Select the profile that you want to evaluate. Then, provide the information for any of the configurable parameters that you want to adjust.
5. Click **Next**.
6. Select the scope that you want to target. Then, click **Next**.

   The scopes that are available in this view are filtered only to those scopes that contain resources that can be evaluated against your selected profile. If you aren't seeing the scope that you created, select a different profile or adjust the resources included in your scope.
   {: tip}

7. In the annotation section, add custom annotations to individual controls. These annotations are for reference only and do not affect the evaluation process. Then, click **Next**.

   An annotation is a note that a user can add to a control. While these can be anything, typically they are used to highlight how your organization manages, mitigates, or remediates a control. For example, if you are looking at Control ID A.10.11 - Encryption of data, you might add the following test procedures as an annotation.

   * Verify that encryption is enabled on all storage volumes containing sensitive data by inspecting system configurations.
   * Review a sample of transmission logs to ensure data in transit is being encrypted using TLS 1.2 or higher.
   * Conduct a key management audit to confirm that keys are being stored securely and are rotated as required.

8. Define your scan settings.

   1. Select the **Frequency** at which you want your evaluation to be conducted.
   2. Configure notifications regarding failures that are identified.
   3. Click **Next**.

9. Review your selections. If everything looks correct, click **Create**.


When you create your attachment, a scan is scheduled. When the scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard.


## Running a scan on demand
{: #scan-ondemand}

If you already have an attachment that is being evaluated on a schedule, but you don't want to wait for your next evaluation, you can initiate a scan on-demand.

1. In the {{site.data.keyword.cloud_notm}} console, go to the **Resource list** page and select your instance of {{site.data.keyword.compliance_short}}.
2. In your instance of {{site.data.keyword.compliance_short}}, go to the **Attachments** page.
3. From the overflow menu on row of the attachment that you want to scan, select **Run scan**.

After your scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard.
