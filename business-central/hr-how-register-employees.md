---
title: Register Employees and Modify Information
description: Describes how to use the Human Resources functionality to register new personnel or edit employee information for existing staff.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: personnel, people, employee, staff, HR, register employees
ms.search.form: 5200, 5201, 5204, 5206, 5208, 5209, 5211, 5221, 5228
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Register employees

To use the Human Resources functionality, you must first add each employee by filling out the fields on the **Employee Card** page.

## Adding new employees

You can add new employees manually, by filling out the fields on the **Employee Card** page, or you can use templates that contain predefined information. For example, you can create a template for different types of employee profiles. Using templates saves time when adding new employees, and helps ensure that the information is correct each time. If you create templates for more than one type of employee, you can choose the template to use when you add an employee. If you create only one template, it's used for all new employees. After you create a template, you can use the **Apply Template** action to apply it to one or more selected employees. To create a template, you fill in the information that you want to reuse on the Employee Card page, and then save it as a template.

> [!TIP]
> It can be helpful to personalize the **Employee Template** page when you create a template. For example, you might want to add a field that isn't already displayed on the page. Learn more in [Personalize Your Workspace](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).

You can modify an employee's details at any time. Keeping employee records up-to-date can simplify personnel-related tasks. For example, if an employee's address changes, you register this on the Employee Card page.

> [!NOTE]  
> You can reimburse employees for their expenses during business activities. For this purpose, you must fill in the fields on the **Payments** FastTab on the **Employee Card** page. Learn more in [Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md).

## Set up an employee

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Employees**, and then choose the related link.
2. Choose the **New** action.
3. On the **Employee Card** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Insert a picture of an employee

If you have a picture of an employee, you can insert it on the employee card.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Employees**, and then choose the related link.
2. Open the card for the relevant employee.
3. In the **Employee Picture** FactBox, choose the drop-down button, and then choose **Import**.
4. On the **Select a picture to upload** page, then do one of the following steps to upload the picture file:

   [!INCLUDE[file-upload](includes/file-upload.md)]

The picture is inserted in the **Employee Picture** FactBox.

## Register various information about an employee

On the employee card, you can set up information, such as union membership, relatives, and contracts for the employee. The following steps describe how to set up an alternate address. The steps are similar for all other information that you can set up from an employee card.

You can use alternate addresses to keep track of your employees’ location. For example, if they're stationed abroad, on a long business trip, or residing at a summer residence.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Employees**, and then choose the related link.
2. Open the card for the relevant employee.
3. Choose the **Alternate Addresses** action.
4. **In the Alternate Address List** page, fill in the fields as necessary.
5. Repeat step 4 for each alternate address.

## Related information

[Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
