---

copyright:
  years: 2020, 2023
lastupdated: "2023-03-31"

keywords: notification not working, notification not sent, event notifications

subcollection: security-compliance

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}

# Why am I not receiving notifications?
{: #notifications-not-sent}
{: troubleshoot}

You enabled event notifications for the {{site.data.keyword.compliance_short}}, but your alerts aren't being forwarded to the connected {{site.data.keyword.en_short}} service instance in your account.
{: shortdesc}

When you [send a test event to {{site.data.keyword.en_short}}](/docs/security-compliance?topic=security-compliance-event-notifications#event-notifications-test-ui), the action completes successfully with an HTTP `202 Accepted` response. However, the notifications aren't reaching your defined {{site.data.keyword.en_short}} destinations.
{: tsSymptoms}

This error can occur when the service authorization between {{site.data.keyword.compliance_short}} and {{site.data.keyword.en_short}} is removed after the connection between the services is initially enabled. You might also receive this error if your {{site.data.keyword.en_short}} topics, destinations, and subscriptions need to be configured or verified.
{: tsCauses}

Verify that you have an [{{site.data.keyword.en_short}} topic](/docs/event-notifications?topic=event-notifications-en-create-en-topic), destination, and subscription in your {{site.data.keyword.en_short}} service instance. Your {{site.data.keyword.en_short}} topic must configured to filter for [{{site.data.keyword.compliance_short}} event types](/docs/security-compliance?topic=security-compliance-event-notifications#event-notifications-list), and a subscription must exist between your topic and a destination. If the issue persists, ensure that an IAM authorization exists between the services in the account:
{: tsResolve}

1. In the console, go to **Manage > IAM > Authorizations**.
2. If an authorization doesn't already exist, click **Create**.
3. Enter **Security and Compliance Center** as the source service.
4. Enter **Event Notifications** as the target service.
5. Select **Resources based on selected attributes**.
6. Select the service instance attribute. From the list of instances, select your {{site.data.keyword.en_short}} service instance.
7. Select the **Event Source Manager** role.
8. Click **Authorize**.
