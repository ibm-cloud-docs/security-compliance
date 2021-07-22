---
copyright:
  years: 2017, 2021
lastupdated: "2021-07-22"
keywords:
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


# What is Security Insights?
{: #insights}

With {{site.data.keyword.compliance_full}}, you can take advantage of built-in insights to analyze your user activity and network communication in order to identify unauthorized or suspicious behavior in your {{site.data.keyword.cloud_notm}} resources or applications.
{: shortdesc}


## What insights are available?
{: #available-insights}

You have the option to enable network or Activity Insights. Check out the following table to learn more.

| Feature          | Description |
|------------------|-------------|
| Activity Insights | By comparing user activity that is logged by {{site.data.keyword.at_short}} against predefined rule packages, you can identify suspicious behavior as it relates to your IBM Cloud resources, which can help to prevent malicious attacks on your applications. |
| Network Insights | By monitoring and analyzing your VPC flow logs, you can identify Virtual Server Instances that might be compromised or attempts to compromise your VSIs. |
{: caption="Table 1. Available Insights features" caption-side="top"}


## What classifies as suspicious activity?
{: #suspicious-activity}

When you enable Activity Insights, a group of predefined rules are automatically used to analyze the {{site.data.keyword.at_short}} data that is collected. The rules are used to detect situations where any behavior in your account is out of the ordinary. For example, user activity that has a significant security implication or security sensitive activity that is performed at an odd hour.


## What classifies as suspicious network traffic?
{: #suspicious-traffic}

The behavioral patterns of peers that are used as scanners, for mining cryptocurrency, as part of a botnet, for anonymization services, or have been found to distribute malware are continuously monitored by IBM X-Force. When you enable Network Insights, your VPC interface flow logs are analyzed for behavioral patterns and compared to the intelligence that is gathered by IBM X-Force to detect potentially compromised VSIs that run in your VPC. For example, if a VSI application sends an abnormally large payload to a peer that is flagged by the IBM X-Force threat intelligence database, a finding is issued. Additionally, any attempts to compromise a VSI are also reported. For example, if a peer that is flagged by IBM X-Force as suspicious repeatedly communicates with your VSI, a finding is issued.



## What is an insights rule?
{: #insights-rule-example}

A rule is a combination of conditions and an event that is used to analyze your logs for potential security findings. A condition is the combination of a `fact`, `operator`, and `value` that is bound together by using `any` or `all` operators. When a rule is broken, it's considered an event. When the event is reported to {{site.data.keyword.security-advisor_short}}, it is comprised of two fields: `type` and `params`.

Example rule:

```
{
    "comment": "Dormant Rule: Very high risk App ID  activity... ",
    "dormant": true,
    "conditions": {     … },
    "event": { … }
    "type": "aggregate"
}
```
{: screen}



## What services are rules available for?
{: #insights-rules-available}

Rule packages are available for the following services:

* {{site.data.keyword.containerlong_notm}}
* {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM)
* {{site.data.keyword.cloudcerts_long_notm}}
* {{site.data.keyword.appid_long_notm}}
* {{site.data.keyword.keymanagementservicelong_notm}}
* {{site.data.keyword.cos_full_notm}}

For more information about the rules in the predefined packages, see [Available Insights rules](/docs/security-compliance?topic=security-compliance-insights-rules).



## What kind of data is analyzed?
{: #collected-data}

The data that is collected by VPC flow logs and {{site.data.keyword.at_short}} is stored in a Cloud Object Storage bucket in order for analysis to occur. You own and control the collected data, which means that you're responsible for storing, securing, and deleting it. For more information about the security of your collected data, see [Securing your data in {{site.data.keyword.compliance_short}}](/docs/security-compliance?topic=security-compliance-mng-data).


Collected and analyzed VPC flow log information includes:

* The network protocols that are used
* IP addresses and ports of the communicating parties
* Data volumes
* Timestamps

Collected and analyzed Activity Tracker information includes:

* The IP address of the initiator of the API call
* The user that authenticated
* The activity type
* The activity result
* Timestamps

Because you own the data, you are responsible for ensuring that it is deleted in accordance with the legal requirements for your industry and your business. For more information, check out [Deleting objects](/docs/cloud-object-storage?topic=cloud-object-storage-security).
{: tip}


