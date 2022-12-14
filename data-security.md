---

copyright:
  years: 2021
lastupdated: "2021-07-08"

keywords: data encryption in {{site.data.keyword.compliance_short}}, data storage for {{site.data.keyword.compliance_short}}, bring your own keys for {{site.data.keyword.compliance_short}}, BYOK for {{site.data.keyword.compliance_short}}, key management for {{site.data.keyword.compliance_short}}, key encryption for {{site.data.keyword.compliance_short}}, personal data in {{site.data.keyword.compliance_short}}, data deletion for {{site.data.keyword.compliance_short}}, data in {{site.data.keyword.compliance_short}}, data security in {{site.data.keyword.compliance_short}}

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

# Storing and encrypting data in {{site.data.keyword.compliance_short}}
{: #mng-data}

To ensure that you can securely manage your data when you use {{site.data.keyword.compliance_full}}, it is important to know exactly what data is stored and encrypted and how you can delete any stored personal data. Data encryption by using customer-managed keys is supported by using Key Protect or Hyper Protect Crypto Services with the {{site.data.keyword.compliance_short}}.
{: shortdesc}

For more information about how {{site.data.keyword.cloud_notm}} platform secures your data, see [How do I know that my data is safe?](/docs/overview?topic=overview-security)
{: tip}


## How is data stored by the {{site.data.keyword.compliance_short}}?
{: #data-storage}

When you work with the {{site.data.keyword.compliance_short}}, data is generated by the service as you interact with it. That data includes findings, flagged issues, and stored credentials that are used by the collector to scan your resources. Check out the following table to see how the data is managed.

| Component    | Storage information |
|: ------------|:--------------------|
| Posture Management  | The data that is collected and generated by the service: <ul><li> Does contain personally identifiable information. </li><li>Is sent over a TLS 1.2+ protected channel by using {{site.data.keyword.cloud_notm}} Internet Services (powered by Cloudflare). By using Cloud Internet Services there is DDoS protection, a Web Application Firewall, and other network level security mechanisms in place. </li><li>Is cryptographically signed by the collector's private key. </li><li>Is validated by the service with the collector's public key. </li></ul> **Note**: The credentials that you provide to allow a collector to access and scan your resources are securely stored. No one - including IBM can access them. At no time are your credentials available in clear text while they are stored or used by the service. For more information, see [Managing collectors](/docs/security-compliance?topic=security-compliance-collector). |
| Configuration Governance   | The data that is collected and generated by the service:<ul><li>Does not contain any personally identifiable information. </li><li>Is sent over a TLS 1.2+ protected channel by using {{site.data.keyword.cloud_notm}} Internet Services (powered by Cloudflare). By using Cloud Internet Services there is DDoS protection, a Web Application Firewall, and other network level security mechanisms in place. </li><li>Is encrypted while at rest and in transit to a provider-managed Cloudant database (configuration data) or a provider-managed {{site.data.keyword.cloud_notm}} Databases Elastic Search (results data). </li><li>Is securely replicated in US-South and US-East regions. </li></ul> |
| Security Insights | The data that is collected and generated by the service: <ul><li>Does not contain any personally identifiable information. </li><li>Is encrypted at rest and in transit. </li><li>Is stored in a Cloudant database within each region. </li><li>Is backed up daily to Cloud Object Storage. </li><li>Is automatically recovered by IBM in the event of a failure.</li></ul> |
{: caption="Table 1. Data storage information for {{site.data.keyword.compliance_short}}" caption-side="top"}


## Managing your storage location
{: #storage-location}

Currently, the {{site.data.keyword.compliance_short}} manages the storage and processing of the data that is generated by the service. By default, the management is done in the United States. If you need to work in another location for data privacy reasons, you can change the location by using the {{site.data.keyword.compliance_short}} UI or Admin API. Available locations include the United Kingdom, United States, and the European Union.

When you change your location, all of the configurations in your current location are removed and scans are stopped. You must reconfigure all of your settings in the new location to continue working. Any data that is available in your current location is [automatically deleted](#data-delete) after a period of time.????
{: important}

### Changing your location with the console
{: #storage-location-ui}
{: ui}

You can change the location in which your data is stored and processed by using the {{site.data.keyword.compliance_short}} UI.

1. Go to **Security and Compliance Center > Data settings**.
2. In the **Storage and Processing** section, click the **Edit** icon ![Edit icon](../icons/edit-tagging.svg).
3. Select the location that you want to use.

  The United Kingdom location is available only for Security Insights. To work with the other {{site.data.keyword.compliance_short}} components, you must use another location.
  {: note}

4. Confirm that you want to change your location.
5. Click **Save**.

### Changing your location with the API
{: #storage-location-api}
{: api}

You can change the location in which your data is stored and processed by using the Admin API.

1. View your current settings.

  ```sh
  curl -X GET 'https://compliance.cloud.ibm.com/admin/v1/accounts/<account_id>/settings' \
  -H 'accept: application/json'
  ```
  {: codeblock}

2. Update your settings.

  ```sh
  curl -X PATCH 'https://compliance.cloud.ibm.com/admin/v1/accounts/<account_id>/settings' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "location": {
      "id": "us-south"
    }
  }'
  ```
  {: codeblock}

  The United Kingdom location is available only for Security Insights. To work with the other {{site.data.keyword.compliance_short}} components, you must use another location.
  {: note}

  Response:

  ```json
  {
    "location": {
      "id": "us-south",
      "modified": "2021-03-08T07:38:10.730184636Z",
      "cleanup_inactive_locations": false
    }
  }
  ```
  {: screen}


## Protecting your sensitive data
{: #data-encryption}

You can add a higher level of encryption control to your data at rest (when it is stored) by enabling integration with {{site.data.keyword.keymanagementservicelong_notm}} or {{site.data.keyword.hscrypto}}. [{{site.data.keyword.hscrypto}}](/docs/hs-crypto?topic=hs-crypto-get-started) is a single-tenant key management service that is backed by a FIPS140-2 level 4 certified Hardware Security Model (HSM).

The {{site.data.keyword.compliance_short}} encrypts the results that are generated by the service by using either IBM or customer-managed keys. By default, the encryption keys that secure your data are generated on your behalf through {{site.data.keyword.keymanagementserviceshort}} and managed by IBM. If you want to use and manage your own key, you can integrate a key management service by using the **Data settings** tab in the {{site.data.keyword.compliance_short}} UI.

The following table describes your options for managing the encryption of selected {{site.data.keyword.compliance_short}} components.

| Encryption | Description |
| ---- | ---- |
| IBM-managed | The data that you store in {{site.data.keyword.compliance_short}} is encrypted at rest by using an IBM-managed key. This is the default setting. |
| Customer-managed | The data that is stored in selected {{site.data.keyword.compliance_short}} components is encrypted at rest by using a key that you own and manage. You can use a root key that you manage in [{{site.data.keyword.keymanagementserviceshort}}](/catalog/services/key-protect) or [{{site.data.keyword.hscrypto}}](/catalog/services/hs-crypto). |
{: caption="Table 2. Encryption options for {{site.data.keyword.compliance_short}}" caption-side="top"}

Currently, you can use a customer-managed key to protect {{site.data.keyword.compliance_short}} data that is generated by compliance scans and Security Insights. All other data is encrypted at rest by using an IBM-managed key.
{: note}


### What are some best practices when managing my own encryption in {{site.data.keyword.compliance_short}}?
{: #key-best-practices}

When you work with {{site.data.keyword.compliance_short}} data, there are a few best practices to keep in mind to ensure that your data is always secure.

- [Rotate your keys.](/docs/key-protect?topic=key-protect-key-rotation)
- [Set fine-grained access control policies.](/docs/key-protect?topic=key-protect-manage-access)

In {{site.data.keyword.keymanagementserviceshort}}, you can assign various levels of access to limit the number of people who have access to your keys. You can also update the access later if a need to tighten security around your data occurs.

Need to know if changes to your keys occur? You can use [Activity Insights](/docs/security-advisor?topic=security-advisor-setup-activity) to continuously monitor your keys and be [alerted](/docs/security-advisor?topic=security-advisor-notifications) if any change is detected.
{: tip}

### About customer-managed keys
{: #about-encryption}

The {{site.data.keyword.compliance_short}} uses [envelope encryption](#x9860393){:term} to implement customer-managed keys. Envelope encryption describes encrypting one encryption key with another encryption key. The key used to encrypt the actual data is known as a [data encryption key (DEK)](#x4791827){: term}. The DEK itself is never stored but is wrapped by a second key that is known as the key encryption key (KEK) to create a wrapped DEK. To decrypt data, the wrapped DEK is unwrapped to get the DEK. This process is possible only by accessing the KEK, which in this case is your root key that is stored in your key management service.

Depending on your use case and security requirements, the key management service that is most suited for your organization's needs can vary. To learn more about which key management solution is best for you, see [How is {{site.data.keyword.hscrypto}} different from {{site.data.keyword.keymanagementserviceshort}}?](/docs/hs-crypto?topic=hs-crypto-faq-basics#faq-differentiators-key-protect)
{: note}


### Enabling customer-managed keys
{: #using-byok}

If you choose to work with a key that you manage, you must ensure that valid IAM authorization is assigned between the {{site.data.keyword.compliance_short}} and your preferred key management service. To create that authorization, you can use the following steps.


1. Create an instance of [{{site.data.keyword.keymanagementserviceshort}}](/catalog/services/key-protect) or [{{site.data.keyword.hscrypto}}](/catalog/services/hs-crypto)
2. [Generate or import a root key](/docs/key-protect?topic=key-protect-create-root-keys) to your key management service instance.

    When you use {{site.data.keyword.keymanagementserviceshort}} or {{site.data.keyword.hscrypto}} to create a root key, the service generates cryptographic key material that is rooted in cloud-based HSMs. Be sure that the name of your key does not contain any personal information such as your name or location.
3. Grant service access between your key management service and the {{site.data.keyword.compliance_short}}.

    You must be the account owner or an administrator of the key management service instance that you're working with. You must also have at least Viewer access for the {{site.data.keyword.compliance_short}} service.

    1. Go to **Manage > Access IAM > Authorizations**.
    2. Select {{site.data.keyword.compliance_short}} or {{site.data.keyword.security-advisor_short}} as the source service.

       If you're creating an authorization for compliance scans, select **{{site.data.keyword.compliance_short}}**. To create an authorization for security insights, select **{{site.data.keyword.security-advisor_short}}**.

    3. Select {{site.data.keyword.keymanagementserviceshort}} or {{site.data.keyword.hscrypto}} as the target service.
    4. Assign the Reader role.
    5. Click **Authorize** to confirm the authorization.

    If you're enabling customer-managed keys for Security Insights, be sure that you also have the [required permissions](/docs/security-advisor?topic=security-advisor-service-access) to work with {{site.data.keyword.security-advisor_short}}.
    {: note}

4. Enable the integration in the {{site.data.keyword.compliance_short}}.

    After you create an authorization between your key management service and {{site.data.keyword.compliance_short}}, you can integrate it by using {{site.data.keyword.compliance_short}}. To update your encryption settings:

    1. Go to **Security and Compliance Center > Data settings**.
    2. In the Encryption section, click the **Edit** icon ![Edit icon](../icons/edit-tagging.svg) to manage your encryption settings.
    3. Select the service instance and root key that you want to use to protect your data.
    4. Choose the type of {{site.data.keyword.compliance_short}} results that you want to encrypt with your selected key by toggling either **Compliance scans**, **Security insights**, or both to **On**.
    5. To return to IBM-managed encryption, use the toggle to turn customer-managed encryption **Off**.


## Deleting your data
{: #data-delete}

All of the data in your account is automatically deleted. You don't need to take any action to delete data that you no longer require. But, depending on the component of the {{site.data.keyword.compliance_short}} that you're working with, data is stored and deleted differently.

| Component    | Data deletion policy |
|:-------------|:---------------------|
| Posture Management  | Configuration data is deleted after 30 days. Analytics data is deleted after 31 days. |
| Configuration Governance   | Results data is stored for 7 days. |
| Security Insights | Findings data is limited to 18,000 findings per account for a 90-day period. If the findings limit is reached before the 90 days is reached, 50% of the findings are deleted on a first-in, first-out basis. If the limit is not reached, the data is deleted after 90 days. |
{: caption="Table 2. {{site.data.keyword.compliance_short}} data deletion policies " caption-side="top"}

If you delete your account, all of the data that is associated with the {{site.data.keyword.compliance_short}} is automatically deleted.
{: note}
