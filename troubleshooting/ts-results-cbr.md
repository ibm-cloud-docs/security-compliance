---

copyright:
  years: 2020, 2023
lastupdated: "2023-10-17"

keywords: support, help, stack overflow, slack, no results, scan error

subcollection: security-compliance

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# I can't view the resources that are flagged as noncompliant
{: #ts-results-unable-to-view}
{: troubleshoot} 

You're unable to access a resource from the console.


When a resource has been flagged as noncompliant, you attempt to go fix it. When you click on the resource from the resource list page in the console, you receive an error message that says `Access denied`.
{: tsSymptoms} 

There are a few reasons that you might receive this error.
{: tsCauses}

* You do not have the proper access to view the resource.
* Your account has a Context-based restriction that specifies that the service or resource can only be accessed through private endpoints. 

To resolve the issue:
{: tsResolve}

* Verify that you have the correct permissions.
* Update your Context-based restriction rule to include your IP address.
