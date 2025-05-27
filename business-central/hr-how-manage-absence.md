---
title: Manage Employee Absence
description: Describes how to record employees' absence and analyze absence statistics using the Absence Registration and Employee Absences pages.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 5200, 5201, 5204, 5206, 5208, 5209, 5211, 5212
ms.date: 06/16/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Manage Employee Absence
To manage an employee's absence, you must record the absence on the **Absence Registration** page. It can then be viewed in different ways for analysis and reporting needs.

You can view employee absence in two different pages:

* The **Absence Registration** page, where you register all employee absences with a line for each absence.
* The **Employee Absences** page, where the absences for one employee only is shown. This is the information that you entered on the **Absence Registration** page, filtered by the particular employee.

To obtain meaningful statistics, you should always use the same unit of measure (hour or day) when registering employee absences.

## To register employee absence
You can register employee absences on a daily basis or at some other interval that meets your organizational needs.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Absence Registration**, and then choose the related link.
2. Choose the **New** action.
3. Fill in a line for each employee absence you want to register.
4. Close the page.

    > [!Tip]
    > To obtain meaningful statistics, always use the same unit of measure, hour or day, when registering employee absences.

## To view an individual employee's absence
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Employees**, and then choose the related link.
2. Select the relevant employee, and then choose the **Absences** action.

    The **Employee Absences** page opens showing all the absences and the date on which they started and ended.

## To view an employee's absence by categories
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Employees**, and then choose the related link.
2. Select the relevant employee, and then choose the **Absences by Categories** action.
3. On the **Empl. Absences by categories** page, fill in the filter fields as necessary, and then choose the **Show Matrix** action.

    The **Empl. Absences by Cat. Matrix** page opens showing all absences, broken down by causes of absence.

## To view all employee absences by category
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Absence Registration**, and then choose the related link.
2. On the **Absence Registration** page, choose the **Overview by Categories** action.
3. On the **Absence Overview by Categories** page, set a filter in the **Employee No. Filter** field to view employee absences for individual or a defined group of employees.
4. Choose the **Show Matrix** action.

    The **Absence Overview by Categories Matrix** page opens showing all employees’ absences broken down by the various causes of absence.

## To view all employee absences by period
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Absence Registration**, and then choose the related link.
   On the **Absence Registration** page, choose the **Overview by Periods** action.
2. On the **Absence Overview by Periods** page, set a filter in the **Cause of Absence Filter** field to view employee absences for specified causes of absence.
3. Choose the **Show Matrix** action.

    The **Abs. Overview by Periods Matrix** page opens showing employee absences broken down by periods.

## Related information
[Manage Human Resources](hr-manage-human-resources.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
