---

copyright:
  years: 2023
lastupdated: "2023-10-10"

keywords: Centralized security, workload protection, compliance monitoring, compliance, scan, sysdig, multicloud, multi-cloud, azure, amazon, aws

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Connecting {[scc-wp]}
{: #setup-workload-protection}

When you integrate an instance of {[scc-wp-full]} with {[scc]}, you can run scans that validate your level of compliance to a specific predefined profile. Then, you can view all the results and a history of those results in a single location.
{: shortdesc}

You can pull results from multiple environments, including Amazon Web Services and Microsoft Azure, into the {[scc]} by connecting an instance of {[scc-wp]} to the service. In your {[scc-wp]} instance, create a connection that contains the compliance data that you want to see so that you can see both {[cloud]} and {[scc-wp]} results in one view.

To learn more about how the integration is configured, check out the following diagram.

![The image shows the sequence of events that a user follows as part of setting up the integration.](../images/workload-protection.svg){: caption="Figure 1. {[scc-wp]} integration flow" caption-side="bottom"}

1. Register an {[cos]} bucket to store results.
1. Create an instance of {[scc-wp]} from the {[cloud]} catalog.
1. In your {[scc]} instance, register your {[scc-wp]} integration.
1. Create an attachment between the scope and the profile. A scope is the set of resources that you want to evaluate, and the profile contains the controls that you want to evaluate. For AWS and Azure, you specify the filters that you want to get fine-grained results.
1. Navigate to the dashboard in the {[scc]} UI to view your results.

## Before you begin
{: #wp-before}

Before you get started, be sure that you have the following prerequisites:

* An {[cloud]} account. For more information, see [Setting up your {[cloud]} account](/docs/account?topic=account-account-getting-started).
* An instance of the {[scc]} service. For more information, see [Create an instance](/docs/security-compliance?topic=security-compliance-getting-started#gs-instance).
* A {{site.data.keyword.cos_short}} bucket to store results. For more information, see [Setting up data storage and processing for {[scc]}](/docs/security-compliance?topic=security-compliance-storage).
* An instance of {{site.data.keyword.sysdigsecure_full_notm}}. For more information about creating an instance from the {[cloud]} catalog, see [Getting started with {[scc-wp]}](/docs/workload-protection?topic=workload-protection-getting-started).

   Make note of the values of your resources (for example, cluster name and region) from your {[scc-wp]} instance.
   {: important}

* The required level of access to create and manage integrations in {[scc]}. To pull results from {[scc-wp]}, you must have the *administrator* platform role or higher for the {[scc]} service. For more information, see [Assigning access]({[link]}-access-management).


You must select a profile that targets another environment. For example, Azure Kubernetes Service (AKS) profile or Amazon Web Services (AWS) profile. If you want to use controls from multiple profiles, you are able to create a custom profile that contains only the controls that you want to evaluate.
{: tip}


## Registering the integration
{: #wp-register}

Register an integration with the {[scc]}.

1. In the {[cloud]} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) > **Security and Compliance** to access the {[scc]}.
1. In the navigation, click **Integrations**.
1. In the **{[scc-wp]}** tile, click **Connect**.
1. On the **Connect your {[scc-wp]}** account panel, provide a name for your connection.
1. Set up service-to-service authorization, which allows {[scc]} to communicate with {[scc-wp]}.
   1. When you are prompted for service authorization, click **Authorize**.
   1. For the target service, select {[scc-wp]}. {[scc]} is the source service. Reader access is automatically selected. Click **Review**.
   1. On the **Review** page, ensure that the target service and role are correct, and then click **Assign**.

   Alternatively, you can use IAM to create an authorization to allow the {[scc]} service instance access to the {[scc-wp]} service instance.
   {: note}

1. Select the {[scc-wp]} instance, and then click **Connect**.

After the connection is successfully created, click the **Connected** tab. If you want to open the {[scc-wp]} instance dashboard, click **Dashboard URL**.

## Creating the attachment
{: #wp-attachment}

To evaluate your resources, you create an attachment. An attachment is the association between the set of resources that you want to evaluate and a profile that contains the specific controls that you want to evaluate. An attachment is how you target a specific grouping of your resources to evaluate against a specific profile.

You must have already have a {{site.data.keyword.cos_short}} bucket available. Be sure to use a bucket that's located in the same region that your data is processed.

To create an attachment, complete these steps:

1. In the {[scc]} UI, navigate to the **Attachments** page and click **Create**. A flat list of all of the attachments in your account is displayed.
2. Provide a name and description for your attachment. Be sure to be as descriptive as possible so that it's easy for other members of your team to understand what is being evaluated. Then, click **Next**.
3. If you don't already have {[cos]} bucket configured, you will be prompted to **Connect** one. You must connect a {[cos]} bucket to store your evaluation results. As a best practice, it is recommended that you use a bucket that is located in the same region in which your data is processed.
4. Select the **Profile** and **Profile version** that you want to use for your evaluation.

   You must select a profile that targets another environment by using `wp-rule` evaluations in order to scan other cloud platforms. For example, Azure Kubernetes Service (AKS) profile or Amazon Web Services (AWS) profile target other environments. If you want to use controls from multiple profiles, you are able to create a custom profile that contains only the controls that you want to evaluate. 
   {: tip}

5. Customize the underlying evaluations in your scan by editing the default parameters to match your specific use case.
6. Target the resources you want to evaluate by defining a scope. If you are working with {[cloud]} resources, you can also specify resources that you want to exclude from your scope. If you are working with resources from other environments, you must [connect an instance of the {[scc-wp]} service]({[link]}-setup-workload-protection) and provide the requested information to move forward.
7. Select the frequency at which you want to evaluate your attachment. Options include every day, every 7 days, and every 30 days. Additionally, you can pause your scans if you need to. Then, click **Next**.
8. Indicate whether you want to be notified if evaluations fail during a scan. For more information about setting up the notifications, see [Running an evaluation]({[link]}-scan-resources).
9. Review your settings, and ensure that all of the configurations are correct for your targeted scope. Then, click **Create**.

Based on the schedule that you defined in your connection, {[scc-wp]} pulls the data in your account to the {[scc]}.

## Viewing the results
{: #wp-results}

To view the results of your scan, go to the dashboard in the UI of the {[scc]} instance that you are working with. For more information about the details in your results, see [Viewing results]({[link]}-results).

