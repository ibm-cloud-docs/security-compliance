---

copyright:
  years: 2020, 2023
lastupdated: "2023-03-29"

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
{:release-note: data-hd-content-type='release-note'}


# Running a scan
{: #schedule-scan}

When you're working with {{site.data.keyword.compliance_full}}, you can run scans that determine resource availability, resource configuration, and a resource's adherence to regulatory controls as defined in a profile.
{: shortdesc}

The collector-based architecture is deprecated. For more information, see the [release notes](/docs/security-compliance?topic=security-compliance-releases).
{: deprecated}

## Before you begin
{: #before-scans}

Before you get started, be sure that you have the required level of access to view and schedule scans. To schedule scans, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).


## Understanding scan types
{: #scan-types}

Depending on what you're trying to accomplish, you might run different types of scans. Check out the following table to learn more about types of scans and when to run each type.

| Scan type | Description |
|:----------|:------------|
| Discovery | A scope is often defined at the highest level and includes one or more resource groups. When a discovery scan is run, a list of all the available resources in a scope is returned. |
| Fact collection | When you collect facts, you're collecting the configuration information of the resources that were found during discovery. If any new resource configurations are found, then the scope is updated to include them. |
| Validation | Validation scans determine a specified scope's adherence to regulatory controls by creating an attachment between that scope and profile. When a validation scan is run, the service also runs a fact collection scan before the validation occurs. |
| Fact validation | Fact validation is run on previously collected facts. You might run a fact validation to determine whether previous configurations meet your current profile requirements. |
{: caption="Table 1. Types of scans" caption-side="top"}



### Configuring scanning for VMs
{: #vm-prereqs}

If you're attempting to configure fact collection for cloud-based infrastructure, you must complete the following steps before you schedule your scan.

Scanning for {{site.data.keyword.cloud_notm}} classic infrastructure is not available.
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

To check to see whether the computer has `WinRM` enabled, check whether the HTTPS listener is ready by running the following command in a PowerShell window: `dir wsman:\localhost\listener`.

1. Enable WinRM Remoting.

   ```sh
   Enable-PSRemoting -SkipNetworkProfileCheck -Force
   ```
   {: codeblock}

2. Set up your certificates and enable your HTTPS listener.

   ```sh
   $myhost=(Get-WmiObject win32_computersystem).DNSHostName+"."+ (Get-WmiObject win32_computersystem).Domain

   $Cert = New-SelfSignedCertificate -CertstoreLocation Cert:\LocalMachine\My -DnsName $myhost

   New-Item -Path WSMan:\LocalHost\Listener -Transport HTTPS -Address * -CertificateThumbPrint $Cert.Thumbprint -Force
   ```
   {: codeblock}

3. Enable your Windows server firewall to allow for incoming communication.

   ```sh
   New-NetFirewallRule -DisplayName "Windows Remote Management (HTTPS-In)" -Name "Windows Remote Management (HTTPS-In)" -Profile Any -LocalPort 5986 -Protocol TCP
   ```
   {: codeblock}

4. Ensure that basic authentication is set to true.

   ```sh
   winrm set winrm/config/Service/Auth '@{Basic="True"}'
   ```
   {: codeblock}

5. Validate that your configuration and network connection are running correctly.

   ```sh
   winrm get winrm/config -NetConnectionProfile
   ```
   {: codeblock}


## Scheduling a scan
{: #run-scan}

You can use the {{site.data.keyword.compliance_short}} UI to schedule a scan.

The easiest way to schedule a scan is to do it when you create your scope.
{: tip}

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Hybrid cloud configurations > Scans > Schedule**. A side panel opens.
3. Give your scan a name and optionally provide a description.
4. Select the type of scan that you want to initiate from the following options.

   * Validation: Evaluate the compliance of your resource configurations by creating an attachment between an existing scope and profile.
   * Fact collection: Gather resource configuration information for a specific scope, but don't perform an evaluation.
   * Discovery: Discover the resources that are available in a specific scope.

5. Select a scope that exists in your account from the drop-down.
6. If you selected **Validation** in step 4, choose a profile to use for validation.

   Be sure to select a profile that is applicable to your scope. For example, if you select an IBM scope but use an AWS profile to validate it, no results are returned as part of your scan.
   {: tip}

7. If you selected an {{site.data.keyword.cloud_notm}} profile, enable **Integrations** to ensure that any resources that are connected through an integration is included in the evaluation.
8. Click **Next**.
9. Set the schedule by providing the frequency at which you want the scan to run and when you want the scan to stop.
10. Click **Create**.


## Running a scan on demand
{: #run-on-demand}

If you need to run a one-time scan on a specific scope, you can initiate it from the scope details page in the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Hybrid cloud configurations > Scopes**. 
3. Click the name of the scope that you want to scan. A details page opens for your selected scope.
4. From the **Actions** drop-down, select **on demand scan**.
5. Select the type of scan that you want to initiate from the following options.

   * Validation: Evaluate the compliance of your resource configurations by creating an attachment between an existing scope and profile.
   * Fact collection: Gather resource configuration information for a specific scope, but don't perform an evaluation.
   * Discovery: Discover the resources that are available in a specific scope.

6. If you selected **Validation** in step 4, choose a profile to use for validation.

   Be sure to select a profile that is applicable to your scope. For example, if you select an IBM scope but use an AWS profile to validate it, no results are returned as part of your scan.
   {: tip}
7. Click **Create**. The scan automatically starts.

