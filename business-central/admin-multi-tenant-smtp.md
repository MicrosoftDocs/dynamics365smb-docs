---
title: Use SMTP for email in a multitenant environment
author: brentholtorf
description: Learn how to resolve SMTP email challenges in multitenant environments. Follow this guide to configure OAuth 2.0 authentication in Microsoft 365.
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: get-started
ms.search.keywords: SMTP, mail, Microsoft 365
ms.date: 12/08/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Use SMTP for email in a multitenant environment

This article explains how to configure your Microsoft 365 tenant so that [!INCLUDE [prod_short](includes/prod_short.md)] can send emails through the SMTP Connector using OAuth 2.0 (client credentials flow).

This article also covers how to enable cross-tenant scenarios. For example, where you have an app registration in Azure portal in one Microsoft Entra tenant but you use it to send emails from another tenant.

## Tenant roles used in the example in this article

The examples in this article involve two Microsoft Entra tenants, as described in the following table.

|Tenant name in this article  |Description |
|---------|---------|
|Tenant A (App / Mailbox tenant) | The tenant where the app registration is created and where the Exchange Online mailbox used for sending emails exists. |
|Tenant B (Business Central tenant)   | The tenant where [!INCLUDE [prod_short](includes/prod_short.md)] is deployed and where SMTP is configured. |

> [!NOTE]
> Here are a couple of key rules to remember:
>
> * Business Central configuration is set in Tenant B.
> * Mailbox permissions and Exchange Online configuration are set in Tenant A.

> [!IMPORTANT]
> Exchange Online is deprecating Basic authentication for SMTP. This change doesn't affect tenants that currently use SMTP AUTH. However, we recommend that you use the latest version, and set up OAuth 2.0 authentication for SMTP. If you can't set up OAuth 2.0 authentication, we encourage you to explore non-Microsoft alternatives if you want to use SMTP email in earlier versions.
>
> [!INCLUDE [prod_short](includes/prod_short.md)] doesn't support certificate-based authentication.

## Overview of the process and the tenant used in each step

The following list gives an overview of the steps to use OAuth 2.0 with the SMTP connector, and links to descriptions of each step. This is a long article, so it can serve as a mini table of contents.

|Step  |Action  |Tenant  |
|------|---------|---------|
|1     | [Create an application registration in Azure portal](#create-an-application-registration-in-azure-portal)  | Tenant A (App / Mailbox tenant)        |
|2     |[Grant API permissions](#grant-api-permissions)|  Tenant A (App / Mailbox tenant)       |
|3     |    [Create a client secret or certificate](#create-a-client-secret-or-certificate)     |Tenant A (App / Mailbox tenant)|
|4     | [Register the service principal in Exchange Online](#register-the-service-principal-in-exchange-online)  | Tenant A (App / Mailbox tenant)        |
|5     |[Grant the app permission to send as your mailbox](#grant-the-app-permission-to-send-as-your-mailbox)| Tenant A (App / Mailbox tenant)        |
|6     | [Verify your SMTP OAuth configuration](#verify-your-smtp-oauth-configuration) | Tenant A (App / Mailbox tenant)        |
|7     | [Set up the SMTP connector in Business Central](#set-up-the-smtp-connector-in-business-central) | Tenant B (Business Central tenant)        |

> Some of the steps require that you run one or more commands in PowerShell. Be sure to run the commands as an administrator.

## Prerequisites

Before you start, ensure that you have:

- A Microsoft 365 tenant with Exchange Online.  
- Global Administrator or Exchange Administrator permissions.  
- A mailbox, for example, service@yourdomain.com, that you use as the "From" address in Tenant A(App / Mailbox tenant).  
- A [!INCLUDE [prod_short](includes/prod_short.md)] online or on-premises environment in Tenant B(Business Central tenant).

## Create an application registration in Azure portal

The first step is to create an app registration for the app you have in "Tenant A" (App / Mailbox tenant) in Microsoft Entra ID. The app registration lets [!INCLUDE [prod_short](includes/prod_short.md)] send email from a mailbox that's in another Microsoft Entra tenant.

> [!NOTE]
> Be sure to sign in with the Global Administrator account for Tenant A.

1. Go to [Azure portal](https://portal.azure.com).
1. Under **Azure services**, choose **Microsoft Entra ID**.
1. In the navigation pane, choose **App registrations**.
1. On the **App registrations** page, choose **New registration**.
1. On the **Register an application** page, fill in the fields as follows:

    1. In the **Name** field, enter a name for your app. For example, **SMTP_OAuth_App**.
    1. Under **Supported account types**, choose **Accounts in any organizational directory (Any Microsoft Entra ID tenant - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)**. This setting is required for cross-tenant consent.
    1. Under **Redirect URI (optional)**, for the platform, choose **Web**, and then enter the URI:
       1. Business Central online (SaaS): https://businesscentral.dynamics.com/oauthlanding.htm
       2. Business Central on-premises: Specify a redirect URI appropriate for your on-premises deployment.

1. Choose **Register**.

> [!NOTE]
> After you register the app in Microsoft Entra ID, make a note of the following information. You need it to complete a later step.
>
> |Field  |Example  |Description  |
> |---------|---------|---------|
> |Application (client) ID | 00001111-aaaa-2222-bbbb-3333cccc4444 |  App ID       |
> |Directory (tenant) ID   | aaaabbbb-0000-cccc-1111-dddd2222eeee | Tenant ID     |
> |Object ID   | aaaaaaaa-0000-1111-2222-bbbbbbbbbbbb       | Service Principal ID|

## Grant API permissions

The next step is to give the app permission to send email. In this example, this is Tenant A (the app / mailbox tenant).

> [!NOTE]
> Be sure to sign in with the Global Administrator account for Tenant A.

1. In Azure portal, on the app page, choose **API permissions**, and then choose **Add a permission**.
1. Choose **APIS my organization uses**.
1. Search for **Office 365 Exchange Online**.
1. Choose **Application permissions**.
1. Expand **SMTP**, and then choose **SMTP.SendAsApp**.
1. Choose **Add permissions**.
1. Double-check that **SMTP.SendAsApp** has a green checkmark.

## Create a client secret or certificate

> * Tenant: Tenant A (App / Mailbox tenant)
> * Sign in with: Tenant A Global Administrator

1. In Azure portal, on the app page, choose **Certificates & secrets**.
1. In the **Client secret** field, choose **New client secret**, give it a name and define an expiry period.

   > [!IMPORTANT]
   > Make a note of the **Client Secret Value**. The value displays only one time, and you need it to generate tokens.

## Register the service principal in Exchange Online

To learn more about the service principal, go to [Register a Microsoft Entra app and create a service principal](/entra/identity-platform/howto-create-service-principal-portal).

> [!NOTE]
> Be sure to sign in with the Global Administrator or Exchange Administrator account for Tenant A. 

1. Open your browser, use the following link to consent. Replace the `TenantA_ID` and `Client_ID from Tenant A` (App ID) with the values for your "Tenant A."

   `https://login.microsoftonline.com/<TenantA_ID>/oauth2/v2.0/authorize?client_id=<Client_ID from Tenant A>&scope=https://graph.microsoft.com/.default&response_type=code&response_mode=query&prompt=consent`

2. In Microsoft Entra admin center of **Tenant A**, go to **Enterprise apps**, find your app, and then copy the value in the **Object ID** field. The object ID is used as the service ID in the command in the next step in this process.
3. To create a new service principal in your tenant, in PowerShell, run the following command as an administrator.

   ```powershell

   Install-Module ExchangeOnlineManagement -Scope CurrentUser

   Import-Module ExchangeOnlineManagement
   # Login with Tenant A admin
   
   $AppId     = <your app ID> # The App ID of the enterprise app in Tenant A's Microsoft Entra admin center.
   $ServiceId = <your service ID> # The object ID of the enterprise app in Tenant A's Microsoft Entra admin center.
   $Display   = "SMTP_OAuth_App" # The name of the service principal you want to create.

   New-ServicePrincipal -AppId $AppId -ServiceId $ServiceId -DisplayName $Display

   ```

> [!NOTE]
> If a service principal already exists, the command might show an error, but you can safely ignore it.

## Grant the app permission to send as your mailbox

Sometimes Azure portal hides the SMTP option, so you must use PowerShell to grant permission to send as your mailbox. Do this in Tenant A ([!INCLUDE [prod_short](includes/prod_short.md)] tenant).

> [!NOTE]
> Be sure to sign in with the Global Administrator or Exchange Administrator account for Tenant A.

1. Retrieve the service principal Object ID from the Microsoft Entra admin center (Enterprise applications), and use that Object ID in the following commands. Then go to PowerShell, run the following command:

   ```powershell
       # Replace this with the mailbox you use as the from_addr / user= in XOAUTH2.
      $Mailbox = "someuser@xxx.onmicrosoft.com"
      $ObjectID = "{Your object ID}"

      Add-MailboxPermission -Identity $Mailbox `
          -User $ObjectId `
          -AccessRights FullAccess `
          -AutoMapping:$false

      Add-RecipientPermission -Identity $Mailbox `
          -Trustee $ObjectId `
          -AccessRights SendAs `
          -Confirm:$false 
                

       # If you have multiple users, create a group for them and then assign them.
      Get-DistributionGroupMember "Your group name" |
        ForEach-Object {
            Add-MailboxPermission -$_.PrimarySmtpAddress `
                -User $ObjectId `
                -AccessRights FullAccess `
                -AutoMapping:$false

            Add-RecipientPermission -Identity $Mailbox `
                -Trustee $ObjectId `
                -AccessRights SendAs `
                -Confirm:$false             
        }

      ```

1. To verify the permissions, run the following command:

   ```powershell
   Get-MailboxPermission  -Identity $Mailbox | ? {$_.User -eq $Display}
   ```

   You should have **FullAccess**, or **SendAs**.

## Verify your SMTP OAuth configuration

Do this step in Tenant A (App / Mailbox tenant).

> [!NOTE]
> Be sure to sign in with the Global Administrator or Exchange Administrator account for Tenant A.

1. In PowerShell, connect to Exchange Online in Tenant A and verify that SMTP AUTH and OAuth2 are enabled:

   ```powershell
   
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -UserPrincipalName admin@yourtenantA.onmicrosoft.com

   # Organization-level settings (recommended starting point)
   Get-TransportConfig | Format-List SmtpClientAuthenticationDisabled
   Get-OrganizationConfig | Format-List OAuth2ClientProfileEnabled

   # If SMTP AUTH is disabled at the organization level, enable it (false means enabled):
   Set-TransportConfig -SmtpClientAuthenticationDisabled $false

   # If OAuth2 client profiles are not enabled, enable them (true means enabled):
   Set-OrganizationConfig -OAuth2ClientProfileEnabled $true


   ```

1. If you need to enable SMTP AUTH for a specific mailbox (mailbox-level override), verify and update the mailbox setting:

   ```powershell

   Get-CASMailbox -Identity admin@yourtenantA.onmicrosoft.com | Format-List SmtpClientAuthenticationDisabled

   # If SMTP AUTH is disabled for the mailbox, enable it:

   Set-CASMailbox -Identity admin@yourtenantA.onmicrosoft.com -SmtpClientAuthenticationDisabled $false

   ```

1. Verify the expected values:

   ```powershell

    Get-TransportConfig | Format-List SmtpClientAuthenticationDisabled
    Get-OrganizationConfig | Format-List OAuth2ClientProfileEnabled

   ```

   The following are the expected output:

   - `SmtpClientAuthenticationDisabled` is `False`.
   - `OAuth2ClientProfileEnabled` is `True`.

## Set up the SMTP connector in Business Central

Do this step in Tenant B (Business Central tenant).

To learn more about the SMTP connector, go to [Set up email](admin-how-setup-email.md).

1. In [!INCLUDE [prod_short](includes/prod_short.md)], [!INCLUDE [open-search-lowercase](includes/open-search-lowercase.md)], enter **Assisted Setup**, and then choose the related link.
1. Choose **Set up SMTP Account**.
1. Fill in the fields as described in the following table.

   |Field  |Example value  |Notes  |
   |---------|---------|---------|
   |Server     | smtp.office365.com        |         |
   |Server Port     |  587       |         |
   |Authentication Type     | OAuth 2.0        |         |
   |Client ID | 00001111-aaaa-2222-bbbb-3333cccc4444 | The application ID from Tenant A. |
   |Client Secret     |         | The secret generated in the app from Tenant A.        |
   |Tenant ID     | aaaabbbb-0000-cccc-1111-dddd2222eeee  | The ID of Tenant A (App / Mailbox tenant). |
   |Redirect URI     |         | This URI is only relevant for [!INCLUDE [prod_short](includes/prod_short.md)] on-premises. You can customize the value, but if you do, you must update your app registration in Azure portal.     |
   |Use custom app registration| | If you want to use a custom app registration, turn on the toggle. |

2. To complete the account setup, choose **Next**, and then give consent.

## Send a test email

The following example shows a way to test OAuth 2.0 for the SMTP connector.

```powershell
param(
    [string]$TenantId     = "<Tenant A ID>",  
    # Tenant A (App registration tenant)
    # Application (Client) ID of the app registered in Tenant A
    [string]$ClientId     = "<Tenant A Client ID>",  
    # Tenant A (App registration tenant)
    # Client Secret created for the app in Tenant A
    [string]$ClientSecret = "<Tenant A Client Secret>",
    # Tenant B (Business Central tenant)
    # Must be a mailbox that exists in Tenant A and has SendAs permission granted
    [string]$From         = "<Tenant A mailbox address>",
    # Any valid email address (internal or external)
    [string]$To           = "<Recipient email address>",
    # Email subject
    [string]$Subject      = "SMTP OAuth Test",
    # Email body
    [string]$Body         = "Hello! This is a test email using SMTP OAuth."
)

#---------------------------
# 0. Prepare & Import Module
#---------------------------
# If you don't have MSAL.PS module, uncomment the next line to install it
# Install-Module MSAL.PS -Scope CurrentUser
Import-Module MSAL.PS -ErrorAction Stop

#---------------------------
# 1. Get Access Token
#---------------------------
Write-Host "Getting access token from AAD..." -ForegroundColor Cyan

$secureSecret = ConvertTo-SecureString $ClientSecret -AsPlainText -Force

$tokenResult = Get-MsalToken `
    -ClientId      $ClientId `
    -ClientSecret  $secureSecret `
    -TenantId      $TenantId `
    -Scopes        "https://outlook.office365.com/.default"

$accessToken = $tokenResult.AccessToken.Trim()

function Convert-FromBase64Url {
    param([string]$InputString)

    $pad = 4 - ($InputString.Length % 4)
    if ($pad -lt 4) {
        $InputString += "=" * $pad
    }

    $InputString = $InputString.Replace('-', '+').Replace('_', '/')
    $bytes = [System.Convert]::FromBase64String($InputString)
    return $bytes
}

$parts = $accessToken.Split('.')
$payloadBytes = Convert-FromBase64Url -InputString $parts[1]
$payloadJson  = [System.Text.Encoding]::UTF8.GetString($payloadBytes)
$claims       = $payloadJson | ConvertFrom-Json

Write-Host "Access token acquired."
Write-Host "aud   =" $claims.aud
Write-Host "roles =" ($claims.roles -join ", ")
Write-Host "appid =" $claims.appid
Write-Host "tid   =" $claims.tid
Write-Host ""

#---------------------------
# 2. Build AUTH XOAUTH2
#---------------------------

function New-XOAuth2String {
    param(
        [string]$User,
        [string]$Token
    )
    $ctrlA = [char]1

    $auth  = "user=$User$ctrlA" + "auth=Bearer $Token$ctrlA$ctrlA"
    $bytes = [System.Text.Encoding]::UTF8.GetBytes($auth)
    return [System.Convert]::ToBase64String($bytes)
}

$authB64 = New-XOAuth2String -User $From -Token $accessToken
Write-Host "AUTH (base64) generated." -ForegroundColor Cyan


$msg =
"From: $From`r`n" +
"To: $To`r`n" +
"Subject: $Subject`r`n" +
"`r`n" +
"$Body`r`n"


function Read-SmtpResponse {
    param([System.IO.StreamReader]$Reader)

    $line = $Reader.ReadLine()
    if ($line -ne $null) {
        Write-Host $line
    }
    return $line
}

$server = "smtp.office365.com"
$port   = 587

Write-Host ""
Write-Host "Connecting to $server : $port ..." -ForegroundColor Cyan

$tcpClient     = New-Object System.Net.Sockets.TcpClient($server, $port)
$networkStream = $tcpClient.GetStream()

$reader = New-Object System.IO.StreamReader($networkStream)
$writer = New-Object System.IO.StreamWriter($networkStream)
$writer.NewLine   = "`r`n"
$writer.AutoFlush = $true

# init  banner
Read-SmtpResponse -Reader $reader | Out-Null

# EHLO (before STARTTLS)
$writer.WriteLine("EHLO localhost")
do {
    $line = Read-SmtpResponse -Reader $reader
} while ($line -match "^[0-9]{3}-")

# STARTTLS
$writer.WriteLine("STARTTLS")
$line = Read-SmtpResponse -Reader $reader
if (-not $line.StartsWith("220")) {
    throw "STARTTLS failed: $line"
}

$sslStream = New-Object System.Net.Security.SslStream(
    $networkStream,
    $false,
    { param($sender, $cert, $chain, $errors) return $true }
)
$sslStream.AuthenticateAsClient($server)

$reader = New-Object System.IO.StreamReader($sslStream)
$writer = New-Object System.IO.StreamWriter($sslStream)
$writer.NewLine   = "`r`n"
$writer.AutoFlush = $true

# EHLO (after STARTTLS)
$writer.WriteLine("EHLO localhost")
do {
    $line = Read-SmtpResponse -Reader $reader
} while ($line -match "^[0-9]{3}-")

# AUTH XOAUTH2
Write-Host ""
Write-Host "Sending AUTH XOAUTH2 ..." -ForegroundColor Cyan
$writer.WriteLine("AUTH XOAUTH2 $authB64")
$line = Read-SmtpResponse -Reader $reader
if (-not $line.StartsWith("235")) {
    throw "AUTH failed: $line"
}

# MAIL FROM
$writer.WriteLine("MAIL FROM:<$From>")
$line = Read-SmtpResponse -Reader $reader
if (-not $line.StartsWith("250")) {
    throw "MAIL FROM failed: $line"
}

# RCPT TO
$writer.WriteLine("RCPT TO:<$To>")
$line = Read-SmtpResponse -Reader $reader
if (-not $line.StartsWith("250")) {
    throw "RCPT TO failed: $line"
}

# DATA
$writer.WriteLine("DATA")
$line = Read-SmtpResponse -Reader $reader
if (-not $line.StartsWith("354")) {
    throw "DATA command failed: $line"
}

$writer.WriteLine($msg)
$writer.WriteLine(".")
$line = Read-SmtpResponse -Reader $reader
if (-not $line.StartsWith("250")) {
    throw "Message send failed: $line"
}

# QUIT
$writer.WriteLine("QUIT")
Read-SmtpResponse -Reader $reader | Out-Null

$reader.Close()
$writer.Close()
$sslStream.Close()
$networkStream.Close()
$tcpClient.Close()

Write-Host ""
Write-Host "✅ Email sent successfully from $From to $To" -ForegroundColor Green

```

## Troubleshooting

This section lists some typical issues, their causes, and provides suggestions for how to resolve them.

### AADSTS50011: redirect_uri mismatch

- Cause: A Redirect URI isn't configured for your app registration in Azure portal.
- Resolution: Update your app registration in Azure portal to use the same `.../oauthlanding.htm` redirect URI. Learn more at [Create an application registration in Azure portal](#create-an-application-registration-in-azure-portal).

### 535 Authentication unsuccessful

- Cause: SMTP AUTH is disabled, has an incorrect tenant ID or OAuth2ClientProfileEnabled is not enabled in the Exchange Online organization.

- Resolution: Check `Get-TransportConfig` to be sure that `SmtpClientAuthentidationDisabled` is `False` and `OAuth2ClientProfileEnabled` is `true`.

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
