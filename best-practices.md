---

copyright:
  years: 2020, 2023
lastupdated: "2023-02-15"

keywords: scc best practices, enterprise, scc access

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

# Best practices for working with {{site.data.keyword.compliance_short}}
{: #best-practices}

As you start working with {{site.data.keyword.compliance_short}}, there are a few best practices that you can follow to have the best experience with the service.
{: shortdesc}


## Managing access
{: #bp-access}

There are several people in your organization who might require varying levels of access to the service or integrations. To ensure that you're following best practices, be sure that you create access groups and assign only the minimum required permissions to perform their duties. To manage compliance for an individual account, a compliance focal needs [access](/docs/security-compliance?topic=security-compliance-assign-roles) to the {{site.data.keyword.compliance_short}} service, {{site.data.keyword.en_short}}, and Cloud Object Storage through IAM. To manage compliance for an enterprise, additional permissions are required. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-assign-roles).



## Managing profiles
{: #bp-profiles}

In {{site.data.keyword.compliance_short}}, a [profile](/docs/security-compliance?topic=security-compliance-key-concepts) is the collection of controls that you use to evaluate your compliance. When you work with the service, you have the option to use a predefined profile or create a custom profile. There are pros and cons to both. 

### Working with predefined profiles
{: #bp-predefined}

Predefined profiles are versioned and periodically updated with bug fixes, more checks, or changes to the compliance program. [Learn more about versioning](/docs/security-compliance?topic=security-compliance-predefined-profiles#profile-update-levels). If you are monitoring compliance for a specific program, such as {{site.data.keyword.cloud_notm}} for Financial Services, it is recommended that you work with a predefined profile. This way you can take advantages of new versions of the profile as they become available. 

To avoid having to create and maintain a fully customized profile, you can customize a predefined profile by using parameters. Each parameter is assigned a default value that can be edited at the time of attachment. Each attachment can be assigned a different parameter value, which then changes the evaluation that is completed. However, when a new version of a profile is released, you need to ensure that your customizations are made for the new profile version.


### Custom profiles
{: #bp-custom} 

However, if you want total control over your profile - the number of assessments, versioning, or naming, you might want to create a custom profile. With custom profiles, you can mix and match controls from different libraries or only select the assessments that apply to your use case. Or, you can create your own controls.

Although it is possible to add both custom and predefined controls to a profile, it is recommended that you create a separate profile for any controls you want to add in addition to a predefined profile. By keeping predefined and custom controls separate, you are able to update to new versions of the predefined profiles more easily as you won't need to redo your customizations.



## Managing enterprises
{: #bp-enterprise}

When you work with {{site.data.keyword.compliance_short}} through an enterprise account, your experience is a bit different when it comes to your set-up options. As an enterprise, you have more scope options than a stand-alone account. You can choose to evaluate your entire enterprise, specific account groups, or individual accounts. It is recommended that if you want to evaluate a single account that you do so from that account.

If you are managing {{site.data.keyword.compliance_short}} from an enterprise, you must have additional permissions for the enterprise to manage and see results. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-assign-roles).
{: note}


### Defining scopes
{: #bp-enterprise-scope}

A scope defines which resources in your accounts are evaluated. It is defined when you create an attachment by selecting the parent account or resource group that you want to evaluate. Anything that exists within that account or group is evaluated. So, for example, if you create an attachment at the Enterprise level, then all of the account groups and accounts within them are included in your evaluation. If you don't want to evaluate a specific account, you can always exclude it from your scope when you create the attachment. When an account is excluded, any of its child accounts are also excluded. However, as new accounts are added to your Enterprise, they are automatically evaluated according to the parent accounts attachment.

Check out the following diagram to see how three attachments can coexist within an enterprise.

![The image shows how two attachments are applied across an enterprise. One rule moves down the hierarchy. Another rule is attached only to a specific account, so its properties are applied only to the resources that it contains.](images/access-model.svg){: caption="Figure 1. Attachment hierarchy" caption-side="bottom"}

Attachment A
:   In Attachment A, the target scope is the full enterprise. As you can see, all account groups and accounts that exist within the enterprise are evaluated. That is, unless they have been purposefully excluded. 

Attachment B
:   The target scope of Attachment B is a specific account group within an enterprise. As you can see, the resources in the account group are now being evaluated against the profile that is selected during Attachment A and are evaluated according to the profile selected when Attachment B was created.

Attachment C
:   The target scope of Attachment C is an individual account. This attachment was created in the account, outside of the context of the enterprise. As you can see, the account is now evaluated against the profile that was selected in attachment A, but the resource groups within the account are only evaluated against the profile that was selected when Attachment C was created.

To view the results of an evaluation, you look in the account where the attachment was created. If you were to use the previous image as an example, attachment A and B's results would exist within the Enterprise account, and the Enterprise account is charged for the evaluation. However, attachment C's results would exist within the individual account. 


