---

copyright:
  years: "2023"
lastupdated: "2023-09-19"

keywords: security compliance developer tools, integrate with application, API, SDK, CLI

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Integrating {{site.data.keyword.compliance_short}} with your resources
{: #integrate-with-resources}

Ready to integrate {{site.data.keyword.compliance_full}} with your existing apps or services? Try out the supported developer tools.
{: shortdesc}

## Supported developer tools
{: #dev-tool-list}

{{site.data.keyword.compliance_short}} offers APIs that you can use to connect to the service.


### {{site.data.keyword.compliance_short}} SDKs
{: #dev-tool-sdks}

{{site.data.keyword.compliance_short}} offers software development kits (SDKs) that you can use to connect with the service in various programming languages. For more information about getting started with {{site.data.keyword.compliance_short}} SDKs, check out the following repositories on GitHub:

- [Go SDK](https://github.com/IBM/scc-go-sdk){: external}
- [Java SDK](https://github.com/IBM/scc-java-sdk){: external}
- [Node.js SDK](https://github.com/IBM/scc-node-sdk){: external}
- [Python SDK](https://github.com/IBM/scc-python-sdk){: external}




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

