<staging>---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-15"

keywords: documenting security and compliance, onboard security and compliance, onboard fortress, onboard, scc, integrated services, fortress, scc, enable controls, enable scc, enable fortress

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

# Documenting {{site.data.keyword.compliance_short}} for your service's end users
{: #doc-scc}


{{site.data.keyword.compliance_full}} is a service that allows users to monitor and enforce security and compliance across their accounts and resources. The {{site.data.keyword.compliance_short}} topic enables users to find the goals and rule properties that your service has enabled in {{site.data.keyword.cloud_notm}}.

As part of onboarding to the {{site.data.keyword.compliance_short}}, your service must complete several steps. As the writer for a service team, you are asked to:

1. Review the goal spreadsheet that is provided to the {{site.data.keyword.compliance_short}} team.
2. Review the rule property descriptions that are provided to the {{site.data.keyword.compliance_short}} team.
3. Update your docs with the {{site.data.keyword.compliance_short}} template.



## Reviewing goals
{: #scc-review-goals}

When your service integrates with the {{site.data.keyword.compliance_short}}, they create a spreadsheet that lists the goals that your service provides. In your review, confirm that:

* All acronyms that are used are approved through legal.
* The goals don't have any typographical errors.
* Capitalization and punctuation are correct. There are no periods at the end of a goal.

### Sample goals
{: #sample-goals}

Review the following sample goals to get a feel for what they should look like before you edit the goals for your service.

* _Check whether Cloud Object Storage is accessible only using private endpoints_
* _Check whether Cloud Object Storage is enabled with customer-managed encryption and Bring Your Own Key (BYOK)_
* _Check whether Cloud Object Storage buckets are enabled with IBM Activity Tracker_



## Reviewing rule descriptions
{: #scc-review-rules}

Each rule, as displayed in the UI, has a description that you should review before it displays in the {{site.data.keyword.compliance_short}} UI.

For example, if you select Certificate Manager as your target service and instance as the type of resource, you are shown the following JSON object.

```json
{
  resource_kind: 'instance',
  additional_target_attributes: [],
  properties: [
    {
      name: 'private_network_only',
      description: 'A boolean that indicates whether access to an instance is enabled only through a private network.'
    }
  ],
  description: 'Certificate Manager Service instance'
}
```
{: screen}

You are editing both the property description and description of the resource. When you edit the file, pay close attention to the same areas you focused on for Goals.

* Be sure that all acronyms that are used are approved through legal.
* Be sure that there are no typographical errors.
* Be sure that capitalization and punctuation are correct. There are periods at the end of a property description.



## Documenting security and compliance for your service
{: #scc-end-user}

**If you have already named a topic in your docs titled *Security and Compliance*, please rename that topic.**

### Template
{: #scc-template}

To get started, review the [Managing security and compliance for *service_name* template](https://github.ibm.com/cloud-docs-internal/writing/blob/draft/content-kit/manage-scc-template.md) and copy it to a new file in your service's documentation folder. Be sure to place the topic in the **Enhancing security** topic group in the **How to** nav group.


### Example topics
{: #template-examples}

* [Certificate Manager](/docs/certificate-manager?topic=certificate-manager-manage-security-compliance)
* [App ID](/docs/appid?topic=appid-manage-security-compliance)
* [Container Registry](/docs/Registry?topic=Registry-manage-security-compliance)
* [Key Protect](/docs/key-protect?topic=key-protect-manage-security-compliance)

</staging>
