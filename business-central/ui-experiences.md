---
title: Choosing the User Experience to Show or Hide Advanced Features | Microsoft Docs
description: Learn what the Basic and Essential user experience tiers mean for the user interface, application areas, and your company.
documentationcenter: ''
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: essential, basic, user interface, application area, experience
ms.date: 04/17/2018
ms.author: edupont

---
# Changing Which Features are Displayed in [!INCLUDE[d365fin](includes/d365fin_md.md)]
[!INCLUDE[d365fin](includes/d365fin_md.md)] is designed to help you run your business, regardless which line of business you are in. At the core of [!INCLUDE[d365fin](includes/d365fin_md.md)], you find financial reporting and sales and purchasing processes. You add experiences to that according to your business needs by adding extensions from AppSource or by changing the Experience setting for your company. For more information, see [Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md), or the "Choosing a User Experience to Show or Hide Features" section below.

## Choosing a User Experience to Show or Hide Features
The user experience determines how much of the core functionality is available when you and your colleagues use [!INCLUDE[d365fin](includes/d365fin_md.md)]. You can choose the user experience for your company in the **Company Information** window, in the **Experience** field.

> [!NOTE]  
> This setting applies to all users in your company. Users can customize their own experience even further by changing page layouts and content. For more information, see [Personalizing Your Workspace and Pages](ui-personalization-user.md).  

The following table lists the experiences that are currently available.

| Experience | Impact on User Interface |
| --- | --- |
| **Basic** |Shows only core actions and fields within the most common business functionality, such as sales, purchasing, inventory, and finance. |
| **Essential** |Shows all actions and fields for all common business functionality.|
| **Premium** |Shows all actions and fields for all business functionality, including Manufacturing and Service Management.|

> [!NOTE]  
> The experiences that you can select from in [!INCLUDE[d365fin](includes/d365fin_md.md)] depend on your solution license, called a plan. For information about the **Essential** and **Premium** plans, see [Business Central](https://go.microsoft.com/fwlink/?linkid=870242) on the Microsoft Dynamics 365 marketing site.

> [!IMPORTANT]  
> All regular users in a solution must be assigned the same plan, Essential or Premium, before that experience can be selected for the company. Accordingly, one user cannot access Premium features if one or more other users can only access Essential features. This is not the case for non-regular users of type Team Member, Internal Admin, External Accountant, and Delegated Admin, who can each be assigned a different plan than other users in the solution.

## Enabling Premium Features after Upgrading a Plan
Users are assigned to plans in Office 365 Admin Center in connection with the general work to create the Business Central users. For more information, see [Add Users to Office 365 for business](https://support.office.com/en-us/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).

You can then define which specific functions and windows within the experience those users are allowed to access by assigning permission sets. For more information, see [Managing Users and Permissions](ui-how-users-permissions.md).

### To update plan changes in users groups
When you have made a change to users plans in Office 365 Admin Center, such as assigned more users to the Premium plan, you must reflect the change in [!INCLUDE[d365fin](includes/d365fin_md.md)].

1. Sign is as an administrator.
2. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Users**, and then choose the related link.
3. In the **Users** window, choose the **Refresh all User Groups** action.

All new information about the users’ plans and their assigned user groups are now updated according to the plan changes.

### To select the Premium experience
You can now proceed to select the new experience.
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Company Information**, and then choose the related link.
2. In the **Company Information** window, on the **User Experience** FastTab, select Premium  in the **Experience** field.

## Business Central versus Dynamics NAV – Differences in UI
In [!INCLUDE[d365fin](includes/d365fin_md.md)], the Application Areas system and the Experience options enable you to show/hide relevant parts of the product according to the purchased plan (Essential or Premium) and according to business processes (application areas reflect features).

The UI for [!INCLUDE[d365fin](includes/d365fin_md.md)] is also generally simplified so that it is now different from the Dynamics NAV UI. For example, fields that are not commonly used, such as **Fax No.**, have been removed, and on ribbons on lists and cards , duplicate actions are removed and the most used actions are promoted. A few complete features, such as Comments, are being optimized for the web client and are, therefore, not available in [!INCLUDE[d365fin](includes/d365fin_md.md)] yet.

Accordingly, certain differences currently exist between [!INCLUDE[d365fin](includes/d365fin_md.md)] and Dynamics NAV because selected UI fields and actions are hidden. A detailed list of the features not currently surfaced in the UI will be added to this topic soon. Such controls have the #Advanced application area tag.

## How to Get Dynamics NAV UI in [!INCLUDE[d365fin](includes/d365fin_md.md)]
If you want your [!INCLUDE[d365fin](includes/d365fin_md.md)] solution to have the same UI experience as your previous on-premise Dynamics NAV solution, then you can surface the #Advanced controls, through an extension.

> [!NOTE]  
> If you chose to surface all #Advanced controls, then you will also loose the UI simplifications that are made the standardversion of [!INCLUDE[d365fin](includes/d365fin_md.md)].

The procedure for extending the application areas list and adding it to an experience is found here: [Extending Application Areas](https://docs.microsoft.com/en-us/dynamics-nav/developer/devenv-extending-application-areas).

> [!TIP]  
> Since the application area that you want to use, #Advanced , is already in the list, you can skip the "Add a new application area in the Application Area Setup Table” step and go straight to step two, "Enable the application Area in the OnInstallAppPerCompany."


## See also
[Creating New Companies](about-new-company.md)  
[Managing Users and Permissions](ui-how-users-permissions.md)    
[Changing Basic Settings](ui-change-basic-settings.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
## [!INCLUDE[d365fin](includes/training_link_md.md)]
