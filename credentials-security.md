---

copyright:
  years: 2021
lastupdated: "2021-09-22"

keywords: credentials, security and compliance, collector access, collector communication, resource scan, configuration scanning, credentials stored

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

# Managing the security of your credentials
{: #passphrase}

A credential passphrase is an arbitrary string that you can use to ensure the security of the credentials that you add to the service. As a user, you can choose to have IBM manage the security of your credentials, or you can choose to manage it yourself.
{: shortdesc}

## Understanding passphrases
{: #understand-passphrase}

In most cases, IBM-managed credential security is appropriate. If your industry requires that you maintain total secrecy of your data - including from IBM, then you might choose to create and enable your own passphrase. However, if you choose to enable your own passphrase, it is important that you understand that IBM does not have access to it. Given that IBM cannot access the passphrase that you enabled:

* IBM cannot help you recover your passphrase if it is ever lost or forgotten.
* The password is not validated when it is entered to complete an action.

For security reasons, if a passphrase is entered incorrectly, the credentials that were already added become unusable by the service.
{: important}


Check out the following diagram to understand more about how credential security works. 

![This image is a visual representation of how credentials are secured. The information that is shown in the image is detailed in the surrounding text.](images/passphrase.svg)

As you can see in the previous image, a user adds their credentials to the service UI. The credentials that they add might be a username and password or an API key that the {{site.data.keyword.compliance_short}} might need to scan a specific resource. Then, if a user wants to manage their own security, they enable their own passphrase. If they want to have IBM manage their security, the service generates a passphrase. Either way, the passphrase is used to create a data encryption key. That key is used to encrypt the credentials before they are stored by the service.

## Before you begin
{: #before-passphrase}

Before you get started, be sure that you have the required level of access to view and manage credentials. To enable a passphrase in your account, you need the [**Administrator** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).

## Enabling a passphrase
{: #enable-passphrase}

To enable a passphrase in your account, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) > **Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, in the **Manage posture** section, click **Configure > Credentials**.
3. In the **Credentials security** box, click the **Edit** icon. A side panel opens. 
4. Enter your **New passphrase**.
5. Confirm your passphrase by retyping it. 
6. Validate that you understand the risk of enabling your own passphrase by checking the box. 
   
   For security reasons, if you enter the passphrase incorrectly after it is enabled, any mapped credentials become unusable by the {{site.data.keyword.compliance_short}}.
   {: important}
   
7. Click **Save**.



