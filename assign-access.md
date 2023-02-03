---

copyright:
  years: 2020, 2023
lastupdated: "2023-02-01"

keywords: IAM access for {{site.data.keyword.compliance_short}}, permissions for {{site.data.keyword.compliance_short}}, identity and access management for {{site.data.keyword.compliance_short}}, roles for {{site.data.keyword.compliance_short}}, actions for {{site.data.keyword.compliance_short}}, assigning access for {{site.data.keyword.compliance_short}}

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


# Assigning access to {{site.data.keyword.compliance_short}}
{: #assign-roles}

As an account owner, you are automatically assigned Administrator platform access to the {{site.data.keyword.compliance_short}} so that you can further assign roles and customize access policies for others. 

1. [Create an access group](/docs/account?topic=account-groups#create_ag) for the type of users that you want to give access to and add those users to the group. For example, you might have a team of compliance specialists that need the same level of access.
2. After you create a group and add users, go to the **Manage > Access (IAM) > Access Groups** page of the console.
3. Select the name of the group that you want to assign access to.
4. Click **Access > Assign access**.
5. Select **{{site.data.keyword.compliance_short}}** as the **Service** and click **Next**.
6. Leave **All resources** selected and click **Next**.
7. Assign the appropriate level of access.
   
   To manage event notifications, you must select the `Administrator` role. To work with the updated architecture, you must also have `Editor` access to Cloud Object Storage. You must  To determine which permissions are needed to complete other actions, see [Managing IAM Access](/docs/security-compliance?topic=security-compliance-access-management&interface=ui#iam-roles).

8. Click **Add**.
9. Review your selections and click **Assign**.


