---

copyright:
  years: 2020, 2022
lastupdated: "2022-06-13"

keywords: default property values, customized defaults, templates properties, resource governance

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


# Applying templates
{: #templates-apply}

After you've created a template, you can use the {{site.data.keyword.compliance_full}} to target a specific area of your organization where you want to apply the template by using the console or the APIs.
{: shortdesc}

To apply your template, you create an attachment between a scope, such as an account, an account group, or an entire enterprise to ensure that your template is applied on only those resources that you want to target.

To learn more about how templates are applied in an enterprise, see [Applying your rules and templates](/docs/security-compliance?topic=security-compliance-what-is-governance#hierarchy).


## Before you begin
{: #before-templates-apply}

Before you get started, be sure that you have the required level of access to view and manage templates. To create a template, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).



## Attaching a template to a scope in the UI
{: #attach-template-ui}
{: ui}

By creating an attachment between a template and a scope, you can apply your customized defaults in your selected accounts. If you have a specific account that you don't want the template to apply to, you can choose to exclude it. For example, if you apply a template to an entire enterprise you might want to exclude a scope that is used primarily for testing.

To create an attachment for a template by using the {{site.data.keyword.compliance_short}} UI:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance**.
2. In the **Govern resources** section, click **Configure > Templates**.
3. From the list of templates, click the name of the template that you want to attach.
4. Click **Attachments**. If the template that you selected is attached to any scopes, you see them in a table.
5. Click **Attach** to review your attachment options.
   1. Decide whether to apply the template across your entire enterprise or narrow it to a specific account.
   2. Review the hierarchy of the account or enterprise that you selected.
   3. If you want to exclude a scope, switch the toggle to **Yes**. Select the scopes that you want to exclude and click **Add**.
6. Click **Attach**.

   Now that your template is attached to a scope, the scope is used to apply your customized defaults in your selected accounts.


## Attaching a template to a scope with the API
{: #attach-template-api}
{: api}

By creating an attachment between a template and a scope, you can apply your customized defaults in your selected accounts. If you have a specific account that you don't want the template to apply to, you can choose to exclude it. For example, if you apply a template to an entire enterprise you might want to exclude a scope that is used primarily for testing.

The following example request creates an attachment between an existing template and a scope.

```sh
curl -X POST \
"https://compliance.<domainName>/config/v1/templates/<templateID>/attachments" \
  -H 'Authorization: Bearer <accessToken>' \
  -H 'Content-type: application/json' \
  -d '{
  "attachments": [
    {
      "included_scope": {
        "scope_id": "<includedScopeID>",
        "scope_type": "<scopeType>",
        "note": "<description>"
      },
      "excluded_scopes": [
        {
          "scope_id": "<excludedScopeID",
          "scope_type": "<scopeType>",
          "note": "<description>"
        }
      ]
    }
  ]
}'
```
{: codeblock}

A successful `POST config/v1/templates/<templateID>/attachments` response returns the ID value for the attachment, along with other metadata. For more information about the required and optional request parameters, see [Create attachments](/apidocs/security-compliance-config#create-attachments).


