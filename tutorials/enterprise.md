---

copyright:
  years: 2020, 2023
lastupdated: "2023-02-01"

keywords: scc getting started, enterprise, scc access requirements

subcollection: security-compliance

content-type: tutorial
services: security-compliance, iam
completion-time: 20m

---

{:codeblock: .codeblock}
{:screen: .screen}
{:download: .download}
{:external: target="_blank" .external}
{:faq: data-hd-content-type='faq'}
{:gif: data-image-type='gif'}
{:important: .important}
{:note: .note}
{:pre: .pre}
{:tip: .tip}
{:preview: .preview}
{:deprecated: .deprecated}
{:beta: .beta}
{:term: .term}
{:shortdesc: .shortdesc}
{:script: data-hd-video='script'}
{:support: data-reuse='support'}
{:table: .aria-labeledby="caption"}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:help: data-hd-content-type='help'}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tsSymptoms: .tsSymptoms}
{:java: .ph data-hd-programlang='java'}
{:javascript: .ph data-hd-programlang='javascript'}
{:swift: .ph data-hd-programlang='swift'}
{:curl: .ph data-hd-programlang='curl'}
{:video: .video}
{:step: data-tutorial-type='step'}
{:tutorial: data-hd-content-type='tutorial'}
{:ui: .ph data-hd-interface='ui'}
{:cli: .ph data-hd-interface='cli'}
{:api: .ph data-hd-interface='api'}
{:release-note: data-hd-content-type='release-note'}

# Configuring your enterprise in {{site.data.keyword.compliance_short}}
{: #enterprise-scc}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, iam"}
{: toc-completion-time="20m"} 

In this tutorial, you learn how to configure your enterprise account to evaluate your resources for compliance by using {{site.data.keyword.compliance_full}}.
{: shortdesc}


## Before you begin
{: #enterprise-before}

Before you get started, be sure that you are either the owner of an Enterprise account or have a minimum of Editor access

To complete this tutorial, be sure that you have the following requirements:

* A Pay-As-You-Go or Subscription [{{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started) where you are the owner or have [full **Administrator** access](/docs/account?topic=account-assign-access-resources)
* Docker
* Resources in your {{site.data.keyword.cloud_notm}} account


## Assign access
{: #enterprise-access}
{: step}

As an account administrator, you must provide your compliance focal specific access to ensure that they are able to configure scanning across the entire enterprise.

1. [Create an access group](/docs/account?topic=account-groups#create_ag) and add all of the people in your account that need to manage compliance.
2. After you create the group, go to **Manage > Access (IAM) > Access Groups** and select the name of the group that you created.
3. Click **Access > Assign access**.
4. From the **Service** drop down, select **Enterprise**. 

for the type of users that you want to give access to and add those users to the group. For example, you might have a team of compliance specialists that need the same level of access.
2. After you create a group and add users, go to the **Manage > Access (IAM) > Access Groups** page of the console.
3. Select the name of the group that you want to assign access to.
4. Click **Access > Assign access**.
5. Select **{{site.data.keyword.compliance_short}}** as the **Service** and click **Next**.
6. Leave **All resources** selected and click **Next**.
7. Assign the appropriate level of access.

enterprise.enterprise.attach-config-rules
enterprise.enterprise.detach-config-rules
enterprise.enterprise.update-config-rules
enterprise.account-group.attach-config-rules
enterprise.account-group.detach-config-rules
enterprise.account-group.update-config-rules
enterprise.account.attach-config-rules
enterprise.account.detach-config-rules
enterprise.account.update-config-rules
enterprise.account.retrieve
enterprise.account-group.retrieve
enterprise.enterprise.retrieve
global-search-tagging.resource.read


10:53
They also want to make sure it's documented what permissions they need on the COS and events notification services to do the initial setup of SCC. I'm not sure if that should go in the enterprise topic because it's not specific to enterprise, but it should go somewhere in the docs


## Set up storage
{: #enterprise-storage}
{: step}




## Configure an attachment
{: #enterprise-attachment}
{: step}



## Optional: Configure notifications
{: #enterprise-notifications}
{: step}








