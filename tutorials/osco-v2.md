---

copyright:
  years: 2021, 2023
lastupdated: "2023-10-10"

keywords: goals, parameters, customize parameters, customize goals, security and compliance,

subcollection: security-compliance

content-type: tutorial
services: security-compliance, openshift
completion-time: 20m

---

{{site.data.keyword.attribute-definition-list}}

# Evaluate the compliance of your {[os]} clusters 
{: #osco-scan}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, openshift"}
{: toc-completion-time="20m"}

By using the OpenShift Compliance Operator (OSCO) through Security and Compliance Center, you can run scans to validate your level of compliance to a grouping of controls, also known as a profile. In this scenario, you configure your cluster to be able to run the OSCO scan.

## Before you begin
{: #osco-before}

Before you get started with this tutorial, be sure you have the prerequisites:

* An {[cloud]} account
* A {[os]} cluster
* The required permissions:

   | Service | Required role | Reason |
   |:--------|:--------------|:-------|
   | {[scc]} | Compliance Management | Needed to enable a service-to-service authorization  \n To view this role, you must be assigned the Administrator role for the service |
   | {[os]} | Manager | Required to install OSCO |
   {: caption="Table 1. Required user permissions" caption-side="top"}


## Enable an authorization
{: #osco-auth}
{: step}

To ensure that the services can talk with each other, create a service-to-service authorization between {[scc]} and {[iks]}. To create this policy, you must have the Administrator platform role for the {[scc]} service.

1. In the {[cloud]} console, go to **Manage > Access (IAM)** and select **Authorizations**.
2. Click **Create**.
3. If you're working in an enterprise account, select the account which has the cluster with OSCO deployed in it as the **Source** account.
4. Select **{[scc]}** in the **Source** drop-down and choose **All resources** as the scope.
5. Select **Kubernetes Service** in the **Target** drop-down. Optionally, you can narrow the focus by selecting specific resources that you want to target.
6. Select **Platform** access as **Compliance Management** and click **Authorize**.

If you are scanning Satellite resources, you must also [enable an authorization for Satellite]({[link]}-assign-roles#assign-access-sat).
{: note}


## Install the OSCO
{: #osco-install}
{: step}

Before you can start evaluating your resources, the OSCO must be installed to your cluster. For help with installing it, see [the documentation](https://docs.openshift.com/container-platform/4.8/security/compliance_operator/compliance-operator-installation.html){: external}. When you deploy the OSCO, a bundle of predefined profiles is automatically installed and available for you to scan your resources with. In the next section, you select the profile that you want to use.


## Scan your resources
{: #osco-resources}
{: step}

To scan your resources, you create an attachment between the resource that you want to evaluate and the profile that you want to use to run the evaluation. To create an attachment, you can use the following steps.

1. In **Profiles** section of the UI, select **{[cloud]} Red Hat OpenShift Kubernetes OCP4**. A details page opens.

   Optionally, you can use the **{[cloud]} Red Hat OpenShift Kubernetes OCP4** profile to create a custom profile with a subset of the controls.
   {: tip}

2. In the **Attachments** tab, click **Create**.
2. Target your resources by selecting a **Scope**. Optionally, you can choose to exclude portions of your selected scope to ensure that they are not included in your scan.
3. Click **Next**.
4. Unless your profile contains additional controls, you can skip the **Parameters** tab by clicking **Next**.
5. Toggle **Enable scan** to **On** to ensure that the scan runs.
6. Select the frequency at which you want to evaluate your resource. Options include, **Every day**, **Every 7 days**, and **Every 30 days**.
7. Optionally, you can enable notifications.
8. Click **Next**. Review your selections and click **Create**.

## Next steps
{: #osco-next}

When the scan completes, your results become available in the {[scc]} dashboard. Be sure to check back in a few hours to see what your results returned.

