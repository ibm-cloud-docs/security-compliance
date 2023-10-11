---

copyright:
  years: 2020, 2023
lastupdated: "2023-10-11"

keywords: support, help, stack overflow, slack, no results, scan error

subcollection: security-compliance

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# I can't view my resources
{: #ts-results-cbr}
{: troubleshoot} 

You are unablet to view a resource from the UI.

You set a Context-Based Restriction for a service to use private endpoints in order to gain compliance to a profile but are unable to view that resource from the UI.
{: tsSymptoms} 

There are a few reasons that you 
{: tsCauses}

* Your scope does not contain any OpenShift clusters.
* You're not using the correct profile. 

To resolve the issue:
{: tsResolve}

* Verify that your scope contains OpenShift clusters.
* Ensure that you selected the {{site.data.keyword.cloud_notm}} OpenShift Kubernetes OCP4 profile.

