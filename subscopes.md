---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: scope, subscope, view results access, 

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Segmenting your scope
{: #subscopes}


As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


To run an evaluation by using {{site.data.keyword.compliance_full}}, you must target the specific resources that you want to scan by creating a scope. After your scope is created, you can segment your scope into subscopes that can be used to limit access to scan results. To learn more about scopes and best practices, see [Best practices](/docs/security-compliance?topic=security-compliance-best-practices).
{: shortdesc}

Only {{site.data.keyword.cloud_notm}} scopes can be segmented into subscopes.
{: important}

## Before you begin
{: #before-subscopes}

Before you get started, be sure that you have the following prerequisites.

* The required level of access to create and manage subscopes. To manage subscopes, you must have [the **Writer** service role or higher](/docs/security-compliance?topic=security-compliance-access-management).
* An existing scope.


## Creating a subscope
{: #create-subscope}
{: ui}

You can create a subscope by using the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, go to the **Resource list** page and select your instance of {{site.data.keyword.compliance_short}}.
2. In your instance of {{site.data.keyword.compliance_short}}, go to the **Scopes** page and select the scope that you want to segment by clicking its name.
3. In the **Subscopes** section of the **Details** panel that opens, click **Manage**
4. Click **Create**.
5. Provide a name and description for your subscope.
6. Select the resources that you want to include in the subscope.


Next, you can [create an attachment](/docs/security-compliance?topic=security-compliance-attachments) to start evaluating your resources. Or, you can [provide access](/docs/security-compliance?topic=security-compliance-access-management) to the users in your account that need to work with the subscope that you created.
