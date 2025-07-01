---
title: Creating VAT Document for Advance Letter  
description: This section describes how to create and post a VAT document for an advance letter using the Czech Advance Payments Localization extension in Business Central.  
author: v-pejano  

ms.service: dynamics365-business-central  
ms.topic: article  
ms.search.keywords: Czech, Advance Payments, VAT Document, Localization  
ms.date: 10/01/2021  
ms.reviewer: v-pejano  
ms.author: v-pejano  
---

# Creating VAT Document for an Advance Letter

## Automatic VAT Posting from Advance Letter

If the **Automatic Post VAT Document** field in the header of the sales advance letter is set to **Yes**, the VAT document and VAT entry are created automatically when the advance letter is paid.

A **VAT Payment** entry is added to the advance history, showing the base amount and VAT amount.

### Printing VAT Document for Advance Invoice

To print the VAT document related to the advance invoice:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters**, and then select the related link.  
2. In the list of sales advance letters, select the relevant advance.  
3. Choose **Advance Letter Entries** from section.  
4. Highlight the line with **Entry Type = VAT Payment**, and then use the **VAT Document** function from the **Reports** section to print the advance VAT document with detailed VAT recapitulation.

- If multiple VAT rates are used on the advance letter, a separate **VAT Payment** entry is created for each rate. If the advance is only partially paid, the **VAT Payment** entries are generated proportionally.
- When the advance is fully paid, the **Advance Status** changes to **To  Use**. If partially paid, the status remains **To Pay**. The advance letter can be used to a final invoice up to the paid amount, even if not fully settled.
- The VAT document is posted using the document number from the number series specified in the advance letter template in filed **Advance Letter Invoice Nos.**

## Manual VAT Document Posting

If the **Automatic Post VAT Document** field is set to **No**, no VAT document is created automatically when the advance letter is paid. The advance can still be applied to the final invoice.

If you want to post the VAT document later, you can trigger VAT document creation manually from the **Advance Letter Entries**.

### Manually Creating VAT Document

To manually create a VAT document:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters**, and then select the related link.  
2. In the list of sales advance letters, select the relevant advance.  
3. Choose **Advance Letter Entries** and highlight the line with **Entry Type = Payment**.  
4. From the action bar, run the **Post Payment VAT** action. The **VAT Payment** entry (and related VAT and general ledger entries) will be posted using the same posting date as the original payment.

- If the **Auto Post VAT Document** field is still set to **No** when posting the final invoice, the advance will not be automatically posted for VAT. You must handle VAT posting manually. You can change this setting to **Yes** before posting the final invoice to enable automatic VAT posting.
- If the advance was used in the final invoice but VAT was not posted, you can still post it manually afterward.

### Manual VAT Deduction from Advance

To manually deduct VAT from an advance:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters**, and then select the related link.  
2. In the list of sales advance letters, select the relevant advance.  
3. Choose **Advance Letter Entries** and highlight an entry of type **Usage**, then select the **Post Payment VAT Usage** action.  
   This posts the VAT deduction using the date and document number of the posted final invoice.

## See Also

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
