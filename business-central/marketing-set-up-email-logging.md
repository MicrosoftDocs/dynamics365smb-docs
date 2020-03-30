---
title: Set Up Email Logging| Microsoft Docs
description: Learn how to turn email interactions between salespeople and customers into real sales opportunities.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect, opportunity, email
ms.date: 04/01/2020
ms.author: bholtorf

---
# Track Email Message Exchanges Between Salespeople and Contacts
Get more out of the communications between salespeople and your existing or potential customers by tracking email exchanges, and then turning them into actionable opportunities. [!INCLUDE[d365fin](includes/d365fin_md.md)] can work with Exchange Online to keep a log of the inbound and outbound messages. You can view and analyze the contents of each message on the **Interaction Log Entries** page.

> [!VIDEO https://go.microsoft.com/fwlink/?linkid=2085401]

## Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)] to Log Email Messages
Get started with email logging in two easy steps:

1. Connect [!INCLUDE[d365fin](includes/d365fin_md.md)] with Exchange Online for your Office 365 subscription. Exchange Online handles your email messages. We've made this step easy by providing an assisted setup guide. You just need your administrator credentials for your administrator account in Office 365. To start the guide, go to **Assisted Setup**, and then choose **Set up email logging**. 
2. Make sure that valid email addresses have been entered in [!INCLUDE[d365fin](includes/d365fin_md.md)] for your sales people and contacts, depending on whether they are potential or existing customers. To do that, for each customer or salesperson, open the **Contact** or **Salesperson/Purchaser** card and have a look in the **Email** field.

> [!Tip]
> After you complete the steps in the guide you can check whether the connection was successful. Search for **Marketing Setup**, choose **Process**, then **Functions**, and then **Validate Email Logging Setup**.

## Viewing Email Message Exchanges in the Interaction Log
[!INCLUDE[d365fin](includes/d365fin_md.md)] creates an entry on the **Interaction Log** page each time a salesperson and a contact exchange an email message. To view the interaction log, open the **Contact** or **Salesperson*Purchaser** card for the person, and then choose **Navigate**, **History**, and then choose **Interaction Log Entries**. There are a few things we can do with each entry in the log, for example:

* View the content of the email message that was exchanged by clicking the **Show Attachments** action.
* Turn an email exchange into a sales opportunity - If an entry looks promising, you can turn it into an opportunity and then manage its progress toward a sale. To do that, choose the entry, and then choose the **Create Opportunity** action. For more information, see [Managing Sales Opportunities](marketing-manage-sales-opportunities.md).

## See Also
[Managing Relationships](marketing-relationship-management.md)

