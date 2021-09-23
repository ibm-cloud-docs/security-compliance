---

copyright:
  years: 2017, 2021
lastupdated: "2021-09-22"

keywords: Centralized security, security management, alerts, security risk, insights, threat detection

subcollection: security-compliance

content-type: tutorial
account-plan: lite
completion-time: 30m

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

# Integrate custom findings
{: #integrate-nmap}
{: toc-content-type="tutorial"}
{: toc-completion-time="30m"}

With {{site.data.keyword.compliance_full}}, you can integrate your existing custom security tools to see all of your security information in one location. By completing this tutorial, you learn how to run an Nmap scan on your resources and display any findings that are flagged in {{site.data.keyword.compliance_short}}.
{: shortdesc}


## Understanding the example code
{: #nmap-code}

Before you get into the tutorial, let's take a minute to examine the sample code. Check out the following table to see what each file contains and why it's needed.

| Files      | Description |
|:-----------|:------------|
| `adapters` | Files that are related to the Findings API can be found in the `adapters` folder. The files help to generate the card and then record the findings in the dashboard. |
| `scanners` | Files that are related to any security scan that you run can be placed in a `scanners` folder. For this example, the scanner files are related to Nmap. The files in this folder also convert the findings to the appropriate format that can be consumed by the Findings API adapter. |
| `src` | Files that are related to the various commands and parameters that are required to be passed by the scanner. |
| `utils` | Files that are related to general utilities. `IAMClient.js` and `restClient.js` generate an access token that is used for authentication. `nmapScanner.js` starts the scan. You can replace the information in this file with your own custom tool. `logger.js` is a Winston logger for logging information that can help with debugging. |
{: caption="Table 1. Understanding the sample code" caption-side="top"}


## Before you begin
{: #nmap-before}

Before you get started, be sure that you have the following prerequisites installed and that you are assigned the **Manager** [IAM role](https://cloud.ibm.com/iam/users){: external} the account that you're using.

* [Nmap](https://nmap.org/download.html){: external}: The command for your custom tool must be available in the system's path. This tutorial uses `nmap`.
* [Node.js](https://nodejs.org/en/download/){: external}: The `node` command must be available in the system's path.


## Install sample code
{: #nmap-install}
{: step}

To get started with {{site.data.keyword.compliance_short}}, install the sample code.
{: shortdesc}

1. Clone the following repository to use Nmap as an example or clone the repository for your own third-party tool or service. 

   ```
   https://github.com/ibm-cloud-security/security-advisor-nmap-integration.git
   ```
   {: codeblock}

2. Change into the directory on your local system.
3. Install the dependencies that are needed to work with Nmap.

   ```
   npm install
   ```
   {: codeblock}


## Set your environment variables
{: #nmap-variables}
{: step}

In order for the executable to know where to display the findings, set your {{site.data.keyword.cloud_notm}} information as environment variables within the code.
{: shortdesc}

1. Find your account ID by navigating to **Manage > Account > Account Settings**. Your ID is listed in the account information.
2. Obtain an {{site.data.keyword.cloud_notm}} API key. For more information about IAM, see the [documentation](/docs/account?topic=account-access-getstarted).
   1. In the {{site.data.keyword.cloud_notm}} console, click **Manage > Access (IAM)**.
   2. Select **{{site.data.keyword.cloud_notm}} API keys**.
   3. Click **Create an {{site.data.keyword.cloud_notm}} API key**
   4. Give your key a name and describe it. Click **Create**. A screen displays with your key.
   5. Click **Copy** or **Download** your key. When you close the screen, you can no longer access the key.
3. Set the following variables by using the command line.

   ```
   export apiKey= <apiKey>
   export accountID= <accountID>
   export region= <region>
   ```
   {: codeblock}

  <table>
  <caption>Table 2. Understanding the commands variables</caption>
    <tr>
      <th>Variable</th>
      <th>Description</th>
    </tr>
    <tr>
      <td><code>apiKey</code></td>
      <td>The {{site.data.keyword.cloud_notm}} API Key that you obtained in step 1.</td>
    </tr>
    <tr>
      <td><code>accountID</code></td>
      <td>Your {{site.data.keyword.cloud_notm}} account ID that you obtained in step 2.</td>
    </tr>
    <tr>
      <td><code>region</code></td>
      <td>The location that the {{site.data.keyword.compliance_short}} is configured to use. For more information, see <a href="/docs/security-compliance?topic=security-compliance-mng-data">Storing and encrypting data in {{site.data.keyword.compliance_short}}</a>. </td>
    </tr>
  </table>



## Generate findings
{: #nmap-generate}
{: step}

To generate findings, you must first define the card and format the results. Then, you can run the scan.
{: shortdesc}


### Define the dashboard card
{: #nmap-define-card}

For this demo, the card values are predefined as shown in the following code example. If you want, you can edit them by opening the `src > adapters > findingsApi > config.js` file and updating the values.

Example values:

```
"sectionName": 'Network',
"cardId" : 'network-scan-nmap-Card',
"cardTitle" : 'Port Discovery',
```
{: screen}

If you make a change, be sure to run the scan with the `--updateDashboardCard` set to yes. 
{: note}


### Format the results
{: #nmap-format}

When you run the service, in this case the Nmap scan, the findings can be returned in different forms. To display your findings in the dashboard, you must modify the scan results to match the format that is required by the Findings API. For example, the results that Nmap returns are shown as a string: `Port10(open)response10ms:`. In order to show in the dashboard, the Findings API accepts the results as: `Findingname(), prioritylevel()`. To see an example of reformatting, check out the scanners folder in the GitHub source repository.


### Run the scan
{: #nmap-scan}

To generate findings, you can run the following utility command from the root directory of the repository.

For Windows:

```
node ./src/app.js <scan_type> -t 'IPv4 address'
```
{: codeblock}

For macOS and UNIX systems, append command with `sudo -E`:

```
sudo -E node ./src/app.js <scan_type> -t 'IPv4 address' --updateDashboardCard 'yes'
```
{: codeblock}

| Scan type | Description | 
|:-----------------|:-----------------|
| `allNetworkLayersScan` | Scan all of the network layers.  |
| `applicationLayerScan` | Scan only the application layer. |
| `transportLayerScan` | Scan only the transport layer. |
| `networkLayerScan` | Scan only the network layer. |
| `dataLinkLayerScan` | Scan only the data link layer. |
{: class="simple-tab-table"}
{: caption="Table 3. Understanding scan types" caption-side="top"}
{: #nmap1}
{: tab-title="Scan type"}
{: tab-group="run-scan"}

| Options | Description | 
|:-----------------|:-----------------|
| `-t` | The target IP or hostnames. |
| `-p` | The port range that you want to scan. The default is to scan all ports. |
| `--excludePorts` | The port or range of ports that you want to exclude from the scan. |
| `--updateDashboardCard` | The type of resource. |
{: class="simple-tab-table"}
{: caption="Table 3. Understanding the command's components" caption-side="top"}
{: #nmap2}
{: tab-title="Options"}
{: tab-group="run-scan"}

IPV6 and IP ranges are not currently supported.
{: note}


## (Optional): Delete the card
{: #nmap-remove}
{: step}

The scan alerts are visible in the service dashboard cards for 24 hours after which they can be found in the Findings table. If you run the scan again within the initial 24 hours of the first scan, and the same findings are found, they are still added in the card. For example, if you run the scan and find an open port 22/SSH the KPI in the card shows as 1. If you run the scan again without fixing the existing vulnerability, the same finding is added to the KPI and the value is now 2. So, if you need to run the scan again within 24 hours and want to see only the latest vulnerabilities, clear the findings in the card by using the [Findings API](/apidocs/security-compliance/findings){: external}.
{: shortdesc}

If you no longer have a need to see findings from Nmap in your dashboard, you can delete the card that displays the information.

```
node ./src/app.js deleteCard
```
{: codeblock}

Ready to start integrating your own security tools? Check out the [custom findings documentation](/docs/security-compliance?topic=security-compliance-setup_custom).
{: tip}
