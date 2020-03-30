---
title: Establishment of charges and deductions in Russia
description: Russian enhancements include charges and deductions.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Establishing Charges and Deductions to the Employee

The Employee Journal is the primary means of changes in the list of charges/deductions established for the employee. The employee journal can also be used to record non-financial personnel orders.

The most often through journal recorded:

- orders on the bonuses of the employee;


- orders on administrative fine;

- orders on allocation to the employee of the benefits/social payments defined by law;

- statements on the employee deductions specified in law;

- orders on allocation to the employee of financial assistance, a gift.

> [!NOTE
> The employee journal has no restrictions on the registration of certain types of charges and deductions, but the essential working conditions should be changed by supplementing the employment contract. This ensures the possibility of forming the necessary printed forms of documents for the employee.

The list of fields that must be filled on the employee journal line is determined by the payroll element code.

### Fill in the journal lines, which is used to register charges/deductions with a predetermined amount.

| Field                           | Description                                                  |
| ------------------------------- | ------------------------------------------------------------ |
| Posting Date                    | Specifies the entry's posting date.                          |
| Period Code                     | Payment period of charges/deductions. By default, the period code is determined based on the posting date. If necessary, the period code can be changed. The period code determines whether charges/deduction is included in the payroll document |
| Document Date                   | Specifies the date when the related document was created.    |
| Document No.                    | Specifies the number of the related document.                |
| HR Order No.                    | The number of the personnel order that will be displayed in the printed form of the document. By default, the field value is the same as the document Number field |
| HR Order Date                   | Date of the personnel order to be displayed in the printed form of the document. By default, the field value is the same as the document date field |
| Employee No.                    | Specifies the number of the involved employee.               |
| Element Code                    | Specifies the code of the related payroll element for tax registration purposes. |
| Post Action                     | Add                                                          |
| Description                     | A text description of the charges/deductions                 |
| Starting Date                   | Specifies the first day of activity in question.             |
| Ending Date                     | Specifies the last day of the activity in question. The field can be empty. In this case, the accrual is interpreted as indefinite and will be included in the payroll calculation until it is canceled. |
| Wage Period To/Wage Period From | The period for which this type of accrual is set. The field is required for salary elements of the Bonuses type. |
| Amount                          | Amount of charges/deductions                                 |

The journal line must be posted for the charges/deductions to take effect.

All charges and deductions are recorded in the employee Ledger entries. The list of charges and deductions of each employee is available in the employee card.

The generated accrual will be automatically included in the payroll calculation for the period defined by the start date and end date fields.

### Update charges

In order to cancel or change a previously made employee accrual, you must generate the employee journal line as described above, except for the following fields:

| Field            | Description                                                  |
| ---------------- | ------------------------------------------------------------ |
| Post Action      | **Close** – to stop the inclusion of the payroll item in the payroll.The date from which the payroll item is no longer included in the payroll calculation must be specified in the end date field (usually the last date of the month). You can leave the Amount field blank because the value of this field does not change in the employee Ledger.                                                             **Update** – change the amount for an existing charge/hold. Please note that the Amount field must be filled in. Otherwise, the transaction amount will be set to 0, that is, the accrual/deduction is actually canceled. |
| Applies-to entry | The entry number from the Employee Ledger Entries that you want to close or update. |

In the process of posting a journal line of this type, the specified entry is modified in the Employee Ledger Entries. The modification changes the Amount or end date of the operation.

## See Also

[Human Resources](Human-Resources.md)
