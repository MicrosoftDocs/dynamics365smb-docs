---
title: Use Invoicing and Business Central | Microsoft Docs
description: Workaround for accessing Microsoft Invoicing when you have signed up for Dynamics 365 Business Central.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Invoicing, Office 365
ms.date: 04/01/2020
ms.author: bholtorf

---
# Using the same Office 365 Account in [!INCLUDE[d365fin](includes/d365fin_long_md.md)] and Microsoft Invoicing
When you sign up for a trial with [!INCLUDE[d365fin](includes/d365fin_md.md)], you can move to a 30-day evaluation phase, you can start a subscription, or you can stop using [!INCLUDE[d365fin](includes/d365fin_md.md)]. In all cases, if you sign in to the Office Portal, you might see a tile called **Microsoft Invoicing** and click it. This is part of the Office 365 Business Premium subscription, so not everyone will see that tile in the Office Portal.  

If you access Microsoft Invoicing, you will see a message that you cannot access Microsoft Invoicing because your account is used in [!INCLUDE[d365fin](includes/d365fin_md.md)].  

You see a similar message if you install the mobile app for Invoicing.  

## Workaround
Invoicing and [!INCLUDE[d365fin](includes/d365fin_md.md)] have a shared platform. That means that you are recognized as an existing user of [!INCLUDE[d365fin](includes/d365fin_md.md)] when you click Invoicing in the Office Portal. The reason is that Invoicing cannot use the same company as [!INCLUDE[d365fin](includes/d365fin_md.md)].  

So you will have to sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)] and rename your existing company, and then create a new company that you can then use in Invoicing. No data is moved or overwritten during this workaround.

### To rename your company
1. Sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)].
2. In the top right corner, choose the **Settings** icon ![Settings](media/ui-experience/settings_icon_small.png "Settings icon for role center"), and then choose **My Settings**.
3. In the **Company** field, choose a different company.
4. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Companies**, and then choose the related link.  
5. On the **Companies** page, choose **Edit List**.  
6. Change the name of the *My Company* entry to something else.  

    Wait a number of minutes. We’ll be making a number of changes in the underlying database, and that takes a while.
7.	When the system is ready again, choose the **Create New Company** button.  
8.  In the dialog that appears, specify the name as *My Company*, and choose the **Production – Setup Data Only** option.  

This again takes a number of minutes. When the process completes, you will be able to access Invoicing as part of your Office 365 Business Premium experience.  

### What about my data?
When you rename the original My Company, the database tables that store your existing [!INCLUDE[d365fin](includes/d365fin_md.md)] data are renamed, but the data itself is not touched.  

If you use both Invoicing and [!INCLUDE[d365fin](includes/d365fin_md.md)], the data is stored in two different containers (the two companies). Nothing is shared, so you'll have to manage customers and items in both companies.  

## See Also
[Frequently Asked Questions](across-faq.md)  
[Administration](admin-setup-and-administration.md)  
