---

copyright:
  years: 2020, 2022
lastupdated: "2022-05-12"

keywords: Admin API changelog, Admin API change log, change log for Admin API, updates to Security and Compliance Center Admin API

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

# Admin API change log
{: #admin-api-change-log}

In this change log, you can learn about the latest changes, improvements, and updates for the [{{site.data.keyword.compliance_full}} Admin API](/apidocs/security-compliance-admin). The change log lists changes that have been made, ordered by the date they were released. Changes to existing API versions are designed to be compatible with existing client applications.
{: shortdesc}

To learn about general updates and improvements to the {{site.data.keyword.compliance_short}}, see [Release notes](/docs/security-compliance?topic=security-compliance-release-notes).

For information about the latest changes to the {{site.data.keyword.compliance_short}} SDKs, see the change logs in the SDK repositories:

- [Java SDK change log](https://github.com/IBM/scc-java-sdk/releases)
- [Node SDK change log](https://github.com/IBM/scc-node-sdk/releases)
- [Python SDK change log](https://github.com/IBM/scc-python-sdk/releases)
- [Go SDK change log](https://github.com/IBM/scc-go-sdk/releases)




## 13 December 2021
{: #admin-13dec21}

This release includes the following updates:

- Updated the [View account settings](/apidocs/security-compliance-admin#getsettings) and [Update account settings](/apidocs/security-compliance-admin#patchaccountsettings) methods to support the ability to register with the {{site.data.keyword.en_short}} service. For more information, see [Enabling event notifications](/docs/security-compliance?topic=security-compliance-event-notifications&interface=api).
- Added the [Send test event](/apidocs/security-compliance-admin#sendtestevent) method that can be used to send a test event to your configured {{site.data.keyword.en_short}} instance.

## 23 March 2021
{: #admin-13mar21}

This release includes the following updates:

- Admin API is now available. This release includes the [View account settings](/apidocs/security-compliance-admin#getsettings) and [Update account settings](/apidocs/security-compliance-admin#patchaccountsettings) methods that can be used to manage your storage location. For more information, see [Managing your storage location](/docs/security-compliance?topic=security-compliance-mng-data&interface=api#storage-location).

