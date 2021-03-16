---
title: Share contacts between Business Central and Outlook| Microsoft Docs
description: This service has deep integration with Microsoft 365 so you can share contacts between Outlook and Business Central.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: contacts, Microsoft 365
ms.date: 10/01/2020
ms.author: edupont

---
# Synchronize Contacts in Business Central with Contacts in Microsoft Outlook
You can see the same contacts in [!INCLUDE[prod_short](includes/prod_short.md)] as you see in Outlook if you set up contact synchronization. For example, if you are a sales person, you might do some of your work in Outlook and some of your work in [!INCLUDE[prod_short](includes/prod_short.md)]. If the contacts are the same in both places, your work is more straightforward.  

A dedicated folder in Outlook makes contacts easy to find, and you can set a filter to synchronize only the contacts from [!INCLUDE[prod_short](includes/prod_short.md)] that you want to see in Outlook. Once the contact synchronization is set up, you can start synchronization manually or set up an automatic synchronization that will keep the contacts in sync on a scheduled basis.  

## Set Up Synchronization
You set up how you want to synchronize contacts with Outlook on the **Exchange Sync. Setup** page in [!INCLUDE[prod_short](includes/prod_short.md)]. As a prerequisite, your user profile in [!INCLUDE[prod_short](includes/prod_short.md)] must specify your Microsoft 365 email account. You can check this in the **Microsoft 365 Authentication** section of your user profile in the **Users** list.  

Then, on the **Exchange Sync. Setup** page, you can validate that the connection to Exchange is working and then set up contact synchronization. Open the **Contact Sync. Setup** page and start the synchronization. Optionally, set a filter for which contacts to synchronize between [!INCLUDE[prod_short](includes/prod_short.md)] and Outlook. For example, you can set a filter on name, type, company, or similar. You can also change the default name of the folder that the contacts will synchronize to in Outlook. The default name is *Business Central*.  

Once this synchronization has been set up, any changes to that you make to the contact in either Outlook or in [!INCLUDE[prod_short](includes/prod_short.md)] is synchronized to the other.  

Each of your coworkers can also set up their own Exchange synchronization and set their own filter on which contacts to synchronize.  

## Synchronize Contacts
If you are used to working with contacts in [!INCLUDE[prod_short](includes/prod_short.md)], then you will find it easy to start the synchronization manually whenever it suits you from the **Contacts** list. Simply choose the **Sync with Office 365** action, and then decide if you want to change the filter that you have set up. When you choose the OK button, the synchronization starts immediately, and the latest changes are applied to your contacts in Outlook.  

In the **Contacts** list, you can synchronize contacts in two ways:

* **Sync with Office 365**

  This action synchronizes all changes from [!INCLUDE[prod_short](includes/prod_short.md)] to Microsoft 365 since the previous synchronization, based on the last modified date. Any new contacts from Microsoft 365 will be synchronized back to [!INCLUDE[prod_short](includes/prod_short.md)] as well. This is typically faster than doing a full sync.  

* **Full Sync with Office 365**

  This action synchronizes all contacts in both directions regardless of the last sync date and last modified date.  

In both cases, contacts are only synchronized from Outlook if they have the required fields filled in. The required fields to synchronize to Microsoft 365 are **Name**, **Email address** and they must be of type Person. [!INCLUDE[prod_short](includes/prod_short.md)] is the master of the contact information, so the [!INCLUDE[prod_short](includes/prod_short.md)] contact information will be saved in the event of duplicates.  

In Outlook, the contacts from [!INCLUDE[prod_short](includes/prod_short.md)] are shown in a folder under **Other contacts** in the **People**  view. If you are not familiar with the People view in Outlook, then you can get to it from the navigation options in the bottom left corner of Outlook.  

## See Also
[Getting Started](product-get-started.md)  
[Finance](finance.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Using contacts (People) in Outlook on the web](https://support.office.com/article/Using-contacts-People-in-Outlook-on-the-web-1e3438c7-26b2-420c-87de-3cea9d31b5cb?appver=OWB150)  


[!INCLUDE[footer-include](includes/footer-banner.md)]