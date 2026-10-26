---
title: VAT by customer prepayment in Russia
description: Learn how to report VAT on customer prepayments in Russia, including setup and processing steps in Business Central.
author: DianaMalina
ms.topic: article
ms.search.keywords: customer prepayment, receiving prepayment,return prepayment, VAT prepayment, unrealized VAT, realized VAT, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# VAT by customer prepayment

You can create VAT entries and a VAT invoice when you post a customer prepayment. The result depends on the prepayment and VAT posting setup.

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

When you post a customer prepayment with the required VAT setup, [!INCLUDE[prod_short](../../includes/prod_short.md)] creates unrealized VAT entries. Automatic creation of the prepayment invoice also requires **Create Prepayment Invoice** and the relevant number series in **Sales & Receivables Setup**.

Post prepayment in the General journal (see [Prepayment to the vendor and customers](Prepayments-Vendor-and-Customers.md)).

## Return prepayment

Use **Return Prepayment** for an open payment entry marked as a prepayment. The remaining amount in local currency must equal the original amount, so the prepayment can't be partially applied.

1. Open **Customer Ledger Entries**, select the prepayment payment entry, and choose **Return Prepayment**.

1. Fill in the fields:

   | Field | Description |
   |--|--|
   | Posting Date | Specifies the posting date of the entries that you want to include in the report or batch job. |
   | Document No. | Specifies the number of the related document. |
   | New posting Date | Specifies the new posting date. |
   | New Document No. | Specifies the new document number for the prepayment. |
   | Posting Description | Specifies the description that is added to the resulting posting. |
   | Correction | Specifies the operation is corrective. |

1. Select **OK**. [!INCLUDE[prod_short](../../includes/prod_short.md)] posts the entries that reset the prepayment as a payment.

## Related information

[Russia Local Functionality](russia-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
