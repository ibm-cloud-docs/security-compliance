---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: security compliance developer tools, integrate with application, API, SDK, CLI

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Integrating {{site.data.keyword.compliance_short}} with your resources
{: #integrate-with-resources}


As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.compliance_short}} {{site.data.keyword.sysdigsecure_short}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


Ready to integrate {{site.data.keyword.compliance_full}} with your existing apps or services? Try out the supported developer tools.
{: shortdesc}

## Supported developer tools
{: #dev-tool-list}

{{site.data.keyword.compliance_short}} offers APIs, SDKs, a CLI, and Terraform support that you can use to connect to the service.


### {{site.data.keyword.compliance_short}} SDKs
{: #dev-tool-sdks}

{{site.data.keyword.compliance_short}} offers software development kits (SDKs) that you can use to connect with the service in various programming languages. For more information about getting started with {{site.data.keyword.compliance_short}} SDKs, check out the following repositories on GitHub:

- [Go SDK](https://github.com/IBM/scc-go-sdk){: external}
- [Java SDK](https://github.com/IBM/scc-java-sdk){: external}
- [Node.js SDK](https://github.com/IBM/scc-node-sdk){: external}
- [Python SDK](https://github.com/IBM/scc-python-sdk){: external}




### {{site.data.keyword.compliance_short}} CLI plug-in
{: #dev-tool-cli}

Building an automated flow? If you're already using the [{{site.data.keyword.cloud_notm}} Command Line Interface (CLI)](/docs/cli?topic=cli-getting-started), you can install the {{site.data.keyword.compliance_short}} plug-in so that you can automate the evaluation of your resources.

To install {{site.data.keyword.compliance_short}} commands, run the following command: 

```sh
ibmcloud plugin install security-compliance
```
{: pre}

After you create your instance, for example, you can run the following CLI command to [create a custom library](/docs/security-compliance?topic=security-compliance-security-compliance-cli&interface=cli#security-compliance-cli-control-libraries-create-command):

```sh
ibmcloud security-compliance control-library create
--control-library-name='IBM Cloud for Financial Services'
--control-library-description='IBM Cloud for Financial Services'
--control-library-type=custom
--controls='[
  {
    "control_name": "SC-7",
    "control_id": "1fa45e17-9322-4e6c-bbd6-1c51db08e790",
    "control_description": "Boundary Protection",
    "control_category": "System and Communications Protection",
    "control_parent": "exampleString",
    "control_tags": [
      "1fa45e17-9322-4e6c-bbd6-1c51db08e790"
      ],
    "control_specifications": [
      {
        "control_specification_id": "5c7d6f88-a92f-4734-9b49-bd22b0900184",
        "responsibility": "user",
        "component_id": "iam-identity",
        "component_name": "exampleString",
        "environment": "ibm-cloud",
        "control_specification_description": "IBM cloud",
        "assessments_count": 38,
        "assessments": [
          {
            "assessment_id": "rule-238a6025-2522-4d36-831b-a32f81f97304",
            "assessment_method": "ibm-cloud-rule",
            "assessment_type": "automated",
            "assessment_description": "Check whether authorized IP ranges are configured for the account",
            "parameter_count": 38,
            "parameters": [
              {
                "parameter_name": "session_invalidation_in_seconds",
                "parameter_display_name": "Sign out due to inactivity in seconds",
                "parameter_type": "numeric",
                "parameter_value": "public"
                }
              ]
            }
          ]
        }
      ],
    "control_docs": {
      "control_docs_id": "sc-7",
      "control_docs_type": "ibm-cloud"
      },
    "control_requirement": true,
    "status": "enabled"
    }
  ]'
--version-group-label=33fc7b80-0fa5-4f16-bbba-1f293f660f0d
--control-library-version=1.0.0
--latest=true
--controls-count=38
--x-correlation-id=exampleString
--x-request-id=exampleString
```
{: pre}


For more information, check out the [{{site.data.keyword.compliance_short}} CLI reference](/docs/security-compliance?topic=security-compliance-security-compliance-cli).
{: note}



### {{site.data.keyword.compliance_short}} API
{: #dev-tool-api}

If you're trying out {{site.data.keyword.compliance_short}} for the first time, you might want to use the {{site.data.keyword.compliance_short}} API to automate the evaluation of your resources. 

Start by copying the service endpoint URL from the **Endpoints** page in your {{site.data.keyword.compliance_short}} service dashboard. Then, generate an [{{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) token](/docs/account?topic=account-iamtoken_from_apikey) to include in your request. For example, after you configure your service instance, you can use the following API request to retrieve all the control libraries.


```sh
curl -X GET 
  --location --header "Authorization: Bearer {iam_token}" 
  --header "Accept: application/json" 
  "{base_url}/control_libraries"

```
{: codeblock}

Replace `{base_url}` with your service endpoint URL (`https://us-south.compliance.cloud.ibm.com/instances/{instance_id}/v3/`), and `{iam_token}` with your IAM token. To run the API request, you can paste it into your command line, or preferred API testing tool. 

For more information about using {{site.data.keyword.compliance_short}} APIs, check out the [{{site.data.keyword.compliance_short}} API reference](/apidocs/security-compliance).
{: note}


### {{site.data.keyword.compliance_short}} Terraform
{: #dev-tool-terraform}

Already using Terraform? You can continue to use [Terraform with {{site.data.keyword.compliance_short}}](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/scc_rule){: external} to read data sources and create resources. 
