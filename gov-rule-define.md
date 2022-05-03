---

copyright:
  years: 2020, 2022
lastupdated: "2022-05-03"

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

When you create a rule for a service, you give the {{site.data.keyword.compliance_short}} permission to access the configuration details for services instances that are provisioned in your account.
{: note}

## Creating rules in the UI
{: #create-rules-ui}
{: ui}

You can use the {{site.data.keyword.compliance_short}} UI to define the rules that you want to enforce or monitor for your {{site.data.keyword.cloud_notm}} resources. To create rules by using the {{site.data.keyword.cloud_notm}} console, you can either use the rule builder or edit the JSON directly. For more information about the make-up of a rule, see [Formatting rules and templates](/docs/security-compliance?topic=security-compliance-formatting-rules-templates).


1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Configure > rules**, and click **Create**.
2. Give your rule a meaningful name and description.
3. Optional: Add one or more labels that you can use to organize and search for similar rules and click **Next**.
4. Target your resource.
   1. From the **Target service** drop-down, select a service. For example, *Cloud Object Storage*.
   2. From the **Resource kind** drop-down, select the type of resource that you want to create a rule for. For example, *bucket*.
   3. Optional: Add additional target attributes to further qualify the resources that you want to target.

      For example, to target all of your Cloud Object Storage buckets in the US South location, you would make the following selections: **Attribute**: `Location`, **Value**: `string_equals`, and enter `us_south` for **Value**.
   4. Click **Add to rule**.
5. Configure your properties. To add additional properties to your rule, repeat this step. You can select up to 5 different conditions and 16 properties to create your rule.

   To see all of the properties that are available for the service that you selected, you can click **Available Properties** in the **Definition** step. To see the available properties for all integrated services, see [Available properties](/docs/security-compliance?topic=security-compliance-available-rule-properties).
   {: tip}

   1. Select a **Condition**.

      * **And**: When you select *And* as your condition, all of the property configurations that you add to your rule must evaluate to true in order for the rule to be compliant.
      * **Or**: When you select *Or* as your condition, only part of your rule must evaluate to true for it to be compliant.
   2. From the **Property** drop-down, select the property that you want to set a configuration for.
   3. From the **Operator** drop-down, select an operator.
   4. Input the **Value** that you want the rule to enforce or monitor.
   5. Click **Add to rule**.

6. If you want to enforce your rule, toggle **Enforcement** to **On**. If you only want to monitor the rule, toggle **Enforcement** to **Off**.
7. Click **Next**.
8. Review your selections and click **Create**.

After you create a rule, you can view it by navigating to the {{site.data.keyword.compliance_short}} UI and selecting the rule that you want to view in the **Configuration rules** table. To see which scope attachments are associated with a rule, click **Attachments** in the navigation.

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


