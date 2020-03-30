---
title: Choosing the User Experience to Show or Hide Advanced Features | Microsoft Docs
description: Learn what the Essential and Premium user experience tiers mean for the user interface, application areas, and your company.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: essential, basic, user interface, application area, experience
ms.date: 04/01/2020
ms.author: sgroespe

---
# Change Which Features are Displayed
[!INCLUDE[d365fin](includes/d365fin_md.md)] is designed to help you run your business regardless of the size and complexity. At the core of the product, you find essential features, such as financial reporting, sales, purchasing, and inventory management. As business complexity increases, you can turn on functionality for manufacturing and service management, for example.

You can define the product complexity level, and thereby which features the company's users get access to, by changing the **Experience** setting on the **Company Information** page. Note that the experience setting can also be changed by adding certain extensions from AppSource. For more information, see [Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md).

The following table lists the experiences that are currently available.

| Experience | Impact on User Interface |
| --- | --- |
| **Essential** |Shows all actions and fields for all common business functionality.|
| **Premium** |Shows all actions and fields for all business functionality, including Manufacturing and Service Management.|

The experiences that can be selected in [!INCLUDE[d365fin](includes/d365fin_md.md)] reflect the solution licenses, called plans, that are defined for the product. For information about the Essential and Premium plans, see [Business Central](https://go.microsoft.com/fwlink/?linkid=870242) on the Microsoft Dynamics 365 marketing site. See also the [[!INCLUDE[d365fin](includes/d365fin_md.md)] Licensing Guide](https://go.microsoft.com/fwlink/?linkid=2068931) (requires access to CustomerSource or PartnerSource).

> [!IMPORTANT]  
> All regular users in a solution must be assigned the same plan, Essential or Premium, before that experience can be selected for the company. Accordingly, one user cannot access Premium features if one or more other users can only access Essential features. This is not the case for non-regular users of type Team Member, Internal Admin, External Accountant, and Delegated Admin, who can each be assigned a different plan than other users in the solution.<br /><br /> Only users of type Evaluation or Premium can change the value in the **Experience** field from Essential to Premium.

Prior to defining a company's experience setting, you define users' access to specific functions and pages by assigning permission sets. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).

The **Experience** setting applies to all users in a company, but each user can personalize their own experience further by changing page layouts and content. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

## Enabling Premium Features after Upgrading a Plan
Users are assigned to plans in Microsoft 365 Admin Center in connection with the general work to create the Business Central users. For more information, see [Add users individually or in bulk to Office 365](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).

### To update plan changes in users groups
When you have made a change to users plans in Microsoft 365 Admin Center, such as assigned more users to the Premium plan, you must reflect the change in [!INCLUDE[d365fin](includes/d365fin_md.md)].

1. Sign is as an administrator.
2. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
3. On the **Users** page, choose the **Refresh all User Groups** action.

All new information about the users’ plans and their assigned user groups are now updated according to the plan changes.

### To select the Premium experience
You can now proceed to select the new experience.
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.
2. On the **Company Information** page, on the **User Experience** FastTab, select Premium  in the **Experience** field.

## Help Assumes Premium Experience
All feature descriptions in user documentation for [!INCLUDE[d365fin](includes/d365fin_md.md)] assume the **Premium** experience, meaning the descriptions cover the full scope of UI elements.

## See also
[Personalize Your Workspace](ui-personalization-user.md)  
[Customizing Business Central](ui-customizing-overview.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Creating New Companies](about-new-company.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[[!INCLUDE[d365fin](includes/d365fin_md.md)] Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=871590&clcid=0x409)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
