---

copyright:
  years: 2021
lastupdated: "2021-10-13"

keywords: available Network Insights finding types, Network Insights,

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

# Available Network Insights finding types
{: #network-insights-finding-types}

With Network Insights, you can monitor and analyze your VPC flow logs and identify potential attempts to compromise or compromised Virtual Server Instances.
{: shortdesc}


## Suspicious Outbound Traffic
{: #suspicious-outbound-traffic}



### Outbound approaches to suspicious servers
{: #outbound-approaches}

| Finding Type     | Severity         |  Description     |
|:-----------------|:-----------------|:-----------------|
| `xforce-anonym_server` | Medium | One of the services in your asset is approaching a server that appears to be concealing its identity behind anonymization services. This data is based on IBM threat intelligence. |
| `xforce-malware_server` | Medium | One of the services in your asset is approaching a suspicious server, suspected of distributing malware. |
| `xforce-bot_server` | Medium | One of the services in your asset is approaching a server suspected as a bot. |
| `xforce-miner_server` | Medium | One of the services in your asset is approaching a server suspected as mining cryptocurrency. |
| `xforce-server_suspected_ratio` | High | High % of approaches by a client to destinations with bad reputation. One of the clients in your asset is approaching network addresses considered suspicious suggesting that your asset may be compromised. |
| `xforce-server_response_multiple_ips` | High | Client approaches and communicate with multiple destinations with bad reputation. One of the clients in your asset is interacting with multiple external services considered suspicious. |
| `xforce-server_response` | High | One of the clients in your asset was observed interacting with a suspicious network destination (two-way communication observed). |
| `xforce-server_response_multiple_flows` | High | Client performs multiple interactions with network destinations that have bad reputation. One of the clients in your asset repeatedly interacting with a suspicious services. |
{: caption="Table 1. Finding Types that are referred in the Suspicious Outbound Traffic" caption-side="bottom"}

### Abnormally large payloads exchanged with suspicious servers
{: #abnormal-payloads}

| Finding Type     | Severity         |  Description     |
|:-----------------|:-----------------|:-----------------|
| `xforce-data_extrusion_multi` | High | Total volume sent to server peers with bad reputation exceed a threshold. One of the clients in your asset was observed sending large amount of data to destinations considered suspicious. |
| `xforce-data_extrusion` | High | Total volume sent to a server peer with bad reputation exceed a threshold. One of the clients in your asset was observed sending large amounts of data to a suspicious destination. |
| `xforce-server_weaponized_total_multi` | High | Total volume downloaded from suspected network addresses exceed a threshold. One of the clients in your asset was observed receiving large amount of data from suspected external services, which is indicative of Malware Installation. |
| `xforce-server_weaponized_total` | High | Total volume sent from a suspected external network address exceed a threshold. One of the clients in your asset was observed receiving large amounts of data from a suspicious service which may represent Malware Installation. |
{: caption="Table 1. Finding Types that are referred in the Suspicious Outbound Traffic" caption-side="bottom"}


## Suspicious Inbound Traffic
{: #suspicious-inbound-traffic}

### Reconnaissance by suspicious clients
{: #reconnaissance-client}

| Finding Type     | Severity         |  Description     |
|:-----------------|:-----------------|:-----------------|
| `xforce-client_multiple_flows` | Low | A peer with bad reputation is excessively approaching one or more closed port of your asset. An unexpectedly high number of approaches. |
| `xforce-clients_multiple_ips` | Low | Peers with bad reputation are excessively approaching one or more closed port of your asset. An unexpectedly high number of approaches. |
| `xforce-distributed_vulnerability_scan` | Medium | Excessive number of unique peers with bad reputation are approaching open ports of the asset and might be scanning for the asset vulnerabilities. |
| `xforce-reconnaissance_multi` | Low | Peers with bad reputation are excessively approaching unique closed ports (scanning). Your asset may be under reconnaissance by suspicious clients. |
| `xforce-vulnerability_scan` | Medium | A peer with bad reputation is excessively approaching open ports and might be scanning for asset vulnerabilities. |
| `xforce-reconnaissance` | Low  | A peer with bad reputation is excessively approaching unique closed ports of your asset (scanning). Your asset may be under reconnaissance by a suspicious client. |
| `xforce-client_response` | Low | Your asset was observed interacting with a suspicious client (two-way communication observed). |
{: caption="Table 2. Finding Types that are referred in the Suspicious Inbound Traffic" caption-side="bottom"}

### Abnormally large payloads sent by suspicious clients
{: #abnormal-payload-suspicious-client}

| Finding Type     | Severity         |  Description     |
|:-----------------|:-----------------|:-----------------|
| `xforce-client_weaponized` | Medium | A peer with bad reputation sends a large payload to your asset. Your asset was observed receiving large amount of data from a suspicious client which may represent an attempt to exploit your service. |
| `xforce-client_weaponized_total` | Medium | A peer with bad reputation sends accumulated large amount of data to your asset. Your asset was observed receiving large amounts of data from a suspicious client which may represent an attempt to exploit your service. |
{: caption="Table 2. Finding Types that are referred in the Suspicious Inbound Traffic" caption-side="bottom"}
