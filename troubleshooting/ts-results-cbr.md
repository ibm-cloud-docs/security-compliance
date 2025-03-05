---

copyright:
  years: 2020, 2025
lastupdated: "2025-03-03"

keywords: support, help, stack overflow, slack, no results, scan error

subcollection: security-compliance

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# I can't view the resources that are flagged as noncompliant
{: #ts-results-unable-to-view}
{: troubleshoot} 

You're unable to access a resource from the console.


When a resource is flagged as noncompliant, you attempt to go fix it. When you click the resource from the resource list page in the console, you receive an error message that says `Access denied`.
{: tsSymptoms} 

A few reasons that you might receive this error include:
{: tsCauses}

* You do not have the proper access to view the resource.
* Your account has a Context-based restriction that specifies that the service or resource can be accessed only through private endpoints. 

To resolve the issue:
{: tsResolve}

* Verify that you have the correct permissions.
* Update your Context-based restriction rule to include your IP address.
