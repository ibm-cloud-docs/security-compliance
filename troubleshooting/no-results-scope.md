---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: support, help, stack overflow, slack, no results, scan error

subcollection: security-compliance

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why can't I see results for a particular scope?
{: #ts-results-scope}
{: troubleshoot}
{: support}


As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the replacement service {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


You can't find results for a specific scope or subscope.
{: shortdesc}


You have access to a scope or subscope but are unable to see the results of an evaluation.
{: tsSymptoms}

You might not be able to view the results for the following reasons:
{: tsCauses}

* Your attachment hasn't been evaluated yet.
* Any scans that were generated before the segmentation feature was released are not able to be viewed in the same way.
* Your permissions are not assigned correctly.
* An error occurred during the scan.

Depending on the reason, you might try one or more of the following options to resolve the issue.
{: tsResolve}

* Verify that the attachment was evaluated.
* Verify the age of the scope. Any scope created before 13 August 2024 will not be able to be segmented.
* Contact your account administrator to verify that your IDs were added correctly when permissions were assigned.
* Wait 24 hours for the next scan to run, or open a support ticket.
