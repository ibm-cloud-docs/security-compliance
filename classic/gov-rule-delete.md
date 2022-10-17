---

copyright:
  years: 2020, 2022
lastupdated: "2022-10-17"

keywords: resource configuration, resource governance, governance, rule, config rule, properties, conditions, enforcement actions, evaluation results

subcollection: security-compliance

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


# Deleting rules
{: #rules-delete}

When you no longer need an {{site.data.keyword.compliance_full}} rule, you can delete it through the console or by using the APIs.
{: shortdesc}

A new and improved experience for {{site.data.keyword.compliance_short}} is coming soon! As part of the updates, the Configuration Governance component of the service will be temporarily removed in November 2022. Currently there is not a timeline for its return, but we'll keep you updated.
{: note}

## Before you begin 
{: #before-delete-rules}

Before you get started, be sure that you have the required level of access to delete rules. To delete a rule, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).

Be sure that you validate that the rule is no longer needed in your account before you delete it.
{: note}


## Deleting rules with the UI
{: #delete-rules-ui}
{: ui}

If you no longer need to use a rule, you can choose to delete it by using the {{site.data.keyword.compliance_short}} UI. To delete an existing rule by using the {{site.data.keyword.compliance_short}} UI:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and Compliance**.
2. In the navigation, click **Configure rules**.
3. Use the **Configuration rules** table to browse the rules in your account.
4. Click the **Actions** icon ![Actions icon](../../icons/actions-icon-vertical.svg) to open a list of options for the rule that you want to delete.
5. From the options menu, click **Delete** and confirm the deletion in the next screen.

## Deleting rules with the API
{: #delete-rules-api}
{: api}

If you no longer need to use a rule, you can choose to delete it by using the {{site.data.keyword.compliance_short}} APIs. The following example request deletes an existing rule.

```sh
curl -X DELETE \
"https://compliance.<domainName>/config/v1/rules/<ruleID> \
  -H 'Authorization: Bearer <accessToken>'
  -H 'Content-type: application/json'
```
{: codeblock}

A successful `DELETE config/v1/rules/<ruleID>` response returns a `204 No Content` status code to indicate that your rule was successfully deleted. For more information about the required and optional request parameters, see [Delete a rule](/apidocs/security-compliance-config#delete-rule).

