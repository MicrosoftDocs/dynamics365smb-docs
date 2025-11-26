---
title: Use SMTP for email in a multi-tenant environment
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

# Use SMTP for email in a multi-tenant environment

This article explains how to configure your Microsoft 365 tenant so that [!INCLUDE [prod_short](includes/prod_short.md)] can send emails through SMTP AUTH using OAuth 2.0 (client credentials flow).

This article also covers how to enable cross-tenant scenarios, where you have an Azure App is registered in one tenant but use it to send emails from another tenant.

In the following procedures we refer to the tenant where you have the app as "Tenant A," and the tenant where you use it for SMTP as "Tenant B."

## Prerequisites

Before starting, ensure you have:

- A Microsoft 365 tenant with Exchange Online.  
- Global Administrator or Exchange Administrator permissions.  
- A mailbox, for example, service@yourdomain.com, that you use as the “From” address.  
- A [!INCLUDE [prod_short](includes/prod_short.md)] online or on-premises environment.
- (Optional) Python 3.10+ or any other environment that supports OAuth-based SMTP authentication for testing.

## Register your application in Azure portal

The first step is to register the app you have in "Tenant A" in Microsoft Entra ID.

1. Go to [Azure portal](https://portal.azure.com).
1. Under **Azure services, choose **JMicrosoft Entra ID**.
1. In the navigation pane, choose **App registrations**.
1. On the **App registrations** page, choose **New registration**.
1. On the **Register an application** page, fill in the fields as follows:
    1. In the **Name** field, enter a name for your app. For example, **SMTP_OAuth_App**.
    1. Under **Supported account types**, choose **Accounts in any organizational directory (Any Microsoft Entra ID tenant - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)**. This is required for cross-tenant consent.
    1. Under **Redirect URI (optional)**, for the platform, choose **Web**, and then enter the URI.

1. Choose **Register**.

> [!NOTE]
> After you register the app in Microsoft Entra ID, make a note of the following information. You'll need it in a later step.
>
> |Field  |Example  |Description  |
> |---------|---------|---------|
> |Application (client) ID | 11111111-2222-3333-4444-555555555555 |  App ID       |
> |Directory (tenant) ID   | 11111111-2222-3333-4444-555555555555 | Tenant ID     |
> |Object ID   | 11111111-2222-3333-4444-555555555555       | Service Principal ID|

## Grant API permissions

1. In Azure portal, on the app page, choose **API permissions**, and then choose **Add a permission**.
1. Choose **APIS my organization uses**.
1. Search for **Office 365 Exchange Online**.
1. Choose **Application permissions**.
1. Expand **SMTP**, and then choose **SMTP.SendAsApp**.
1. Choose **Add permissions**.
1. On the permissions page, choose **Grant admin consent for your \<your organization>**.
1. Double-check that **SMTP.SendAsApp** has a green checkmark.

## Create a client secret or certificate

1. In Azure portal, on the app page, choose **Certificates & secrets**.
1. In the **Client secret** field, choose **New client secret**, give it a name and define an expiry period.

   > [!IMPORTANT]
   > Make a note of the **Client Secret Value**. The value displays only one time, and you need it to generate tokens.

## Register the service principal in Exchange Online

<!--Think we need to introduce this section. For example, why are they doing this?-->

1. In PowerShell, use the following link to consent. Replace the tenant ID and client ID (App ID) with the values for your "Tenant B."

   ```PowerShell
   https://login.microsoftonline.com/\<TenantB_ID>/oauth2/v2.0/authorize?client_id=\<Client_ID>&scope=https://graph.microsoft.com/.default&response_type=code&response_mode=query&prompt=consent

   ```

1. In Microsoft Entra admin center, go to **Enterprise apps**, find your app, and then copy the value in the **Object ID** field. The object ID is used as the service ID in the command in the next step in this process.
1. To create a new service principal in your tenant, run the following in PowerShell as an administrator

   ```PowerShell

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

```PowerShell

$sp = Get-ServicePrincipal | Where-Object { $_.AppId -eq "{AppID}" }

 \<Replace this with the mailbox you use as the from_addr / user= in XOAUTH2>
$Mailbox = "someuser@xxx.onmicrosoft.com"

Add-MailboxPermission -Identity $Mailbox `
    -User $sp.ObjectId `
    -AccessRights FullAccess `
    -AutoMapping:$false

 \<If you have multiple users, create a group for them and then assign them.>
Get-DistributionGroupMember "Your group name" |
  ForEach-Object {
      Add-MailboxPermission -$_.PrimarySmtpAddress `
          -User $sp.ObjectId `
          -AccessRights FullAccess `
          -AutoMapping:$false
  }

```

1. Run the following command to verify the permissions.

   ```PowerShell
   Get-MailboxPermission  -Identity $Mailbox | ? {$_.User -eq $Display}
   ```

   You should have either **AccessRights**, **SendAs**, or both.

## Verify your SMTP OAuth configuration

1. In PowerShell, run the following command to verify your SMTP OAuth configuration.

   ```PowerShell
   
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -UserPrincipalName admin@yourtenant.onmicrosoft.com
   Get-CASMailbox -Identity admin@yourtenant.onmicrosoft.com | Select SmtpClientAuthenticationDisabled

   \<If the output is false, it's enabled. But if it's true, SMTP is disabled and you must run the following command to enable it:>

   Set-CASMailbox -Identity admin@yourtenant.onmicrosoft.com -SmtpClientAuthenticationDisabled $false

   ```

1. To enable SMTP for your entire organization level, run the following command:

   ```PowerShell

   Get-TransportConfig | Select SmtpClientAuthenticationDisabled

   \<If the output is false it's enabled. If it's true, SMTP is disabled and you must run the following command to enable it:>

   Set-TransportConfig -SmtpClientAuthenticationDisabled $false

   ```

1. To verify that SMTP OPAuth is globally enabled, run the following command:

   ```PowerShell

   Get-TransportConfig | fl SmtpClientAuthenticationDisabled,OAuth2ClientProfileEnabled

   ```

   The following are the expected output:

   - `SmtpClientAuthenticationDisabled` is `False`.
   - `OAuth2ClientProfileEnabled` is `True`.

   If `SmtpClientAuthenticationDisabled` is `True`, run the following command to enable it:

   ```PowerShell 

   Set-TransportConfig -SmtpClientAuthenticationDisabled $false

   ```

## Set up your SMTP account in Business Central

1. In [!INCLUDE [prod_short](includes/prod_short.md)], [!INCLUDE [open-search-lowercase](includes/open-search-lowercase.md)], enter **Assisted Setup**, and then choose the related link.
1. Choose **Set up SMTP Account**.
1. Fill in the fields as described in the following table.

   |Field  |Example value  |Notes  |
   |---------|---------|---------|
   |Server     | smtp.office365.com        |         |
   |Server Port     |  587       |         |
   |Authentication Type     | OAuth 2.0        |         |
   |Client ID | 11111111-2222-3333-4444-555555555555 | The application ID from Tenant A |
   |Client Secret     |         | The secr4et generated in the app.        |
   |Tenant ID     | 11111111-2222-3333-4444-555555555555  | The ID of Tenant B, where you host the email account.  |
   |Redirect URI     |         | This URI is only relevant for [!INCLUDE [prod_short](includes/prod_short.md)] on-premises. You can customize the value, but if you do, you must        |
   |Use custom app registration| | If you want to use a custom app registration, turn on the toggle. |

1. Choose **Authenticate OAuth**, and consent to the terms. 
1. To complete the account setup, choose **Next**.

## Send a test email via Python

The following is a basic example you can use to test SMTP OAuth.

```Python

import base64, smtplib, requests

tenant_id = "b3a79c38-359b-430b-99c7-f82f93215001"
client_id = "2f761990-2353-46a5-a000-f1693818df25"
client_secret = "YOUR_CLIENT_SECRET"

  # Get an access token
token_url = f"https://login.microsoftonline.com/{tenant_id}/oauth2/v2.0/token"
data = {
    "client_id": client_id,
    "client_secret": client_secret,
    "scope": "https://outlook.office365.com/.default",
    "grant_type": "client_credentials"
}
access_token = requests.post(token_url, data=data).json()["access_token"]

  # Build an XOAUTH2 authentication string
user = "service@yourdomain.com"
auth_string = f"user={user}\x01auth=Bearer {access_token}\x01\x01"
auth_b64 = base64.b64encode(auth_string.encode()).decode()

  # Send a test email
from_addr = user
to_addr = "recipient@example.com"
msg = f"Subject: SMTP OAuth Test\n\nThis is a test email via App Registration."

with smtplib.SMTP("smtp.office365.com", 587) as s:
    s.starttls()
    s.docmd("AUTH", "XOAUTH2 " + auth_b64)
    s.sendmail(from_addr, [to_addr], msg)

print("✅ Email sent successfully!")

```

## Troubleshooting

This section lists some typical issues, their causes, and provides suggestions for how to resolve them.

### AADSTS50011: redirect_uri mismatch

- Cause: A Redirect URI isn't configured for your app registration in Azure portal.
- Resolution: Update your app registration in Azure portal to use the same `.../oauthlanding.htm` redirect URI.

### 535 Authentication unsuccessful

- Cause: SMTP AUTH is disabled or has an incorrect tenant ID.
- Resolution: Check `Get-TransportConfig` to be sure that `SmtpClientAuthentidationDisabled` is `False`.

### 530 5.7.57 Client not authenticated

- Cause: The token is missing or invalid.
- Resolution: Verify `SMTP.SendAsApp` and admin consent.

### 430 mailbox logon failure

- Cause: Missing `SendAs` rights.
- Resolution: Run `Add-RecipientPermission`.

### 550 5.7.708 Service unavailable

- Cause: The new tenant is restricted or has an incorrect tenant ID. For example, you entered Tenant A's ID but your account is from Tenant B.
- Resolution: Contract Microsoft 365 support or check your tenant ID.

## Best practices and recommendations

The following list provides some things to consider:

- For production mailboxes, use a custom domain and not onmicrosoft.com.
- For production environments, use certificate-based authentication.
- Grant only the required permissions, for example, only `SMTP.SendAsApp`.
- Review Azure and Exchange permissions regularly.

## Related information

[Set up email](admin-how-setup-email.md)