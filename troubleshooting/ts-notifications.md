---

copyright:
  years: 2020, 2025
lastupdated: "2025-05-16"

keywords: notification not working, notification not sent, event notifications

subcollection: security-compliance

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why am I not receiving notifications?
{: #notifications-not-sent}
{: troubleshoot}



As of 16 June 2025, you cannot create new instances in this version of this product. All of the functionality is now available in the updated experience of {{site.data.keyword.sysdigsecure_full}}. For more information, see [the transition documentation](/docs/security-compliance?topic=security-compliance-scc-transition). 
{: important}


You enabled event notifications for the {{site.data.keyword.compliance_short}}, but your alerts aren't being forwarded to the connected {{site.data.keyword.en_short}} service instance in your account.
{: shortdesc}

When you [send a test event to {{site.data.keyword.en_short}}](/docs/security-compliance?topic=security-compliance-event-notifications#event-notifications-test-ui), the action completes successfully with an HTTP `202 Accepted` response. However, the notifications aren't reaching your defined {{site.data.keyword.en_short}} destinations.
{: tsSymptoms}

This error can occur when the service authorization between {{site.data.keyword.compliance_short}} and {{site.data.keyword.en_short}} is removed after the connection between the services is initially enabled. You might also receive this error if your {{site.data.keyword.en_short}} topics, destinations, and subscriptions need to be configured or verified.
{: tsCauses}

Verify that you have an [{{site.data.keyword.en_short}} topic](/docs/event-notifications?topic=event-notifications-en-create-en-topic), destination, and subscription in your {{site.data.keyword.en_short}} service instance. Your {{site.data.keyword.en_short}} topic must be configured to filter for [{{site.data.keyword.compliance_short}} event types](/docs/security-compliance?topic=security-compliance-event-notifications#event-notifications-list), and a subscription must exist between your topic and a destination. If the issue persists, ensure that an IAM authorization exists between the services in the account:
{: tsResolve}

1. Go to **Manage > IAM > Authorizations** in the console.
2. Click **Create**, if an authorization doesn't exists.
3. Enter **Security and Compliance Center** as the source service.
4. Enter **Event Notifications** as the target service.
5. Select **Resources based on selected attributes**.
6. Select the service instance attribute. From the list of instances, select your {{site.data.keyword.en_short}} service instance.
7. Select the **Event Source Manager** role.
8. Click **Authorize**.
