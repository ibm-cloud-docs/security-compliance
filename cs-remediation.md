---

copyright:
  years: 2020, 2023
lastupdated: "2023-03-31"

keywords: remediation, aws, compliance, security, 

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Remediating issues
{: #remediation}

If you're working with an Amazon Web Services, Microsoft Azure, or Google Cloud Platform account, you can use the {{site.data.keyword.compliance_full}} to remediate issues that are found.
{: shortdesc}


The collector-based architecture is deprecated. For more information, see the [release notes](/docs/security-compliance?topic=security-compliance-releases).
{: deprecated}



## Before you begin
{: #before-remediation}

Before you get started, be sure that you have the required level of access to remediate potential issues. To remediate issues, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management). The credentials that you provide for remediation must also have the appropriate permissions for the resources that you want to remediate.

Remediation is available for Amazon Web Services, Microsoft Azure, and Google Cloud Platform only. To remediate issues through {{site.data.keyword.compliance_short}}, you must have a scan that is targeted to scan your AWS or Azure resources.
{: note}


## Running remediation
{: #run-remediation} 

You can use the {{site.data.keyword.compliance_short}} UI to get the remediation scripts that you can run to fix issues as they're found.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Hybrid cloud results > Remediation**. 
3. In the **Remediation** table, select the issue that you want to remediate.
4. If the screen shows **Pending input**, click the **User inputs** edit icon.
5. In the configuration inputs page, enter the values for the fields that are displayed. Options vary depending on the issue that is flagged.
6. Click **Save**. 
   1. If automatic remediation is in place, the status is set to **Ready to fix** or **Processing**, which indicates that the job is waiting in the queue to run.
   2. If the screen shows **Pending approval**, the script is ready to be run. Click the run icon. Remediation is initiated.

