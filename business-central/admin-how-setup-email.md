---
title: Set up email in Business Central | Microsoft Docs
description: Describes how to use the company's SMTP server to send and receive email messages within Business Central, or alternatively how to use the email server settings created with the Office 365 subscription.
documentationcenter: ''
author: edupont04

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: SMTP, mail, Office 365
ms.date: 04/01/2019
ms.author: edupont

---
# Set Up Email Manually or Using the Assisted Setup
To send and receive emails from within [!INCLUDE[d365fin](includes/d365fin_md.md)], you must fill in the fields on the **SMTP Mail Setup** page.

> [!NOTE]  
>   Instead of entering the SMTP server details, you can use a function to enter them with information from your Office 365 subscription.

You can either set email up manually or you can get help by using the **Email Setup** assisted setup guide. For more information, see [Getting Ready for Doing Business](ui-get-ready-business.md).  

## To set up email
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SMTP Email Setup**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Alternatively, choose the **Apply Office 365 Server Settings** action to insert any information that is already defined for your Office 365 subscription.
4. When all the fields are correctly filled in, choose the **Test Email Setup** action.
5. When the test succeeds, close the page.

## Sending Email Messages from a Send As Email Address
You can let one or more users send email messages from an email address that you own, but is different than their normal address. For example, if you are running a sales campaign, you might want people to send messages from the same address, such as sales@yourcompanyname.com. To set that up, you must specify the address to send as in two places:

* In [!INCLUDE[d365fin](includes/d365fin_md.md)], on the **SMTP Email Setup** page, specify the address in the **Send As** field.   
* In the **Exchange admin center** for your Office 365 account, specify the address in the **Send As** field for each user that can send messages from the address. For more information, see [Manage permissions for recipients](https://docs.microsoft.com/en-us/Exchange/recipients/mailbox-permissions?view=exchserver-2019).

 > [!Note] 
 > After you specify the account to send messages as, the address will display for each user in the Office 365 admin center, but that is only for informational purposes. You can only change or remove the account in the Exchange admin center.

## See Also  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Setting Up [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Using [!INCLUDE[d365fin](includes/d365fin_md.md)] as Your Business Inbox in Outlook](admin-outlook.md)  
[Getting [!INCLUDE[d365fin](includes/d365fin_md.md)] on My Mobile Device](install-mobile-app.md)
