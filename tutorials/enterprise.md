---

copyright:
  years: 2020, 2023
lastupdated: "2023-01-31"

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

# Configuring scans from an enterprise account
{: #enterprise-scc}
{: toc-content-type="tutorial"}
{: toc-services="security-compliance, iam"}
{: toc-completion-time="20m"} 

In this tutorial, you learn how to configure your enterprise account to evaluate your resources for compliance by using {{site.data.keyword.compliance_full}}.
{: shortdesc}


## Before you begin
{: #ibm-customer-collector-cluster-before}

To complete this tutorial, be sure that you have the following requirements:

* A Pay-As-You-Go or Subscription [{{site.data.keyword.cloud_notm}} account](/docs/account?topic=account-account-getting-started) where you are the owner or have [full **Administrator** access](/docs/account?topic=account-assign-access-resources)
* Docker
* Resources in your {{site.data.keyword.cloud_notm}} account


## Create a collector
{: #ibm-customer-collector-cluster-create}
{: step}

one request from BNPP for the enterprise documentation - they want to make sure all of the necessary permissions are documented for a person in the enterprise account to be able to set up and use SCC in the enterprise. I did some experimentation and if someone wants to create a custom role giving someone just the enterprise actions they need to use SCC, here is the list:
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