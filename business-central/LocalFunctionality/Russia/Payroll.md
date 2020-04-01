---
title: Payroll in Russia
description: Russian enhancements include support for payrolls.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Payroll

The basic unit of payroll is the **salary element**. Each salary element has an individual setting that provides calculation of accrual/deduction/deduction according to pre-defined rules. 

Types of salary element:

- Wage
- Bonus
- Income tax
- Tax deduction
- Deduction
- Other
- Funds

Salary elements that are similar in purpose are combined into **calculation types**. Each type of calculation has a certain priority, which determines its sequence in the overall payroll.

Other types of calculation that must be made when calculating the final or interim payments of wages, forms a **Calculated payroll group** (or **the calculation Group**). The calculation group is set in the employee card.

Main functions of the payroll module:

- Appointment of wages; 
- Implementation of compensation and incentive payments (bonuses); 
- Calculation of average earnings;
- Provision of basic types of deduction defined by the current legislation; 
- Provision of tax deductions according to the current legislation; 
- Calculation of personal income tax and payments to funds according to the current legislation.

## Payroll accounting groups

Accounting payroll group belongs to the category of special accounting groups.

For each payroll item, a payroll accounting group can be defined, the setup  determines the Ledger accounts to be used when generating transactions. The posting group that is set up for the item can be overridden in the calculation type (to enable payroll expenses to be allocated to different Ledger accounts). The accounting group specified in the calculation type has a higher priority. By default, all payroll items use the posting group specified on the employee card (the Posting group field), which has the lowest priority.

## Payroll

Payroll is performed by a special salary document, individual for each employee.

[!INCLUDE[prodshort](../../includes/prodshort.md)] supports two types of payroll documents: 

- Payment of salary in interperiod; 
- Basic payroll. 

The first type of document is used to calculate employee payments during the month (prepayment, vacation, sick leave, dismissal). When you post a payroll document of this type, no transactions are generated in the General Ledger and transactions in the payroll Ledger. On the basis of documents of this type can be formed payment documents for payment to an individual. 

The second type of document – the basic payroll – should be formed for each employee at the end of each month after taking into account all types of orders for the absence and approval of the timesheet. When you post a payroll document of the second type, transactions are generated in the payroll Ledger, as well as financial transactions in the Ledger; the resulting wage arrears are reflected on the corresponding card of the individual vendor. On the basis of the existing debt can be formed for each individual employee payment documents.

The organization and principle of calculation of both types of documents is the same:

1. Go to **Human Resources > Payrol > Payroll documents**
2. To automatically generate payroll documents, run the **Suggest documents** function.
3. Fill in the fields:

| Field                  | Description                                                  |
| ---------------------- | ------------------------------------------------------------ |
| Calculation Period     | Specify the period for which the salary will be calculated.  |
| Calculation Date       | The calculation date is set equal to the last day of the month of the selected calculation period and corresponds to the date of accounting of the salary document (date of payroll employee). |
| Calculation Group Code | Do not fill the field for the final payroll at the end of the month. Calculation group will be used from imployee card. To pay in the interperiod, enter the code of the desired calculation group. |
| Create New Documents   | Select the check box if you want to create new payroll documents in any case. If the field is not marked, the system will try to use previously created payroll documents for this employee (the employee Code and period Code fields must match the parameters of the current calculation) |
| Show Messages          | Select the check box to display detailed messages about errors that occur at the time of calculation. If the field is not marked, error messages will not be displayed, and incorrect payroll documents will not be generated |

4. To generate salary documents, click OK. 

  > [!NOTE]
  > If you have generated documents but have not found any new documents in the list, try to update the page (Actions – Update).

5. For the formation of transactions in the Ledger and the possibility of payment of wages in the inter-period salary documents must be post.

## See Also

[Human Resources](Human-Resources.md)  
