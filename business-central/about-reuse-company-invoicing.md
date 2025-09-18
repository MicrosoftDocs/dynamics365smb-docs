---
title: Use Invoicing and Business Central
description: Workaround for accessing Microsoft Invoicing when you have signed up for Dynamics 365 Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Invoicing, Microsoft 365
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Use the same Microsoft 365 Account in [!INCLUDE[prod_short](includes/prod_long.md)] and Microsoft Invoicing
When you sign up for a trial with [!INCLUDE[prod_short](includes/prod_short.md)], you can move to a 30-day evaluation phase, you can start a subscription, or you can stop using [!INCLUDE[prod_short](includes/prod_short.md)]. In all cases, you may at some point have seen something called **Microsoft Invoicing** and clicked it. This was an app that was part of what is now Microsoft 365 Business Standard and was formerly known as Microsoft 365 Business Premium subscription, so not everyone will have seen that tile in their Microsoft 365 experience.  

Microsoft Invoicing is no longer available, but if you need to sign into Invoicing to retrieve your data, you might see a message that you cannot access Microsoft Invoicing because your account is used in [!INCLUDE[prod_short](includes/prod_short.md)].  

You see a similar message if you install the mobile app for Invoicing.  

## Workaround
Invoicing and [!INCLUDE[prod_short](includes/prod_short.md)] have a shared platform. That means that you are recognized as an existing user of [!INCLUDE[prod_short](includes/prod_short.md)] when you click Invoicing in the Microsoft 365 admin center. The reason is that Invoicing cannot use the same company as [!INCLUDE[prod_short](includes/prod_short.md)].  

So you will have to sign in to [!INCLUDE[prod_short](includes/prod_short.md)] and rename your existing company, and then create a new company that you can then use in Invoicing. No data is moved or overwritten during this workaround.

### To rename your company
1. Sign in to [!INCLUDE[prod_short](includes/prod_short.md)].
2. In the top right corner, choose the **Settings** icon ![Settings.](media/ui-experience/settings_icon_small.png "Settings icon for role center"), and then choose **My Settings**.
3. In the **Company** field, choose a different company.
4. [!INCLUDE[open-search](includes/open-search.md)], enter **Companies**, and then choose the related link.  
5. On the **Companies** page, choose **Edit List**.  
6. Change the name of the *My Company* entry to something else.  

    Wait a number of minutes. We’ll be making a number of changes in the underlying database, and that takes a while.
7.	When the system is ready again, choose the **Create New Company** button.  
8.  In the dialog that appears, specify the name as *My Company*, and choose the **Production – Setup Data Only** option.  

This again takes a number of minutes. When the process completes, you will be able to access Invoicing as part of your Microsoft 365 Business Standard experience. but only to export data since the Invoicing app is deprecated.  

### What about my data?
When you rename the original My Company, the database tables that store your existing [!INCLUDE[prod_short](includes/prod_short.md)] data are renamed, but the data itself is not touched.  

If you use both Invoicing and [!INCLUDE[prod_short](includes/prod_short.md)], the data is stored in two different containers (the two companies). Nothing is shared, so you'll have to manage customers and items in both companies.  

## Related information
[Frequently Asked Questions](across-faq.yml)  
[Administration](admin-setup-and-administration.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
