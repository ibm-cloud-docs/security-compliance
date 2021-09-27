---

copyright:
  years: 2021
lastupdated: "2021-09-27"

keywords: support, help, stack overflow, slack, IP address is not permitted, managed collector, IP addresses

subcollection: security-compliance

content-type: troubleshoot

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

# Why am I blocked from scanning resources in my account?
{: #ip-address-not-permitted}
{: troubleshoot} 
{: support}

You schedule a scan of your resources, but the collector is unable to complete the task.
{: shortdesc}

When you run a scan, you encounter the following error:
{: tsSymptoms}

```
Collector aborted the task. Reason: Discovery: {'Error': 'User login from given IP address is not permitted.'}
```
{: screen}

This error can occur when the account that you want to scan restricts access to specific IP addresses. To allow a managed collector to collect data in the account, you must specify a required list of IP addresses, along with your own IP address.
{: tsCauses}

To resolve the issue, ensure that the IP address restriction settings in the account are updated to allow the IP addresses that correspond with your location.
{: tsResolve}

| Location | IP addresses |
| --- | --- |
| United States | `150.239.179.224/27`, `52.116.28.0/27`, `169.62.230.48/28`, `52.116.224.64/28`, `169.46.94.0/28`, `150.238.252.224/27` |
| European Union | `158.177.77.112/28`, `159.122.112.96/27`, `161.156.11.32/27`, `161.156.18.0/28`, `149.81.148.224/28`, `149.81.181.224/27`, `149.81.131.192/28`, `158.177.244.192/28`, `161.156.178.96/28` |
{: caption="Table 1. IP addresses for IBM managed collectors" caption-side="top"}

To learn more about updating your IP address settings, see [Allowing specific IP addresses for an account](/docs/account?topic=account-ips#ips_account).

