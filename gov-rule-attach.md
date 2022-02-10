---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-10"

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


# Applying rules
{: #rules-apply}

After you've created a rule, you can use the {{site.data.keyword.compliance_full}} to target a specific area of your organization where you want to apply the rule by using the console or the APIs.
{: shortdesc}

To apply your rule, you create an attachment between a scope, such as an account, an account group, or an entire enterprise to ensure that your rule is applied on only those resources that you want to target.

To learn more about how rules are applied in an enterprise, see [Applying your rules and templates](/docs/security-compliance?topic=security-compliance-what-is-governance#hierarchy).

## Before you begin
{: #before-rules}

Before you get started, be sure that you have the required level of access to view and manage rules. To create a rule, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management). Be sure that you also have an instance of {{site.data.keyword.at_short}} in the region that you provision resources. You must also have a [defined rule](/docs/security-compliance?topic=security-compliance-rules-define) before it can be applied.


## Attaching a rule to a scope with the UI
{: #evaluate-rules-ui}
{: ui}

By creating an attachment between a rule and a scope, you can monitor the resources that exist in that scope against the rule that you defined. If you have a specific account that you don't want the rule to apply to, you can choose to exclude it. For example, if you apply a rule to an entire enterprise you might want to exclude a scope that is used primarily for testing.

To create an attachment for a rule by using the {{site.data.keyword.compliance_short}} UI:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance**.
2. In the navigation, click **Configure rules**.
3. From the list of rules, click the name of the rule that you want to attach.
4. Click **Attachments**. If the rule that you selected is attached to any scopes, you see them in a table.
5. Click **Attach** to review your attachment options.
   1. Decide whether to apply the rule across your entire enterprise or narrow it to a specific account.
   2. Review the hierarchy of the account or enterprise that you selected.
   3. If you want to exclude a scope, switch the toggle to **Yes**. Select the scopes that you want to exclude and click **Add**.
6. Click **Attach**.

   Now that your rule is attached to a scope, the scope is scanned for possible noncompliance the next time that a scan is scheduled to run. Updated reports are generated automatically for your resources once every 24 hours.

## Attaching a rule to a scope with the API
{: #evaluate-rules-api}
{: api}

By creating an attachment between a rule and a scope, you can monitor the resources that exist in that scope against the rule that you defined. If you have a specific account that you don't want the rule to apply to, you can choose to exclude it. For example, if you apply a rule to an entire enterprise you might want to exclude a scope that is used primarily for testing.

The following example request creates an attachment between an existing rule and a scope.

```sh
curl -X POST \
"https://compliance.{DomainName}/config/v1/rules/<rule_ID>/attachments" \
  -H 'Authorization: Bearer <access_token>' \
  -H 'Content-type: application/json' \
  -d '{
  "attachments": [
    {
      "included_scope": {
        "scope_id": "<included_scope_ID>",
        "scope_type": "<scope_type>",
        "note": "<description>"
      },
      "excluded_scopes": [
        {
          "scope_id": "<excluded_scope_ID",
          "scope_type": "<scope_type>",
          "note": "<description>"
        }
      ]
    }
  ]
}'
```
{: codeblock}

A successful `POST config/v1/rules/{rule_ID}/attachments` response returns the ID value for the attachment, along with other metadata. For more information about the required and optional request parameters, see [Create attachments](/apidocs/security-compliance/config#create-attachments).

