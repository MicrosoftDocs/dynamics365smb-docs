---
author: edupont04

ms.service: dynamics365-accountant
ms.topic: include
ms.date: 06/25/2020
ms.author: edupont
---

Before you can set up email logging, you must prepare your Exchange Online with [public folders](/exchange/collaboration/public-folders/public-folders?view=exchserver-2019). You can do this in the [Exchange admin center](/Exchange/architecture/client-access/exchange-admin-center?view=exchserver-2019), or you can use the [Exchange Management Shell](/powershell/exchange/exchange-management-shell?view=exchange-ps).  

> [!TIP]
> If you want to use the [Exchange Management Shell](/powershell/exchange/exchange-management-shell?view=exchange-ps), you can find inspiration for how to set up your script in a sample script that we published to [the BCTech repo](https://github.com/microsoft/BCTech/tree/master/samples/EmailLogging).

The following list describes the main steps with links to learn more.  

- Create an admin role for public folders based on the information in the following table:

  |Property        |Value                     |
  |----------------|--------------------------|
  |Name            |Public Folders Management |
  |Selected roles  |Public Folders            |
  |Selected members|The email of the user account that Business Central will use to run the email logging job|

  For more information, see [Manage role groups](/exchange/permissions/role-groups?view=exchserver-2019).

- Create a new public folder mailbox based on the information in the following table:

  |Property        |Value                     |
  |----------------|--------------------------|
  |Name            |Public MailBox            |

  For more information, see [Create a public folder mailbox in Exchange Server](/exchange/collaboration/public-folders/create-public-folder-mailboxes).  

- Create new public folders

  - Create a new public folder with the name *Email Logging* in the root so that the full path to the folder becomes ```\Email Logging\```
  - Create two subfolders so that the the result is the following full paths to the folders:
    - ```\Email Logging\Queue\```
    - ```\Email Logging\Storage\```

  For more information, see [Create a public folder](/exchange/collaboration/public-folders/create-public-folders?view=exchserver-2019).

- Mail-enable the *Queue* public folder

  For more information, see [Mail-enable or mail-disable a public folder](/exchange/collaboration/public-folders/mail-enable-or-disable?view=exchserver-2019)

- Mail-enable sending emails to the *Queue* public folder using Outlook or the Exchange Management Shell

  For more information, see [Allow anonymous users to send email to a mail-enabled public folder](/exchange/collaboration/public-folders/mail-enable-or-disable?view=exchserver-2019#allow-anonymous-users-to-send-email-to-a-mail-enabled-public-folder)

- Set the email logging user as an owner of both public folders, *Queue* and *Storage* public folders  using Outlook or the Exchange Management Shell based on the information in the following table:

  |Property        |Value                     |
  |----------------|--------------------------|
  |User            |The email of the user account that Business Central will use to run the email logging job|
  |Permission level|Owner                     |

  For more information, see [Assign permissions to the public folder](/exchange/collaboration-exo/public-folders/set-up-public-folders#step-3-assign-permissions-to-the-public-folder).

- Create two mail flow rules based on the information in the following table

  |Purpose  |Name |Conditions                        |Action                                       |
  |---------|-----|----------------------------------|---------------------------------------------|
  |A rule for incoming email |Log Email Sent to This Organization|*The sender* is located *Outside the organization*, and *the recipient* is located *Inside the organization*|BCC the email account that is specified for the *Queue* public folder|
  |A rule for outgoing email | Log Email Sent from This Organization |*The sender* is located *Inside the organization*, and *the recipient* is located *Outside the organization*|BCC the email account that is specified for the *Queue* public folder|
  
  For more information, see [Manage mail flow rules in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) and [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-action).

> [!NOTE]
> If you make changes in the Exchange Management Shell, the changes become visible in the Exchange admin center after a delay. Also, the changes made in Exchange will be available in [!INCLUDE [prodshort](prodshort.md)] after a delay.
