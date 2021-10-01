---

copyright:
  years: 2021
lastupdated: "2021-09-27"

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


# Deleting templates
{: #templates-delete}

When you no longer need an {{site.data.keyword.compliance_full}} template, you can delete it through the console or by using the APIs.
{: shortdesc}




## Before you begin
{: #before-templates}

Before you get started, be sure that you have the required level of access to delete templates. To delete a template, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).

Be sure that you validate that the template is no longer needed in your account before you delete it.
{: note}


## Deleting templates in the UI
{: #delete-templates-ui}
{: ui}

If you no longer need to use a template, you can choose to delete it by using the {{site.data.keyword.compliance_short}} UI. To delete an existing template by using the {{site.data.keyword.compliance_short}} UI:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance**.
2. In the **Govern resources** section, click **Configure > Templates**.
3. Use the **Templates** table to view the templates in your account.
4. Click the **Actions** icon ![Actions icon](../icons/actions-icon-vertical.svg) to open a list of options for the template that you want to delete.
5. From the options menu, click **Delete** and confirm the deletion in the next screen.



## Deleting templates with the API
{: #delete-templates-api}
{: api}

If you no longer need to use a template, you can choose to delete it by using the {{site.data.keyword.compliance_short}} APIs. The following example request deletes an existing template.

```sh
curl -X DELETE \
"https://compliance.{DomainName}/config/v1/templates/<template_ID> \
  -H 'Authorization: Bearer <access_token>'
  -H 'Content-type: application/json'
```
{: codeblock}

A successful `DELETE config/v1/templates/{template_ID}` response returns a `204 No Content` status code to indicate that your template was successfully deleted. For more information about the required and optional request parameters, see [Delete a template](/apidocs/security-compliance/config#delete-template).
