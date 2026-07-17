---
title: Enable Premium features
description: Learn what the Essentials and Premium user experience tiers mean for the user interface, application areas, and your company.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: Premium, activate Premium, enable Premium, Premium experience, Company Information, Manufacturing, Service Management, trial, essential, user interface, application area, experience
ms.search.form: 1,
ms.date: 07/16/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Enable premium features

[!INCLUDE[prod_short](includes/prod_short.md)] helps you run your business regardless of the size and complexity. At the core of the product, you find essential features, such as financial reporting, sales, purchasing, and inventory management. As business complexity increases, you can turn on premium functionality for manufacturing and service management.

You can define the product complexity level, and thereby which features the company's users get access to, by changing the **Experience** setting on the **Company Information** page. Note that the experience setting can also be changed by adding certain extensions from Marketplace. For more information, see [Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md).

## To select the premium experience

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Company Information**, and then choose the related link.
1. On the **Company Information** page, on the **User Experience** FastTab, select **Premium** in the **Experience** field.

The following table lists the experiences that are currently available.

| Experience | Impact on User Interface |
| --- | --- |
| **Essentials** |Shows all actions and fields for all common business functionality.|
| **Premium** |Shows all actions and fields for all business functionality, including Manufacturing and Service Management.|

## Licenses and permissions

Only users with an Evaluation or Premium license can change the **Experience** field from **Essentials** to **Premium**. If your administrator recently assigned or changed premium licenses, first [update user information and license assignments in [!INCLUDE[prod_short](includes/prod_short.md)]](ui-how-users-permissions.md#adduser). Selecting the **Premium** experience doesn't assign premium licenses.

The **Experience** setting controls which features are available to all users in the company. Permission sets are more specific, and control which features and pages each user can access. Each user can also [personalize their workspace](ui-personalization-user.md) by changing page layouts and content.

> [!IMPORTANT]
> Users with an Essentials license can't sign in to a company that uses the **Premium** experience.

Learn about the different types of licenses and how licensing works in the [Dynamics 365 Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=866544).

## Help assumes the Premium experience

All feature descriptions in user documentation for [!INCLUDE[prod_short](includes/prod_short.md)] assume the **Premium** experience, meaning the descriptions cover the full scope of UI elements.

## Related information

[Create Users According to Licenses](ui-how-users-permissions.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Personalize Your Workspace](ui-personalization-user.md)  
[Customizing Business Central](ui-customizing-overview.md)  
[Company Information Overview](admin-company-information.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
