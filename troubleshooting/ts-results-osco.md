---

copyright:
  years: 2020, 2023
lastupdated: "2023-06-07"

keywords: support, help, stack overflow, slack, no results, scan error

subcollection: security-compliance

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why aren't my OpenShift clusters being scanned?
{: #ts-osco-results}
{: troubleshoot} 

You created a connection between the OpenShift Compliance Operator and the {{site.data.keyword.compliance_short}}, but your clusters are not being scanned.
{: tsSymptoms} 

There are a few reasons that this might happen:
{: tsCauses}

* Your scope does not contain any OpenShift clusters.
* The integration might not be enabled in your scan settings.

To resolve the issue:
{: tsResolve}

* Verify that your scope contains OpenShift clusters.
* Verify that the integration is enabled in your scan settings.
