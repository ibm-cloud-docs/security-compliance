---

copyright:
  years: 2020, 2023
lastupdated: "2023-08-29"

keywords: custom profiles, user-defined, controls, goals, security, compliance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Creating custom control libraries
{: #custom-library}

With {{site.data.keyword.compliance_full}}, you can create a custom control library that is specific to your organization's needs. You define the controls and specifications before you map previously created assessments.
{: shortdesc}

![The diagram shows the layout of a control library. The information is conveyed in the surrounding text.](images/control-library.svg){: caption="Figure 1. Understanding control libraries" caption-side="bottom"}


A control library is a grouping of controls that are added to {{site.data.keyword.compliance_short}}. The service offers several predefined libraries that are designed to help meet compliance for a specific use case. Each control has several specifications and assessments that are mapped to it. A specification is a defined requirement that is specific to a component. When met by an organization, the specification helps to ensure that they are compliant with the control. An assessment, or several, are mapped to each specification with a detailed evaluation that is done to check whether the specification is compliant. For more information, see [Key Concepts](/docs/security-compliance?topic=security-compliance-posture-management).


## Before you begin
{: #before-custom-library}

Before you get started, be sure that you have the required level of access to create and manage libraries. To manage libraries, you need the [**Editor** platform role or higher](/docs/security-compliance?topic=security-compliance-access-management).


## Creating a library
{: #create-custom-library-ui}
{: ui}

You can create a custom library by using the {{site.data.keyword.compliance_short}} UI.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access the {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Controls > Control libraries**. 
3. Click **Create**. A side panel opens.
4. Provide a name, description, and version for your library.
5. Click **Create**. Your library opens in a new page but is empty.
6. To start adding controls, click **Create**.
	1. Provide the details for your control by including a **Name**, **Description**, and **Category**.
	2. Click **Add** to start adding existing specifications to your control.
	3. Provide a **Description** for your specification.
	4. Select a **Component**.
	5. Select the existing assessments that can help to evaluate your specification, then click **Create**.

	If you don't see an assessment that is specific to your use case, you can create a rule. When the rule is created, it shows in the assessment section.
	{: tip}

	6. When you are finished adding specifications to your control, click **Create**.
	7. Repeat these steps until you add all your controls.


## Creating a library with the API
{: #create-custom-library-api}
{: api}

You can create a custom library by using the {{site.data.keyword.compliance_short}} API.

```bash
curl -X POST 
	--location --header "Authorization: Bearer {iam_token}" 
	--header "Accept: application/json" 
	--header "Content-Type: application/json" 
	--data '{ 
				"id": "60351ac6-2dba-495e-9c98-057601069723", 
				"account_id": "cg3335893hh1428692d6747cf300yeb5", 
				"control_library_name": "IBM Cloud for Financial Services", 
				"control_library_description": "IBM Cloud for Financial Services", 
				"control_library_type": "predefined", 
				"version_group_label": "33fc7b80-0fa5-4f16-bbba-1f293f660f0d", 
				"control_library_version": "1.1.0", 
				"controls": [ { "control_name": "SC-7", 
				"control_id": "1fa45e17-9322-4e6c-bbd6-1c51db08e790", 
				"control_description": "Boundary Protection", 
				"control_category": "System and Communications Protection", 
				"control_parent": "", "control_requirement": false, 
				"control_tags": [ 
					"1fa45e17-9322-4e6c-bbd6-1c51db08e790" 
					], 
				"control_specifications_count": 0, 
				"control_specifications": [
					 {
						"control_specification_id": "5c7d6f88-a92f-4734-9b49-bd22b0900184", 
						"responsibility": "user", 
						"component_id": "iam-identity", 
						"component_name": "IAM Identity Service", 
						"environment": "ibm-cloud", 
						"control_specification_description": "IBM cloud", 
						"assessments_count": 0 
						} 
					], 
				"control_docs": { 
					"control_docs_id": "sc-7", 
					"control_docs_type": "ibm-cloud" 
					} 
				} 
			] 
		}' 
	"https://us-south.compliance.cloud.ibm.com/instances/{instance_id}/v3/control_libraries"
```
{: pre}
{: curl}



```go
(securityAndComplianceCenterApi *SecurityAndComplianceCenterApiV3) CreateCustomControlLibrary(createCustomControlLibraryOptions *CreateCustomControlLibraryOptions) (result *ControlLibrary, response *core.DetailedResponse, err error)
```
{: codeblock}
{: go}





A successful response returns a boolean that confirms that `success` is `true`. For more information about the required and optional request parameters, check out the [API docs](/apidocs/security-compliance#create-custom-control-library).



## Next steps
{: #library-next}

After your library is added to the service, you can use it to create a profile. From your library details, click **Actions > Create profile** to start evaluating your resources.


