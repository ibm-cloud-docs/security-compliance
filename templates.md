---

copyright:
  years: 2021
lastupdated: "2021-07-12"

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

# Managing templates
{: #templates}

You can use the {{site.data.keyword.compliance_full}} to create and manage templates by using the console or the APIs.
{: shortdesc}

Templates help you define your preferred property values for supported resources in your accounts. After you create a template and attach it to a scope, your defined values override the defaults that are provided by IBM. Later, when an account user creates a resource that is targeted by the template, your customized defaults are applied.

Templates are compatible only with select {{site.data.keyword.cloud_notm}} services and resource properties. To see a list of services that support templates, see [What is a template?](/docs/security-compliance?topic=security-compliance-what-is-template)
{: note}


## Before you begin
{: #before-templates}

Before you get started, be sure that you have the required level of access to view and manage templates. To create a template, you need the editor platform role or higher. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).

To avoid duplicated definitions, you can add each property to one template per scope.
{: note}

## Creating templates in the UI
{: #create-templates-ui}
{: ui}

You can use the {{site.data.keyword.compliance_short}} UI to create the templates that you want to apply to your {{site.data.keyword.cloud_notm}} resources. To create templates by using the {{site.data.keyword.cloud_notm}} console:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Actions icon](../icons/actions-icon-vertical.svg) > **Security and Compliance**.
2. In the **Govern resources** section, click **Configure > Templates**.
3. Click **Create**.
4. Give your template a meaningful name and description.
5. Optional: Add one or more labels that you can use to organize and search for similar templates.
6. Click **Next**.
7. Select the service and resource kind that you want to target.
8. Use the JSON editor to set customized default properties for the template.
9. Click **Next**.
10. Review your selections. To make an update, click **Back** to return to the section that you want to edit.
11. Click **Finish and attach** to create your template and [attach it to a scope](#attach-template-ui).

    If you're not ready to attach your template, you can always save your template and attach it later. But, your template is not enforced until it is attached to a scope


## Creating templates with the API
{: #create-template-api}
{: api}

You can create templates programmatically by using the {{site.data.keyword.compliance_short}} API. For example, the following request sets your required default values for Cloud Object Storage buckets that are located in the `us-south` region. In the `customized_defaults` object, the `firewall.allowed_ip` property is set to a list of IP addresses to be applied.

```bash
curl -X POST "https://compliance.{DomainName}/config/v1/templates" \
  -H 'Authorization: Bearer <access_token>' \
  -H 'Content-type: application/json' \
  -H 'Transation-Id: <optional_transaction_ID>' \
  -d '{
    "templates": [
      {
        "request_id": "<optional_request_ID>",
        "template": {
          "account_id": "<account_ID>",
          "name": "example-cos-template",
          "description": "IP addresses authorized to access storage buckets.",
          "target": {
            "service_name": "cloud-object-storage",
            "resource_kind": "bucket",
            "additional_target_attributes": [
              {
                "name": "location",
                "value": "us-south"
              }
            ]
          },
          "customized_defaults": [
            {
              "property": "firewall.allowed_ip",
              "value": [
                  "10.168.175.0/24",
                  "10.168.243.79",
                  "2001:db8::/32",
                  "2000:db8:ffff:ffff:ffff:ffff:ffff:ffff"
              ]
            }
          ]
        }
      }
    ]
  }'
```
{: codeblock}

A successful `POST config/v1/templates` response returns the ID value for your template, along with other metadata. For more information about the required and optional request parameters, see [Create templates](/apidocs/security-compliance/config).


## Attaching a template to a scope in the UI
{: #attach-template-ui}
{: ui}

By creating an attachment between a template and a scope, you can apply your customized defaults in your selected accounts. If you have a specific account that you don't want the template to apply to, you can choose to exclude it. For example, if you apply a template to an entire enterprise you might want to exclude a scope that is used primarily for testing.

To create an attachment for a template by using the {{site.data.keyword.compliance_short}} UI:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Actions icon](../icons/actions-icon-vertical.svg) **> Security and Compliance**.
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

```bash
curl -X POST \
"https://compliance.{DomainName}/config/v1/templates/<template_ID>/attachments" \
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

A successful `POST config/v1/templates/{template_ID}/attachments` response returns the ID value for the attachment, along with other metadata. For more information about the required and optional request parameters, see [Create attachments](/apidocs/security-compliance/config#create-attachments).


## Updating templates in the UI
{: #update-templates-ui}
{: ui}

After you create a template, you can view it by navigating to the {{site.data.keyword.compliance_short}} UI. To view templates by using the {{site.data.keyword.compliance_short}} UI:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Actions icon](../icons/actions-icon-vertical.svg) **> Security and Compliance**.
2. In the **Govern resources** section, click **Configure > Templates**.
3. Use the **Templates** table to view the templates in your account.
4. Click the **Actions** icon ![Actions icon](../icons/actions-icon-vertical.svg) to open a list of options for the template that you want to delete.
5. Click **Edit** and follow the prompts to update your template.
6. Click **Edit and attach** to confirm your selections.

   From the **Attachments** tab, you can also view and edit [scope attachments](#attach-template-ui) for the template.



## Updating templates with the API
{: #update-templates-api}
{: api}

After you create a template, you can update it by using the API. The following request example updates an existing template. To run the request, be sure to replace the placeholder variables with values that are specific to your account and template.

To use this API, you need to supply an `Etag` value in an `If-Match` request header so that the server allows the operation to continue. To find the `Etag` value, run a GET request on the template that you want to update, and check the response headers. For more information, see the [API reference](/apidocs/security-compliance/config#list-templates).
{: tip}

```bash
curl -X PUT "https://compliance.{DomainName}/config/v1/templates/<template_ID>" \
  -H 'Authorization: Bearer <access_token>' \
  -H 'If-Match: <required_etag>' \
  -H 'Content-type: application/json' \
  -H 'Transation-Id: <optional_transaction_ID>' \
  -d '{
    "request_id": "<optional_request_ID>",
    "account_id": "<account_ID>",
    "name": "<updated_name>",
    "description": "<updated description>",
    "target": {
      "service_name": "<service_name>",
      "resource_kind": "<resource_type>",
      "additional_target_attributes": [
        {
          "name": "location",
          "value": "<region>"
        }
      ]
    },
    "customized_defaults": [
      {
        "property": "<property_name>",
        "operator": "string_equals",
        "value": "<value>"
      }
    ]
  }'
```
{: codeblock}

A successful `PUT config/v1/templates` response returns the IDs values for your available templates, along with other summary details. For more information about the required and optional request parameters, see [List templates](/apidocs/security-compliance/config#list-templates).



## Deleting templates in the UI
{: #delete-templates-ui}
{: ui}

If you no longer need to use a template, you can choose to delete it by using the {{site.data.keyword.compliance_short}} UI. To delete an existing template by using the {{site.data.keyword.compliance_short}} UI:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Actions icon](../icons/actions-icon-vertical.svg) **> Security and Compliance**.
2. In the **Govern resources** section, click **Configure > Templates**.
3. Use the **Templates** table to view the templates in your account.
4. Click the **Actions** icon ![Actions icon](../icons/actions-icon-vertical.svg) to open a list of options for the template that you want to delete.
5. From the options menu, click **Delete** and confirm the deletion in the next screen.



## Deleting templates with the API
{: #delete-templates-api}
{: api}

If you no longer need to use a template, you can choose to delete it by using the {{site.data.keyword.compliance_short}} APIs. The following example request deletes an existing template.

```bash
curl -X DELETE \
"https://compliance.{DomainName}/config/v1/templates/<template_ID> \
  -H 'Authorization: Bearer <access_token>'
  -H 'Content-type: application/json'
```
{: codeblock}

A successful `DELETE config/v1/templates/{template_ID}` response returns a `204 No Content` status code to indicate that your template was successfully deleted. For more information about the required and optional request parameters, see [Delete a template](/apidocs/security-compliance/config#delete-template).

