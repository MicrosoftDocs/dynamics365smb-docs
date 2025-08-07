---
title: VAT by customer prepayment in Russia
description: Learn how to report VAT on customer prepayments in Russia, including setup and processing steps in Business Central.
author: DianaMalina
ms.topic: article
ms.search.keywords: customer prepayment, receiving prepayment,return prepayment, VAT prepayment, unrealized VAT, realized VAT, Russia
ms.date: 07/22/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# VAT by customer prepayment

When a company receives a prepayment from a Customer, you must create a VAT invoice and a VAT record for the amount of VAT.

## Setup

1. To enable the unrealized VAT in the window **General Ledger Setup**.
1. Setup the unrealized VAT type and choose the account, which will be taken of the operation of unrealized VAT **VAT posting setup**.
1. To configure the customer posting groups: set account, which is taken of the operation of the prepayment.
1. For each account in the chart of accounts, assign:

   - General type of accounting
   - VAT business group  
   - VAT product posting group  

1. Set up the VAT posting in **VAT Posting setup** page.

## Receive prepayment

After you receive prepayment from a customer, the system creates unrealized VAT records and VAT invoices.

Post prepayment in the General journal (see [Prepayment to the vendor and customers](Prepayments-Vendor-and-Customers.md)).

## Return prepayment

To return a prepayment, you must create a realized VAT record.

Go to **Customer ledger entries** > select **returned prepayment** > select **return payment**.

Fill in the fields:

| Field | Description |
|--|--|
| Posting Date | Specifies the posting date of the entries that you want to include in the report or batch job. |
| Document No. | Specifies the number of the related document. |
| New posting Date | Specifies the new posting date. |
| New Document No. | Specifies the new document number for the prepayment. |
| Posting Description | Specifies the description that is added to the resulting posting. |
| Correction | Specifies the operation is corrective. |

Select **OK**. The system automatically creates corrective entries.

## Related information

[Russia Local Functionality](russia-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
