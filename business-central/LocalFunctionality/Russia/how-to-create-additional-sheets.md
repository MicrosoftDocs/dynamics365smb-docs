---
title: Create additional sheets in Russia
description: Russian enhancements include additional sheets for VAT purchase ledgers and sales ledgers.
author: DianaMalina
ms.topic: how-to
ms.search.keywords:
ms.date: 11/06/2023
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---
# Create additional sheets

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can create additional sheets based on VAT purchase ledgers and VAT sales ledgers.

## To create entries for an additional sheet for a VAT purchase or sales ledger

1. Select the VAT purchase or sales line in the **VAT Ledger List** window with the required accounting period.

2. Choose the **Create Additional Sheet** action.

3. Fill in the batch job according to the guidelines at Create VAT Sales Led. Ad. Sh..

   The parameters for creating a VAT purchase ledger additional sheet and VAT sales ledger additional sheet are the same as the parameters for creating the VAT Purchase Ledger and the VAT Sales Ledger.

## To print additional sheets on a VAT Ledger

1. On the **VAT Purch. Ledger** or **VAT Sales Ledger** page, choose the **Additional Sheet** action.
2. In the **Period Type** field, select one of the following options:

   - **Day**
   - **Month**
   - **Quarter**

   > [!NOTE]
   > In the **VAT Ledger** tab, the **Type** field and the **Code** field are automatically created.

4. Choose the **Preview** or **Print** action.

## Create corrective documents to include in additional sheets

The information changed in the tax invoice after the invoice is registered in the previous purchase book must be reflected in the additional sheet of the previous book (corrected book). The additional sheet is part of the purchase book.

The first line contains the totals of the purchase book at the end of the period when the tax invoice is registered. The next lines are the annulled tax invoices. The annulled tax invoices have a negative sign if the corrected invoice amount is lesser than the initial amount, and a positive sign if the corrected invoice amount is greater than the initial amount. The last line is calculated as the sum of the amounts of the first total line and the annulled tax invoices.

The information changed in the tax invoice after the invoice is registered in the previous sales book must be reflected in the additional sheet of the previous book (corrected book). The additional sheet is part of the sales book.

The first line contains totals of the sales book at the end of the period when the tax invoice is registered. The next lines are the annulled tax invoices with a negative sign. The corrected invoices with positive amounts belong to the previous period. The last line is calculated as the sum of the amounts of the first total line, annulled tax invoices, and the corrected invoices.

Processing of corrective documents for sales book is similar to processing for purchases book with one difference. In additional sheets, the number and the date of initial factura must be reflected.

### To create a correction entry for posted purchase credit memos

1. Create and post a purchase credit memo.
2. Choose **Additional VAT Ledger Sheet** field.
3. Enter information in the following fields:
   - **Corrected Document Date**
   - **Vendor VAT Invoice Date**
   - **Vendor VAT Invoice Rcvd Date**
   - **Vendor VAT Invoice No.**

### To create a correction entry for a posted purchase invoice

1. Create and post a purchase invoice.
2. Choose the **Corrected Document Date** field.
3. Enter information in the following fields:

   - **Vendor VAT Invoice Date**
   - **Vendor VAT Invoice Rcvd. Date**
   - **Vendor VAT Invoice No.**

   > [!NOTE]
   > You can also create corrective documents in the general journal. General journal lines contain all the fields mentioned above.

### To post additional VAT

1. In the **Sales Invoice** window or the **Credit Memo** window, choose the **VAT** tab.

2. Enter the **Posting No.** field.

   > [!NOTE]
   > You cannot post an invoice with the same number as the initial invoice. You must use an extra symbol in addition to the initial number.

3. Select the **Additional VAT Ledger Sheet** field.

4. Enter information in the **Corrected Document Date** field.

5. In the additional sheet, the **Date of Facture** field reflects the corrected document date.

## Related information

[VAT Ledgers](VAT-Ledgers.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
