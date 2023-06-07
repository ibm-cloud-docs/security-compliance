---

copyright:
  years: 2020, 2023
lastupdated: "2023-06-07"

keywords: cbr in {{site.data.keyword.compliance_short}}, context-based restrictions for {{site.data.keyword.compliance_short}}, 

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Protecting {{site.data.keyword.compliance_short}} resources with context-based restrictions
{: #cbr}

Context-based restrictions give account owners and administrators the ability to define and enforce access restrictions for {{site.data.keyword.cloud_notm}} resources based on the context of access requests. Access to {{site.data.keyword.compliance_short}} resources can be controlled with context-based restrictions and identity and access management (IAM) policies. 
{: shortdesc}

These restrictions work with traditional IAM policies, which are based on identity, to provide an extra layer of protection. Unlike IAM policies, context-based restrictions don't assign access. Context-based restrictions check that an access request comes from an allowed context that you configure. Since both IAM access and context-based restrictions enforce access, context-based restrictions offer protection even in the face of compromised or mismanaged credentials. For more information, see [What are context-based restrictions](/docs/account?topic=account-context-restrictions-whatis).

A user must have the Administrator role on the {{site.data.keyword.compliance_short}} service to create, update, or delete rules. A user must also have either the Editor or Administrator role on the Context-based restrictions service to create, update, or delete network zones. A user with the Viewer role on the Context-based restrictions service can add only network zones to a rule. 
{: note}

Any {{site.data.keyword.cloudaccesstraillong_notm}} or audit log events generated come from the context-based restrictions service, not {{site.data.keyword.compliance_short}}. For more information, see [Monitoring context-based restrictions](/docs/account?topic=account-cbr-monitor).

To begin protecting your {{site.data.keyword.compliance_short}} resources with context-based restrictions, see the tutorial for [Leveraging context-based restrictions to secure your resources](/docs/account?topic=account-context-restrictions-tutorial).

## How {{site.data.keyword.compliance_short}} integrates with context-based restrictions
{: #cbr-overview}

Context-based restrictions that are set to {{site.data.keyword.compliance_short}} apply holistically to all components of {{site.data.keyword.compliance_short}}. By enabling context-based restrictions, you can restrict access to {{site.data.keyword.compliance_short}}’s user interface features and {{site.data.keyword.compliance_short}}’s public APIs.

To restrict access, you must create [zones](/docs/account?topic=account-context-restrictions-create&interface=ui#network-zones-create) and [rules](/docs/account?topic=account-context-restrictions-create&interface=ui#context-restrictions-create-rules). First, create a zone with the appropriate details for network or resource definitions. Then, create a rule, and attach that zone to the rule to restrict access. After you create or update a zone or a rule, it might take a few minutes for the change to take effect.

## Limitations
{: #cbr-limitations}

After you create a rule, it might take up to 10 minutes for the rule to take effect.

{{site.data.keyword.compliance_short}} does not support granular adoption of context-based restrictions to specific resources. When you're creating a new rule, you must ensure that the restrictions are scoped to “All resources,” instead of “Specific resources.”

{{site.data.keyword.compliance_short}} makes service-to-service calls to Cloud Object Storage. To ensure your {{site.data.keyword.compliance_short}} features are functioning correctly, you must add {{site.data.keyword.compliance_short}} as a service reference in network zones for rules that target Cloud Object Storage. You must use the same process for rules that target {{site.data.keyword.en_short}}.

Context-based restrictions are available only for the updated architecture. 
{: note}

Context-based restrictions protect only the actions associated with the [{{site.data.keyword.compliance_short}} API](/apidocs/security-compliance/posture-v2.0). Actions that are associated with the following platform APIs are not protected by context-based restrictions. Reference the API docs for the specific action IDs.

- [Resource Instance APIs](/apidocs/resource-controller/resource-controller#list-resource-instances)
- [Resource Keys APIs](/apidocs/resource-controller/resource-controller#list-resource-keys)
- [Resource Bindings APIs](/apidocs/resource-controller/resource-controller#list-resource-bindings)
- [Resource Aliases APIs](/apidocs/resource-controller/resource-controller#list-resource-aliases)
- [IAM Policy APIs](/apidocs/iam-policy-management#list-policies)
- [Global Search APIs](/apidocs/search)
- [Global Tagging Attach](/apidocs/tagging#attach-tag) and [Detach](/apidocs/tagging#detach-tag) APIs
- [Context-based Restriction Rule APIs](/apidocs/context-based-restrictions#create-rule)
- [Secrets Manager APIs](/apidocs/secrets-manager)


## Creating network zones
{: network-zone}

A network zone represents an allowlist of IP addresses where an access request is created. It defines a set of one or more network locations with the following attributes:
- IP addresses, which include individual addresses, ranges, or subnets.
- VPCs
- Service references, which allow access from other {{site.data.keyword.cloud_notm}} services.

Make sure to add {{site.data.keyword.compliance_short}} to network zones for rules that target other {{site.data.keyword.cloud_notm}} resources, or some operations in your workflow might fail. 
{: important}


### Creating network zones in the console
{: #network-zone-ui} 
{: ui}

To create network zones in the UI, complete the following steps. 

1. Determine the resources that you want add to your allowlist.
2. Follow the steps to [create network zones in the console](/docs/account?topic=account-context-restrictions-create). Add the {{site.data.keyword.compliance_short}} service to your network zones to allow {{site.data.keyword.compliance_short}} to access services and resources that are in your account.


### Creating network zones by using the API
{: #network-zone-api} 
{: api}

You can create network zones by using the `create-zone` command. For more information, see the [API docs](/apidocs/context-based-restrictions#create-zone). You can add {{site.data.keyword.compliance_short}} to network zones as a service reference to allow {{site.data.keyword.compliance_short}} to access resources and services in your account that are the subject of a rule.

The `serviceRef` attribute for {{site.data.keyword.compliance_short}} is `compliance`. 
{: tip}

Example payload to add {{site.data.keyword.compliance_short}} to a network zone.

```sh
{
  "name": "Example zone 1",
  "description": "",
  "addresses": [
    {
      "type": "serviceRef",
      "ref": {
        "service_name": "compliance",
        "account_id": "ACCOUNT-ID"
      }
  ]
}
```
{: codeblock}


Example payload to add multiple services, IP addresses, and VPCs to a network zone.

```sh
{
  {
  "name": "zone",
  "description": "",
  "addresses": [
    {
      "type": "ipAddress",
      "value": "192.168.0.0"
    },
    {
      "type": "vpc",
      "value": "crn:v1:bluemix:public:is:us-east:a/CRN"
    },
    {
      "type": "vpc",
      "value": "crn:v1:bluemix:public:is:us-south:a/CRN"
    },
    {
      "type": "serviceRef",
      "ref": {
        "service_name": "cloud-object-storage",
        "account_id": "ACCOUNT-ID"
    },
    {
      "type": "serviceRef",
      "ref": {
        "service_name": "codeengine",
        "account_id": "ACCOUNT-ID"
    },
    {
      "type": "serviceRef",
      "ref": {
        "service_name": "containers-kubernetes",
        "account_id": "ACCOUNT-ID"
    },
    {
      "type": "serviceRef",
      "ref": {
        "service_type": "platform_service",
        "account_id": "ACCOUNT-ID"
    },
    {
      "type": "serviceRef",
      "ref": {
        "service_name": "iam-groups",
        "account_id": "ACCOUNT-ID"
      }
    ],
    "excluded": []
  }
}
```
{: codeblock}

### Creating network zones by using the CLI
{: #network-zone-cli} 
{: cli}

You can use the `cbr-zone-create` command to add network locations, VPCs, and service references to network zones. For more information, see the CBR [CLI reference](/docs/account?topic=account-cbr-plugin). Add {{site.data.keyword.compliance_short}} to network zones as a service reference to allow Security and Compliance Center to access resources and services in your account that are the subject of a rule.

To find a list of available service refs, run the `ibmcloud cbr service-ref-targets` [command](/docs/account?topic=account-cbr-plugin#cbr-cli-service-ref-targets-command). The `service_name` for SCC is `compliance`.
{: tip}

Example command to add the `compliance` service to a network zone.

```sh
ibmcloud cbr zone-create --name example-zone-1 --description "Example zone 1" --service-ref service_name=compliance
```
{: pre}

Example command to add a single IP address to a network zone.

```sh
ibmcloud cbr zone-create --addresses 129.41.86.7 --description "Allow only client IP" --name allow-client-ip
```
{: pre}


## Creating rules
{: #create-rules}

Define rules to protect access to resources in your account. The contexts that you define in your rules determine how the resources in your network zones (allowlists) can interact with the resources that are defined in the rule.

Review the [limitations](/docs/security-compliance?topic=security-compliance-cbr&interface=ui#cbr-limitations) before you create rules.
{: note} 

### Creating rules in the console
{: #rules-ui} 
{: ui}

Complete the following steps to create rules for {{site.data.keyword.compliance_short}}.

1. Review the network zones that you created for your account.
2. Follow the steps to [create rules in the console](/docs/account?topic=account-context-restrictions-create&interface=ui#context-restrictions-create-rules).

### Creating rules by using the API
{: #rules-api} 
{: api}

Review the following example to learn how to create rules for {{site.data.keyword.compliance_short}} by using the API. For more information, see the [API docs](/apidocs/context-based-restrictions#create-rule).

This payload creates a rule that targets the {{site.data.keyword.compliance_short}} service and allows only private endpoints from the specified network zone to access the service.

```sh
{
  "description": "Example rule 1",
  "resources": [
    {
      "attributes": [
        {
          "name": "accountId",
          "value": "ACCOUNT-ID"
        },
        {
          "name": "serviceName",
          "value": "compliance"
        }
      ]
    }
  ],
  "contexts": [
    {
      "attributes": [
        {
          "name": "networkZoneId",
          "value": "NETWORK-ZONE-ID"
        },
        {
          "name": "endpointType",
          "value": "private"
        }
      ]
    }
  ]
}
```
{: codeblock}


### Creating rules by using the CLI
{: #rules-cli} 
{: cli}

Review the following example to learn how to create rules for {{site.data.keyword.compliance_short}} by using the CLI. For more information, see the CBR [CLI reference](/docs/account?topic=account-cbr-plugin#cbr-rules-cli).

This command creates a rule that targets the {{site.data.keyword.compliance_short}} service and allows only private endpoints from the specified network zone to access the service.

```sh
ibmcloud cbr rule-create --description 'Example Rule Description' --service-name compliance --context-attributes endpointType=private --zone-id ZONE_ID --enforcement-mode report
```
{: pre}

For the enforcement-mode option, the CLI accepts the values `enabled`, `disabled`, and `report`. If no enforcement is specified, the rule is enabled by default. 
{: tip}


## Next steps
{: #cbr-next-steps}

Follow the creation or modification of zones or rules with adequate testing to ensure access and availability.

Users who attempt to access your resources outside of the defined zones receive `HTTP error 403` when the appropriate rules are not established.
{: note}
