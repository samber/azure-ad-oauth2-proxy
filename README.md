
# Proof of concept

Adding a proxy in front of an internal corp. application, using Azure AD identity platform.

Application access will be limited to a Azure AD role.

## Setup

1- Register a new webapp here => https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app
2- Copy Tenant ID + Client ID to `docker-compose.yml`
3- Navigate to the "Certificates & secrets" page and create a new "client secret". Paste-it to `docker-compose.yml`.
4- Navigate to "Authentication" page and set the redirect url to `http://localhost:8080/oauth2/callback`
5- Navigate to "Manifest" page and set `groupMembershipClaims` to `All`. If you have an Azure AD P1

⚠️  For prod environment, remove the `-cookie-secure=false` argument ;)

## Epitech

This has been tested for Epitech internal tools.

Epitech does not manage user groups and permissions in AzureAD, but over school intranet.

I wrote a small provider for Epitech Intranet here: https://github.com/Epitech/oauth2_proxy
