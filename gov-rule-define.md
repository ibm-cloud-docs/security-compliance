---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-15"

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


# Defining rules
{: #rules-define}

You can use the {{site.data.keyword.compliance_full}} to create config rules by using the console or the APIs.
{: shortdesc}

After you create a rule, you can monitor for configuration changes by [attaching the rule to a scope](/docs/security-compliance?topic=security-compliance-rules-apply), such as an account group, specific accounts, or an entire enterprise. You can further investigate noncompliant resources by reviewing your evaluation results in the {{site.data.keyword.compliance_short}} UI.

To learn more about the different components of a rule, see [Formatting rules and templates](/docs/security-compliance?topic=security-compliance-formatting-rules-templates).

## Before you begin 
{: #before-rules}

Before you get started, be sure that you have the required level of access to view and manage rules. To create a template, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management). You must also have an instance of {{site.data.keyword.at_short}} that exists in the same region in which you provision your resources.

<prod>

## Creating rules in the UI
{: #create-rules-ui}
{: ui}

You can use the {{site.data.keyword.compliance_short}} UI to define the rules that you want to enforce or monitor for your {{site.data.keyword.cloud_notm}} resources. To create rules by using the {{site.data.keyword.cloud_notm}} console, use the following steps as a guide.

When you create a rule for a service, you give the {{site.data.keyword.compliance_short}} permission to access the configuration details for services instances that are provisioned in your account.
{: note}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance**.
2. In the navigation, click **Configure rules**.
3. Click **Create**.
4. Give your rule a meaningful name and description.
5. Optional: Add one or more labels that you can use to organize and search for similar rules.
6. Click **Next**.
7. Select the service and resource kind that you want to target.
8. Use the JSON editor to set configuration properties for the rule.

   For example, if you wanted to create a rule that prohibited access to a specific bucket unless the request came from a private endpoint, it might look similar to the following code snippet.

   ```json
   {
      "target": {
         "service_name": "cloud-object-storage",
         "resource_kind": "bucket",
         "additional_target_attributes": [
         {
            "name": "resource_id",
            "operator": "string_equals",
            "value": "My_bucket"
         }
         ]
      },
      "required_config": {
         "description": "Check whether my bucket is accessible by using only private endpoints.",
         "and": [
         {
            "property": "firewall.allowed_network_type",
            "operator": "strings_in_list",
            "value": [
               "private"
            ]
         }
         ]
      }
   }
   ```
   {: screen}

   | Parameter | Description |
   | --------- | ----------- |
   | `service_name` | The service that you want to target with your rule. You select this field from a drop-down and it is automatically populated in your definition. |
   | `resource_kind` | A specific part of the service that you want to target. |
   | `additional_target_attributes` | An extra qualifier for the type of resource that you selected. |
   | `operator` | The way in which an additional target attribute or property is evaluated against the specified value. For a full list of operators, see [Supported operators](/docs/security-compliance?topic=security-compliance-formatting-rules-templates#operators). |
   | `value` | The way in which you want to apply your attribute or property. Value options differ depending on the rule that you configure. If you use a boolean operator, you do not need to include a value. |
   | `required_config` | The requirements that must be met to determine the your resources level of compliance in accordance with the rule. You can use logical operators (`and`/`or`) to define multiple property checks and conditions. To define requirements for a rule, list one or more property check objects in the `and` array. To add conditions to a property check, use `or`. For more information about defining a rule with multiple conditions, see [Available properties](/docs/security-compliance?topic=security-compliance-available-rule-properties). |
   | `property` | The individual resource configuration variable that follows the syntax `property_name`. Options are dependent upon the target that you choose and can be found in the UI. |
   {: caption="Table 1. Rule parameters" caption-side="top"}

9. If the rule is enforceable and you want to ensure it can't be broken, toggle enforcement to **On**.
10. Click **Next**.
11. Review your selections. To make an update, click **Back** to return to the section that you want to edit.
12. Click **Finish and attach** to create your rule and [attach it to a scope](/docs/security-compliance?topic=security-compliance-rules-apply). If you're not ready to attach your rule, you can always save your rule and attach it later. But, your rule is not enforced until it is attached to a scope.

When you create a rule, it can take up to 10 minutes to be in effect.
{: note}


After you create a rule, you can view it by navigating to the {{site.data.keyword.compliance_short}} UI and selecting the rule that you want to view in the **Configuration rules** table. To see which scope attachments are associated with a rule, click **Attachments** in the navigation.

</prod>

<staging>



## Creating rules in the UI
{: #create-rules-ui}
{: ui}

You can use the {{site.data.keyword.compliance_short}} UI to define the rules that you want to enforce or monitor for your {{site.data.keyword.cloud_notm}} resources. 

When you create a rule for a service, you give the {{site.data.keyword.compliance_short}} permission to access the configuration details for services instances that are provisioned in your account.
{: note}

### Providing rule details
{: #create-rule-details}


1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Configure > rules**.
2. Click **Create**.
3. Give your rule a meaningful name and description.
4. Optional: Add one or more labels that you can use to organize and search for similar rules.
5. Click **Next**.

### Defining your rule
{: #create-rule-define}

To create rules by using the {{site.data.keyword.cloud_notm}} console, you can either use the rule builder or edit the JSON directly.

To take advantage of the JSON editor, you can switch to the **Documentation** tab in the **Build your rule** section to learn about possible inputs and formatting requirements. Then, you can start editing the JSON directly. If you need more help with formatting, you can work with the **Rule builder**.

1. Target your rule by selecting a service and resource kind.
2. Optional: If the option is available for your selected resource, you can add **Additional attributes** that help to further target a specific resource. You can repeat this process as many times as neccessary.
   1. Select an available property and operator.
   2. Input the value that you want to target.
   3. Click **Add to rule**.
3. Select your **Condition**.




8. Use the JSON editor to set configuration properties for the rule.

   For example, if y

</staging>

## Creating a rule with the API
{: #create-rule-api}
{: api}

You can create rules programmatically by using the {{site.data.keyword.compliance_short}} API. For example, if you wanted to create a rule prohibited access to a specific bucket unless the request came from a private endpoint, your request might look similar to the following code snippet.

```sh
curl -x POST "https://compliance.{DomainName}/config/v1/rules" \
  -H 'Authorization: Bearer <access_token>' \
  -H 'Content-type: application/json' \
  -H 'Transaction-Id: a7f48341-a2b0-4649-a95d-d416d5fb4170' \
  -d '{
    "rules": [
      {
        "request_id": "80e8c8ce-06ea-44dd-8a45-3e33293ddd78",
        "rule": {
          "account_id": "<account_id>",
          "name": "Limit access to private network traffic only",
          "description": "For My bucket, limit access to only private network traffic.",
          "target": {
            "service_name": "cloud-object-storage",
            "resource_kind": "bucket",
            "additional_target_attributes": [
              {
                "name": "resource_id",
                "operator": "string_equals",
                "value": "My_bucket"
              }
            ],
            "required_config": {
            "description": "Limit access to private network traffic"
            "and": [
              {
                property: "firewall.allowed_network_type",
                operator: "strings_in_list",
                value: [
                  "private"
                ]
              }
            ],
            "enforcement_actions": [
              {
                "action": "disallow"
              }
            ],
            "labels": [
              "storage"
            ]
          }
        }
      }
    }
  ]
}'
```
{: codeblock}

A successful `POST config/v1/rules` response returns the ID value for your rule, along with other metadata. For more information about the required and optional request parameters, see [Create rules](/apidocs/security-compliance-config#post-rule-attachments).


After you create a rule, you can view it by using the API. For more information about the required and optional request parameters, see [List rules](/apidocs/security-compliance-config#list-rules).


## Next steps
{: #rule-next}

Now that you've defined a rule, be sure that you [attach it to a scope](/docs/security-compliance?topic=security-compliance-rules-apply) in order to apply it.

