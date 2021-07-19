---

copyright:
  years: 2021
lastupdated: "2021-07-19"

keywords: profiles, user-defined, predefined profiles, controls, goals, nist, best practices, security, compliance

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


# Working with profiles
{: #profiles}

With the {{site.data.keyword.compliance_full}}, you can create your own profiles or take advantage of predefined profiles that are curated based on industry standards.
{: shortdesc}


## Understanding profiles
{: #understand-profiles}

A profile is a collection of related goals, or security checks, are used to validate that your resources are compliant with internal and external regulations. The {{site.data.keyword.compliance_short}} maps goals to external regulatory libraries of controls, divided into families (groups), that are used to prove that you are compliant with the required standards for your industry. Each control can apply to one or more profiles and there might be one or more goals required to be fully compliant with each control. To see how control libraries map to goals, check out the following image. 


![Profile layout shown in diagram format. The information shown in the image is described in the surrounding text.](/images/profiles.svg){: caption="Figure 1. Understanding profiles" caption-side="bottom"}

When you work with {{site.data.keyword.cloud_notm}}, several goals are met by default. To learn more about what makes {{site.data.keyword.cloud_notm}} secure by default, see [Available default goals](/docs/security-compliance?topic=security-compliance-default-goals).
{: tip}


## Before you begin
{: before-profiles}

Before you get started, be sure that you have the required level of access to view and manage profiles. To manage profiles, you need the editor platform role or higher. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).


## Viewing profiles
{: #view-profiles}

You can view the profiles that are associated with your account in the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Profiles**. 

  From the list of available profiles, you can see whether a profile is predefined or custom by checking the **Category** column. You can also view the number of controls that each profile contains.

3. To view the controls that are associated with the profile, click the row of the table that you want to investigate.
4. To view the goals that are associated with the controls, click the control that you want to review. A screen opens with goal details.



## Building a profile
{: #build-profile}

You can choose to create a profile by using other predefined profiles as a base. To build a profile, you can use the UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Profiles**. 
3. Click the **Build profile** icon.
4. Give your profile a name and description.
5. Click **Next**.
6. Select a predefined profile to use as a base.
7. Click **next**.
7. Review the controls and goals from those profiles and check the corresponding box for the goals that you want to include.
8. Click **Save**.


## Creating a profile
{: #create-profile}

If you know the controls and goals that you want to meet, you can create a profile that is specific to your needs from scratch.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Profiles**. 
3. Click **Create**.
4. Give your profile a name and description.
5. Create your first grouping by providing a **Control description**.
6. Click the **GCL ID** box.
7. Select one or more goals that you want to add to your control. 
8. Click **Done**.
9. Click the **Save** icon.
10. Repeat the steps until you have the profile configuration that you want.
11. Click **Create**.

If you accidentally add a control that you don't need, you can click the **Trash** icon to delete it or the **Edit** icon to edit your profile.
{: tip}



## Editing a profile in the UI
{: #edit-profile}

If you create a custom profile, you can edit it if the need arises by using the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Profiles**. 
3. From the list of profiles, select the profile that you want to edit.
4. Click the **Edit** symbol.
5. Update the details, controls, or goals associated with your profile.
6. Click **Update**.


## Editing profiles locally
{: #editing-profile locally}

If you prefer to edit profiles in a CSV format, you can export a profile and make changes locally. Then, you can import the profile to the {{site.data.keyword.compliance_short}} to start validating scopes.

As a compliance focal, you might also choose to export profiles with specific configurations that you want to ensure are used by every member of your team. Be sure to have each member of your team import the same version of the profile to ensure consistency across individual accounts as well as team accounts.

### Formatting your CSV
{: #CSV-format}

When you're working with profiles locally, it's important that you stay within the format parameters so that the service is able to parse the information that you import. For example, if you were working with NIST controls, your CSV file would look similar to the following image.

![This image shows an example of how your CSV file might be formatted when you work with profiles locally. The information in the image is explained in further detail in the surrounding text.](images/csv-nist.svg){: caption="Figure 2. CSV formatting" caption-side="bottom"}

<dl>
  <dt> External Control ID and Parent </dt>
    <dd> An external ID is used along with the parent to structure how a control tree is shown in the UI when the file is imported. Be sure that you use a sequential pattern for your external control ID and that the parent is mapped to the correct level. </dd>
   <dt> Goal ID </dt>
    <dd> Goal IDs are provided by the {{site.data.keyword.compliance_short}}. To find the goal ID, you must log in to the console and go to <strong>Security and compliance > Configure > Goals</strong>.</dd>
  <dt> Tags </dt>
    <dd> For more information about tags, see [Mapping tags](/docs/security-compliance?topic=security-compliance-tags). </dd>
</dl>



### Importing a profile
{: #import-profile}

To import a profile, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Profiles**. 
3. Click the **Import profile** icon.
4. Upload the CSV version of the profile that you want to import.
5. Click **Submit**.


### Exporting a profile
{: #export-profile}

To export a profile, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Profiles**. 
3. From the list of profiles, select the profile that you want to export.
4. Click the **Export profile** icon.


## Deleting a profile
{: #delete-profile}

If you no longer need to use a custom profile, you can choose to remove it from your list of profiles by using the {{site.data.keyword.compliance_short}} UI. The profile is moved to a deleted section to ensure that previous scans are able to be properly rendered. But, it cannot be used in future scans.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Profiles**.
3. From the list of profiles, select the profile that you want to delete.
4. Click the **Trash** icon.
5. Confirm that you want to delete the profile by clicking **Delete**.
6. Optional: To see deleted profiles, click the **Overflow** icon and select **Show deleted profiles**.
