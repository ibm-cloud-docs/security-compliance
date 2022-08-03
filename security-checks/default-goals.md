\---

copyright:
  years: 2020, 2022
lastupdated: "2022-08-03"

keywords: goals, secure by default, secure, secure platform, default goals, available goals

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

# Available default goals
{: #default-goals}

{{site.data.keyword.cloud_notm}} is secure-by-design. Just by working with {{site.data.keyword.cloud_notm}} platform, you are compliant with several goals. Because they are always compliant, default goals are not validated as part of a scan. To learn more about goals in general and how they are used in the {{site.data.keyword.compliance_short}}, see [Understanding profiles](/docs/security-compliance?topic=security-compliance-profiles#understand-profiles). 
{: shortdesc}

To see which goals are met by default, check out the following table.

| Goal ID | Goal |
|:--------|:-----|
| `3000053` | IBMid enforces a limit of 5 consecutive unsuccessful sign in attempts | 
| `3000054` | IBMid automatically locks an account for 30 minutes after 5 consecutive unsuccessful sign in attempts |
| `3000055` | IBM Cloud console conceals information previously visible on the display when the user has been signed out due to inactivity |
| `3000056` | IBM Cloud retains the session lock until access is reestablished by signing in |
| `3000057` | IBM Cloud provides the means to associate a customer-defined security identifier and attributes with IBM Cloud resources (for example, tags) |
| `3000058` | IBM Cloud provides the ability to immediately terminate a user session for an account |
| `3000059` | IBM Cloud accounts are one of the account types used to support your applications |
| `3000060` | IBMid uniquely identifies and authenticates organizational users or processes that act on behalf of organizational users |
| `3000061` | IBM Cloud IAM uniquely identifies and authenticates organizational users or processes that act on behalf of organizational users |
| `3000062` | IBMid selects and assigns identifiers that identify individuals |
| `3000063` | IBM Cloud assigns identifiers that identify individuals, groups, roles, and devices |
| `3000064` | IBM Cloud prevents reuse of identifiers |
| `3000065` | IBMid ensures that passwords have sufficient strength for their intended use |
| `3000066` | IBM Cloud IAM ensures that authenticators, such as API keys, have sufficient strength for their intended use |
| `3000067` | IBMid establishes minimum and maximum lifetime restrictions and reuse conditions for authenticators |
| `3000068` | IBM Cloud IAM establishes minimum and maximum lifetime restrictions and reuse conditions for authenticators, such as API keys |
| `3000069` | IBMid does not allow changed or reset passwords to be the same as any of the 24 previously used passwords |
| `3000070` | IBMid stores and transmits only encrypted representations of passwords |
| `3000071` | IBMid enforces password expiry after 90 days |
| `3000073` | IBMid employs automated tools to determine if password authenticators satisfy IBMid password requirements |
| `3000074` | IBMid protects user information during the authentication process from possible exploitation by unauthorized individuals by obscuring it  |
| `3000075` | IBM Cloud IAM establishes initial authenticator content for authenticators that are defined by the organization (for example, API keys) |
| `3000076` | IBM Cloud VPC uniquely identifies all physical devices before accepting a network connection |
{: caption="Table 1. Default goals met by working with {{site.data.keyword.cloud_notm}}" caption-side="bottom"}

