---

copyright:
  years: 2022
lastupdated: "2022-04-13"

keywords: best practices, security and compliance, governance, profile, predefined profiles, benchmark, controls, goals, security, compliance, ibm profiles, ibm financial, financial services, financial profile

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

# IBM Cloud for Financial Services vO.2.0
{: #ibm-financial-services}

IBM Cloud Financial Services is designed to address your cybersecurity and regulatory challenges and deliver the benefits and flexibility of a hybrid cloud in a secure and compliant environment.
{: shortdesc}

Through the IBM Cloud for Financial Services profile,  you have access to a unified set of pre-configured security and ocmpliance controls, which was build specifically for and with the financial services industry. To address your evolving needs as a financial institution, IBM continuously validates these controls with global Councils of CSOs, CTOs, and CIOs from major banks, insurance providers, and regulatory advisors. 

## Access control
{: #access-controls}

With the controls that belong to the access category, you can manage your account, establish conditions for group and role membership, and authorize access to the information system.

![Checkmark icon](../../icons/checkmark-icon.svg)

### Account Management AC-2
{: #account-management-goals}

To adhere to accepted standards and best practices, you can manage your account through an automated system account management, disable inactive accounts, manage role-based schemes, and validate access authorization.

#### Account Management | Automated System Account Management AC-2(1)
{: #account-management-automated-goals}

By enabling the following automated system account management goals, you can increase the security of your account.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000001 | Check whether IBMid password policy requires at least one uppercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000002 | Check whether IBMid password policy requires at least one lowercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000003 | Check whether IBMid password policy requires at least one number
| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000004 | Check whether IBMid password policy requires minimum length of 12 characters | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000005 | Check whether IBMid password policy prevents password reuse below the minimum of # | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000006 | Check whether IBMid password may contain only printable ASCII characters (in the range 33 - 126) | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000007 | Check whether IBMid password policy contains spaces or any of the following characters: \;:("?)<> | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000008 | Check whether IBMid uses a password meter that coaches users to create strong passwords that exceed the minimum requirements| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000015 | Check whether IAM users are attached to at least one access group |   |
| 3000016 | Check whether IAM policies for users are attached only to groups or roles |   |
| 3000023 | Check whether the account owner does not have an IBM Cloud API key created in IAM |   |
| 3000024 | Check whether IBM Cloud API keys that are managed in IAM are rotated at least every # days |   |
| 3000025 | Check whether an account owner has logged in to IBM Cloud in the past # days |   |
| 3000026 | Check whether user list visibility restrictions are configured in IAM settings for the account owner |   |
| 3000035 | Check whether account service access is managed only by IAM access groups |   |
| 3000039 | Check whether IBM Cloud API keys that are unused for 180 days are detected and optionally disabled |   |
| 3000235 | Check whether Hyper Protect Crypto Services encryption keys that are generated by the service are rotated automatically at least every # months |   |
| 3000425 | Check whether VPN for VPC authentication is configured with a strong pre-shared key with at least # alphanumeric characters |   |
| 3000707 | Check whether App ID user profile updates from client apps is disabled |   |
| 3000708 | Check whether App ID Cloud Directory users aren't able to update their own accounts |   |
| 3000709 | Check whether App ID Cloud Directory users aren't able to self-sign up to applications |   |
| 3000711 | Check whether App ID social identity providers are disabled |   |
| 3000712 | Check whether App ID anonymous authentication is disabled |   |
| 3000713 | Check whether App ID password strength regex is configured |   |
| 3000714 | Check whether App ID advanced password policies are enabled |   |
| 3000715 | Check whether App ID avoid password reuse policy is enabled |   |
| 3000716 | Check whether App ID lockout policy after failed # of sign-in attempts is enabled |   |
| 3000717 | Check whether App ID lockout policy after a maximum specified time is set to # minute(s) |   |
| 3000718 | Check whether App ID minimum period between password changes policy is set to greater than 0 |   |
| 3000719 | Check whether App ID password expiration policy is enabled |   |
| 3000720 | Check whether App ID prevent username in password policy is enabled |   |
{: caption="Table 1. Automated system management goals" caption-side="top"}

#### Account Management | Role-Based Schemes AC-2(7)
{: #account-management-schemes-goals}

Lower the risk of your organization by managing role-based schemes.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000010 | Check whether a support role has been assigned in IAM to manage cases in the IBM Cloud Support Center | ![Checkmark icon](../../icons/checkmark-icon.svg) |
{: caption="Table 2. Role-based schemes management goals" caption-side="top"}

#### Establishes conditions for group and role membership AC-2(c)
{: #membership-role-goals}

By enabling goals that establish conditions for group and role membership, you can improve the security of your account.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000009 | Check whether IAM roles are used to create IAM policies for IBM resources | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| 3000010 | Check whether a support role has been assigned in IAM to manage cases in the IBM Cloud Support Center | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| 3000015 | Check whether IAM users are attached to at least one access group |  |
| 3000016 | Check whether IAM policies for users are attached only to groups or roles |  |
| 3000035 | Check whether account service access is managed only by IAM access groups |  |
| 3000707 | Check whether App ID user profile updates from client apps is disabled |  |
| 3000708 | Check whether App ID Cloud Directory users aren't able to update their own accounts |  |
| 3000709 | Check whether App ID Cloud Directory users aren't able to self-sign up to applications |  |
| 3000711 | Check whether App ID social identity providers are disabled |  |
| 3000712 | Check whether App ID anonymous authentication is disabled |  |
{: caption="Table 3. Conditions of group and role membership goals" caption-side="top"}

#### Creates, enables, modifies, disables, and removes information system accounts in accordance with organization-defined procedures or conditions AC-2(f)
{: #system-account-procedures-goals} 

Increase the security of yur account by managing your information system accounts in accordance with organization-defined procedures or conditions.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000001 | Check whether IBMid password policy requires at least one uppercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000002 | Check whether IBMid password policy requires at least one lowercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000003 | Check whether IBMid password policy requires at least one number
| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000004 | Check whether IBMid password policy requires minimum length of 12 characters | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000005 | Check whether IBMid password policy prevents password reuse below the minimum of # | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000006 | Check whether IBMid password may contain only printable ASCII characters (in the range 33 - 126) | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000007 | Check whether IBMid password policy contains spaces or any of the following characters: \;:("?)<> | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000008 | Check whether IBMid uses a password meter that coaches users to create strong passwords that exceed the minimum requirements| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000023 | Check whether the account owner does not have an IBM Cloud API key created in IAM |  |
| 3000027 | Check whether permissions for API key creation are limited and configured in IAM settings for the account owner |  |
| 3000425 | Check whether VPN for VPC authentication is configured with a strong pre-shared key with at least # alphanumeric characters |  |
| 3000713 | Check whether App ID password strength regex is configured |  |
| 3000714 | Check whether App ID advanced password policies are enabled |  |
| 3000715 | Check whether App ID avoid password reuse policy is enabled |  |
| 3000716 | Check whether App ID lockout policy after failed # of sign-in attempts is enabled |  |
| 3000717 | Check whether App ID lockout policy after a maximum specified time is set to # minute(s) |  |
| 3000718 | Check whether App ID minimum period between password changes policy is set to greater than 0 |  |
| 3000719 | Check whether App ID password expiration policy is enabled |  |
| 3000720 | Check whether App ID prevent username in password policy is enabled |  |
| 3000724 | Check whether App ID access tokens are configured to expire within # minutes |  |
{: caption="Table 4. Information systems accounts goals" caption-side="top"}

#### Authorizes access to the information system based on: 1. A valid access authorization; 2. Intended system usage; and 3. Other attributes as required by the organization or associated missions/business functionss AC-2(i)
{: #access-auth-goals}

Manage the authorized access to the informaton system to improve the security of your account.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000009 | Check whether IAM roles are used to create IAM policies for IBM resources | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| 3000010 | Check whether a support role has been assigned in IAM to manage cases in the IBM Cloud Support Center | ![Checkmark icon](../../icons/checkmark-icon.svg) |
| 3000017 | Check whether multifactor authentication (MFA) is enabled at the account level |  |
| 3000023 | Check whether the account owner does not have an IBM Cloud API key created in IAM |  |
| 3000024 | Check whether IBM Cloud API keys that are managed in IAM are rotated at least every # days |  |
| 3000027 | Check whether permissions for API key creation are limited and configured in IAM settings for the account owner |  |
| 3000039 | Check whether IBM Cloud API keys that are unused for 180 days are detected and optionally disabled |  |
| 3000106 | Check whether Cloud Object Storage bucket access is restricted by using IAM and S3 access control |  |
| 3000425 | Check whether VPN for VPC authentication is configured with a strong pre-shared key with at least # alphanumeric characters |  |
| 3000713 | Check whether App ID password strength regex is configured |  |
| 3000714 | Check whether App ID advanced password policies are enabled |  |
| 3000715 | Check whether App ID avoid password reuse policy is enabled |  |
| 3000716 | Check whether App ID lockout policy after failed # of sign-in attempts is enabled |  |
| 3000717 | Check whether App ID lockout policy after a maximum specified time is set to # minute(s) |  |
| 3000718 | Check whether App ID minimum period between password changes policy is set to greater than 0 |  |
| 3000719 | Check whether App ID password expiration policy is enabled |  |
| 3000720 | Check whether App ID prevent username in password policy is enabled |  |
| 3000723 | Check whether App ID multifactor authentication (MFA) is enabled for Cloud Directory users |  |
| 3000724 | Check whether App ID access tokens are configured to expire within # minutes |  |
{: caption="Table 5. Information systems authorized access goals" caption-side="top"}

#### Reviews accounts for compliance with account management requirements Assignment: organization-defined frequency AC-2(j)
{: #access-auth-goals}

Manage the authorized access to the informaton system to improve the security of your account.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000001 | Check whether IBMid password policy requires at least one uppercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000002 | Check whether IBMid password policy requires at least one lowercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000003 | Check whether IBMid password policy requires at least one number
| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000004 | Check whether IBMid password policy requires minimum length of 12 characters | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000005 | Check whether IBMid password policy prevents password reuse below the minimum of # | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000006 | Check whether IBMid password may contain only printable ASCII characters (in the range 33 - 126) | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000007 | Check whether IBMid password policy contains spaces or any of the following characters: \;:("?)<> | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000008 | Check whether IBMid uses a password meter that coaches users to create strong passwords that exceed the minimum requirements| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000035 | Check whether account service access is managed only by IAM access groups |  |
| 3000707 | Check whether App ID user profile updates from client apps is disabled |  |
| 3000708 | Check whether App ID Cloud Directory users aren't able to update their own accounts |  |
| 3000709 | Check whether App ID Cloud Directory users aren't able to self-sign up to applications |  |
| 3000711 | Check whether App ID social identity providers are disabled |  |
| 3000712 | Check whether App ID anonymous authentication is disabled |  |
{: caption="Table 6. Information systems authorized access goals" caption-side="top"}

### Access Enforcement AC-3
{: #account-enforcement-goals}

To increase the security of your account, you can manage goals that enforce your conditions for access.  

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000015 | Check whether IAM users are attached to at least one access group |  |
| 3000016 | Check whether IAM policies for users are attached only to groups or roles |  |
| 3000020 | Check whether authorized IP ranges are configured by the account owner |  |
| 3000022 | Check whether Cloud Object Storage public access is disabled in IAM settings (not applicable to ACLs managed using S3 APIs) |  |
| 3000023 | Check whether the account owner does not have an IBM Cloud API key created in IAM |  |
| 3000027 | Check whether permissions for API key creation are limited and configured in IAM settings for the account owner |  |
| 3000035 | Check whether account service access is managed only by IAM access groups |  |
| 3000106 | Check whether Cloud Object Storage bucket access is restricted by using IAM and S3 access control |  |
| 3000707 | Check whether App ID user profile updates from client apps is disabled |  |
| 3000708 | Check whether App ID Cloud Directory users aren't able to update their own accounts |  |
| 3000709 | Check whether App ID Cloud Directory users aren't able to self-sign up to applications |  |
| 3000711 | Check whether App ID social identity providers are disabled |  |
| 3000712 | Check whether App ID anonymous authentication is disabled |  |
| 3000724 | Check whether App ID access tokens are configured to expire within # minutes |  |
{: caption="Table 7. Access enforcement goals" caption-side="top"}

#### Information Flow Enforcement AC-4
{: #information-flow-enforcement-goals}

You can manage goals that enforce your conditions for information flow to improve the security of your account.  

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000022 | Check whether Cloud Object Storage public access is disabled in IAM settings (not applicable to ACLs managed using S3 APIs) |  |
| 3000105 | Check whether Cloud Object Storage is accessible only by using private endpoints |  |
| 3000107 | Check whether Cloud Object Storage network access is restricted to a specific IP range |  |
| 3000306 | Check whether Event Streams is accessible only by using private endpoints |  |
| 3000307 | Check whether Event Streams network access is restricted to a specific IP range |  |
| 3000404 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to SSH port |  |
| 3000405 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to RDP port |  |
| 3000406 | Check whether Virtual Private Cloud (VPC) has no rules in the default security group |  |
| 3000410 | Check whether Virtual Private Cloud (VPC) security groups have no inbound ports open to the internet (0.0.0.0/0) |  |
| 3000411 | Check whether Virtual Private Cloud (VPC) security groups have no outbound ports open to the internet (0.0.0.0/0) |  |
| 3000412 | Check whether all virtual server instances have at least one Virtual Private Cloud (VPC) security group attached |  |
| 3000413 | Check whether all network interfaces of a virtual server instance have at least one Virtual Private Cloud (VPC) security group attached |  |
| 3000418 | Check whether account has at least one VPN or Direct Link configured |  |
| 3000427 | Check whether Application Load Balancer for VPC has public access disabled |  |
| 3000428 | Check whether Application Load Balancer for VPC is configured with multiple members in the pool |  |
| 3000429 | Check whether Application Load Balancer for VPC listener is configured with default pool |  |
| 3000441 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to SSH port |  |
| 3000442 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to RDP port |  |
| 3000444 | Check whether Security Groups for VPC contains no outbound rules in security groups that specify source IP 8.8.8.8/32 to DNS port |  |
| 3000445 | Check whether Security Groups for VPC doesn't allow SSH for the default security group |  |
| 3000446 | Check whether Security Groups for VPC doesn't allow PING for the default security group |  |
| 3000447 | Check whether Virtual Private Cloud (VPC) classic access is disabled |  |
| 3000448 | Check whether Virtual Private Cloud (VPC) has no public gateways attached at the time of provisioning |  |
| 3000449 | Check whether Virtual Private Cloud (VPC) has no public gateways attached |  |
| 3000451 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to any port |  |
| 3000452 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow egress from 0.0.0.0/0 to any port |  |
| 3000453 | Check whether Virtual Servers for VPC instance has the minimum # interfaces |  |
| 3000454 | Check whether Virtual Servers for VPC instance doesn't have a floating IP |  |
| 3000455 | Check whether Virtual Servers for VPC instance has all interfaces with IP-spoofing disabled |  |
| 3000456 | Check whether Virtual Servers for VPC is in a resource group other than "Default" |  |
| 3000467 | Check whether Virtual Private Cloud (VPC) has no subnet with public gateway attached |  |
| 3000468 | Check whether Virtual Private Cloud (VPC) is configured with public gateways that are provisionable only within permitted zones |  |
| 3000469 | Check whether Application Load Balancer for VPC is configured with at least one VPC security group |  |
| 3000510 | Check whether Hyper Protect Crypto Services is accessible only through private endpoints |  |
| 3000526 | Check whether Hyper Protect DBaaS for MongoDB is accessible only using private endpoints |  |
| 3000534 | Check whether Hyper Protect DBaaS for PostgreSQL is accessible only using private endpoints |  |
| 3000625 | Check whether Container Registry image pushes and pulls take place only over private endpoints |  |
| 3000704 | Check whether App ID redirect URIs are not using localhost or 127.0.0.1 |  |
| 3000705 | Check whether App ID redirect URIs are not using wildcards (*) |  |
| 3000902 | Check whether OpenShift clusters are accessible only by using private endpoints |  |
| 3000903 | Check whether OpenShift cluster has image pull secrets enabled |  |
{: caption="Table 8. Information flow enforcement goals" caption-side="top"}

### Separation of Duties AC-5
{: #separation-duties-goals}

Improve the security and compliance of your account by managing the separation of the duties of individuals in your organization.

#### Documents separation of duties of individuals AC-5(b)
{: #documents-separation-goals}

Enable goals that document the separation of duties of individuals to manage the security of your account.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000015 | Check whether IAM users are attached to at least one access group |  |
| 3000016 | Check whether IAM policies for users are attached only to groups or roles |  |
| 3000035 | Check whether account service access is managed only by IAM access groups |  |
| 3000106 | Check whether Cloud Object Storage bucket access is restricted by using IAM and S3 access control |  |
| 3000707 | Check whether App ID user profile updates from client apps is disabled |  |
| 3000708 | Check whether App ID Cloud Directory users aren't able to update their own accounts |  |
| 3000709 | Check whether App ID Cloud Directory users aren't able to self-sign up to applications |  |
| 3000711 | Check whether App ID social identity providers are disabled |  |
| 3000712 | Check whether App ID anonymous authentication is disabled |  |
{: caption="Table 9. Separation of duties goals" caption-side="top"}

### Least privilege AC-6
{: #least-privilege-goals}

Improve the security and compliance of your account by following the principle of least privilege when you are assigning access to individuals in your organization.

#### Least privilege goals AC-6-0
{: #least-privileges-goals}

Enable the following goals to assign the least privilege required to individuals in your organization.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000015 | Check whether IAM users are attached to at least one access group |  |
| 3000016 | Check whether IAM policies for users are attached only to groups or roles |  |
| 3000020 | Check whether authorized IP ranges are configured by the account owner |  |
| 3000022 | Check whether Cloud Object Storage public access is disabled in IAM settings (not applicable to ACLs managed using S3 APIs) |  |
| 3000023 | Check whether the account owner does not have an IBM Cloud API key created in IAM |  |
| 3000025 | Check whether an account owner has logged in to IBM Cloud in the past # days |  |
| 3000026 | Check whether user list visibility restrictions are configured in IAM settings for the account owner |  |
| 3000027 | Check whether permissions for API key creation are limited and configured in IAM settings for the account owner |  |
| 3000028 | Check whether permissions for service ID creation are limited and configured in IAM settings for the account owner |  |
| 3000035 | Check whether account service access is managed only by IAM access groups |  |
| 3000106 | Check whether Cloud Object Storage bucket access is restricted by using IAM and S3 access control |  |
| 3000707 | Check whether App ID user profile updates from client apps is disabled | 
| 3000708 | Check whether App ID Cloud Directory users aren't able to update their own accounts |  |
| 3000709 | Check whether App ID Cloud Directory users aren't able to self-sign up to applications |  |
| 3000711 | Check whether App ID social identity providers are disabled |  |
| 3000712 | Check whether App ID anonymous authentication is disabled |  |
| 3000724 | Check whether App ID access tokens are configured to expire within # minutes |  |
{: caption="Table 10. Least privilege goals" caption-side="top"}

#### Least Privilege | Prohibit Non-privileged Users from Executing Privileged Functions AC-6(10)
{: #least-privilege-functions-goals}

To better secure your account, prohibit non-privileged students from executing privilege functions by upholding the principle of least privilege.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000023 | Check whether the account owner does not have an IBM Cloud API key created in IAM |  |
| 3000027 | Check whether permissions for API key creation are limited and configured in IAM settings for the account owner |  |
| 3000724 | Check whether App ID access tokens are configured to expire within # minutes |  |
{: caption="Table 11. Least privilege prohibition goals" caption-side="top"}

### Unsuccessful logon attempts AC-6
{: #unsuccessful-logon-goals}

Improve the security and compliance of your account by enforcing limits on consecutive invalid logon attempts and by automatically locking the account when needed.

#### Enforce a limit of [Assignment: organization-defined number] consecutive invalid logon attempts by a user during a [Assignment: organization-defined time period] AC-7(a)
{: #assignment-limit-goals}

Limit consecutive invalid logon attempts from a use during a specified time period to improve the security of your account.

| ID | Goal | Met by default |
| -- | ---- | -------------- |
| 3000716 | Check whether App ID lockout policy after failed # of sign-in attempts is enabled |  |
{: caption="Table 12. Assignment limit goal" caption-side="top"}

#### Automatically [Selection (one or more): lock the account or node for an [Assignment: organization-defined time period]; lock the account or node until released by an administrator; delay next logon prompt per ... AC-7(b)
{: #assignment-lock-goals}

To improve the security of your account, lock your account during a specified time period until an administrator releases it.

| ID | Goal | Met by default |
| -- | ---- | -------------- |
| 3000717 | Check whether App ID lockout policy after a maximum specified time is set to # minute(s) |  |
{: caption="Table 13. Assignment lock goal" caption-side="top"}

#### Permitted Actions Without Identification or Authentication AC-6
{: #unsuccessful-logon-goals}

Improve the security and compliance of your account by defining which actions can be done without requiring your users to identify themselves or authenticating them.

#### Identify that can be performed on the system without identification or authentication consistent with organizational mission and business function AC-14(a)
{: #assignment-lock-goals}

To improve the security of your account, define which actions can users perform on your system without identifying themselves or getting authenticated.

| ID | Goal | Met by default |
| -- | ---- | -------------- |
| 3000022 | Check whether Cloud Object Storage public access is disabled in IAM settings (not applicable to ACLs managed using S3 APIs) |  |
| 3000712 | Check whether App ID anonymous authentication is disabled |  |
{: caption="Table 14. Identification goals" caption-side="top"}

### Use of External Systems AC-20
{: #wireless-access-goals}

Define the parameters of use of external systems to increase the security of your account.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000047 | Check whether provisioned services are IAM enabled |  |
{: caption="Table 15. External system use goals" caption-side="top"}

## Audit and accountability
{: #audit-accountability-controls}

With the controls that belong to the audit and accountability category, you can audit events, storage capacity, record retention, and generation.

![Checkmark icon](../../icons/checkmark-icon.svg)

### Audit Events AU-2
{: #audit-events-goals}

You can increase the security of your systems by auditing events and their frequency.

#### Determines that the information system is capable of auditing organization-defined auditable events AU-2(a)
{: #organization-audit-events-goals}

Determine whether your information system can audit organization-defined auditable events to improve the security of your systems.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000408 | Check whether Flow Logs for VPC are enabled |   |
| 3000710 | Check whether App ID runtime activity capture is enabled |   |
{: caption="Table 16. Auditable events goals" caption-side="top"}

#### Determines that organization-defined audited events along with the frequency of auditing for each identified event are to be audited within the information system AU-2(d)
{: #organization-audit-frequency-goals}

Improve the security of your systems by auditing organization-defined events and their frequency.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000408 | Check whether Flow Logs for VPC are enabled |   |
| 3000710 | Check whether App ID runtime activity capture is enabled |   |
{: caption="Table 17. Auditing events and frequency goals" caption-side="top"}

### Audit storage capacity AU-4
{: #audit-storage-goals}

To increase the security of your systems, audit your Cloud Storage buckets quota enforcement and alerts.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000282 | Check whether Cloud Object Storage quota enforcement is off for buckets that are configured to use Activity Tracker event routing |   |
| 3000283 | Check whether Cloud Object Storage buckets with a quota have threshold-based alerts enabled |   |
{: caption="Table 18. Audit storage capacity goals" caption-side="top"}

### Audit record retention AU-11
{: #audit-record-goals}

To increase the security of your systems, audit your record retention.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000282 | Check whether Cloud Object Storage quota enforcement is off for buckets that are configured to use Activity Tracker event routing |   |
| 3000283 | Check whether Cloud Object Storage buckets with a quota have threshold-based alerts enabled |   |
{: caption="Table 18. Audit record retention goals" caption-side="top"}

### Audit generation AU-12
{: #audit-generation-goals}

Audit the flow logs for Virtual Private Cloud.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000408 | Check whether Flow Logs for VPC are enabled |   |
{: caption="Table 19. Audit generation goals" caption-side="top"}

## 	Configuration management
{: #configuration-management-controls}

To increase the security of your resources, configure the baseline, establish configuration settings, follow the principle of least functionality, and inventory your system components.

![Checkmark icon](../../icons/checkmark-icon.svg)

### Baseline configuration CM-2
{: #baseline-configuration-goals}

Improve the security of your resources by configuring access to Cloud Object Storage, Event Streams, Virtual Private Cloud (VPC), virtual server instances, Application Load Balancer for VPC, Hyper Protect services, Container Registry, App ID, and Red Hat OpenShift.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000105 | Check whether Cloud Object Storage is accessible only by using private endpoints |   |
| 3000107 | Check whether Cloud Object Storage network access is restricted to a specific IP range |   |
| 3000306 | Check whether Event Streams is accessible only by using private endpoints |   |
| 3000307 | Check whether Event Streams network access is restricted to a specific IP range |   |
| 3000404 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to SSH port |   |
| 3000405 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to RDP port |   |
| 3000406 | Check whether Virtual Private Cloud (VPC) has no rules in the default security group |   |
| 3000410 | Check whether Virtual Private Cloud (VPC) security groups have no inbound ports open to the internet (0.0.0.0/0) |   |
| 3000411 | Check whether Virtual Private Cloud (VPC) security groups have no outbound ports open to the internet (0.0.0.0/0) |   |
| 3000412 | Check whether all virtual server instances have at least one Virtual Private Cloud (VPC) security group attached |   |
| 3000413 | Check whether all network interfaces of a virtual server instance have at least one Virtual Private Cloud (VPC) security group attached |   |
| 3000418 | Check whether account has at least one VPN or Direct Link configured |   |
| 3000427 | Check whether Application Load Balancer for VPC has public access disabled |   |
| 3000428 | Check whether Application Load Balancer for VPC is configured with multiple members in the pool |   |
| 3000429 | Check whether Application Load Balancer for VPC listener is configured with default pool |   |
| 3000441 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to SSH port |   |
| 3000442 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to RDP port |   |
| 3000444 | Check whether Security Groups for VPC contains no outbound rules in security groups that specify source IP 8.8.8.8/32 to DNS port |   |
| 3000445 | Check whether Security Groups for VPC doesn't allow SSH for the default security group |   |
| 3000446 | Check whether Security Groups for VPC doesn't allow PING for the default security group |   |
| 3000447 | Check whether Virtual Private Cloud (VPC) classic access is disabled |   |
| 3000448 | Check whether Virtual Private Cloud (VPC) has no public gateways attached at the time of provisioning |   |
| 3000449 | Check whether Virtual Private Cloud (VPC) has no public gateways attached |   |
| 3000451 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to any port |   |
| 3000452 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow egress from 0.0.0.0/0 to any port |   |
| 3000453 | Check whether Virtual Servers for VPC instance has the minimum # interfaces |   |
| 3000454 | Check whether Virtual Servers for VPC instance doesn't have a floating IP |   |
| 3000455 | Check whether Virtual Servers for VPC instance has all interfaces with IP-spoofing disabled |   |
| 3000456 | Check whether Virtual Servers for VPC is in a resource group other than "Default" |   |
| 3000462 | Check whether Virtual Servers for VPC is provisioned from customer-defined list of images |   |
| 3000467 | Check whether Virtual Private Cloud (VPC) has no subnet with public gateway attached |   |
| 3000468 | Check whether Virtual Private Cloud (VPC) is configured with public gateways that are provisionable only within permitted zones |   |
| 3000469 | Check whether Application Load Balancer for VPC is configured with at least one VPC security group |   |
| 3000510 | Check whether Hyper Protect Crypto Services is accessible only through private endpoints |   |
| 3000526 | Check whether Hyper Protect DBaaS for MongoDB is accessible only using private endpoints |   |
| 3000534 | Check whether Hyper Protect DBaaS for PostgreSQL is accessible only using private endpoints |   |
| 3000625 | Check whether Container Registry image pushes and pulls take place only over private endpoints |   |
| 3000704 | Check whether App ID redirect URIs are not using localhost or 127.0.0.1 |   |
| 3000705 | Check whether App ID redirect URIs are not using wildcards (*) |   |
| 3000902 | Check whether OpenShift clusters are accessible only by using private endpoints |   |
| 3000907 | Check whether OpenShift version is up-to-date |   |
{: caption="Table 20. Baseline configuration goals" caption-side="top"}

### Configuration settings CM-6
{: #configuration-settings-goals}

Enable configuration settings that are consistent with operational requirements to better secure your resources.

#### Establish and document configuration settings for components employed within the system that reflect the most restrictive mode consistent with operational requirements using organization-defined common secure configurations CM-6(a)
{: #configuration-settings-document-goals}

To improve the security of your resrouces, establish and document configuration settings for components that are employed within the system that reflect the most restrictive mode. The mode must be consistent with operational requirements by using organization-defined common secure configurations.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000045 | Check whether the Financial Services Validated setting is enabled in account settings |   |
{: caption="Table 21. Document configuration settings goal" caption-side="top"}

### Least functionality CM-7
{: #least-functionality-goals}

Apply the principle of least functionality to better secure your resources. 

#### Configures the information system to provide only essential capabilities CM-7(a)
{: #configuration-essential-capabilities-goals}

Configure your information system by assigning it only essential capabilities.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000462 | Check whether Virtual Servers for VPC is provisioned from customer-defined list of images |   |
| 3000907 | Check whether OpenShift version is up-to-date |   |
{: caption="Table 22. Least functionality goals" caption-side="top"}

### System component inventory CM-8
{: #system-inventory-goals}

To improve the security of your resources, inventory your system components.

#### System Component Inventory | Updates During Installation and Removal CM-8(1)
{: #installation-removal-goals}

Inventory your system components to provide updates during installation and removal to better secure your resources.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000907 | Check whether OpenShift version is up-to-date |   |
{: caption="Table 23. Inventory system during installation and removal goal" caption-side="top"}

#### System Component Inventory | Automated Unauthorized Component Detection CM-8(3)
{: #component-detection-goals}

To improve the security of your resources, inventory your system to detect automatically unauthorized components.

##### Employs automated mechanisms in organization-defined frequency to detect the presence of unauthorized hardware, software, and firmware components within the information system CM-8(3)(a)
{: #automated-mechanism-goals}

Detect the presence of unauthorized hardware, software, and firmware components within the information system by employing automated mechanisms to better secure your system.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000462 | Check whether Virtual Servers for VPC is provisioned from customer-defined list of images |   |
| 3000601 | Check whether Container Registry Vulnerability Advisor scans for critical or high vulnerabilities in the system at least every # day(s) |   |
| 3000611 | Check whether Container Registry Vulnerability Advisor scans images for OS vulnerability detection |   |
| 3000901 | Check whether OpenShift worker nodes are updated to the latest image to ensure patching of vulnerabilities |   |
| 3000907 | Check whether OpenShift version is up-to-date |   |
{: caption="Table 24. Inventory automated mechanisms goals" caption-side="top"}

#### System Component Inventory | Accountability Information CM-8(4)
{: #accountability-information-goals}

To better secure your resources, inventory your system components for accountability information.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000013 | Check whether account has a contact email defined |   |
| 3000014 | Check whether account has a contact phone number defined |   |
{: caption="Table 25. Accountability information goals" caption-side="top"}

## Contingency plan
{: #contingency-plan-controls}

To improve the security of your resources, create a contigency plan by setting up an alternate storage site and system recovery and reconstitution.

![Checkmark icon](../../icons/checkmark-icon.svg)

###  Alternate storage site CP-6
{: #alternate-site-goals}

Set up an alternate storage site to better secure your resources.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000116 | Check whether Cloud Object Storage bucket resiliency is set to cross region |   |
{: caption="Table 26. Alternate storage site goal" caption-side="top"}

##  Alternate Processing Site | Separation from Primary Site CP-7(1)
{: #alternate-processing-site-goals}

Set up an alternate processing site that is separate from the primary site to better secure your resources.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000915 | Check whether an OpenShift cluster has worker nodes across multiple zones |   |
{: caption="Table 27. Alternate processing site goal" caption-side="top"}


## 	Enterprise System and Services Acquisition
{: #enterprise-system-controls}

To better secure your resources, configure the your enterprise system and services acquisition.

![Checkmark icon](../../icons/checkmark-icon.svg)

### Non-Permitted Technology (NPT) List ESA-3
{: #technology-permission-goals}

Inspect your list for non-permitted technology to increase the security of your resources.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000047 | Check whether provisioned services are IAM enabled |   |
{: caption="Table 28. Non-permitted technology goal" caption-side="top"}

### Subcontractor Risk Management ESA-5
{: #technology-permission-goals}

Inspect your subcontractor risk management to improve the security of your resources. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000047 | Check whether provisioned services are IAM enabled |   |
{: caption="Table 29. Risk management goal" caption-side="top"}

## 	Identification and authentication
{: #contingency-plan-controls}

To better secure your resources, manage identification and authentication by inspecting user identification and authorization, identifier management, and authenticator management.

![Checkmark icon](../../icons/checkmark-icon.svg)

###  User Identification and Authorization IA-2
{: #identification-auth-goals}

To increase the security of your resources, manage user identification and authorization including network access to privileged and non-privileged accounts and remote access from a separate device.

####  User Identification and Authorization IA-2-0
{: #user-identification-auth-goals}

Improve the security of your resources by managing the IAM, VPN, and App ID settings that you want to set for user identification and authorization. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000001 | Check whether IBMid password policy requires at least one uppercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000002 | Check whether IBMid password policy requires at least one lowercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000003 | Check whether IBMid password policy requires at least one number
| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000004 | Check whether IBMid password policy requires minimum length of 12 characters | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000005 | Check whether IBMid password policy prevents password reuse below the minimum of # | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000006 | Check whether IBMid password may contain only printable ASCII characters (in the range 33 - 126) | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000007 | Check whether IBMid password policy contains spaces or any of the following characters: \;:("?)<> | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000008 | Check whether IBMid uses a password meter that coaches users to create strong passwords that exceed the minimum requirements| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000425 | Check whether VPN for VPC authentication is configured with a strong pre-shared key with at least # alphanumeric characters |   |
| 3000713 | Check whether App ID password strength regex is configured |   |
| 3000714 | Check whether App ID advanced password policies are enabled |   |
| 3000715 | Check whether App ID avoid password reuse policy is enabled |   |
| 3000716 | Check whether App ID lockout policy after failed # of sign-in attempts is enabled |   |
| 3000717 | Check whether App ID lockout policy after a maximum specified time is set to # minute(s) |   |
| 3000718 | Check whether App ID minimum period between password changes policy is set to greater than 0 |   |
| 3000719 | Check whether App ID password expiration policy is enabled |   |
| 3000720 | Check whether App ID prevent username in password policy is enabled |   |
{: caption="Table 30. User identification and authorization goals" caption-side="top"}

####  Identification and Authentication (Organizational Users) | Network Access to Privileged Accounts IA-2(1)
{: #privileged-identification-auth-goals}

To better secure your resources, configure the identification and authentication settings that are related to network access to privileged accounts.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000017 | Check whether multifactor authentication (MFA) is enabled at the account level |   |
| 3000723 | Check whether App ID multifactor authentication (MFA) is enabled for Cloud Directory users |   |
{: caption="Table 31. Network access to privileged accounts goals" caption-side="top"}

####   Identification and Authentication (Organizational Users) | Network Access to Non-Privileged Accounts IA-2(2)
{: #non-privileged-identification-auth-goals}

To better secure your resources, manage the identification and authentication settings that are related to network access to non-privileged accounts.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000017 | Check whether multifactor authentication (MFA) is enabled at the account level |   |
| 3000723 | Check whether App ID multifactor authentication (MFA) is enabled for Cloud Directory users |   |
{: caption="Table 32. Network access to non-privileged accounts goals" caption-side="top"}

####  Identification and Authentication (organizational Users) | Remote Access - Separate Device IA-2(11)
{: #remote-identification-auth-goals}

To improve the security, manage the identification and authentication settings that are related to remote access from separate devices.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000017 | Check whether multifactor authentication (MFA) is enabled at the account level |   |
| 3000723 | Check whether App ID multifactor authentication (MFA) is enabled for Cloud Directory users |   |
{: caption="Table 33. Remote access from separate device goals" caption-side="top"}

### Identifier Management IA-4
{: #identifier-management-goals}

Improve the security of your resources by configuring identifier management based on Auto Scale VPC instance group definitions. 

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000463 | Check whether Virtual Servers for VPC instances are identifable by the workload they are running based on the Auto Scale for VPC instance group definition |   |
| 3000464 | Check whether Application Load Balancer for VPC has application port of the workload that is identifiable by the Auto Scale for VPC instance group definition |   |
| 3000465 | Check whether Application Load Balancer for VPC has subnet identifiers of the workload that are identifiable by the Auto Scale for VPC instance group definition |   |
{: caption="Table 34. Identifier management goals" caption-side="top"}

### Authenticator management IA-5
{: #authenticator-management-goals}

To better secure your resources, manage password-based authentication and automated support for password strength of your authenticators, as well as the strength of mechanism for their intended use. 

#### Authenticator Management | Password-based Authentication IA-5(1)
{: #authenticator-management-password-goals}

Improve the security of your resources by managing your authenticators' password-based authentication.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000001 | Check whether IBMid password policy requires at least one uppercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000002 | Check whether IBMid password policy requires at least one lowercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000003 | Check whether IBMid password policy requires at least one number
| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000004 | Check whether IBMid password policy requires minimum length of 12 characters | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000005 | Check whether IBMid password policy prevents password reuse below the minimum of # | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000006 | Check whether IBMid password may contain only printable ASCII characters (in the range 33 - 126) | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000007 | Check whether IBMid password policy contains spaces or any of the following characters: \;:("?)<> | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000008 | Check whether IBMid uses a password meter that coaches users to create strong passwords that exceed the minimum requirements| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000425 | Check whether VPN for VPC authentication is configured with a strong pre-shared key with at least # alphanumeric characters |   |
| 3000713 | Check whether App ID password strength regex is configured |   |
| 3000714 | Check whether App ID advanced password policies are enabled |   |
| 3000715 | Check whether App ID avoid password reuse policy is enabled |   |
| 3000716 | Check whether App ID lockout policy after failed # of sign-in attempts is enabled |   |
| 3000717 | Check whether App ID lockout policy after a maximum specified time is set to # minute(s) |   |
| 3000718 | Check whether App ID minimum period between password changes policy is set to greater than 0 |   |
| 3000719 | Check whether App ID password expiration policy is enabled |   |
| 3000720 | Check whether App ID prevent username in password policy is enabled |   |
{: caption="Table 35. Password-based authentication goals" caption-side="top"}

#### Authenticator Management | Automated Support for Password Strength Determination IA-5(4)
{: #authenticator-management-automated-goals}

To better secure your resources, manage your authenticators' automated support for password strength determination.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000001 | Check whether IBMid password policy requires at least one uppercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000002 | Check whether IBMid password policy requires at least one lowercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000003 | Check whether IBMid password policy requires at least one number
| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000004 | Check whether IBMid password policy requires minimum length of 12 characters | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000005 | Check whether IBMid password policy prevents password reuse below the minimum of # | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000006 | Check whether IBMid password may contain only printable ASCII characters (in the range 33 - 126) | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000007 | Check whether IBMid password policy contains spaces or any of the following characters: \;:("?)<> | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000008 | Check whether IBMid uses a password meter that coaches users to create strong passwords that exceed the minimum requirements| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000425 | Check whether VPN for VPC authentication is configured with a strong pre-shared key with at least # alphanumeric characters |   |
| 3000713 | Check whether App ID password strength regex is configured |   |
| 3000714 | Check whether App ID advanced password policies are enabled |   |
| 3000715 | Check whether App ID avoid password reuse policy is enabled |   |
| 3000716 | Check whether App ID lockout policy after failed # of sign-in attempts is enabled |   |
| 3000717 | Check whether App ID lockout policy after a maximum specified time is set to # minute(s) |   |
| 3000718 | Check whether App ID minimum period between password changes policy is set to greater than 0 |   |
| 3000719 | Check whether App ID password expiration policy is enabled |   |
| 3000720 | Check whether App ID prevent username in password policy is enabled |   |
{: caption="Table 36. Password strength determination goals" caption-side="top"}

#### Ensuring that authenticators have sufficient strength of mechanism for their intended use IA-5(c)
{: #authenticator-management-automated-goals}

Increase the security of your resources, by ensuring that your authenticators have sufficient strength of mechanism for their intended use.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000001 | Check whether IBMid password policy requires at least one uppercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000002 | Check whether IBMid password policy requires at least one lowercase letter | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000003 | Check whether IBMid password policy requires at least one number
| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000004 | Check whether IBMid password policy requires minimum length of 12 characters | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000005 | Check whether IBMid password policy prevents password reuse below the minimum of # | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000006 | Check whether IBMid password may contain only printable ASCII characters (in the range 33 - 126) | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000007 | Check whether IBMid password policy contains spaces or any of the following characters: \;:("?)<> | ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000008 | Check whether IBMid uses a password meter that coaches users to create strong passwords that exceed the minimum requirements| ![Checkmark icon](../../icons/checkmark-icon.svg)  |
| 3000425 | Check whether VPN for VPC authentication is configured with a strong pre-shared key with at least # alphanumeric characters |   |
| 3000713 | Check whether App ID password strength regex is configured |   |
| 3000714 | Check whether App ID advanced password policies are enabled |   |
| 3000715 | Check whether App ID avoid password reuse policy is enabled |   |
| 3000716 | Check whether App ID lockout policy after failed # of sign-in attempts is enabled |   |
| 3000717 | Check whether App ID lockout policy after a maximum specified time is set to # minute(s) |   |
| 3000718 | Check whether App ID minimum period between password changes policy is set to greater than 0 |   |
| 3000719 | Check whether App ID password expiration policy is enabled |   |
| 3000720 | Check whether App ID prevent username in password policy is enabled |   |
{: caption="Table 37. Sufficient strength of mechanism goals" caption-side="top"}

## Risk assessment
{: #risk-assessment-controls}

To better secure your resources, scan your system and applications for vulnerabilities. 

![Checkmark icon](../../icons/checkmark-icon.svg)

### Vulnerability scanning RA-5
{: #vulnerability-scanning-goals}

Reduce the risk that your resources are exposed to by scanning them for vulnerabilities.

#### Scans for vulnerabilities in the information system and hosted applications in organization-defined frequency and/or randomly in accordance with organization-defined process and when new vulnerabilities potentially affecting the system/applications ... RA-5(a)
{: #vulnerabilities-organization-process-goals}

Examine the vulnerabilities that your systems and hosted applications are exposed to at a frequency defined by your organization following the process you set in place.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000601 | Check whether Container Registry Vulnerability Advisor scans for critical or high vulnerabilities in the system at least every # day(s) |   |
| 3000602 | Check whether Security Insights sends alerts for critical, high, or medium vulnerabilities for images in Container Registry |   |
| 3000611 | Check whether Container Registry Vulnerability Advisor scans images for OS vulnerability detection |   |
| 3000901 | Check whether OpenShift worker nodes are updated to the latest image to ensure patching of vulnerabilities |   |
{: caption="Table 38. Vulnerability scanning goals" caption-side="top"}

## 	System and Services Acquisition
{: #system-acquisition-controls}

To improve the security of your resources, manage the acquisition of your system and services by configuring the system development life cycle, acquisition process, and external system services.

![Checkmark icon](../../icons/checkmark-icon.svg)

### System Development Life Cycle SA-3
{: #system-development-goals}

Configure the development life cycle of your system to better secure your resources.

#### Employs malicious code protection mechanisms at information system entry and exit points to detect and eradicate malicious code SA-3(a) 
{: #code-protection-goals}

Improve the security of your resources by detecting and eradicating malicious code by using malicious code protection mechanisms at entry and exit points of your information system.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000462 | Check whether Virtual Servers for VPC is provisioned from customer-defined list of images |   |
| 3000907 | Check whether OpenShift version is up-to-date |   |
{: caption="Table 39. Malicious code protection mechanism goals" caption-side="top"}

### Acquisition Process SA-4
{: #acquisition-process-goals}

Configure the acquisition process of your system to better secure your resources by managing the security and privacy, strength of mechanism, and security and privacy assurance requirements.

#### Security and privacy functional requirements SA-4(a) 
{: #security-privacy-requirement-goals}

To improve the security of your resources, ensure that your systems meet the security and privacy functional requirements.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000047 | Check whether provisioned services are IAM enabled |   |
{: caption="Table 40. Security and privacy functional requirements goals" caption-side="top"}

#### Strength of mechanism requirements SA-4(b) 
{: #strength-mechanism-requirement-goals}

To increase the security of your resources, inspect your systems to verify that they meet the password strength of mechanism requirements.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000047 | Check whether provisioned services are IAM enabled |   |
{: caption="Table 41. Strength of mechanism requirements goals" caption-side="top"}

#### Security and privacy assurance requirements SA-4(c) 
{: #security-privacy-assurance-requirement-goals}

To improve the security of your resources, ensure that your systems meet the security and privacy assurance requirements.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000047 | Check whether provisioned services are IAM enabled |   |
{: caption="Table 42. Security and privacy assurance requirements goals" caption-side="top"}

### External System Services SA-9 
{: #external-system-goals}

To improve the security of your resources, configure your external system services.

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000047 | Check whether provisioned services are IAM enabled |   |
{: caption="Table 43. External system services goals" caption-side="top"}

## 	System and Communication Protection
{: #system-communication-protection-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### Application Partitioning SC-2
{: #system-development-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000015 | Check whether IAM users are attached to at least one access group |   |
| 3000016 | Check whether IAM policies for users are attached only to groups or roles |   |
| 3000035 | Check whether account service access is managed only by IAM access groups |   |
| 3000533 | Check whether Hyper Protect DBaaS for MongoDB service access is managed only by IAM access groups |   |
| 3000541 | Check whether Hyper Protect DBaaS for PostgreSQL service access is managed only by IAM access groups |   |
| 3000639 | Check whether Container Registry service access is managed only by IAM access groups |   |
| 3000707 | Check whether App ID user profile updates from client apps is disabled |   |
| 3000708 | Check whether App ID Cloud Directory users aren't able to update their own accounts |   |
| 3000709 | Check whether App ID Cloud Directory users aren't able to self-sign up to applications |   |
| 3000711 | Check whether App ID social identity providers are disabled |   |
| 3000712 | Check whether App ID anonymous authentication is disabled |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Boundary Protection SC-7
{: #boundary-protection-goals}

XXXXXXXXXXX

#### Boundary Protection SC-7-0
{: #boundary-protect-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000020 | Check whether authorized IP ranges are configured by the account owner |   |
| 3000022 | Check whether Cloud Object Storage public access is disabled in IAM settings (not applicable to ACLs managed using S3 APIs) |   |
| 3000105 | Check whether Cloud Object Storage is accessible only by using private endpoints |   |
| 3000107 | Check whether Cloud Object Storage network access is restricted to a specific IP range |   |
| 3000306 | Check whether Event Streams is accessible only by using private endpoints |   |
| 3000307 | Check whether Event Streams network access is restricted to a specific IP range |   |
| 3000404 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to SSH port |   |
| 3000405 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to RDP port |   |
| 3000406 | Check whether Virtual Private Cloud (VPC) has no rules in the default security group |   |
| 3000410 | Check whether Virtual Private Cloud (VPC) security groups have no inbound ports open to the internet (0.0.0.0/0) |   |
| 3000411 | Check whether Virtual Private Cloud (VPC) security groups have no outbound ports open to the internet (0.0.0.0/0) |   |
| 3000412 | Check whether all virtual server instances have at least one Virtual Private Cloud (VPC) security group attached |   |
| 3000413 | Check whether all network interfaces of a virtual server instance have at least one Virtual Private Cloud (VPC) security group attached |   |
| 3000414 | Check whether Direct Link (2.0) allows no cross account connection approvals at the account level |   |
| 3000415 | Check whether Direct Link (2.0) allows no cross account connection requests at the account level |   |
| 3000416 | Check whether Transit Gateway allows no cross account connection approvals at the account level |   |
| 3000417 | Check whether Transit Gateway allows no cross account connection requests at the account level |   |
| 3000427 | Check whether Application Load Balancer for VPC has public access disabled |   |
| 3000428 | Check whether Application Load Balancer for VPC is configured with multiple members in the pool |   |
| 3000429 | Check whether Application Load Balancer for VPC listener is configured with default pool |   |
| 3000441 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to SSH port |   |
| 3000442 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to RDP port |   |
| 3000444 | Check whether Security Groups for VPC contains no outbound rules in security groups that specify source IP 8.8.8.8/32 to DNS port |   |
| 3000445 | Check whether Security Groups for VPC doesn't allow SSH for the default security group |   |
| 3000446 | Check whether Security Groups for VPC doesn't allow PING for the default security group |   |
| 3000447 | Check whether Virtual Private Cloud (VPC) classic access is disabled |   |
| 3000448 | Check whether Virtual Private Cloud (VPC) has no public gateways attached at the time of provisioning |   |
| 3000449 | Check whether Virtual Private Cloud (VPC) has no public gateways attached |   |
| 3000451 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to any port |   |
| 3000452 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow egress from 0.0.0.0/0 to any port |   |
| 3000453 | Check whether Virtual Servers for VPC instance has the minimum # interfaces |   |
| 3000454 | Check whether Virtual Servers for VPC instance doesn't have a floating IP |   |
| 3000455 | Check whether Virtual Servers for VPC instance has all interfaces with IP-spoofing disabled |   |
| 3000456 | Check whether Virtual Servers for VPC is in a resource group other than "Default" |   |
| 3000467 | Check whether Virtual Private Cloud (VPC) has no subnet with public gateway attached |   |
| 3000468 | Check whether Virtual Private Cloud (VPC) is configured with public gateways that are provisionable only within permitted zones |   |
| 3000469 | Check whether Application Load Balancer for VPC is configured with at least one VPC security group |   |
| 3000510 | Check whether Hyper Protect Crypto Services is accessible only through private endpoints |   |
| 3000526 | Check whether Hyper Protect DBaaS for MongoDB is accessible only using private endpoints |   |
| 3000534 | Check whether Hyper Protect DBaaS for PostgreSQL is accessible only using private endpoints |   |
| 3000704 | Check whether App ID redirect URIs are not using localhost or 127.0.0.1 |   |
| 3000705 | Check whether App ID redirect URIs are not using wildcards (*) |   |
| 3000902 | Check whether OpenShift clusters are accessible only by using private endpoints |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Boundary Protection | Deny by Default - Allow by Exception SC-7(5)
{: #boundary-protect-deny-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000020 | Check whether authorized IP ranges are configured by the account owner |   |
| 3000022 | Check whether Cloud Object Storage public access is disabled in IAM settings (not applicable to ACLs managed using S3 APIs) |   |
| 3000105 | Check whether Cloud Object Storage is accessible only by using private endpoints |   |
| 3000107 | Check whether Cloud Object Storage network access is restricted to a specific IP range |   |
| 3000306 | Check whether Event Streams is accessible only by using private endpoints |   |
| 3000307 | Check whether Event Streams network access is restricted to a specific IP range |   |
| 3000404 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to SSH port |   |
| 3000405 | Check whether Virtual Private Cloud (VPC) security groups have no inbound rules that specify source IP 0.0.0.0/0 to RDP port |   |
| 3000406 | Check whether Virtual Private Cloud (VPC) has no rules in the default security group |   |
| 3000410 | Check whether Virtual Private Cloud (VPC) security groups have no inbound ports open to the internet (0.0.0.0/0) |   |
| 3000411 | Check whether Virtual Private Cloud (VPC) security groups have no outbound ports open to the internet (0.0.0.0/0) |   |
| 3000412 | Check whether all virtual server instances have at least one Virtual Private Cloud (VPC) security group attached |   |
| 3000413 | Check whether all network interfaces of a virtual server instance have at least one Virtual Private Cloud (VPC) security group attached |   |
| 3000414 | Check whether Direct Link (2.0) allows no cross account connection approvals at the account level |   |
| 3000415 | Check whether Direct Link (2.0) allows no cross account connection requests at the account level |   |
| 3000416 | Check whether Transit Gateway allows no cross account connection approvals at the account level |   |
| 3000417 | Check whether Transit Gateway allows no cross account connection requests at the account level |   |
| 3000427 | Check whether Application Load Balancer for VPC has public access disabled |   |
| 3000428 | Check whether Application Load Balancer for VPC is configured with multiple members in the pool |   |
| 3000429 | Check whether Application Load Balancer for VPC listener is configured with default pool |   |
| 3000441 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to SSH port |   |
| 3000442 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to RDP port |   |
| 3000444 | Check whether Security Groups for VPC contains no outbound rules in security groups that specify source IP 8.8.8.8/32 to DNS port |   |
| 3000445 | Check whether Security Groups for VPC doesn't allow SSH for the default security group |   |
| 3000446 | Check whether Security Groups for VPC doesn't allow PING for the default security group |   |
| 3000447 | Check whether Virtual Private Cloud (VPC) classic access is disabled |   |
| 3000448 | Check whether Virtual Private Cloud (VPC) has no public gateways attached at the time of provisioning |   |
| 3000449 | Check whether Virtual Private Cloud (VPC) has no public gateways attached |   |
| 3000451 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow ingress from 0.0.0.0/0 to any port |   |
| 3000452 | Check whether Virtual Private Cloud (VPC) network access control lists don't allow egress from 0.0.0.0/0 to any port |   |
| 3000453 | Check whether Virtual Servers for VPC instance has the minimum # interfaces |   |
| 3000454 | Check whether Virtual Servers for VPC instance doesn't have a floating IP |   |
| 3000455 | Check whether Virtual Servers for VPC instance has all interfaces with IP-spoofing disabled |   |
| 3000456 | Check whether Virtual Servers for VPC is in a resource group other than "Default" |   |
| 3000467 | Check whether Virtual Private Cloud (VPC) has no subnet with public gateway attached |   |
| 3000468 | Check whether Virtual Private Cloud (VPC) is configured with public gateways that are provisionable only within permitted zones |   |
| 3000469 | Check whether Application Load Balancer for VPC is configured with at least one VPC security group |   |
| 3000510 | Check whether Hyper Protect Crypto Services is accessible only through private endpoints |   |
| 3000526 | Check whether Hyper Protect DBaaS for MongoDB is accessible only using private endpoints |   |
| 3000534 | Check whether Hyper Protect DBaaS for PostgreSQL is accessible only using private endpoints |   |
| 3000704 | Check whether App ID redirect URIs are not using localhost or 127.0.0.1 |   |
| 3000705 | Check whether App ID redirect URIs are not using wildcards (*) |   |
| 3000902 | Check whether OpenShift clusters are accessible only by using private endpoints |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Transmission confidentiality and Integrity SC-8
{: #transmission-confidentiality-goals}

XXXXXXXXXXX

#### Transmission confidentiality and Integrity SC-8-0
{: #transmission-integrity-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000103 | Check whether Cloud Object Storage is accessible only through HTTPS |   |
| 3000104 | Check whether Cloudant is accessible only through HTTPS |   |
| 3000407 | Check whether Virtual Private Cloud (VPC) is configured with at least TLS v1.2 for all inbound traffic through a load balancer |   |
| 3000431 | Check whether Application Load Balancer for VPC has a health check protocol that is either HTTP or HTTPS |   |
| 3000432 | Check whether Application Load Balancer for VPC pool uses the HTTPS protocol for HTTPS listeners |   |
| 3000433 | Check whether Application Load Balancer for VPC is configured to convert HTTP client requests to HTTPS |   |
| 3000434 | Check whether Application Load Balancer for VPC uses HTTPS (SSL & TLS) instead of HTTP |   |
| 3000701 | Check whether App ID webhooks are using HTTPS only |   |
| 3000702 | Check whether App ID email dispatchers are using HTTPS only |   |
| 3000703 | Check whether App ID redirect URIs are using HTTPS only |   |
| 3000906 | Check whether OpenShift Ingress is configured with at least TLS v1.2 for all inbound traffic |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Transmission Confidentiality and Integrity | Cryptographic or Alternate Physical Protection SC-8(1)
{: #transmission-integrity-protection-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000103 | Check whether Cloud Object Storage is accessible only through HTTPS |   |
| 3000104 | Check whether Cloudant is accessible only through HTTPS |   |
| 3000407 | Check whether Virtual Private Cloud (VPC) is configured with at least TLS v1.2 for all inbound traffic through a load balancer |   |
| 3000431 | Check whether Application Load Balancer for VPC has a health check protocol that is either HTTP or HTTPS |   |
| 3000432 | Check whether Application Load Balancer for VPC pool uses the HTTPS protocol for HTTPS listeners |   |
| 3000433 | Check whether Application Load Balancer for VPC is configured to convert HTTP client requests to HTTPS |   |
| 3000434 | Check whether Application Load Balancer for VPC uses HTTPS (SSL & TLS) instead of HTTP |   |
| 3000701 | Check whether App ID webhooks are using HTTPS only |   |
| 3000702 | Check whether App ID email dispatchers are using HTTPS only |   |
| 3000703 | Check whether App ID redirect URIs are using HTTPS only |   |
| 3000906 | Check whether OpenShift Ingress is configured with at least TLS v1.2 for all inbound traffic |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Cryptographic Key Establishment and Management SC-12
{: #cryptographic-establishment-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000027 | Check whether permissions for API key creation are limited and configured in IAM settings for the account owner |   |
| 3000234 | Check whether Hyper Protect Crypto Services instance is enabled with a dual authorization deletion policy |   |
| 3000235 | Check whether Hyper Protect Crypto Services encryption keys that are generated by the service are rotated automatically at least every # months |   |
| 3000903 | Check whether OpenShift cluster has image pull secrets enabled |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Cryptographic Protection SC-13
{: #cryptographic-protection-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000103 | Check whether Cloud Object Storage is accessible only through HTTPS |   |
| 3000104 | Check whether Cloudant is accessible only through HTTPS |   |
| 3000108 | Check whether Cloud Object Storage is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000407 | Check whether Virtual Private Cloud (VPC) is configured with at least TLS v1.2 for all inbound traffic through a load balancer |   |
| 3000419 | Check whether VPN for VPC has Internet Key Exchange (IKE) policy encryption that is not set to "triple_des" |   |
| 3000420 | Check whether VPN for VPC has Internet Key Exchange (IKE) policy authentication that is set to minimum "sha256" |   |
| 3000421 | Check whether VPN for VPC has a Diffie-Hellman group set to at least group # |   |
| 3000422 | Check whether VPN for VPC has IPsec policy encryption that is not set to "triple_des" |   |
| 3000423 | Check whether VPN for VPC has IPsec policy authentication that is set to minimum "sha256" |   |
| 3000424 | Check whether VPN for VPC has an IPsec policy that does not have Perfect Forward Secrecy (PFS) disabled |   |
| 3000426 | Check whether VPN for VPC has a Dead Peer Detection policy that is set to "restart" |   |
| 3000431 | Check whether Application Load Balancer for VPC has a health check protocol that is either HTTP or HTTPS |   |
| 3000432 | Check whether Application Load Balancer for VPC pool uses the HTTPS protocol for HTTPS listeners |   |
| 3000433 | Check whether Application Load Balancer for VPC is configured to convert HTTP client requests to HTTPS |   |
| 3000434 | Check whether Application Load Balancer for VPC uses HTTPS (SSL & TLS) instead of HTTP |   |
| 3000437 | Check whether Block Storage for VPC is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000438 | Check whether OS disks are encrypted with customer-managed keys |   |
| 3000439 | Check whether data disks are encrypted with customer-managed keys |   |
| 3000440 | Check whether unattached disks are encrypted with customer-managed keys |   |
| 3000458 | Check whether Virtual Servers for VPC boot volumes are enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000460 | Check whether Virtual Servers for VPC data volumes are enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000528 | Check whether Hyper Protect DBaaS for MongoDB is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000536 | Check whether Hyper Protect DBaaS for PostgreSQL is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000701 | Check whether App ID webhooks are using HTTPS only |   |
| 3000702 | Check whether App ID email dispatchers are using HTTPS only |   |
| 3000703 | Check whether App ID redirect URIs are using HTTPS only |   |
| 3000706 | Check whether App ID user data is encrypted |   |
| 3000906 | Check whether OpenShift Ingress is configured with at least TLS v1.2 for all inbound traffic |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Session Authenticity SC-23
{: #session-authenticity-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000103 | Check whether Cloud Object Storage is accessible only through HTTPS |   |
| 3000104 | Check whether Cloudant is accessible only through HTTPS |   |
| 3000407 | Check whether Virtual Private Cloud (VPC) is configured with at least TLS v1.2 for all inbound traffic through a load balancer |   |
| 3000431 | Check whether Application Load Balancer for VPC has a health check protocol that is either HTTP or HTTPS |   |
| 3000432 | Check whether Application Load Balancer for VPC pool uses the HTTPS protocol for HTTPS listeners |   |
| 3000433 | Check whether Application Load Balancer for VPC is configured to convert HTTP client requests to HTTPS |   |
| 3000434 | Check whether Application Load Balancer for VPC uses HTTPS (SSL & TLS) instead of HTTP |   |
| 3000701 | Check whether App ID webhooks are using HTTPS only |   |
| 3000702 | Check whether App ID email dispatchers are using HTTPS only |   |
| 3000703 | Check whether App ID redirect URIs are using HTTPS only |   |
| 3000906 | Check whether OpenShift Ingress is configured with at least TLS v1.2 for all inbound traffic |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Protection of Information at Rest SC-28
{: #protection-information-rest-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000108 | Check whether Cloud Object Storage is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000437 | Check whether Block Storage for VPC is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000438 | Check whether OS disks are encrypted with customer-managed keys |   |
| 3000439 | Check whether data disks are encrypted with customer-managed keys |   |
| 3000440 | Check whether unattached disks are encrypted with customer-managed keys |   |
| 3000458 | Check whether Virtual Servers for VPC boot volumes are enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000460 | Check whether Virtual Servers for VPC data volumes are enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000528 | Check whether Hyper Protect DBaaS for MongoDB is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000536 | Check whether Hyper Protect DBaaS for PostgreSQL is enabled with customer-managed encryption and Keep Your Own Key (KYOK) |   |
| 3000706 | Check whether App ID user data is encrypted |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

## 	System and Information Integrity
{: #system-information-integrity-controls}

xxxxxxxxx

![Checkmark icon](../../icons/checkmark-icon.svg)

### Flaw Remediation SI-2
{: #flaw-remediation-goals}

xxxxxxxx

#### Flaw Remediation | Automated Flaw Remediation Status SI-2(2)
{: #flaw-remediation-status-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000601 | Check whether Container Registry Vulnerability Advisor scans for critical or high vulnerabilities in the system at least every # day(s) |   |
| 3000611 | Check whether Container Registry Vulnerability Advisor scans images for OS vulnerability detection |   |
| 3000901 | Check whether OpenShift worker nodes are updated to the latest image to ensure patching of vulnerabilities |   |
| 3000907 | Check whether OpenShift version is up-to-date |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

### Information System Monitoring SI-4
{: #system-monitoring-goals}

xxxxxxxx

#### Monitors the information system to detect SI-4(a)
{: #system-monitor-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
| 3000408 | Check whether Flow Logs for VPC are enabled |   |
| 3000430 | Check whether Application Load Balancer for VPC has health check configured when created |   |
| 3000466 | Check whether Application Load Balancer for VPC is attached with an Auto Scale for VPC instance group provided with health check |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Identifies unauthorized use of the information system through organization-defined techniques and methods SI-4(b)
{: #system-technique-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
 3000408 | Check whether Flow Logs for VPC are enabled |   |
| 3000430 | Check whether Application Load Balancer for VPC has health check configured when created |   |
| 3000466 | Check whether Application Load Balancer for VPC is attached with an Auto Scale for VPC instance group provided with health check |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

#### Deploys monitoring devices: (i) strategically within the information system to collect organization-determined essential information; and (ii) at ad hoc locations within the system to track specific types of transactions of interest to the organization SI-4(c)
{: #system-technique-goals}

xxxxxxxx

| ID | Goal | Met by default |
| -- | ---- | -------------- | 
 3000408 | Check whether Flow Logs for VPC are enabled |   |
| 3000430 | Check whether Application Load Balancer for VPC has health check configured when created |   |
| 3000466 | Check whether Application Load Balancer for VPC is attached with an Auto Scale for VPC instance group provided with health check |   |
{: caption="Table 1. Best Practices predefined profiles" caption-side="top"}

