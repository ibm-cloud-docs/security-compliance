---

copyright:
  years: 2021
lastupdated: "2021-07-12"

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


# Working with config rules
{: #rules}

You can use the {{site.data.keyword.compliance_full}} to create and manage config rules by using the console or the APIs.
{: shortdesc}

After you create a rule, you can monitor for configuration changes by attaching the rule to a scope, such as an account group, specific accounts, or an entire enterprise. You can further investigate noncompliant resources by reviewing your evaluation results in the {{site.data.keyword.compliance_short}} UI.

To learn more about the different components of a rule, see [What is a rule?](/docs/security-compliance?topic=security-compliance-what-is-rule).

## Before you begin
{: #before-rules}

Before you get started, be sure that you have the following prerequisites.

- An {{site.data.keyword.cloud_notm}} account.
- The required level of access to view and manage rules. To create a rule, you need the editor platform role or higher. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).
- An instance of {{site.data.keyword.at_short}} in the regions in which you provision resources.


## Creating rules in the UI
{: #create-rules-ui}
{: ui}

You can use the {{site.data.keyword.compliance_short}} UI to define the rules that you want to enforce or monitor for your {{site.data.keyword.cloud_notm}} resources. To create rules by using the {{site.data.keyword.cloud_notm}} console:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) > **Security and Compliance**.
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

  <table>
    <tr>
      <th>Parameter</th>
      <th>Description</th>
    </tr>
    <tr>
      <td><code>service_name</code></td>
      <td>The service that you want to target with your rule. You select this field from a drop-down and it is automatically populated in your definition.</td>
    </tr>
    <tr>
      <td><code>resource_kind</code></td>
      <td>A specific part of the service that you want to target.</td>
    </tr>
    <tr>
      <td><code>additional_target_attributes</code></td>
      <td>An extra qualifier for the type of resource that you selected.</td>
    </tr>
    <tr>
      <td><code>operator</code></td>
      <td><p>The way in which an additional target attribute or property is evaluated against the specified value. For a full list of operators, see [Supported operators](/docs/security-compliance?topic=security-compliance-what-is-rule#rule-operators).</p>
      </td>
    </tr>
    <tr>
      <td><code>value</code></td>
      <td><p>The way in which you want to apply your attribute or property. Value options differ depending on the rule that you configure. If you use a boolean operator, you do not need to include a value.</td>
    </tr>
    <tr>
      <td><code>required_config</code></td>
      <td><p>The requirements that must be met to determine the your resources level of compliance in accordance with the rule.</p><p>You can use logical operators (<code>and</code>/<code>or</code>) to define multiple property checks and conditions. To define requirements for a rule, list one or more property check objects in the <code>and</code> array. To add conditions to a property check, use <code>or</code>. For more information about defining a rule with multiple conditions, see [How do properties work?](/docs/security-compliance?topic=security-compliance-what-is-rule#rule-properties)</p>
      </td>
    </tr>
    <tr>
      <td><code>property</code></td>
      <td>The individual resource configuration variable that follows the syntax <code>property_name</code>. Options are dependent upon the target that you choose and can be found in the UI.</td>
    </tr>
  </table>
10. Click **Next**. 
10. Select the enforcement actions that you want to apply and click **Next**.

  Enforcement actions define how the {{site.data.keyword.compliance_short}} reacts when a resource is created or modified and the requested configuration is not compliant with your rule. The following table describes the supported actions.

  <table>
    <caption>Table 2. Enforcement actions and descriptions</caption>
    <tr>
      <th>Action</th>
      <th>Description</th>
    </tr>
    <tr>
      <td>Disallow</td>
      <td>Blocks the requested action from completing.</td>
    </tr>
    <tr>
      <td>Audit log</td>
      <td>Allows the requested action to complete, but logs an event that indicates noncompliance in {{site.data.keyword.at_short}}. Note: An action is logged in {{site.data.keyword.at_short}} automatically.</td>
    </tr>
  </table>

11. Review your selections. To make an update, click **Back** to return to the section that you want to edit.
12. Click **Finish and attach** to create your rule and [attach it to a scope](#evaluate-rules-ui).

    If you're not ready to attach your rule, you can always save your rule and attach it later. But, your rule is not enforced until it is attached to a scope

## Creating a rule with the API
{: #create-rule-api}
{: api}

You can create rules programmatically by using the {{site.data.keyword.compliance_short}} API. For example, if you wanted to create a rule prohibited access to a specific bucket unless the request came from a private endpoint, your request might look similar to the following code snippet.

```bash
curl -x POST "https://compliance.{DomainName}/config/v1/rules" \
  -H 'Authorization: Bearer <access_token>' \
  -H 'Content-type: application/json' \
  -H 'Transation-Id: a7f48341-a2b0-4649-a95d-d416d5fb4170' \
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
          },
          {
            "action" "audit_log"
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

A successful `POST config/v1/rules` response returns the ID value for your rule, along with other metadata. For more information about the required and optional request parameters, see [Create rules](/apidocs/security-compliance/config#post-rule-attachments).




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

```bash
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


## Viewing rules with the UI
{: #view-rules-ui}
{: ui}

After you create a rule, you can view it by navigating to the {{site.data.keyword.compliance_short}} UI. To view rules by using the {{site.data.keyword.compliance_short}} UI:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance**.
2. In the navigation, click **Configure rules**.

   From the **Configuration rules** table, you can see a list of your available rules and the {{site.data.keyword.cloud_notm}} service that is associated with each rule. You can also view the enforcement actions that are associated with each rule in cases of noncompliance.
3. From the list of rules, click the name of the rule that you want to view.

   You can view the parameters that are associated with the rule. To view or edit the [scope attachments](#evaluate-rules-ui) for the rule, click **Attachments** in the navigation.

## Viewing rules with the API
{: #view-rules-api}
{: api}

After you create a rule, you can view it by using the API. The following request example lists the rules that are available in your account.

```bash
curl -X POST \
"https://compliance.{DomainName}/config/v1/rules?account_id=<account_ID>" \
  -H 'Authorization: Bearer <access_token>' \
  -H 'Content-type: application/json'
```
{: codeblock}

A successful `GET config/v1/rules` response returns the IDs values for your available rules, along with other summary details. For more information about the required and optional request parameters, see [List rules](/apidocs/security-compliance/config#list-rules).



## Deleting rules with the UI
{: #delete-rules-ui}
{: ui}

If you no longer need to use a rule, you can choose to delete it by using the {{site.data.keyword.compliance_short}} UI. To delete an existing rule by using the {{site.data.keyword.compliance_short}} UI:

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance**.
2. In the navigation, click **Configure rules**.
3. Use the **Configuration rules** table to browse the rules in your account.
4. Click the **Actions** icon ![Menu icon](../icons/icon_hamburger.svg) to open a list of options for the rule that you want to delete.
5. From the options menu, click **Delete** and confirm the deletion in the next screen.

## Deleting rules with the API
{: #delete-rules-api}
{: api}

If you no longer need to use a rule, you can choose to delete it by using the {{site.data.keyword.compliance_short}} APIs. The following example request deletes an existing rule.

```bash
curl -X DELETE \
"https://compliance.{DomainName}/config/v1/rules/<rule_ID> \
  -H 'Authorization: Bearer <access_token>'
  -H 'Content-type: application/json'
```
{: codeblock}

A successful `DELETE config/v1/rules/{rule_ID}` response returns a `204 No Content` status code to indicate that your rule was successfully deleted. For more information about the required and optional request parameters, see [Delete a rule](/apidocs/security-compliance/config#delete-rule).
