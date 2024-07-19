---

copyright:
  years: 2020, 2024
lastupdated: "2024-07-10"

keywords: custom profiles, user-defined, controls, goals, security, compliance

subcollection: security-compliance

---

{{site.data.keyword.attribute-definition-list}}


# Scanning your resources
{: #scan-resources}

With {{site.data.keyword.compliance_full}}, you can evaluate your resources on a recurring schedule or you can initiate a scan at any time by creating an attachment. An attachment is the association between the set of resources that you want to evaluate and a profile that contains the specific controls that you want to evaluate.
{: shortdesc}

To scan resources across multiple accounts for {{site.data.keyword.cloud_notm}} resources, register these accounts as targets. Then, use the trusted profile to grant these accounts access to the main {{site.data.keyword.compliance_short}} instance.
{: tip}


If you want to scan your Watson Machine Learning resources with {{site.data.keyword.compliance_short}}, see [Scanning Watson Machine Learning resources](/docs/security-compliance?topic=security-compliance-scan-watson-machine-learning) for more information. 

![A diagram that shows the relationship between a control, profile, and scope.](images/term-flow.svg){: caption="Figure 1. Understanding entities in {{site.data.keyword.compliance_short}}" caption-side="bottom"}


## Before you begin
{: #before-evaluation}

Before you get started, be sure that you have the following Prerequisites:

* The required level of access to create an attachment. To create an attachment, you need the **Editor** platform role or higher. For more information, see [Assigning access](/docs/security-compliance?topic=security-compliance-access-management).
* A connected Cloud Object Storage bucket in which to store your results. To connect your bucket, you must have a service-to-service policy in place that enables communication between {{site.data.keyword.compliance_short}} and Cloud Object Storage.
* A selected profile that you want to use in your attachment.

	Want to use controls from multiple profiles? Create a custom profile from the existing control libraries and use that profile to create your attachment. Because you cannot create custom profiles from deprecated control library versions, work with the most recent version.
	{: tip}

* If you are scanning resources across accounts, a trusted profile with access policies (and assigned roles) set for the target account. For more information, see [Scanning resources across accounts](/docs/security-compliance?topic=security-compliance-scan-resources-cross-account).


## Scheduling a recurring scan
{: #scan-schedule-ui}
{: ui}

To start scanning your resource, you create an attachment. To create an attachment, you can use the {{site.data.keyword.compliance_short}} UI to complete the following steps.

1. In the {{site.data.keyword.compliance_short}} UI, navigate to the **Attachments** page and click **Create**.

	Alternatively, you can create an attachment through the **Profiles** page. After you select the profile you want to use, on the **Attachments** tab of the profile details page, click **Create**.
	{: tip}

2. Provide a name and description for your attachment. Be sure to be as descriptive as possible so that it's easy for other members of your team to understand what is being evaluated. Then, click **Next**.
3. Select the **Profile** that you want to use for your evaluation.
4. Customize the underlying evaluations in your scan by editing the default parameters to match your specific use case. Then, click **Next**.
5. Target the resources that you want to evaluate by defining a scope within a single enterprise account. Or, define a scope across each of the target accounts in an {{site.data.keyword.cloud_notm}} environment that are outside of an enterprise. A flat list of the attachments in your account or across target accounts is displayed. For more information about evaluating resources in other accounts, see [Scanning resources across accounts](/docs/security-compliance?topic=security-compliance-scan-resources-cross-account).

   If you are working with {{site.data.keyword.cloud_notm}} resources, you can also specify resources that you want to exclude from your scope. If you are working with resources from other environments, you must [connect an instance of the {{site.data.keyword.sysdigsecure_short}} service](/docs/security-compliance?topic=security-compliance-setup-workload-protection) and provide any requested information to move forward.
6. Click **Next**.
7. Select the frequency at which you want to evaluate your attachment.
	
	Options include every day, every 7 days, and every 30 days. Also, you can pause your scans if you need to.

8. Optional: Configure failure notifications.
   1. If you want to receive notifications, toggle **Notify me** to **On**.
   2. By default, when notifications are enabled, you are alerted when 15% or more of your controls fail in a single scan. You can change this by adjusting the **Threshold** percentage. 

      For example, if you have a profile with 100 controls and you want to be notified if 5 of them fail, you would select 5% as your threshold.
      {: tip}
	
   3. Select specific controls that you want to be notified about.

	   If there are high priority controls that pertain specifically to your job role, you might want to be notified every time that they fail. You can identify up to 15 controls per scan that you can receive individual notifications for. These notifications are sent regardless of whether the threshold that was identified in the previous step was met.

      1. Click **Select control**.
      2. Select the controls that you want to be notified about by checking the box next to the control.
      3. Click **Ok**.
   4. Click **Next**.
9. Review your choices and click **Create**.

When you create your attachment, a scan is scheduled. When the scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard. If your results are not updated, review the [troubleshooting guide](/docs/security-compliance?topic=security-compliance-ts-cache). 



## Scheduling a recurring scan with the API
{: #scan-schedule-api}
{: api}

To start evaluating your resources, you can use the {{site.data.keyword.compliance_short}} attachments API or SDKs.

```bash
curl -X POST 
	--location --header "Authorization: Bearer {iam_token}" 
	--header "Accept: application/json" 
	--header "Content-Type: application/json" 
	--data '{ 
				"profile_id": "542b1aee-3ad8-49e9-a33c-44b64f117f18", 
				"attachments": { 
					"profile_id": "542b1aee-3ad8-49e9-a33c-44b64f117f18", 
					"account_id": "cg3335893hh1428692d6747cf300yeb5", 
					"instance_id": "edf9524f-406c-412c-acbb-ee371a5cabda", 
					"included_scope": { 
						"scope_id": "cg3335893hh1428692d6747cf300yeb5", 
						"scope_type": "account" 
						}, 
					"exclusions":  [ 
						"created_by": "IBMid-6620049HI3", 
						"created_on": "2023-02-09T10:54:59Z", 
						"updated_by": "IBMid-6620049HI3", 
						"updated_on": "2023-02-09T10:54:59Z", 
						"status": "enabled", 
						"schedule": "daily", 
						"notifications": { 
							"enabled": false, 
							"controls": { 
								"threshold_limit": 15, 
								"failed_control_ids":  
							] 
						} 
					}, 
				"attachment_parameters": [ 
						{ 
							"assessment_type": "Automated", 
							"assessment_id": "rule-a637949b-7e51-46c4-afd4-b96619001bf1", 
							"parameter_name": "session_invalidation_in_seconds", 
							"parameter_default_value": "120", 
							"parameter_display_name": "Sign out due to inactivity in seconds", 
							"parameter_type": "numeric" 
						} 
					], 
				"last_scan": { 
					"id": "0fd7e758-3ab3-492b-8b0d-0cd8ef3569d7", 
					"status": "in_progress", 
					"time": "2023-06-13T12:08:18Z" 
					}, 
				"next_scan_time": "2023-06-13T13:08:18Z",
				 "name": "account-0d8c3805dfea40aa8ad02265a18eb12b" 
				}, 
				"account_id": "130003ea8bfa43c5aacea07a86da3000" 
			}' 
	"https://us-south.compliance.cloud.ibm.com/instances/{instance_id}/v3/attachments"
```
{: pre}
{: curl}

```go
(securityAndComplianceCenterApi *SecurityAndComplianceCenterApiV3) CreateAttachment(createAttachmentOptions *CreateAttachmentOptions) (result *AttachmentPrototype, response *core.DetailedResponse, err error)
```
{: codeblock}
{: go}

```java
PropertyItem propertyItemModel = new PropertyItem.Builder()
  .name("scope_id")
  .value("cg3335893hh1428692d6747cf300yeb5")
  .build();
MultiCloudScope multiCloudScopeModel = new MultiCloudScope.Builder()
  .environment("ibm-cloud")
  .xProperties(java.util.Arrays.asList(propertyItemModel))
  .build();
FailedControls failedControlsModel = new FailedControls.Builder()
  .thresholdLimit(Long.valueOf("15"))
  .failedControlIds(java.util.Arrays.asList())
  .build();
AttachmentsNotificationsPrototype attachmentsNotificationsPrototypeModel = new AttachmentsNotificationsPrototype.Builder()
  .enabled(false)
  .controls(failedControlsModel)
  .build();
AttachmentParameterPrototype attachmentParameterPrototypeModel = new AttachmentParameterPrototype.Builder()
  .assessmentType("Automated")
  .assessmentId("rule-a637949b-7e51-46c4-afd4-b96619001bf1")
  .parameterName("session_invalidation_in_seconds")
  .parameterValue("120")
  .parameterDisplayName("Sign out due to inactivity in seconds")
  .parameterType("numeric")
  .build();
AttachmentsPrototype attachmentsPrototypeModel = new AttachmentsPrototype.Builder()
  .name("account-0d8c3805dfea40aa8ad02265a18eb12b")
  .description("Test description")
  .scope(java.util.Arrays.asList(multiCloudScopeModel))
  .status("enabled")
  .schedule("every_30_days")
  .notifications(attachmentsNotificationsPrototypeModel)
  .attachmentParameters(java.util.Arrays.asList(attachmentParameterPrototypeModel))
  .build();
CreateAttachmentOptions createAttachmentOptions = new CreateAttachmentOptions.Builder()
  .profilesId(profileIdLink)
  .attachments(java.util.Arrays.asList(attachmentsPrototypeModel))
  .build();

Response<AttachmentPrototype> response = securityAndComplianceCenterApiService.createAttachment(createAttachmentOptions).execute();
AttachmentPrototype attachmentPrototype = response.getResult();

System.out.println(attachmentPrototype);
```
{: codeblock}
{: java}

```bash
// Request models needed by this operation.

// PropertyItem
const propertyItemModel = {
  name: 'scope_id',
  value: 'cg3335893hh1428692d6747cf300yeb5',
};

// MultiCloudScope
const multiCloudScopeModel = {
  environment: 'ibm-cloud',
  properties: [propertyItemModel],
};

// FailedControls
const failedControlsModel = {
  threshold_limit: 15,
  failed_control_ids: [],
};

// AttachmentsNotificationsPrototype
const attachmentsNotificationsPrototypeModel = {
  enabled: false,
  controls: failedControlsModel,
};

// AttachmentParameterPrototype
const attachmentParameterPrototypeModel = {
  assessment_type: 'Automated',
  assessment_id: 'rule-a637949b-7e51-46c4-afd4-b96619001bf1',
  parameter_name: 'session_invalidation_in_seconds',
  parameter_value: '120',
  parameter_display_name: 'Sign out due to inactivity in seconds',
  parameter_type: 'numeric',
};

// AttachmentsPrototype
const attachmentsPrototypeModel = {
  name: 'account-0d8c3805dfea40aa8ad02265a18eb12b',
  description: 'Test description',
  scope: [multiCloudScopeModel],
  status: 'enabled',
  schedule: 'every_30_days',
  notifications: attachmentsNotificationsPrototypeModel,
  attachment_parameters: [attachmentParameterPrototypeModel],
};

const params = {
  profilesId: profileIdLink,
  attachments: [attachmentsPrototypeModel],
};

let res;
try {
  res = await securityAndComplianceCenterApiService.createAttachment(params);
  console.log(JSON.stringify(res.result, null, 2));
} catch (err) {
  console.warn(err);
}
```
{: codeblock}
{: node}

```python
property_item_model = {
  'name': 'scope_id',
  'value': 'cg3335893hh1428692d6747cf300yeb5',
}

multi_cloud_scope_model = {
  'environment': 'ibm-cloud',
  'properties': [property_item_model],
}

failed_controls_model = {
  'threshold_limit': 15,
  'failed_control_ids': [],
}

attachments_notifications_prototype_model = {
  'enabled': False,
  'controls': failed_controls_model,
}

attachment_parameter_prototype_model = {
  'assessment_type': 'Automated',
  'assessment_id': 'rule-a637949b-7e51-46c4-afd4-b96619001bf1',
  'parameter_name': 'session_invalidation_in_seconds',
  'parameter_value': '120',
  'parameter_display_name': 'Sign out due to inactivity in seconds',
  'parameter_type': 'numeric',
}

attachments_prototype_model = {
  'name': 'account-0d8c3805dfea40aa8ad02265a18eb12b',
  'description': 'Test description',
  'scope': [multi_cloud_scope_model],
  'status': 'enabled',
  'schedule': 'every_30_days',
  'notifications': attachments_notifications_prototype_model,
  'attachment_parameters': [attachment_parameter_prototype_model],
}

response = security_and_compliance_center_api_service.create_attachment(
  profiles_id=profile_id_link,
  attachments=[attachments_prototype_model],
)
attachment_prototype = response.get_result()

print(json.dumps(attachment_prototype, indent=2))
```
{: codeblock}
{: python}

A successful response returns an array that lists all the attachments to the specified profile, along with other metadata. For more information about the required and optional request parameters, check out the [API docs](/apidocs/security-compliance#create-attachment).




## Scheduling a recurring scan with the CLI
{: #scan-schedule-cli}
{: cli}

To create an attachment, you can use the {{site.data.keyword.compliance_short}} CLI. See the [CLI referencce](/docs/security-compliance?topic=security-compliance-security-compliance-cli&interface=cli#security-compliance-cli-attachments-create-command) for more information.

```sh
ibmcloud security-compliance attachment create
--profile-id=exampleString
--attachments='[
  {
    "id": "130003ea8bfa43c5aacea07a86da3000",
    "name": "account-0d8c3805dfea40aa8ad02265a18eb12b",
    "description": "Test description",
    "scope": [
      {
        "environment": "ibm-cloud",
        "properties": [
          {
            "name": "scope_id",
            "value": "cg3335893hh1428692d6747cf300yeb5"
            }
          ]
        }
      ],
    "status": "enabled",
    "schedule": "every_30_days",
    "notifications": {
      "enabled": false,
      "controls": {
        "threshold_limit": 15,
        "failed_control_ids": []
        }
      },
    "attachment_parameters": [
      {
        "assessment_type": "Automated",
        "assessment_id": "rule-a637949b-7e51-46c4-afd4-b96619001bf1",
        "parameter_name": "session_invalidation_in_seconds",
        "parameter_value": "120",
        "parameter_display_name": "Sign out due to inactivity in seconds",
        "parameter_type": "numeric"
        }
      ]
    }
  ]'
--x-correlation-id=exampleString
--x-request-id=exampleString
```
{: pre}


When you create your attachment, a scan is scheduled. When the scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard.



## Scheduling a recurring scan with Terraform
{: #scan-schedule-terraform}
{: terraform}

To create an attachment, you can use Terraform.

```terraform
resource "ibm_scc_profile_attachment" "scc-profile-attachment-instance" {
  instance_id = ibm_resource_instance.scc_instance.guid
  name        = "scc-ibm-cis-benchmark-attachment"
  description = "The IBM Cloud CIS Benchmark Evaluation"
  profile_id  = <scc_ibm_cloud_cis_profile_id>
  # The following are values for <scc_ibm_cloud_cis_profile_id>:
  #
  # ca-tor: d8ac6f16-a55c-471c-89a1-abc61d90b620
  # eu-es: 98d4e0cc-236a-4de6-b31b-13c6b6cdda8a
  # us-south: 1c13d739-e09e-4bf4-8715-dd82e4498041
  # eu-de: a0bd1ee2-1ed3-407e-a2f4-ce7a1a38f54d


  schedule = "every_7_days"
  status   = "enabled"

  scope {
    environment = "ibm-cloud"
    properties {
      name  = "scope_id"
      value = data.ibm_iam_account_settings.iam-account.account_id
    }

    properties {
      name  = "scope_type"
      value = "account"
    }
  }

  attachment_parameters {
    parameter_value        = jsonencode(["1.2", "1.3"])
    assessment_id          = "rule-e16fcfea-fe21-4d30-a721-423611481fea"
    assessment_type        = "automated"
    parameter_display_name = "IBM Cloud Internet Services TLS version"
    parameter_name         = "tls_version"
    parameter_type         = "string_list"
  }

  attachment_parameters {
    parameter_value        = "22"
    assessment_id          = "rule-f9137be8-2490-4afb-8cd5-a201cb167eb2"
    assessment_type        = "automated"
    parameter_display_name = "Network ACL rule for allowed IPs to SSH port"
    parameter_name         = "ssh_port"
    parameter_type         = "numeric"
  }

  attachment_parameters {
    parameter_value        = "3389"
    assessment_id          = "rule-9653d2c7-6290-4128-a5a3-65487ba40370"
    assessment_type        = "automated"
    parameter_display_name = "Security group rule RDP allow port number"
    parameter_name         = "rdp_port"
    parameter_type         = "numeric"
  }

  attachment_parameters {
    parameter_value        = "22"
    assessment_id          = "rule-7c5f6385-67e4-4edf-bec8-c722558b2dec"
    assessment_type        = "automated"
    parameter_display_name = "Security group rule SSH allow port number"
    parameter_name         = "ssh_port"
    parameter_type         = "numeric"
  }

  attachment_parameters {
    parameter_value        = "3389"
    assessment_id          = "rule-f1e80ee7-88d5-4bf2-b42f-c863bb24601c"
    assessment_type        = "automated"
    parameter_display_name = "Disallowed IPs for ingress to RDP port"
    parameter_name         = "rdp_port"
    parameter_type         = "numeric"
  }

  notifications {
    enabled = false

    controls {
      failed_control_ids = []
      threshold_limit    = 10
    }
  }
}
```
{: codeblock}


When you create your attachment, a scan is scheduled. When the scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard. For more information, check out the [Terraform reference](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/scc_rule_attachment){: external}.




## Running a scan on demand
{: #scan-ondemand-ui}
{: ui}

If your attachment exists, but you don't want to wait for the next scan to see your posture, you can initiate an on-demand scan.

1. In the {{site.data.keyword.cloud_notm}} console, click the **Menu** icon ![Menu icon](../icons/icon_hamburger.svg) **> Security and Compliance** to access {{site.data.keyword.compliance_short}}.
2. In the navigation, click **Profile**.
3. Click the options menu ![options icon](../../icons/actions-icon-vertical.svg) in the row of the profile that you want to evaluate.
3. Click **Run scan**.

After your scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard.

## Running a scan on demand with the API
{: #scan-ondemand-api}
{: api}

If your attachment exists, but you don't want to wait for the next scan to see your posture, you can initiate an on-demand scan.

```bash
curl -X POST 
	--location --header "Authorization: Bearer {iam_token}" 
	--header "Accept: application/json" 
	--header "Content-Type: application/json" 
	--data '{
		"attachment_id":"a34fdceab3d89d91bd4f76d422bf0d26"
		}' 
		"https://us-south.compliance.cloud.ibm.com/instances/{instance_id}/v3/scans"
```
{: pre}
{: curl}


```go
(securityAndComplianceCenterApi *SecurityAndComplianceCenterApiV3) CreateScan(createScanOptions *CreateScanOptions) (result *Scan, response *core.DetailedResponse, err error)
```
{: codeblock}
{: go}


```java
CreateScanOptions createScanOptions = new CreateScanOptions.Builder()
  .attachmentId(attachmentIdLink)
  .build();

Response<Scan> response = securityAndComplianceCenterApiService.createScan(createScanOptions).execute();
Scan scan = response.getResult();

System.out.println(scan);
```
{: codeblock}
{: java}


```bash
const params = {
  attachmentId: attachmentIdLink,
};

let res;
try {
  res = await securityAndComplianceCenterApiService.createScan(params);
  console.log(JSON.stringify(res.result, null, 2));
} catch (err) {
  console.warn(err);
}
```
{: codeblock}
{: node}


```python
create_scan(
        self,
        attachment_id: str,
        *,
        x_correlation_id: str = None,
        x_request_id: str = None,
        **kwargs,
    ) -> DetailedResponse
```
{: codeblock}
{: python}



A successful response returns the scan ID, along with other metadata. For more information about the required and optional request parameters, check out the [API docs](/apidocs/security-compliance#create-scan).



## Running a scan on demand with the CLI
{: #scan-ondemand-cli}
{: cli}

If your attachment exists, but you don't want to wait for the next scan to see your posture, you can initiate an on-demand scan. For more information, see the [CLI reference](/docs/security-compliance?topic=security-compliance-security-compliance-cli&interface=cli#security-compliance-cli-attachments-scan-command).

```sh
ibmcloud security-compliance attachment scan
--attachment-id=exampleString
--x-correlation-id=exampleString
--x-request-id=exampleString
```
{: pre}

After your scan completes, your results are available in the {{site.data.keyword.compliance_short}} dashboard.


