---

copyright:
  years: 2021
lastupdated: "2021-09-27"

keywords: custom profiles, user-defined, controls, goals, security, compliance

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


# Building custom profiles
{: #custom-profiles}

With the {{site.data.keyword.compliance_full}}, you can create your own profiles or take advantage of predefined profiles that are curated based on industry standards.
{: shortdesc}

When you build a custom profile, you can choose a combination of controls and goals to validate that your resources are compliant with internal and external regulations. You can create a profile by using a predefined profile as a base. Or, you can create a profile from scratch by selecting from a list of available goals that you want to meet.

To learn more about profiles, see [What is a profile?](/docs/security-compliance?topic=security-compliance-profiles).


## Before you begin
{: #before-custom-profiles}

Before you get started, be sure that you have the required level of access to view and manage profiles. To manage profiles, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).


## Creating profiles in the UI
{: #create-profile-ui}
{: ui}

### Building profiles from a predefined profile
{: #build-profile-from-predefined-profile-ui}

You can choose to create a profile by using another predefined profile as a base. To build a profile, you can use the UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Profiles**. 
3. Click **Create**.
4. Give your profile a name and description.
5. Click **Next**.
6. Click the **Start from a predefined profile** tile.
7. Select a predefined profile to use as a base.
8. Review the controls and goals for the selected profile and check the corresponding box for the goals that you want to include.
9.  Click **Next**.
10. Review your selections, and click **Create**.
    
After you create your profile, you can choose to edit or export it by clicking its table row in the {{site.data.keyword.compliance_short}} UI. From your list of profiles, use the **Custom** filter to search for custom profiles in your account. If you no longer need to use a custom profile, you can choose to remove it. After you delete a profile, it cannot be used in future scans.

### Creating profiles from scratch
{: #create-profile-from-scratch-ui}

If you know the controls and goals that you want to meet, you can create a profile that is specific to your needs from scratch.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Profiles**. 
3. Click **Create**.
4. Give your profile a name and description.
5. Click the **Start from scratch** tile.
6. Create your first grouping by providing a **Control description**.

   Be sure to provide a meaningful description that summarizes your custom control group or family. For example, if you're creating a grouping that includes access-related controls, you can describe your control as _Access Control_.

7. Click the **Goal ID** box.
8. Select one or more goals that you want to add to your control.

   Not sure which goals to include? Use the search bar to filter the list of available goals by description or keyword. You can also use the Goals page in the {{site.data.keyword.compliance_short}} UI to search for and view information about available goals. If you accidentally add a control that you don't need, you can click the **Trash** icon to delete it or the **Edit** icon to edit your profile.

9. Click **Done**.
10. Click the **Save** icon.
11. Repeat the steps until you have the profile configuration that you want.
12. Click **Next**.
13. Review your selections, and click **Create**.



## Editing profiles locally
{: #edit-profile-locally}
{: ui}

If you prefer to work with profiles in a CSV format, you can export a profile and make changes locally. Then, you can import the profile to the {{site.data.keyword.compliance_short}} to start validating scopes.

As a compliance focal, you might also choose to export profiles with specific configurations that you want to ensure are used by every member of your team. Be sure to have each member of your team import the same version of the profile to ensure consistency across individual accounts as well as team accounts.

### Exporting a profile
{: #export-profile}

To export a profile, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Profiles**. 
3. From the list of profiles, select the profile that you want to export.
4. Click the **Export profile** icon.

### Formatting your CSV file
{: #CSV-format}

When you're working with profiles locally, it's important that you stay within the format parameters so that the service is able to parse the information that you import. For example, if you were working with NIST controls, your CSV file would look similar to the following image.

![This image shows an example of how your CSV file might be formatted when you work with profiles locally. The information in the image is explained in further detail in the surrounding text.](images/csv-nist.svg){: caption="Figure 2. CSV formatting" caption-side="bottom"}

External Control ID and Parent
:   An external ID is used along with the parent to structure how a control tree is shown in the UI when the file is imported. Be sure that you use a sequential pattern for your external control ID and that the parent is mapped to the correct level.

Goal ID
:   Goal IDs are provided by the {{site.data.keyword.compliance_short}}. To find the goal ID, you must log in to the console and go to **Security and compliance > Configure > Goals**.

Tags
:   For more information about tags, see [Mapping tags](/docs/security-compliance?topic=security-compliance-tags).


### Importing a profile
{: #import-profile}

To import a profile, you can use the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Configure > Profiles**. 
3. Click the **Import profile** icon.
4. Upload the CSV version of the profile that you want to import.
5. Click **Submit**.


