---

copyright:
  years: 2014, 2021
lastupdated: "2021-10-13"

keywords: Centralized security, security management, alerts, security risk, insights, threat detection

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

# Leveraging default services
{: #setup-services}

The Security Insights of {{site.data.keyword.compliance_full}} comes with several built-in integrations that can help you to monitor for security risks and threats.
{: shortdesc}

The following services are automatically monitored by Security Insights:

* {{site.data.keyword.registryshort}}
* {{site.data.keyword.cloudcerts_short}}

Although you do not have to do anything to create the connection between the {{site.data.keyword.compliance_short}} and the services, you must have instances of the services configured with information.


## Monitoring vulnerabilities in container images
{: #setup-images}

With {{site.data.keyword.registryshort}}, you have access to Vulnerability Advisor, which continuously scans the images in your {{site.data.keyword.registryshort}} instance for potential security issues. If issues are found, you are alerted and can view a comprehensive report in your {{site.data.keyword.compliance_short}} dashboard.

Learn more about [{{site.data.keyword.registryshort}}](/docs/Registry?topic=Registry-getting-started).


### Before you begin
{: #setup-before}

Before you get started, be sure that you have the required level of access to view Security Insights. To view Security Insights, you must have the [**Viewer** service role or higher for {{site.data.keyword.security-advisor_short}}](/docs/security-compliance?topic=security-compliance-access-management).

Before you can get started with registry, be sure that you have the following CLIs and plug-ins installed:
* [The {{site.data.keyword.cloud_notm}} CLI)](/docs/cli/reference/ibmcloud?topic=cli-install-ibmcloud-cli)
* The Container Registry plug-in

   ```sh
   ibmcloud plugin install container-registry
   ```
   {: codeblock}


### Creating a namespace
{: #setup-create-namespace}

1. Log in to your account by using the CLI.

   ```sh
   ibmcloud login --sso
   ```
   {: codeblock}

2. Log in to {{site.data.keyword.registryshort}}.

   ```sh
   ibmcloud cr login
   ```
   {: codeblock}

3. Optional: Create a namespace. You can always use an existing one.

   ```sh
   ibmcloud cr namespace-add
   ```
   {: codeblock}

4. Tag an image.

   ```sh
   docker tag <image>:<tag> <region>.icr.io/<namespace>/<image>:<tag>
   ```
   {: codeblock}

5. Push the image.

   ```sh
   docker push <region>.icr.io/<namespace>/<image>:<tag>
   ```
   {: codeblock}

After you push images to your {{site.data.keyword.registryshort}} namespace, information about any vulnerabilities found is shown in the **Images with Vulnerabilities** card in the service dashboard. You can also drill down into specific images to find out more information, such as a description of all of the identified vulnerabilities and configuration issues.


## Monitoring certificates
{: #setup-certificates}

By integrating {{site.data.keyword.cloudcerts_short}} and {{site.data.keyword.compliance_short}}, you can get alerts in advance about your certificates expiry which can help prevent a service or application outage.


Depending on the expiration data of the certificate that you upload to {{site.data.keyword.cloudcerts_short}}, the findings appear in the {{site.data.keyword.compliance_short}} dashboard 90, 60, 10, and 1 day before the certificate expires. In addition, you receive daily notifications about expired certificates. The daily notifications start the day after your certificate expires.

To trigger a manual update, you might try uploading a certificate that expires in a day to your {{site.data.keyword.cloudcerts_short}} instance. When the import is successful, you can see that the Key Performance Indicator (KPI) and findings are visible in the {{site.data.keyword.compliance_short}} dashboard.

You can learn more about [{{site.data.keyword.cloudcerts_short}}](/docs/certificate-manager?topic=certificate-manager-getting-started) by reading the docs.
{: tip}


### Creating a certificate
{: #setup-create-cert}

To create a self signed certificate that expires in a day, you can run the following OpenSSL command in your terminal.

```
openssl req -x509 -newkey rsa:2048 -keyout key.pem -subj "/CN=myservice.com" -out server.pem -days 1 -nodes
```
{: codeblock}


### Uploading a certificate
{: #setup-upload-cert}

1. In the {{site.data.keyword.cloud_notm}} catalog, search for "{{site.data.keyword.cloudcerts_short}}".
2. Give your service instance a name, or use the preset name.
3. Click **Create**.
4. To import your organization's certificates into {{site.data.keyword.cloudcerts_short}}, click **Import Certificate**.

Now that your certificates are imported, information such as expiration times and expired certificates, is shown on the **Certificates** card in the {{site.data.keyword.compliance_short}} dashboard. By clicking the card, you can get more specific information about the certificates, such as which service instance that the certificates belong to. You can also see any steps that you can take to fix the security vulnerabilities.

To stop the notifications, you must renew your certificate, upload the certificate to {{site.data.keyword.cloudcerts_short}}, and delete the expired certificate.
{: tip}

