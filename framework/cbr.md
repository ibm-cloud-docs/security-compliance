<cbr>---

copyright:
  years: 2020, 2023
lastupdated: "2023-04-25"

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

Context-based restrictions protect only the actions associated with the [{{site.data.keyword.compliance_short}} API](apidocs/security-compliance/posture-v2.0). Actions that are associated with the following platform APIs are not protected by context-based restrictions. Reference the API docs for the specific action IDs.

- [Resource Instance APIs](/apidocs/resource-controller/resource-controller#list-resource-instances)
- [Resource Keys APIs](/apidocs/resource-controller/resource-controller#list-resource-keys)
- [Resource Bindings APIs](/apidocs/resource-controller/resource-controller#list-resource-bindings)
- [Resource Aliases APIs](/apidocs/resource-controller/resource-controller#list-resource-aliases)
- [IAM Policy APIs](/apidocs/iam-policy-management#list-policies)
- [Global Search APIs](/apidocs/search)
- Global Tagging [Attach](/apidocs/tagging#attach-tag) and [Detach](/apidocs/tagging#detach-tag) APIs
- [Context-based Restriction Rule APIs](/apidocs/context-based-restrictions#create-rule)
- [Secrets Manager APIs](/apidocs/secrets-manager)


## Creating network zones
{: network-zone}

A network zone represents an allowlist of IP addresses where an access request is created. It defines a set of one or more network locations that are specified by the following attributes:
- IP addresses, which include individual addresses, ranges, or subnets.
- VPCs
- Service references, which allow access from other {{site.data.keyword.cloud_notm}} services.

Make sure to add {{site.data.keyword.compliance_short}} to network zones for rules that target other {{site.data.keyword.cloud_notm}} resources, or some operations in your workflow might fail. 
{: important}

### Service references
{: service-references}

List the services that customers must add to network zones as a service reference. This way, they can include it in the rule that targets your service, and still allow the two services to communicate.

### Creating network zones in the console
{: #network-zone-ui} 
{: ui}

***Insert your examples here.***


### Creating network zones by using the API
{: #network-zone-api} 
{: api}

You can create network zones by using the `create-zone` command. For more information, see the [API docs](/apidocs/context-based-restrictions#create-zone). You can add {{site.data.keyword.compliance_short}} to network zones as a service reference to allow {{site.data.keyword.compliance_short}} to access resources and services in your account that are the subject of a rule.

The `serviceRef` attribute for {{site.data.keyword.compliance_short}} is `compliance`. 
{: tip}

***Insert your examples here.***

### Creating network zones by using the CLI
{: #network-zone-cli} 
{: cli}

You can use the `cbr-zone-create` command to add network locations, VPCs, and service references to network zones. For more information, see the CBR [CLI reference](docs/account?topic=account-cbr-plugin). Add {{site.data.keyword.compliance_short}} to network zones as a service reference to allow Security and Compliance Center to access resources and services in your account that are the subject of a rule.


To find a list of available service refs, run the `ibmcloud cbr service-ref-targets` [command](/docs/account?topic=account-cbr-plugin#cbr-cli-service-ref-targets-command). The `service_name` for SCC is `compliance`.
{: tip}

***Insert your examples here.***

## Creating rules
{: #create-rules}

Define restrictions to {{site.data.keyword.compliance_short}} resources by creating rules.

### Creating rules in the console
{: #rules-ui} 
{: ui}

Review the following examples to learn how to create rules for {{site.data.keyword.compliance_short}}.

***Insert your examples here. Include more complex use cases, like scoping a rule to protect specific APIs.***


### Creating rules by using the API
{: #rules-api} 
{: api}

Review the following examples to learn how to create rules for {{site.data.keyword.compliance_short}}. For more information, see the [API docs](/apidocs/context-based-restrictions#create-rule).

***Insert your examples here. Include more complex use cases, like scoping a rule to protect specific APIs.***

### Creating rules by using the CLI
{: #rules-cli} 
{: cli}

Review the following examples to learn how to create rules for {{site.data.keyword.compliance_short}}. For more information, see the CBR [CLI reference](/docs/account?topic=account-cbr-plugin#cbr-rules-cli).

***Insert your examples here. Include more complex use cases, like scoping a rule to protect specific APIs.***


</cbr>