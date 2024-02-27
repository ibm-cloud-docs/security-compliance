---

copyright:
  years: 2020, 2024
lastupdated: "2024-02-27"

keywords: responsibilities for {{site.data.keyword.compliance_short}}

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}

# Understanding your responsibilities when using {{site.data.keyword.compliance_short}}
{: #responsibilities}

Learn about the management responsibilities and terms and conditions that you have when you use {{site.data.keyword.compliance_full}}. For a high-level view of the service types in {{site.data.keyword.cloud_notm}} and the breakdown of responsibilities between the customer and {{site.data.keyword.IBM_notm}} for each type, see [Shared responsibilities for {{site.data.keyword.cloud_notm}} offerings](/docs/overview?topic=overview-shared-responsibilities).
{: shortdesc}

Review the following sections for the specific responsibilities for you and for {{site.data.keyword.IBM_notm}} when you use {{site.data.keyword.compliance_short}}. For the overall terms of use, see [{{site.data.keyword.cloud_notm}} Terms and Notices](/docs/overview?topic=overview-terms).

  
## Incident and operations management
{: #incident-and-ops}

Incident and operations management includes tasks such as monitoring, event management, high availability, problem determination, recovery, and full state backup and recovery.

|  | {{site.data.keyword.IBM_notm}} Responsibilities | Your Responsibilities |
|----------|-----------------------|--------|
| Ensuring high availability | Operate {{site.data.keyword.compliance_short}} in accordance with {{site.data.keyword.cloud_notm}} Public Service Level Agreements (SLAs). | Follow high availability best practices for Cloud Object Storage, including using cross regional or global buckets as needed |
| Monitor the system | Provide integration with select third-party partnership technologies, such as {{site.data.keyword.cloud_notm}} Activity Tracker. | Use the provided tools to review instance logs and activities. |
| Incident management | Provide notifications for planned maintenance, security bulletins, or unplanned outages.  | Set preferences to receive emails about platform notifications, and monitor the {{site.data.keyword.cloud_notm}} status page for general announcements. |
{: row-headers}
{: caption="Table 1. Responsibilities for incident and operations" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the task that the customer or IBM might be responsibility for. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}


## Change management
{: #change-management}

Change management includes tasks such as deployment, configuration, upgrades, patching, configuration changes, and deletion.

|  | {{site.data.keyword.IBM_notm}} Responsibilities | Your Responsibilities |
|----------|-----------------------|--------|
| Updates, fixes, and new features | IBM provides regular updates and bug fixes, as well as new features following a continuous delivery model in a manner transparent to the customer. | |
| Updates, fixes, or the delivery of new profiles | Release updates and new profiles in accordance with changing compliance requirements. Notify customers of changes made through release notes and change logs. | Review change logs to understand the updates and migrate to the new profile by creating new attachments. |
{: row-headers}
{: caption="Table 2. Responsibilities for change management" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the task that the customer or IBM might be responsibility for. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}


## Identity and access management
{: #iam-responsibilities}

Identity and access management includes tasks such as authentication, authorization, access control policies, and approving, granting, and revoking access.

|  | {{site.data.keyword.IBM_notm}} Responsibilities | Your Responsibilities |
|----------|-----------------------|--------|
| Restricting access | Provide the ability to control user access based on role. | Use Identity and Access Management (IAM) to assign access. |
{: row-headers}
{: caption="Table 3. Responsibilities for identity and access management" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the task that the customer or IBM might be responsibility for. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}

## Security and regulation compliance
{: #security-compliance}

Security and regulation compliance includes tasks such as security controls implementation and compliance certification.

|  | {{site.data.keyword.IBM_notm}} Responsibilities | Your Responsibilities |
|----------|-----------------------|--------|
| Meet security and compliance objectives | Provide a secure service that complies with key standards. For more information about data security, see [How do I know that my data is safe](/docs/overview?topic=overview-security)?  | Ensure that you are properly securing your workloads and data so that you are meeting the regulatory standards for your organization. For more information about bucket requirements for results storage, see [Storing and processing data](/docs/security-compliance?topic=security-compliance-storage). |
{: row-headers}
{: caption="Table 4. Responsibilities for security and regulation compliance" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the task that the customer or IBM might be responsibility for. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}

## Disaster recovery
{: #disaster-recovery}

Disaster recovery includes tasks such as providing dependencies on disaster recovery sites, provision disaster recovery environments, data and configuration backup, replicating data and configuration to the disaster recovery environment, and failover on disaster events.

|  | {{site.data.keyword.IBM_notm}} responsibilities | Your responsibilities |
|----------|-----------------------|--------|
| Back up of management and configuration data | Conduct backups of configurations such as attachments and scan settings. |  |
| Back up of scan results |  | Conduct backups of your Cloud Object Storage data according to best practices. |
| Recovery of configuration | Conduct recovery in the original region when availability is returned.  |  |
| Recovery of scan results |  | Conduct recovery of your Cloud Object Storage data according to best practices. |
{: row-headers}
{: caption="Table 5. Responsibilities for disaster recovery" caption-side="bottom"}
{: summary="The rows are read from left to right. The first column describes the task that the customer or IBM might be responsibility for. The second column describes {{site.data.keyword.IBM_notm}} responsibilities for that task. The third column describes your responsibilities as the customer for that task."}


