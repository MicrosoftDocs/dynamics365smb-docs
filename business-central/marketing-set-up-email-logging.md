---
title: Set Up Email Logging| Microsoft Docs
description: Learn how to turn email interactions between salespeople and customers into real sales opportunities.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect, opportunity, email
ms.date: 06/11/2020
ms.author: bholtorf

---
# Track Email Message Exchanges Between Salespeople and Contacts

Get more out of the communications between salespeople and your existing or potential customers by tracking email exchanges, and then turning them into actionable opportunities. [!INCLUDE[d365fin](includes/d365fin_md.md)] can work with Exchange Online to keep a log of the inbound and outbound messages. You can view and analyze the contents of each message on the **Interaction Log Entries** page.

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2085401]

## Set up Public Folders and Rules for Email Logging in Exchange Online

Before you can set up email logging, you must prepare your Exchange Online with [public folders](/exchange/collaboration/public-folders/public-folders?view=exchserver-2019). You can do this in the [Exchange admin center](/Exchange/architecture/client-access/exchange-admin-center?view=exchserver-2019), or you can use the [Exchange Management Shell](/powershell/exchange/exchange-management-shell?view=exchange-ps). The following list describes the main steps with links to learn more.  

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

- Create new public folders (, use the EAC or EMS)

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

  For more information, see [(Assign permissions to the public folder](/exchange/collaboration-exo/public-folders/set-up-public-folders#step-3-assign-permissions-to-the-public-folder).

- Create two mail flow rules based on the information in the following table

  |Purpose  |Name |Conditions                        |Action                                       |
  |---------|-----|----------------------------------|---------------------------------------------|
  |A rule for incoming email |Log Email Sent to This Organization|*The sender* is located *Outside the organization*, and *the recipient* is located *Inside the organization*|BCC the email account that is specified for the *Queue* public folder|
  |A rule for outgoing email | Log Email Sent from This Organization |*The sender* is located *Inside the organization*, and *the recipient* is located *Outside the organization*|BCC the email account that is specified for the *Queue* public folder|
  
  For more information, see [Manage mail flow rules in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) and [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-action).

> [!NOTE]
> If you make changes in the Exchange Management Shell, the changes become visible in the Exchange admin center after a delay. Also, the changes made in Exchange will be available in [!INCLUDE [prodshort](includes/prodshort.md)] after a delay.

Next, you connect [!INCLUDE [prodshort](includes/prodshort.md)] with Exchange Online.

## Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)] to Log Email Messages

Get started with email logging in two easy steps:

1. Connect [!INCLUDE[d365fin](includes/d365fin_md.md)] with Exchange Online for your Office 365 subscription. Exchange Online handles your email messages. We've made this step easy by providing an assisted setup guide. You just need your administrator credentials for your administrator account in Office 365. To start the guide, go to **Assisted Setup**, and then choose **Set up email logging**.  

2. Make sure that valid email addresses have been entered in [!INCLUDE[d365fin](includes/d365fin_md.md)] for your sales people and contacts, depending on whether they are potential or existing customers. To do that, for each customer or salesperson, open the **Contact** or **Salesperson/Purchaser** card and have a look in the **Email** field.

> [!Tip]
> After you complete the steps in the guide you can check whether the connection was successful. Search for **Marketing Setup**, choose **Process**, then **Functions**, and then **Validate Email Logging Setup**.

## Viewing Email Message Exchanges in the Interaction Log

[!INCLUDE[d365fin](includes/d365fin_md.md)] creates an entry on the **Interaction Log** page each time a salesperson and a contact exchange an email message. To view the interaction log, open the **Contact** or **Salesperson*Purchaser** card for the person, and then choose **Navigate**, **History**, and then choose **Interaction Log Entries**. There are a few things we can do with each entry in the log, for example:

- View the content of the email message that was exchanged by clicking the **Show Attachments** action.
- Turn an email exchange into a sales opportunity - If an entry looks promising, you can turn it into an opportunity and then manage its progress toward a sale. To do that, choose the entry, and then choose the **Create Opportunity** action. For more information, see [Managing Sales Opportunities](marketing-manage-sales-opportunities.md).

## See Also
[Managing Relationships](marketing-relationship-management.md)

