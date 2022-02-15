<staging>---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-15"

keywords: documenting security and compliance, onboard security and compliance, onboard fortress, onboard scc, integrated services, fortress, scc, enable rules, enable scc, enable fortress

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

# Onboarding FAQs
{: #internal-onboard-faq}

When onboarding with the {{site.data.keyword.compliance_short}}, you might have questions that other service providers have already asked. Checkout the following FAQs to see if you can find the answer to your question.

## Posture Management FAQs
{: #internal-monitoring-faq}

If your question is not answered by the documentation or the following FAQs, contact the squad in the [#scc-adopters](https://ibm-cloudplatform.slack.com/archives/C0116MQSHRS){: external} Slack channel.

### If our service is not available in the catalog and we don't provision resources, do we have any applicable goals?
{: #internal-faq-instances}

If your service does not provision any instances, it doesn't mean that you don't have valid use-cases in SCC. Consider any goals around settings that are configurable at the account level for your service. For example, `Ensure permissions for API key creation are limited and configured in IAM settings for the account owner` or `Ensure that Cloud Shell is enabled in account settings`.

### How can I request an extension on SEC046 for my service?
{: #internal-faq-extension}

To request an extension, comment on your SEC046 SF issue in GitHub with the following information and post the Service Framework issue in the #scc-adopters channel to request a review.

If your service does not have any controls to integrate with SCC, state in your comment:
1. Reason for extension: no controls to integrate
2. Link to service documentation

If you are unable to contain integration with SCC (SEC046), state in your comment:
1. Reason why integration cannot be contained
2. Control(s) your service plans to integrate
3. AHA epic with the fortress tag and the committed milestone
4. Link to service documentation

Once submitted, please allow up to 2 weeks for the team to review, as a meeting may be needed to discuss further details. The SME will sign off on the SF issue if the extension is approved.

SEC046 is also a SF currency item, please consider this requirement with new features or APIs.
{: note}

###  How often are my service's public APIs being called?
{: #internal-faq-frequency}

This depends on how the customer configures the schedule. Typical usage is estimated to be one scan per day.


###  How can I do integration testing for compliance monitoring?
{: #internal-faq-testing}

Since these are public APIs, they are expected to be working. The {{site.data.keyword.compliance_short}} team has the responsibility to test the integration and goals. For the authorization of the public APIs, the Posture Management component uses the user's API key.



## Configuration Governance FAQs
{: #internal-governance-faqs}

If your question is not answered by the documentation or the following FAQs, contact the squad in the [#scc-adopters](https://ibm-cloudplatform.slack.com/archives/C0116MQSHRS){: external} Slack channel.

### What is the plan to promote a service to production?
{: #internal-faq-production}

To promote your service to production, [submit a request](/docs/security-compliance?topic=security-compliance-internal-onboard-config#internal-config-next).

### Can I change the property values after the initial registration?
{: #internal-faq-property-change}

No. This could cause the case where a user has already created a rule with the property and when you change that property value, the rule will break. If you've implemented a property and want to change it in someway, the new supported config and/or properties must be implemented for monitoring/enforcement if they're enabled **before** updating the service definition.

### Is there a limitation on the number of properties we can have?
{: #internal-faq-property-limit}

No there is not.

### Is there a way to map an action to a platform role in RMC?
{: #internal-faq-map-action}

Yes. Map the action to a service role and save it. Then edit the action and the full list of roles will be displayed.

### What should I do if we receive an error code from the {{site.data.keyword.compliance_short}}?
{: #internal-faq-error}

If you receive an error code, retry the request up to 3 times. If you are unsuccessful after 3 attempts, contact the team in [#cp-compliance-issues](https://ibm-cloudplatform.slack.com/messages/cp-compliance-issues){: external} and if necessary, open a CIE. During the evaluation flow, services providers can't allow for the creation or updating of resources since they are unable to determine if the resource configuration is compliant or not. Service providers must reject the configuration request and return a 500 to the user.

### How can I do integration testing for Configuration Governance?
{: #internal-faq-integration-test}

You can use the [results API](https://compliance.test.cloud.ibm.com/results/api-docs/) for integration testing. The results are available when the scan completes a scheduled run. The scheduler runs one per hour in staging and once per day in production.

You must create an IAM policy for a test service ID to call the CIP. The recommended approach would be to add this action to an existing internal service role or a new one that is owned by the service provider.
{: screen}

### Do I have to enable monitoring?
{: #internal-faq-monitor}

In production we do not support enforcement only. If your service supports enforcement, you must also support monitoring.

### On the evaluation flow, why does the {{site.data.keyword.compliance_short}} need all properties if only one is being changed?
{: #internal-faq-properties}

A user could have a rule with nested conditions that includes more than the one property being changed. Additionally, this is used as a safeguard to ensure that when services update their registration by adding new properties they also update their evaluation and CIP integrations.

### On the evaluation results page, how is the display name of the resource determined?
{: #internal-faq-resource-name}

There are several different ways to choose what is displayed as the resource name. Here is the order of what SCC looks at for a display name:
1. `resource_name` field in additional_target_attributes
2. `resource_id` in additional_target_attributes
3. resource CRN

If `resource_name` is implemented, it must match the resource name in Ghost. 

### How do I get the evals-service-ID of my service when I submit a request to create IAM policies?
{: #internal-evals-service-id}

You will need to use the service ID that was created during your service's IAM onboarding with the operator role. You can find this in the service's [RMC record](https://test.cloud.ibm.com/onboarding) under "Access (IAM)" as the "IAM operator service ID". If you get the comment "Evals Service ID isn't allowed to operate on the service" on your pull request, the value provided for `evals-service-ID` is not valid for the `service-name` provided. You should also check that your service IDs are unlocked. In some cases, you might need to ask your SRE team to share or unlock the evals service ID. After the pull request has been successfully merged, you can lock your service ID.

</staging>