---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: getting started with the security and compliance center, get started, security, compliance

subcollection: security-compliance

content-type: tutorial
services: security-compliance, cloud-object-storage, event-notifications, iam
completion-time: 5m

---

{{site.data.keyword.attribute-definition-list}}

# Getting started with {{site.data.keyword.compliance_short}}
{: #getting-started}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, cloud-object-storage, event-notifications, iam"}
{: toc-completion-time="5m"}


As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the replacement service {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


For highly regulated industries, such as financial services, achieving continuous compliance within a cloud environment is an important first step toward protecting customer and application data. Historically, that process was difficult and manual, which placed your organization at risk. But, with {{site.data.keyword.compliance_full}}, you can integrate daily, automatic compliance checks into your development lifecycle to help minimize that risk.
{: shortdesc}


Running an evaluation does not ensure regulatory compliance. An evaluation provides a point in time statement of your current posture for a specific resource. It is your responsibility to review and interpret the results to ensure that your organization is adhering to the controls that are required for your industry.

## Before you begin
{: #before-gs}

Before you get started, be sure that you have the following prerequisites.

* An instance of {{site.data.keyword.compliance_short}}.
* An instance of Cloud Object Storage that contains a bucket that can be used to store your results data.
* Resources in your account that you want to evaluate.
* The required access to create and manage resources within {{site.data.keyword.compliance_short}}. To create and manage entities within {scc}, you must have [the **Writer** service role or higher](/docs/security-compliance?topic=security-compliance-access-management). 


## Configure storage
{: #gs-storage}
{: step}

Before you can start evaluating your resources for compliance, you must configure a Cloud Object Storage bucket where the service can forward your results data for long-term storage. For more information about bucket requirements, see [Storing and processing data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-storage).

To connect your Cloud Object Storage bucket, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.compliance_short}} navigation, click **Settings**.
2. On the **Storage** tile, click **Connect**.
3. Ensure that the service-to-service policy between Cloud Object Storage and {{site.data.keyword.compliance_short}} is configured. If a policy is already in place, this screen is not shown and you can skip to the next step. 
4. Select an instance of Cloud Object Storage.
5. From the table, select the bucket that you want to use.
6. Click **Connect**.

## Create a scope
{: #gs-scope}
{: step}

A scope is the grouping of resources that you want to evaluate. For help with creating a scope, see [Targeting your resources](/docs/security-compliance?topic=security-compliance-scopes).

## Optional: Review available profiles
{: #gs-profile}
{: step}

Before you start configuring your attachment, you can review the available profiles and compare them to ensure that you're using the one that is best for your use case. You can use the **Profiles** tab of the {{site.data.keyword.compliance_short}} UI or read more about them in [Available predefined profiles](/docs/security-compliance?topic=security-compliance-predefined-profiles).

## Evaluate your resources
{: #gs-attachment}
{: step}

To evaluate your resources, you must create an attachment. An attachment pairs the resources that you grouped as a scope with the profile that you want to evaluate them against.

1. In your instance of {{site.data.keyword.compliance_short}}, go to the **Attachments** page and click **Create**.
2. Provide a name and description for your attachment. Then, click **Next**.
   
   Be sure that this is as descriptive as possible so that other members of your team can quickly find the information that they're looking for.

3. Select the profile that you want to evaluate. Then, provide the information for any of the configurable parameters that you want to adjust.

   New attachments cannot be created on deprecated profile versions. Select the most recent version to use for your evaluation.
   {: important}

4. Click **Next**.
5. Select the scope that you want to target. Then, click **Next**.

   The scopes that are available in this view are filtered only to those scopes that contain resources that can be evaluated against your selected profile. If you aren't seeing the scope that you created, select a different profile or adjust the resources included in your scope.
   {: tip}

6. In the annotation section, add custom annotations to individual controls. These annotations are for reference only and do not affect the evaluation process. Then, click **Next**.

7. Define your scan settings.

   1. Select the **Frequency** at which you want your evaluation to be conducted.
   2. Configure notifications for failures that are identified.
   3. Click **Next**.

8. Review your selections. If everything looks correct, click **Create**.

When you create your attachment, a scan is scheduled. When the scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard.

## Next steps
{: #gs-next}

Now that you've got an attachment up and running, you can choose to [segment your scope](/docs/security-compliance?topic=security-compliance-subscopes) or start creating [custom profiles](/docs/security-compliance?topic=security-compliance-build-custom-profiles) that are tailored to your use cases.
