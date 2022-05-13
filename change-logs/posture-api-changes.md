---

copyright:
  years: 2020, 2022
lastupdated: "2022-05-13"

keywords: Posture Management API changelog, Posture Management API change log, change log for Posture Management API, updates to Security and Compliance Center Posture Management API

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

# Posture Management API change log
{: #posture-api-change-log}

In this change log, you can learn about the latest changes, improvements, and updates for the [{{site.data.keyword.compliance_full}} Posture Management API](/apidocs/security-compliance/posture). The change log lists changes that have been made, ordered by the date they were released. Changes to existing API versions are designed to be compatible with existing client applications.
{: shortdesc}

To learn about general updates and improvements to the {{site.data.keyword.compliance_short}}, see [Release notes](/docs/security-compliance?topic=security-compliance-release-notes).

For information about the latest changes to the {{site.data.keyword.compliance_short}} SDKs, see the change logs in the SDK repositories:

- [Java SDK change log](https://github.com/IBM/scc-java-sdk/releases)
- [Node SDK change log](https://github.com/IBM/scc-node-sdk/releases)
- [Python SDK change log](https://github.com/IBM/scc-python-sdk/releases)
- [Go SDK change log](https://github.com/IBM/scc-go-sdk/releases)

## API versioning
{: #posture-api-versioning}

When the API is changed in a way that is not compatible with previous versions, a new major version is released. To take advantage of the changes in a new version, change the value of the version in the API's path. In the following example, `v2` is used to indicate the API version:

```
https://{location}.compliance.cloud.ibm.com/posture/v2/{method_endpoint}
```
{: screen}


### Active versions
{: #posture-active-versions}

The following table shows the service behavior changes for each version. Switching to a later version will require updates to your client application code.

| Version | Summary of changes |
|---------|--------------------|
| `v2`    | New methods added with improved readability and response details.|
| `v1`    | Beta version that is available for evaluation and testing.|

## 13 May 2022
{: #posture-13may2022}

This release includes the following update:

- Updated the HTTP `403` response status code for all methods to support [pricing plans](/docs/security-compliance?topic=security-compliance-scc-pricing). All Posture Management APIs now return a `403` response if you haven't selected a pricing plan or your trial period has ended.


## 25 January 2022
{: #posture-25jan22}

This release includes the following update:

- Posture Management API Version 2.0.0 is now available. This major version adds 23 new methods that you can use to manage [credentials](/apidocs/security-compliance/posture-v2.0#create-credential), [collectors](/apidocs/security-compliance/posture-v2.0#create-collector), [profiles](/apidocs/security-compliance/posture-v2.0#import-profiles), [scopes](/apidocs/security-compliance/posture-v2.0#create-scope), and [scans](/apidocs/security-compliance/posture-v2.0#list-latest-scans).

  This version is not compatible with previous Posture Management API versions.
  {: important}


## 22 July 2021
{: #posture-22jul21}

This release includes the following updates:

- Changed the URI path for the [List latest scans](/apidocs/security-compliance/posture-v1.0#list-latest-scans) method from `/posture/v1/scans/validations/latest` to `/posture/v1/scans/validations/latest_scans`.
- Added [View a specified scan](/apidocs/security-compliance/posture-v1.0#scans-summary), [View scan summaries](/apidocs/security-compliance/posture-v1.0#scan-summaries), [Create a scope](/apidocs/security-compliance/posture-v1.0#create-scope), [Create a collector](/apidocs/security-compliance/posture-v1.0#create-collector), and [Create a credential](/apidocs/security-compliance/posture-v1.0#create-credential) methods.


## 20 April 2021
{: #posture-20apr21}

This release includes the following update:

- Posture Management API Version 1.0.0 is now available as a beta release. This release includes the following methods: [List latest scans](/apidocs/security-compliance/posture-v1.0#list-latest-scans), [Initiate a validation scan](/apidocs/security-compliance/posture-v1.0#create-validation), [List profiles](/apidocs/security-compliance/posture-v1.0#list-profiles), and [List scopes](/apidocs/security-compliance/posture-v1.0#list-scopes).
