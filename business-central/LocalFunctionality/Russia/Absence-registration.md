---
title: Absence registration in Russia
description: Russian enhancements include absence registration.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Absence registration

All types of absence which are paid according to the legislation on average earnings shall be registered by the corresponding types of orders. 

There are four types of orders in [!INCLUDE[prodshort](../../includes/prodshort.md)]:

- Vacation; 
- Travel; 
- Sick leave; 
- Other types of absence. 

All types of orders are issued in a similar way. 

1. Go to **Departments > Human resources > Absence Orders** 
2. Fill the header of order:

| Field         | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| No.           | Specifies the number of the involved entry or record, according to the specified number series. |
| Employee No.  | Specifies the number of the involved employee.               |
| Document Date | Specifies the date when the related document was created.    |
| Posting Date  | Specifies the entry's posting date.                          |
| HR Order No.  | Number of the order for absence which will be displayed in the corresponding printed form of the document. By default, the value of the field is the same as the value of the No. field, but can be changed manually |
| HR Order Date | Date of the order for absence, which will be displayed in the printed form of the document. By default, the field value is the same as the document date field, but can be changed manually |
| Period Code   | The period code in which the current document must be included in the payroll document. By default, the field is filled in automatically with a period code that corresponds to the posting date |

3. Fill the line:

| Field              | Description                                                  |
| ------------------ | ------------------------------------------------------------ |
| Time Activity Code | Temporary activity code corresponding to the type of order   |
| Element Code       | Specifies the code of the related payroll element for tax registration purposes. |
| Description        | Specifies the description associated with this line.         |
| Start Date         | Specifies the first day of the activity in question.         |
| End Date           | Specifies the last day of the activity in question.          |

4. For the formation of transactions in the books document should be post. 

Absence types defined by a considered order, recorded in the Employee Ledger Entries. 

The considered order can be cancelled. The function is available in the form of a card of the considered order. Only orders for which wages are not calculated may be cancelled.

## See Also

[Human Resources](Human-Resources.md)
