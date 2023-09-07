# Single Sign-On for Claims Automation (formerly Casefunnel)
Single sign-on (SSO) enables users to login to Claims Automation using your organisation's preferred identity provider. We support any provider that supports the OpenID Connect protocol. This includes, but not limited to, Azure AD & Okta.

Once configured correctly we will provide you with an initiate login URI. This will be used by your users and will trigger the authentication flow.

## How-to configure Okta for SSO
**Note:** Before proceeding please ensure you have API access management enabled on your account. This is enabled if you can access the following menu in your Okta Admin Dashboard: `Security > API > Authorization Servers (tab)`.

![API setting page showing Authorization Servers page](Okta/Okta-API-AuthServer-Option.png)

[Follow our guide](Okta/Okta.md)

## How-to configure Azure AD for SSO
A guide on configuring a new application: [Quickstart: Register an app in the Microsoft identity platform - Microsoft Entra | Microsoft Learn](https://learn.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)
*	Redirect URI = https://uk.casefunnel.io/oidc/authorize
*	From the Configure platform settings please select Web
*	From the Add credentials follow instructions Add a client secret
*	Please send us the Client\Application ID & the new client secret
*	Please can you also send across the following two endpoints:
  *	Back in App registrations, select and open the new registration.
  * Whilst the Overview option is selected you should see a tab called Endpoints
    *	OAuth 2.0 authorization endpoint (v2)
    *	OpenID Connect metadata document
*	You may need to configure the admin consent
*	Please select API permissions on the left hand side menu
*	Under configured permissions click the “Grant admin consent for X” (where X is the name of your Azure AD instance)
*	In the list of permissions the final column should update to say “Granted for X” (where X is the name of your Azure AD instance)

This is url you will need to initiate the authentication flow: https://uk.casefunnel.io/oidc/signin/XX once everything is configured
