---

copyright:
  years: 2021, 2023
lastupdated: "2023-06-28"

keywords: goals, parameters, customize parameters, customize goals, security and compliance,

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Customizing goals
{: #custom-goals}

With {{site.data.keyword.compliance_full}}, you can update the default parameters that are associated with the goals within each predefined profile, or you can assign tags to help classify your goals.
{: shortdesc}


The collector-based architecture is deprecated. For more information, see the [release notes](/docs/security-compliance?topic=security-compliance-release-notes).
{: deprecated}



## Before you begin
{: #before-custom-goals}

Before you get started, be sure that you have the required level of access to customize goal parameters. To edit parameters and tags, you need the editor platform role or higher for the {{site.data.keyword.compliance_short}}. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).


## Editing goal parameters
{: #edit-goals}

To update the default parameters for the goals that you use, you can use the {{site.data.keyword.compliance_short}} UI. 

When you change a parameter, it affects all the goals in that profile.
{: note}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Hybrid cloud configurations > Goals**.
3. Select the **Parameters** tab.
4. In the **Parameters** table, select the profile that you want to customize. 
5. Click the **Actions** icon ![Actions icon](../icons/actions-icon-vertical.svg) and click **Edit**.
6. Update the parameters that you want to customize.
7. To save your changes, click **Update**.

If you make an accidental change, you can click **Revert** to return all the profiles back to default.
{: tip}

## Mapping tags
{: #tags}

Tags are platform level labels that are used by {{site.data.keyword.compliance_short}} to guide which goals are applied to which resources. In some standards, for example, *CIS AWS 3-tier Web Architecture Benchmark*, different goals are applicable to different tiers. The Benchmark uses the keywords `Web`, `App`, and `DB`. But within your company you might use different naming conventions. By creating the mapping, you can ensure that the service is aware of the terms that you use for the Web, App, Database, and Data architecture tiers.


1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Hybrid cloud configurations > Goals**.
3. Select the **Tags** tab.
3. Click **Create**.
4. Add the tag that you use in the **Name** field and optionally provide a description.
5. Select the tag type that aligns with your architecture tier.

   | Tier mapping | Definition | Commonly used terms |
   | --------- | ----------- | --------|
   | Web tier | The web tier of your deployment architecture is generally written in HTML, CSS, or JavaScript and is presented to a user through a web browser or application. | Front end, web, browser, client, or presentation. |
   | App tier | The app tier of your deployment architecture is written in a programming language, such as Java or Go, and contains the business logic that supports your application's core function. | Logic, core, application, backend, or APIs. |
   | DB tier | The database tier of your deployment architecture consists of a database and the system that is used to manage it, such as MySQL or MongoDB. | Server, storage, or database. |
   | Data tier | The data tier of your deployment architecture consists of application storage that might not be specific to a database or communication port. | Storage or log files. |
   {: caption="Table 1. Understanding tag mapping" caption-side="top"}

6. Click **Save**.

