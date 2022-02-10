---

copyright:
  years: 2020, 2022
lastupdated: "2022-02-10"

keywords: using the API, accessing the API, getting an access token, authenticating, authentication, access token, API key, account information, IAM access token

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


# Preparing to use the API
{: #api-setup}

To work with the {{site.data.keyword.compliance_full}} APIs, you must first create an API key and retrieve your account information. To do so, you can use the following steps.
{: shortdesc}

1. In the {{site.data.keyword.cloud_notm}} console, go to **Manage > Access (IAM)** and select **API keys**.
2. [Create an {{site.data.keyword.cloud_notm}} API key](/docs/account?topic=account-userapikey#create_user_key). Save the API key by downloading it to a secure location. 
3. Use your API key to generate an access token by calling the [IAM Identity Services API](/apidocs/iam-identity-token-api){: external}.

   ```bash
   curl -X POST \
   'https://iam.{DomainName}/identity/token' \
   --header 'Content-Type: application/x-www-form-urlencoded' \
   --header 'Accept: application/json' \
   --data-urlencode 'grant_type=urn:ibm:params:oauth:grant-type:apikey' \
   --data-urlencode 'apikey=<API_KEY>'
   ```
   {: codeblock}

   In the request, replace `<API_KEY>` with the API key that you created in the
   previous step. The following truncated example shows the sample output:

   ```json
   {
   "access_token": "b3VyIGZhdGhlc...",
   "expiration": 1512161390,
   "expires_in": 3600,
   "refresh_token": "dGhpcyBjb250a...",
   "token_type": "Bearer"
   }
   ```
   {: screen}

   Access tokens are valid for 1 hour, but you can regenerate them as needed. To maintain access, regenerate the access token for your API key regularly by calling the [IAM Identity Services API](/apidocs/iam-identity-token-api){: external}.
   {: note}

4. Retrieve the ID of your {{site.data.keyword.cloud_notm}} account.

   To find your account ID in the {{site.data.keyword.cloud_notm}} console, go to **Manage > Account** and select **Account settings**. In the Account section, copy the ID value that is associated with your account.

Now you have the needed information to make a request to the [Configuration API](https://{DomainName}/apidocs/security-compliance/config){: external}.
