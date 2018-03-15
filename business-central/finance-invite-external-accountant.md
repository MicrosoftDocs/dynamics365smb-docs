---
title: Add your external accountant to your Financials | Microsoft Docs
description: Learn how you can invite your external accountant to your Business Central .
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accountant, accounting
ms.date: 01/25/2018
ms.author: edupont

---
# Inviting Your External Accountant to Your [!INCLUDE[d365fin](includes/d365fin_md.md)]
If you use an external accountant to manage your books and financial reporting, you can invite them to your [!INCLUDE[d365fin](includes/d365fin_md.md)] so they can work with you on your fiscal data.

Once your accountant has gained access to your [!INCLUDE[d365fin](includes/d365fin_md.md)], they can use the **Accountant** Role Center that gives easy access to the most relevant windows for their work.  

## Invite Your Accountant to Your [!INCLUDE[d365fin](includes/d365fin_md.md)]
In the latest version of [!INCLUDE[d365fin](includes/d365fin_md.md)], we have made it easy for you to invite your external accountant. Simply open the **Users** window, and then choose the **Invite External Accountant** action in the ribbon. An email is made ready for you, just add your accountant's work email, and send the invitation.  

![Invite your accountant](./media/finance-invite-accountant/invite-accountant.png)

> [!TIP]  
>  This requires that you have set up SMTP email. You can do this yourself or ask your [!INCLUDE[d365fin](includes/d365fin_md.md)] partner. Also, you must be logged in to [!INCLUDE[d365fin](includes/d365fin_md.md)] as a user administrator, not as the business owner or other users. Finally, you must have left the trial company so that you have an Azure Active Directory administrator.  

> [!IMPORTANT]  
>  The accountant's email address must be a work address that is based an Active Directory. If the accountant uses another type of email, then the invitation cannot be sent.  

### Separate License
Behind the scenes, the accountant is added to your Active Directory tenant. Your administrator can verify that the accountant accepts the invitation and is assigned the correct license. The steps for doing this depends on the type of account that you used when you signed up for [!INCLUDE[d365fin](includes/d365fin_md.md)]. This topic is based on the use of an Office 365 account, which uses Microsoft Azure Active Directory.  

If you have activated your subscription of [!INCLUDE[d365fin](includes/d365fin_md.md)] and are no longer using the evaluation company, you have an Azure Active Directory tenant. Your administrator or [!INCLUDE[d365fin](includes/d365fin_md.md)] partner manages this tenant in the [Azure portal](https://portal.azure.com). This is where new users are added and licenses are applied and removed. For more information, see the [Microsoft Azure portal overview](https://docs.microsoft.com/en-us/azure/azure-portal-overview).  

One of the license types for [!INCLUDE[d365fin](includes/d365fin_md.md)] is the *External Accountant* license. This license type is intended for use by users such as external accountants. This means that you do not have to buy an extra seat in your current Active Directory or use one of your existing [!INCLUDE[d365fin](includes/d365fin_md.md)] user accounts on your external accountant. For example, if your current Office 365 subscription includes 10 users for [!INCLUDE[d365fin](includes/d365fin_md.md)], and you are currently using 10 *Full User* licenses, your administrator can simply add your external accountant as a guest user in the Azure portal and assign this user the *External Accountant* license at no additional cost. However, you can only have one user with the *External Accountant* license. If you want to add more users, you must update your Office 365 subscription accordingly.  

## See Also
[Finance](finance.md)  
[Set Up Email Manually or Using the Assisted Setup](admin-how-setup-email.md)  
[Accountant Experiences in Business Central ](finance-accounting.md)  
[Business Central for Accountants on Microsoft.com](https://www.microsoft.com/en-us/dynamics365/financial-insights-for-accountants)  
