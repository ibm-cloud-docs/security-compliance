---

copyright:
  years: 2020, 2023
lastupdated: "2023-03-31"

keywords: support, help, stack overflow, slack, IP address is not permitted, managed collector, IP addresses

subcollection: security-compliance

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why am I blocked from scanning resources in my account?
{: #ip-address-not-permitted}
{: troubleshoot} 
{: support}

You schedule a scan of your resources, but the collector is unable to complete the task.
{: shortdesc}

When you run a scan, you encounter the following error:
{: tsSymptoms}

```json
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

