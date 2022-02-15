---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-15"

keywords: notification not working, notification not sent, event notifications

subcollection: security-compliance

content-type: troubleshoot

---

{[metadata-attributes.md]}

# Why am I not receiving notifications?
{: #notifications-not-sent}
{: troubleshoot}

You enabled event notifications for the {[scc]}, but your alerts aren't being forwarded to the connected {[en]} service instance in your account.
{: shortdesc}

When you [send a test event to {[en]}]({[link]}-event-notifications#event-notifications-test-ui), the action completes successfully with an HTTP `202 Accepted` response. However, the notifications aren't reaching your defined {[en]} destinations.
{: tsSymptoms}

This error can occur when the service authorization between {[scc]} and {[en]} is removed after the connection between the services is initially enabled. You might also receive this error if your {[en]} topics, destinations, and subscriptions need to be configured or verified.
{: tsCauses}

Verify that you have an [{[en]} topic](/docs/event-notifications?topic=event-notifications-en-create-en-topic), destination, and subscription in your {[en]} service instance. Your {[en]} topic must configured to filter for [{[scc]} event types]({[link]}-event-notifications#event-notifications-list), and a subscription must exist between your topic and a destination. If the issue persists, ensure that an IAM authorization exists between the services in the account:
{: tsResolve}

1. In the console, go to **Manage > IAM > Authorizations**.
2. If an authorization doesn't already exist, click **Create**.
3. Enter **Security and Compliance Center** as the source service.
4. Enter **Event Notifications** as the target service.
5. Select **Resources based on selected attributes**.
6. Select the service instance attribute. From the list of instances, select your {[en]} service instance.
7. Select the **Event Source Manager** role.
8. Click **Authorize**.
