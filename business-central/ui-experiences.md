---
title: Change which features are displayed
description: Learn what the Essentials and Premium user experience tiers mean for the user interface, application areas, and your company.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: essential, basic, user interface, application area, experience
ms.search.form: 1,
ms.date: 03/11/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Change which features are displayed

[!INCLUDE[prod_short](includes/prod_short.md)] is designed to help you run your business regardless of the size and complexity. At the core of the product, you find essential features, such as financial reporting, sales, purchasing, and inventory management. As business complexity increases, you can turn on functionality for manufacturing and service management, for example.

You can define the product complexity level, and thereby which features the company's users get access to, by changing the **Experience** setting on the **Company Information** page. Note that the experience setting can also be changed by adding certain extensions from AppSource. For more information, see [Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md).

The following table lists the experiences that are currently available.

| Experience | Impact on User Interface |
| --- | --- |
| **Essentials** |Shows all actions and fields for all common business functionality.|
| **Premium** |Shows all actions and fields for all business functionality, including Manufacturing and Service Management.|

The experiences that can be selected in [!INCLUDE[prod_short](includes/prod_short.md)] reflect the solution licenses, called plans, that are defined for the product. For information about the Essentials and Premium plans, see [Business Central](https://go.microsoft.com/fwlink/?linkid=2264940) on the Microsoft Dynamics 365 marketing site. See also the [[!INCLUDE[prod_short](includes/prod_short.md)] Licensing Guide](https://go.microsoft.com/fwlink/?linkid=2264939).

> [!IMPORTANT]  
> Users of type Team Member, Internal Admin, External Accountant, and Delegated Admin can be assigned a different plan than other users in the solution. Only users of type Evaluation or Premium can change the value in the **Experience** field from Essentials to Premium.

> [!NOTE]
> In 2024 release wave 1, a user with the Premium plan can sign in to a company that's using the Essentials plan. However, the Premium user can't use any of the features that the Premium license provides. The same isn't true in the opposite direction. Users who have the Essentials plan can't sign in to a company that's using the Premium plan.

Prior to defining a company's experience setting, you define users' access to specific functions and pages by assigning permission sets. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).

The **Experience** setting applies to all users in a company, but each user can personalize their own experience further by changing page layouts and content. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

## Enabling premium features after upgrading a plan

Users are assigned to plans in Microsoft 365 Admin Center in connection with the general work to create the Business Central users. For more information, see [Add users and assign licenses at the same time](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true).

### To update plan changes in users groups

[!INCLUDE [2023rw1-sec-group-short](includes/2023rw1-sec-group-short.md)]

When you have made a change to users plans in Microsoft 365 Admin Center, such as assigned more users to the Premium plan, you must update [!INCLUDE[prod_short](includes/prod_short.md)] to reflect the change.

1. Sign is as an administrator.
2. [!INCLUDE[open-search](includes/open-search.md)], enter **Users**, and then choose the related link.
3. On the **Users** page, choose the **Update users from Microsoft 365** action.

### To select the Premium experience

You can now proceed to select the new experience.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Company Information**, and then choose the related link.
2. On the **Company Information** page, on the **User Experience** FastTab, select Premium  in the **Experience** field.

## Help assumes the Premium experience

All feature descriptions in user documentation for [!INCLUDE[prod_short](includes/prod_short.md)] assume the **Premium** experience, meaning the descriptions cover the full scope of UI elements.

## Related information

[Personalize Your Workspace](ui-personalization-user.md)  
[Customizing Business Central](ui-customizing-overview.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Creating New Companies](about-new-company.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
