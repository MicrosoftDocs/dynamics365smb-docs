---
author: brentholtorf
ms.topic: include
ms.date: 02/15/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

> [!NOTE]
> The following sections assume that you have administrator access for Exchange Online.

Before you can set up email logging, you must prepare Office 365 [public folders](/exchange/collaboration-exo/public-folders/public-folders). You can do this in the [Exchange admin center](/exchange/exchange-admin-center?preserve-view=true), or you can use the [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).

> [!TIP]
> If you want to use the [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps&preserve-view=true), you can find inspiration for how to set up your script in a sample script that we published in [the BCTech repo](https://github.com/microsoft/BCTech/tree/master/samples/EmailLogging).

Follow the steps below to set up Exchange Online, with links to where you can learn more.

### Create an admin role group

Create an admin role group for public folders based on the information in the following table:

|Property        |Value                     |
|----------------|--------------------------|
|Name            |Public Folders Management |
|Selected roles  |Public Folders            |
|Selected users  |The email of the user account that Business Central will use to run the email logging job|

For more information, see [Manage role groups in Exchange Online](/exchange/permissions-exo/role-groups).

### Create a new public folder mailbox

Create a new public folder mailbox based on the information in the following table:

|Property        |Value                     |
|----------------|--------------------------|
|Name            |Public MailBox            |

For more information, see [Create a public folder mailbox](/exchange/collaboration-exo/public-folders/create-public-folder-mailbox).

### Create new public folders

1. Create a new public folder with the name **Email Logging** in the root so that the full path to the folder becomes `\Email Logging\`.
2. Create two sub-folders so that the the result is the following full paths to the folders:

    - `\Email Logging\Queue\`
    - `\Email Logging\Storage\`

For more information, see [Create a public folder](/exchange/collaboration-exo/public-folders/create-public-folder).

### Set public folder ownership

Set the email logging user as an owner of both public folders, *Queue* and *Storage*.

For more information, see [Assign permissions to the public folder](/exchange/collaboration-exo/public-folders/set-up-public-folders#step-3-assign-permissions-to-the-public-folder).

### Mail-enable the *Queue* public folder

  For more information, see [Mail-enable or mail-disable a public folder](/exchange/collaboration-exo/public-folders/enable-or-disable-mail-for-public-folder).

### Mail-enable sending emails to the *Queue* public folder

Mail-enable sending emails to the *Queue* public folder using Outlook or the Exchange Management Shell.

For more information, see [Allow anonymous users to send email to a mail-enabled public folder](/exchange/collaboration-exo/public-folders/enable-or-disable-mail-for-public-folder#allow-anonymous-users-to-send-email-to-a-mail-enabled-public-folder?preserve-view=true).

### Create mail flow rules

Create two mail flow rules based on the information in the following table:

|Purpose  |Name |Apply this rule if...             |Do the following...                          |
|---------|-----|----------------------------------|---------------------------------------------|
|A rule for incoming email |Log Email Sent to This Organization|*The sender* is located *Outside the organization*, and *the recipient* is located *Inside the organization*|BCC the email account that is specified for the *Queue* public folder|
|A rule for outgoing email | Log Email Sent from This Organization |*The sender* is located *Inside the organization*, and *the recipient* is located *Outside the organization*|BCC the email account that is specified for the *Queue* public folder|

For more information, see [Manage mail flow rules in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules?preserve-view=true) and [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions?preserve-view=true).

> [!NOTE]
> If you make changes in the Exchange Management Shell, the changes become visible in the Exchange admin center after a delay. Also, the changes made in Exchange will be available in [!INCLUDE[prod_short](prod_short.md)] after a delay. The delay might be several hours.
