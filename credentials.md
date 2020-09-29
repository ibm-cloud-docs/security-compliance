---

copyright:
  years: 2020
lastupdated: "2020-09-29"

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

# Managing credentials
{: #credentials}

When you work with the {{site.data.keyword.compliance_full}}, you provide the credentials that allow a collector to access and scan your IT resources.
{: shortdesc}

## Understanding credentials
{: #understand-credentials}

Credentials are used by a collector to gather information about your resource configurations, assess them, and initiate any remediation that is required.

**What types of credentials do I provide?**

The credentials that you provide depend upon the type of resources that you want to scan. You might provide an API key, an access key file, or a username and password to a specific resource.


**What level of access do my credentials need to have?**

The level of access that your credentials need depends upon the actions that you want the {{site.data.keyword.compliance_short}} to take. If you only want to run scans on your resources, you must provide credentials that provide the collector `read` access to your resources. This way, the service is able to scan your resource configurations. If you also want to initiate remediation from the {{site.data.keyword.compliance_short}}, then the credentials that you provide must have `write` access.

**How are my credentials stored?**

Credentials are stored securely by using encryption and are not visible in clear text at any point during the storage process. For more information about the security of your stored credentials, see [Storing and encrypting data in the {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-data-storage).




## Before you begin
{: #before-credentials}

Before you begin, be sure that you're using a [Pay-As-You-Go or Subscription](/docs/account?topic=account-accounts) {{site.data.keyword.cloud_notm}} account where you are the owner or have [full administrator access](/docs/account?topic=account-assign-access-resources). You must also have access to the credentials that you want to add to the service. 


## Creating a credential
{: #create-credentials}

To create a new credential, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Settings > Credentials**.
3. Give your credential a meaningful name and a description.
4. Choose a **Credential type** from the following options:

  * AWS Cloud
  * GCP Cloud
  * IBM Cloud
  * Database
  * Username - password
  * Username - PEM

  The type of credential that you create is dependent upon the type of resources that you want to scan.
  {: note}

5. Select a purpose for your credential. Options include **Discovery/Collection**, **Remediation**, or both.   
6. Add the access information. Depending on the type of credential that you selected in step 4, the options on the page change. 

  <table>
    <caption>Table 1. Credential types and input information</caption>
    <tr>
      <th>Credential type</th>
      <th>Needed information</th>
    </tr>
    <tr>
      <td>AWS Cloud</td>
      <td>An AWS access key ID and secret access Key.</td>
    </tr>
    <tr>
      <td>GCP Cloud</td>
      <td>A GCP access key file.</td>
    </tr>
    <tr>
      <td>IBM Cloud</td>
      <td>An IBM Cloud API key. For help with creating an API key, see [Understanding API keys](/docs/account?topic=account-manapikey).</td>
    </tr>
    <tr>
      <td>Database</td>
      <td>The name of the database and the username and password that are needed to access it.</td>
    </tr>
    <tr>
      <td>Username - password</td>
      <td>A username and password combination that is needed to gain access to an on-premises machine.</td>
    </tr>
    <tr>
      <td>Username - PEM</td>
      <td>A username and password combination and PEM file that is needed to gain access to an on-premises machine.</td>
    </tr>
  </table>

7. If a passphrase is configured, enter the passphrase. 
8. Verify your information and click **Save**. The credential is added to a list of available credentials. 

To edit or delete existing credentials, select the credential that you want to modify and click the **Edit** or **Delete** icon.
{: tip}



## Mapping credentials to a scope
{: #map-credentials}

Occasionally, you might have a scope that requires more than one set of credentials to complete a scan. This can happen when users have credentials that are used for individual databases or servers that need to be scanned. To map credentials to your scope, complete the following steps.

To map a credential, it must exist in the service. Before you get started, be sure to [create the credential](/docs/security-compliance?topic=security-compliance-credentials).
{: note}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Scopes**.
3. Select the scope that you want to map credentials for.
4. Click the **Map credentials** icon.
5. Click **Add new**.
6. Enter the criteria that you want to use.

  Criteria specifies the conditions for when a credential can be used. For example, for a specific VPC, a specific IP, or a set of IP ranges.
7. Select the credentials that you want to use.
8. Optional: Select a **Proxy**.
9. Click the check mark icon to add the credential to the scope. Repeat steps 6 - 10 until you add all your needed credentials.
10. Click **Close**.

You can also choose to edit or delete an existing entry if you made a mistake or no longer need to use that credential with that scope.
{: tip}



## Creating a passphrase
{: #passphrase}

A credential passphrase creates an encryption key that provides an extra layer of protection for the credentials that are used to collect configuration settings from your IT resources. If you choose to not create a passphrase, a system-generated passphrase is used in the background to secure the connections.

When you enable a user-generated passphrase, it must be provided for all create and edit operations, including any operations that are associated with [managing collectors](/docs/security-compliance?topic=security-compliance-collector).

The {{site.data.keyword.compliance_full}} does not store the passphrase. It is available only temporarily in memory when it is entered by an administrator when they attempt to add a collector, add credentials, edit credentials, or update passphrase protection.
{: note}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) > **Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Settings > Credential passphrase**.
3. For **Password protection**, click **Enable**.
4. Enter your passphrase in the **Credential passphrase** field.
5. Click **Save**.



