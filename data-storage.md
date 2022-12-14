---

copyright:
  years: 2020, 2022
lastupdated: "2022-12-14"

keywords: custom profiles, user-defined, controls, goals, security, compliance

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


# Setting up data storage and processing for {{site.data.keyword.compliance_short}}
{: #storage}

When you work with {{site.data.keyword.compliance_full}}, you must configure how you want your data to be handled. For more detailed information about the types of data that can be used with the service, see [Understanding data encryption](/docs/security-compliance?topic=security-compliance-mng-data).
{: shortdesc}

## Before you begin
{: #before-storage}

Before you get started, be sure that you have the required level of access to update the settings for {{site.data.keyword.compliance_short}}. To manage settings, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).

## Bucket requirements
{: #scc-bucket}

The bucket that you use to store your results does not require any particular settings or naming format. But, it is recommended that you use a bucket on the Standard plan and Smart tier.

All the traffic between {{site.data.keyword.compliance_short}} and Cloud Object Storage is done over a private network. The retrieval of data for display purposes in the console does not cost you anything. However, if you choose to download the data directly from Cloud Object Storage after it is stored, you do incur a data transfer cost. See Cloud Object Storage pricing for more information.


## Configuring storage
{: #cos-storage}

Before you can start evaluating your resources for compliance, you must configure a Cloud Object Storage bucket where the service can forward your results data for long-term storage.

To connect your Cloud Object Storage bucket, you can use the {{site.data.keyword.compliance_short}} UI.

2. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Settings**.
3. On the **Storage** tile, click **Connect**.
4. If a service-to-service policy is not already enabled, use the in-context settings to create one. If you already have a policy in place, this screen does not show and you can skip to the next step.
5. Select an instance of Cloud Object Storage.
6. From the table, select the bucket that you want to use.
7. Click **Connect**.

If you disconnect your instance of Cloud Object Storage or select a new bucket, {{site.data.keyword.compliance_short}} is not able to read any of your existing results data. An evaluation won't complete if a Cloud Object Storage bucket is not connected.
{: important}



## Configuring data processing
{: #processing}

By default, the processing of your data is done in the United States. To update your configuration, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Settings**.
3. On the **Processing** tile, click **Edit**.
4. Select the location that you want to use and check the confirmation box.
5. Click **Save**.

If you change your location, you must reconfigure any scans that are scheduled in your account. 
{: note}

## Configuring encryption (collectors)
{: #data-encryption-configure}

By default, the data that is stored by {{site.data.keyword.compliance_short}} is encrypted at rest by using an IBM-managed key. You can add a level of control to your data at rest by enabling an integration with {{site.data.keyword.keymanagementservicelong_notm}} or {{site.data.keyword.hscrypto}}. [{{site.data.keyword.hscrypto}}](/docs/hs-crypto?topic=hs-crypto-get-started) is a single-tenant key management service that is backed by a FIPS140-2 level 4 certified Hardware Security Model (HSM).

If you choose to work with a key that you manage, you must ensure that valid IAM authorization is assigned between {{site.data.keyword.compliance_short}} and your preferred key management service. To create that authorization, you can use the following steps.

1. Create an instance of [{{site.data.keyword.keymanagementserviceshort}}](/catalog/services/key-protect) or [{{site.data.keyword.hscrypto}}](/catalog/services/hs-crypto).
2. [Generate or import a root key](/docs/key-protect?topic=key-protect-create-root-keys) to your key management service instance.

   When you use {{site.data.keyword.keymanagementserviceshort}} or {{site.data.keyword.hscrypto}} to create a root key, the service generates cryptographic key material that is rooted in cloud-based HSMs. Be sure that the name of your key does not contain any personal information such as your name or location.

3. Grant service access between your key management service and {{site.data.keyword.compliance_short}}.

   You must be the account owner or an administrator of the key management service instance that you're working with. You must also have at least *Viewer* access for {{site.data.keyword.compliance_short}}.

   1. Go to **Manage > Access IAM > Authorizations**.
   2. Select {{site.data.keyword.compliance_short}} as the source service.

      If you're creating an authorization for compliance scans, select **{{site.data.keyword.compliance_short}}**.

   3. Select {{site.data.keyword.keymanagementserviceshort}} or {{site.data.keyword.hscrypto}} as the target service.
   4. Assign the *Reader* role.
   5. Click **Authorize** to confirm the authorization.

4. Enable the integration in {{site.data.keyword.compliance_short}}.

   After you create an authorization between your key management service and {{site.data.keyword.compliance_short}}, you can integrate it by using {{site.data.keyword.compliance_short}}. To update your encryption settings:

   1. Go to **{{site.data.keyword.compliance_short}} > Settings**.
   2. In the **Data > Encryption** section, click the **Edit** icon ![Edit icon](../icons/edit-tagging.svg) to manage your encryption settings.
   3. Select the service instance and root key that you want to use to protect your data.
   4. Toggle **Compliance scans** to **On** to encrypt your results.
   5. Click **Close**.

To return to IBM-managed encryption, toggle customer-managed encryption to **Off**.
{: note}

