---

copyright:
  years: 2020
lastupdated: "2020-09-21"

keywords: support, help, stack overflow, slack, no results, scan error

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

# Troubleshooting {{site.data.keyword.compliance_short}}
{: #gettinghelp}

General problems with using {{site.data.keyword.compliance_full}} might include not being able to view details about your current posture from your {{site.data.keyword.compliance_short}} dashboard. In many cases, you can recover from the problem by following a few steps.
{: shortdesc}

## I need to contact support
{: #contact-support}

If you encounter an issue that you cannot fix while you work with the {{site.data.keyword.compliance_short}} dashboard, contact the [IBM Cloud support team](https://www.ibm.com/cloud/support){: external}.

If you're opening a support ticket for the security and compliance posture monitoring portion of the service, be sure that you include your cluster logs. To obtain your cluster logs, you can use the following steps:

1. Log in to the collector.
2. Run the following command to package your logs.

  ```
  docker ps
  docker exec -it <collector_name> bash
  zip /opt/data/collector_log.zip /var/log/*.log
  ```
  {: codeblock}

3. Navigate to the installation path on your host machine to find the `collector_log.zip` file.

  ```
  Eg :  ls /home/ubuntu/<collector_folder>/collector_log.zip
  ```
  {: codeblock}


## I don't see any evaluation results
{: #ts-enforce}
{: troubleshoot} 
{: support}

{: tsSymptoms}
You created a rule, but no results are displayed in your dashboard.

{: tsCauses}
You might not be able to view results for the following reasons:

* Your rule isn't attached to a scope.
* The scan hasn't run yet.
* There was an error with the scan.

{: tsResolve}
Depending on the reason that the results page is empty, you might try one or more of the following options to resolve the issue.

* Verify that your [rule](/docs/security-compliance?topic=security-compliance-rules#evaluate-rules) is attached to a scope.
* Wait 24 hours for the next scan to run.



## I deleted a resource but I can still see its results
{: #deleted-results}
{: troubleshoot} 
{: support}

{: tsSymptoms}
You deleted a resource, but you're still seeing results for it in your dashboard.

{: tsCauses}
Results are maintained and displayed in the UI for 7 days, even when a resource is deleted.

{: tsResolve}
Wait 7 days. The data is deleted without action on your behalf.


## My scan failed
{: #credentials-unavailable}
{: troubleshoot} 
{: support}

{: tsSymptoms}
You ran a scan and the scan returned the following error:

```
credentials unavailable
```
{: screen}

{: tsCauses}
When a collector cannot find the credentials that are needed to run a scan, the scan fails.

{: tsResolve}
Ensure that your credentials are correctly [mapped to your scope](/docs/security-compliance?topic=security-compliance-credentials#map-credentials).



## My collector is inactive
{: #collector-inactive}
{: troubleshoot} 
{: support}

{: tsSymptoms}
On the **Collectors** page of the {{site.data.keyword.compliance_short}}, you see that one of your collectors is showing a status of **Inactive**.

{: tsCauses}
A collector is shown as inactive when it is unable to communicate with the {{site.data.keyword.compliance_short}}. 

{: tsResolve}
To resolve the issue, you might take one or more of the following actions:

* Verify that the collector is installed, registered, and approved. 
* If it is installed correctly, restart the collector by running the following Docker command.

  ```
  docker start <container_name>
  ```
  {: codeblock}


