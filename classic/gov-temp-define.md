---

copyright:
  years: 2020, 2022
lastupdated: "2022-10-17"

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


# Defining templates
{: #templates-define}

You can use the {{site.data.keyword.compliance_full}} to create and manage templates by using the console or the APIs.
{: shortdesc}

A new and improved experience for {{site.data.keyword.compliance_short}} is coming soon! As part of the updates, the Configuration Governance component of the service will be temporarily removed in November 2022. Currently there is not a timeline for its return, but we'll keep you updated.
{: note}

Templates help you define your preferred property values for supported resources in your accounts. After you create a template and attach it to a scope, your defined values override the defaults that are provided by IBM. Later, when an account user creates a resource that is targeted by the template, your customized defaults are applied.

Templates are required only with some {{site.data.keyword.cloud_notm}} services and resource properties. To see a list of services that require templates, see [Available properties](/docs/security-compliance?topic=security-compliance-available-rule-properties)
{: note}


## Before you begin
{: #before-templates}

Before you get started, be sure that you have the required level of access to view and manage templates. To create a template, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).

Each property can be added to only one template per scope to avoid any conflicts or duplicated definitions.
{: note}


## Creating templates in the UI
{: #create-templates-ui}
{: ui}

You can use the {{site.data.keyword.compliance_short}} UI to create the templates that you want to apply to your {{site.data.keyword.cloud_notm}} resources. To create templates by using the {{site.data.keyword.cloud_notm}} console:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../../icons/icon_hamburger.svg) **> Security and Compliance**.
2. In the **Govern resources** section, click **Configure > Templates**.
3. Click **Create**.
4. Give your template a meaningful name and description.
5. Optional: Add one or more labels that you can use to organize and search for similar templates.
6. Click **Next**.
7. Select the service and resource kind that you want to target.
8. Use the JSON editor to set customized default properties for the template.
9. Click **Next**.
10. Review your selections. To make an update, click **Back** to return to the section that you want to edit.
11. Click **Finish and attach** to create your template and [attach it to a scope](/docs/security-compliance?topic=security-compliance-templates-apply).

After you create a template, you can view it by navigating to the {{site.data.keyword.compliance_short}} UI and selecting the rule that you want to view in the **Templates** table. To see which scope attachments are associated with a rule, click **Attachments** in the navigation.


## Creating templates with the API
{: #create-template-api}
{: api}

You can create templates programmatically by using the {{site.data.keyword.compliance_short}} API. For example, the following request sets your required default values for Cloud Object Storage buckets that are located in the `us-south` region. In the `customized_defaults` object, the `firewall.allowed_ip` property is set to a list of IP addresses to be applied.

```sh
curl -X POST "https://compliance.<domainName>/config/v1/templates" \
  -H 'Authorization: Bearer <accessToken>' \
  -H 'Content-type: application/json' \
  -H 'Transation-Id: <optionalTransactionID>' \
  -d '{
    "templates": [
      {
        "request_id": "<optionalRequestID>",
        "template": {
          "account_id": "<accountID>",
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

A successful `POST config/v1/templates` response returns the ID value for your template, along with other metadata. For more information about the required and optional request parameters, see [Create templates](/apidocs/security-compliance-config).

