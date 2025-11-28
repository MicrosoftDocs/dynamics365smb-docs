---
title: Use SMTP for email in a multitenant environment
description: 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: get-started
ms.search.keywords: SMTP, mail, Microsoft 365
ms.date: 11/26/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Use SMTP for email in a multitenant environment

This article explains how to configure your Microsoft 365 tenant so that [!INCLUDE [prod_short](includes/prod_short.md)] can send emails through the SMTP connector using OAuth 2.0 (client credentials flow).

This article also covers how to enable cross-tenant scenarios. For example, where you have an app registration in Azure portal in one Microsoft Entra tenant but you use it to send emails from another tenant.

In the following procedures, we refer to the Microsoft Entra tenant where you have the app registration as "Tenant A," and the tenant where you use it for SMTP as "Tenant B." Tenant B contains your [!INCLUDE [prod_short](includes/prod_short.md)].

> [!IMPORTANT]
> Exchange Online is deprecating use of Basic authentication for SMTP. This change doesn't affect tenants that currently use SMTP AUTH. However, we recommend that you use the latest version, and set up OAuth 2.0 authentication for SMTP. If you can't set up OAuth 2.0 authentication, we encourage you to explore non-Microsoft alternatives if you want to use SMTP email in earlier versions.
>
> We currently don't support certificate-based authentication.

The following list gives an overview of the steps to use OAuth 2.0 with the SMTP connector. This article describes each step.

1. [Create an application registration in Azure portal](#create-an-application-registration-in-azure-portal)
1. [Grant API permissions](#grant-api-permissions)
1. [Create a client secret or certificate](#create-a-client-secret-or-certificate)
1. [Register the service principal in Exchange Online](#register-the-service-principal-in-exchange-online)
1. [Grant the app permission to send as your mailbox](#grant-the-app-permission-to-send-as-your-mailbox)
1. [Verify your SMTP OAuth configuration](#verify-your-smtp-oauth-configuration)

## Prerequisites

Before you start, ensure that you have:

- A Microsoft 365 tenant with Exchange Online.  
- Global Administrator or Exchange Administrator permissions.  
- A mailbox, for example, service@yourdomain.com, that you use as the "From" address.  
- A [!INCLUDE [prod_short](includes/prod_short.md)] online or on-premises environment.
- (Optional) Python 3.10+ or any other environment that supports OAuth-based SMTP authentication for testing.

## Create an application registration in Azure portal

The first step is to create an app registration for the app you have in "Tenant A" in Microsoft Entra ID. The app registration lets [!INCLUDE [prod_short](includes/prod_short.md)] send email from a mailbox that's in another Microsoft Entra tenant.

1. Go to [Azure portal](https://portal.azure.com).
1. Under **Azure services**, choose **Microsoft Entra ID**.
1. In the navigation pane, choose **App registrations**.
1. On the **App registrations** page, choose **New registration**.
1. On the **Register an application** page, fill in the fields as follows:

    1. In the **Name** field, enter a name for your app. For example, **SMTP_OAuth_App**.
    1. Under **Supported account types**, choose **Accounts in any organizational directory (Any Microsoft Entra ID tenant - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)**. This setting is required for cross-tenant consent.
    1. Under **Redirect URI (optional)**, for the platform, choose **Web**, and then enter the URI.

1. Choose **Register**.

> [!NOTE]
> After you register the app in Microsoft Entra ID, make a note of the following information. You need it in a later step.
>
> |Field  |Example  |Description  |
> |---------|---------|---------|
> |Application (client) ID | 11111111-2222-3333-4444-555555555555 |  App ID       |
> |Directory (tenant) ID   | 11111111-2222-3333-4444-555555555555 | Tenant ID     |
> |Object ID   | 11111111-2222-3333-4444-555555555555       | Service Principal ID|

## Grant API permissions

The next step is to give the app permission to send email.

1. In Azure portal, on the app page, choose **API permissions**, and then choose **Add a permission**.
1. Choose **APIS my organization uses**.
1. Search for **Office 365 Exchange Online**.
1. Choose **Application permissions**.
1. Expand **SMTP**, and then choose **SMTP.SendAsApp**.
1. Choose **Add permissions**.
1. Double-check that **SMTP.SendAsApp** has a green checkmark.

## Create a client secret or certificate

1. In Azure portal, on the app page, choose **Certificates & secrets**.
1. In the **Client secret** field, choose **New client secret**, give it a name and define an expiry period.

   > [!IMPORTANT]
   > Make a note of the **Client Secret Value**. The value displays only one time, and you need it to generate tokens.

## Register the service principal in Exchange Online

To learn more about the service principal, go to [Register a Microsoft Entra app and create a service principal](/entra/identity-platform/howto-create-service-principal-portal).

1. In PowerShell, use the following link to consent. Replace the tenant ID and client ID (App ID) with the values for your "Tenant B."

   https://login.microsoftonline.com/\<TenantB_ID>/oauth2/v2.0/authorize?client_id=\<Client_ID>&scope=https://graph.microsoft.com/.default&response_type=code&response_mode=query&prompt=consent

1. In Microsoft Entra admin center, go to **Enterprise apps**, find your app, and then copy the value in the **Object ID** field. The object ID is used as the service ID in the command in the next step in this process.
1. To create a new service principal in your tenant, run the following command in PowerShell as an administrator.

   ```powershell

   Install-Module ExchangeOnlineManagement -Scope CurrentUser

   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -UserPrincipalName yourname@yourdomain.com

   $AppId     = \<your app ID>
   $ServiceId = \<your service ID> # The object id of the enterprise app 
   $Display   = "SMTP_OAuth_App" # The name of the service principal you want to create

   New-ServicePrincipal -AppId $AppId -ServiceId $ServiceId -DisplayName $Display

   ```

> [!NOTE]
> If a service principal already exists, the command might show an error, but you can safely ignore it.

## Grant the app permission to send as your mailbox

1. In PowerShell, run the following command to grant the app permission to send email from your mailbox.

```powershell

$sp = Get-ServicePrincipal | Where-Object { $_.AppId -eq "{AppID}" }

 # Replace this with the mailbox you use as the from_addr / user= in XOAUTH2.
$Mailbox = "someuser@xxx.onmicrosoft.com"

Add-MailboxPermission -Identity $Mailbox `
    -User $sp.ObjectId `
    -AccessRights FullAccess `
    -AutoMapping:$false

 # If you have multiple users, create a group for them and then assign them.
Get-DistributionGroupMember "Your group name" |
  ForEach-Object {
      Add-MailboxPermission -$_.PrimarySmtpAddress `
          -User $sp.ObjectId `
          -AccessRights FullAccess `
          -AutoMapping:$false
  }

```

1. To verify the permissions, run the following command:

   ```powershell
   Get-MailboxPermission  -Identity $Mailbox | ? {$_.User -eq $Display}
   ```

   You should have either **AccessRights**, **SendAs**, or both.

## Verify your SMTP OAuth configuration

1. In PowerShell, run the following command to verify your SMTP configuration:

   ```powershell
   
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -UserPrincipalName admin@yourtenant.onmicrosoft.com
   Get-CASMailbox -Identity admin@yourtenant.onmicrosoft.com | Select SmtpClientAuthenticationDisabled

   # If the output is false, it's enabled. But if it's true, SMTP is disabled and you must run the following command to enable it:

   Set-CASMailbox -Identity admin@yourtenant.onmicrosoft.com -SmtpClientAuthenticationDisabled $false

   ```

1. Optionally, if you want to enable SMTP for your entire organization level, run the following command:

   ```powershell

   Get-TransportConfig | Select SmtpClientAuthenticationDisabled

   # If the output is false it's enabled. If it's true, SMTP is disabled and you must run the following command to enable it:

   Set-TransportConfig -SmtpClientAuthenticationDisabled $false

   ```

1. To verify that OAuth 2.0 is globally enabled for SMTP, run the following command:

   ```powershell

   Get-TransportConfig | fl SmtpClientAuthenticationDisabled,OAuth2ClientProfileEnabled

   ```

   The following are the expected output:

   - `SmtpClientAuthenticationDisabled` is `False`.
   - `OAuth2ClientProfileEnabled` is `True`.

   If `SmtpClientAuthenticationDisabled` is `True`, SMTP _isn't_ enabled. To enable it, run the following command:

   ```powershell 

   Set-TransportConfig -SmtpClientAuthenticationDisabled $false

   ```

## Set up the SMTP connector in Business Central

To learn more about the SMTP connector, go to [Set up email](admin-how-setup-email.md).

1. In [!INCLUDE [prod_short](includes/prod_short.md)], [!INCLUDE [open-search-lowercase](includes/open-search-lowercase.md)], enter **Assisted Setup**, and then choose the related link.
1. Choose **Set up SMTP Account**.
1. Fill in the fields as described in the following table.

   |Field  |Example value  |Notes  |
   |---------|---------|---------|
   |Server     | smtp.office365.com        |         |
   |Server Port     |  587       |         |
   |Authentication Type     | OAuth 2.0        |         |
   |Client ID | 11111111-2222-3333-4444-555555555555 | The application ID from Tenant A |
   |Client Secret     |         | The secret generated in the app.        |
   |Tenant ID     | 11111111-2222-3333-4444-555555555555  | The ID of Tenant B, where you host the email account.  |
   |Redirect URI     |         | This URI is only relevant for [!INCLUDE [prod_short](includes/prod_short.md)] on-premises. You can customize the value, but if you do, you must update your app registration in Azure portal.     |
   |Use custom app registration| | If you want to use a custom app registration, turn on the toggle. |
 
1. To complete the account setup, choose **Next**, and then give consent.

## Send a test email

The following example shows a basic way to test SMTP OAuth.

```powershell


```

## Troubleshooting

This section lists some typical issues, their causes, and provides suggestions for how to resolve them.

### AADSTS50011: redirect_uri mismatch

- Cause: A Redirect URI isn't configured for your app registration in Azure portal.
- Resolution: Update your app registration in Azure portal to use the same `.../oauthlanding.htm` redirect URI. Learn more at [Create an application registration in Azure portal](#create-an-application-registration-in-azure-portal).

### 535 Authentication unsuccessful

- Cause: SMTP AUTH is disabled or has an incorrect tenant ID.
- Resolution: Check `Get-TransportConfig` to be sure that `SmtpClientAuthentidationDisabled` is `False`.

### 530 5.7.57 Client not authenticated

- Cause: The token is missing or invalid.
- Resolution: Verify `SMTP.SendAsApp` and admin consent.

### 430 mailbox sign in failure

- Cause: Missing `SendAs` rights.
- Resolution: Run `Set-CASMailbox`.

### 550 5.7.708 Service unavailable

- Cause: The new tenant is restricted or has an incorrect tenant ID. For example, you entered Tenant A's ID but your account is from Tenant B.
- Resolution: Contact Microsoft 365 support or check your tenant ID.

## Related information

[Set up email](admin-how-setup-email.md)