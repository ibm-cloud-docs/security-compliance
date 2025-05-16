---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: support, help, stack overflow, slack, no results, scan error

subcollection: security-compliance

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why aren't my Red Hat OpenShift clusters being scanned?
{: #ts-osco-results}
{: troubleshoot} 



As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the replacement service {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}



Your clusters are not being scanned.
{: tsSymptoms} 

A few reasons for your clusters not being scanned include:
{: tsCauses}

* Your scope does not contain any Red Hat OpenShift clusters.
* You're not using the correct profile. 

To resolve the issue:
{: tsResolve}

* Verify that your scope contains Red Hat OpenShift clusters.
* Ensure that you selected the {{site.data.keyword.cloud_notm}} Red Hat OpenShift Kubernetes OCP4 profile.
