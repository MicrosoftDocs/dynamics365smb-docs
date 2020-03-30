---
title: VAT by customer prepayment in Russia
description: Russian enhancements include reporting VAT by customer prepayment.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# VAT by Customer Prepayment

When a company receives a prepayment from a Customer, you must create a VAT invoice and a VAT record for the amount of VAT. 

## Setup

1. To enable the unrealized VAT in the window **General Ledger Setup**.
2. Setup the unrealized VAT type and choose the account which will be taken of the operation of unrealized VAT **VAT posting setup**.
3. To configure the customer posting groups: set account, which will be taken of the operation of the prepayment. 
4. For each account in the chart of accounts, assign: 

- General type of accounting 
- VAT business group  
- VAT product posting group  

4. Setup the VAT posting in **VAT Posting setup** page.

## Receiving prepayment

After you receive prepayment from a customer, the system creates unrealized VAT records and VAT invoices. 

Post prepayment in the General journal (see [Prepayment to the vendor and customers](Prepayments-Vendor-and-Customers.md)).

## Return prepayment

To return a prepayment, you must create a realized VAT record. 

Go to **Customer ledger entries** -> select returned prepayment -> press **return payment.** 

Fill in the fields:

| Field               | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| Posting Date        | Specifies the posting date of the entries that you want to include in the report or batch job. |
| Document No.        | Specifies the number of the related document.                |
| New posting Date    | Specifies the new posting date.                              |
| New Document No.    | Specifies the new document number for the prepayment.        |
| Posting Description | Specifies the description that will be added to the resulting posting. |
| Correction          | Specifies the operation is corrective.                       |

Click "OK". The system will automatically create corrective entries.

## See Also

[Russia Local Functionality](russia-local-functionality.md)  
