---

copyright:
  years: 2021
lastupdated: "2021-03-15"

keywords: template, customized defaults, default property values, resource configuration

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

# What is a template?
{: #what-is-template}

A resource template is a JSON document that defines default property values for a target resource. With the {{site.data.keyword.compliance_full}}, you can create and manage templates to set your required default values for integrated {{site.data.keyword.cloud_notm}} services and resources.
{: shortdesc}

Templates are compatible with select {{site.data.keyword.cloud_notm}} services and resource properties. Be sure to review the [list of integrated services](#template-integrated-services) that you can use to apply customized defaults.
{: note}


## Customizing default values for your resources
{: #customize-default-values}

With templates, you can define your preferred values, or customized defaults, on properties that are used to configure an {{site.data.keyword.cloud_notm}} resource. By creating templates that users in your accounts can regularly review and reference, you set guidelines for teams to follow. After you attach a template to a [scope](#x2037763){:term}, your customized defaults are applied by target services to ensure that your selections override the IBM-defined values each time that a target resource is created.

You can use templates to override IBM-defined property values only. Configurations that are selected by users at resource creation aren't replaced by the values that you define as part of a template.
{: note}

Check out the following diagram to see an example template sequence:

![The image shows an example template sequence.](images/template-sequence.svg){: caption="Figure 1. Template sequence flow" caption-side="bottom"}

1. As a security focal, you create a template for a target resource and attach it to a scope.
2. A developer makes a request to create a resource that is owned by the target service.
3. The target service checks for an existing template in the {{site.data.keyword.compliance_short}}.
4. The target service uses the template data to apply your customized default values on the new resource.



### Use case: Setting defaults for a Cloud Object Storage bucket
{: #template-use-case}

Let's say that your team is looking for a way to ensure that Cloud Object Storage buckets are always configured with the default values that are required by your organization. To meet a guideline, buckets that are created in the Dallas region must always be accessible only through a list of trusted networks.

You decide to create the following template:

```json
{
  "template": {
    "account_id": "b5sky5809vcatdp94d8la97e236k233e",
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
            "10.168.243.79"
        ]
      }
    ]
  }
}
```
{: screen}

In your template, you use the [`firewall.allowed_ip`](/docs/cloud-object-storage?topic=cloud-object-storage-manage-security-compliance#govern-cloud-object-storage) property to define the list of default IP addresses that your organization requires.

Later, a user creates a bucket in the location that is targeted by your template. But, the user forgets to configure the bucket with the required firewall settings. To validate the request, the Cloud Object Storage service checks for an existing template in {{site.data.keyword.compliance_short}}. Instead of applying the system defaults to the bucket's configuration, Cloud Object Storage applies the list of trusted IPs that you defined as part of your template.


## List of integrated services
{: #template-integrated-services}

You can use templates to set defaults values only for select {{site.data.keyword.cloud_notm}} services and resource properties. Review the following list of integrated services to understand whether this feature is compatible with a specific service.

The default values that can be customized with templates vary depending on each integrated service. To understand whether you can customize default values for a specific property, refer to the service documentation.
{: note}

- [Cloud Object Storage](/docs/cloud-object-storage?topic=cloud-object-storage-manage-security-compliance#govern-cloud-object-storage)


## How do I get started?
{: #template-get-started}

To get started with templates, you can go to the **Menu icon** ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance > Configure > Templates**, or check out the [API reference](/apidocs/security-compliance/config) to learn more about creating templates programmatically.

For more information, see [Managing templates](/docs/security-compliance?topic=security-compliance-templates).
