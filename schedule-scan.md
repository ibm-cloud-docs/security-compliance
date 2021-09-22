---

copyright:
  years: 2021
lastupdated: "2021-09-22"

keywords: scans, compliance, schedule scan, create scan, discovery, validation, fact collection, fact validation

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


# Scheduling a scan
{: #schedule-scan}

When you're working with {{site.data.keyword.compliance_full}}, you can run scans of specific scopes to determine resource availability, resource configuration, and a scope's adherence to regulatory controls as defined in a profile.
{: shortdesc}


## Understanding scan types
{: #scan-types}

Depending on what you're trying to accomplish, you might run different types of scans. Check out the following table to learn more about types of scans and when to run each type.

| Scan type | Description |
|:----------|:------------|
| Discovery | A scope is often defined at the highest level and includes one or more resource groups. When a discovery scan is run, a list of all of the available resources in a scope is returned. |
| Fact collection | When you collect facts, you're collecting the configuration information of the resources that were found during discovery. If any new resource configurations are found, then the scope is updated to include them. |
| Validation | Validation scans determine a specified scope's adherence to regulatory controls by creating an attachment between that scope and profile. When a validation scan is run, the service also runs a fact collection scan before the validation occurs. |
| Fact validation | Fact validation is run on previously collected facts. You might run a fact validation to determine whether previous configurations meet your current profile requirements. |
{: caption="Table 1. Types of scans" caption-side="top"}

## Before you begin
{: #before-scans}

Before you get started, be sure that you have the required level of access to view and schedule scans. To schedule scans, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).



### Configuring scanning for VMs
{: #vm-prereqs}

If you're attempting to configure fact collection for cloud-based infrastructure, you must complete the following steps before you schedule your scan.

Scanning for {{site.data.keyword.cloud_notm}} Gen 1 classic infrastructure is not available.
{: note}

#### Supported VM types
{: #supported-vms}

* Red Hat Enterprise Linux (RHEL)
* CentOS
* Suse
* Debian
* Ubuntu
* Windows

#### Linux prerequisites
{: #linux-prereq}

1. SSH must be running with port 22 open.
2. Passwordless `sudo` must be enabled.


#### Windows prerequisites
{: #windows-prereq}

Enable your Windows Server computers to access PowerShell remotely (`WinRM`).

To check to see if the computer has `WinRM` enabled, check if the HTTPS listener is running by running the following command in a PowerShell window: `dir wsman:\localhost\listener`.

1. Enable WinRM Remoting.

  ```
  Enable-PSRemoting -SkipNetworkProfileCheck -Force
  ```
  {: codeblock}

2. Set up your certificates and enable your HTTPS listener.

  ```
  $myhost=(Get-WmiObject win32_computersystem).DNSHostName+"."+ (Get-WmiObject win32_computersystem).Domain $Cert = New-SelfSignedCertificate -CertstoreLocation Cert:\LocalMachine\My -DnsName $myhost New-Item -Path WSMan:\LocalHost\Listener -Transport HTTPS -Address * -CertificateThumbPrint $Cert.Thumbprint -Force
  ```
  {: codeblock}

3. Enable your Windows server firewall to allow for incoming communication.

  ```
  New-NetFirewallRule -DisplayName "Windows Remote Management (HTTPS-In)" -Name "Windows Remote Management (HTTPS-In)" -Profile Any -LocalPort 5986 -Protocol TCP
  ```
  {: codeblock}

4. Ensure that basic authentication is set to true.

  ```
  winrm set winrm/config/Service/Auth '@{Basic="True"}'
  ```
  {: codeblock}

5. Validate that your configuration and network connection are running correctly.

  ```
  winrm get winrm/config -NetConnectionProfile
  ```
  {: codeblock}



## Running discovery and fact collection scans
{: #run-discovery}

You can schedule a discovery or fact collection scan by using the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Assess > Scans > Scheduled scans**. 
3. Click **Schedule**. A side panel opens.
4. Give your scan a name and description.
5. Select **Discovery** or **Fact collection**.
6. Select a scope and click **Next**
7. Optional: If you selected an Amazon Web Services (AWS) scope, set your remediation preference.
8. Select the frequency at which you want the scan to run.
9. Select when you want the scan to stop. Options include never, a specific number of scans, or on a set date.
10. Click **Create**.



## Running validation scans
{: #run-validation}

You can schedule a validation scan by using the {{site.data.keyword.compliance_short}} UI.

Running a scan against a specific profile does not ensure regulatory compliance. The scan is intended to provide a point in time statement of your current posture for a specific group of resources.
{: important}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Assess > Scans > Scheduled scans**. 
3. Click **Create**. A side panel opens.
4. Give your scan a name and description.
5. Select **Validation**.
6. Select a scope.
7. Select the profile that you want to use validate compliance.

   Be sure to select a profile that is applicable to your scope. For example, if you select an IBM scope but use an AWS profile to validate it, no results are returned as part of your scan.

8. Click **Next**.
9. If you selected an AWS or Azure scope, set your remediation preference.

   | Remediation type | Description |
   | --------- | ----------- |
   | None | There is no remediation configuration in place. |
   | Approved | The service must wait for approval from a user before the remediation is run. |
   | Automatic | The service runs remediation immediately. |
   {: caption="Table 2. Remediation types" caption-side="top"}

10. Select the frequency at which you want the scan to run.
11. Select when you want the scan to stop. Options include never, a specific number of scans, or on a set date.
12. Click **Create**.


## Running a fact validation scan
{: #run-fact-validation}

You can schedule a fact validation scan by using the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) > **Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Scopes**. 
3. Select the name of the scope that you want to scan.
4. Optional: From the history of scans, select the scan that you want to revalidate.
5. Click the **Validate** icon. 


## Running a scan on demand
{: #run-on-demand}

If you need to run a one-time scan on a specific scope, you can initiate it in the scope details page.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) > **Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Scopes**. 
3. Click the name of the scope that you want to scan.
4. From the **Actions** drop-down, select **Scan**.
5. Provide a name, select a scan type, and select a profile.
6. Click **Create**. The scan automatically starts.




