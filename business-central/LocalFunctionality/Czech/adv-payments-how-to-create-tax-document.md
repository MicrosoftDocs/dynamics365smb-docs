---
title: Create a VAT document for an advance letter  
description: This section describes how to create and post a VAT document for an advance letter using the Czech Advance Payments Localization extension.  
author: v-pejano  
ms.reviewer: v-pejano  
ms.author: v-pejano
ms.service: dynamics365-business-central  
ms.topic: article  
ms.search.keywords: Czech, Advance Payments, VAT Document, Localization  
ms.date: 09/17/2025  
ms.custom: bap-template  
---

# Create a VAT document for an advance letter

## Automatic VAT posting from an advance letter

If the **Automatic Post VAT Document** field in the header of the sales advance letter is set to **Yes**, the VAT document and VAT entry are created automatically when the advance letter is paid.

A **VAT Payment** entry is added to the advance history, showing the base amount and VAT amount.

## Print a VAT document for an advance invoice

To print the VAT document related to the advance invoice, follow these steps:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters**, and then select the related link.  
2. In the list of sales advance letters, select the relevant advance.  
3. Choose the **Advance Letter Entries** action.  
4. Select the line where the **Entry Type** field contains **VAT Payment**, and then use the **VAT Document** function to print the advance VAT document with detailed VAT recapitulation.

- If the advance letter has multiple VAT rates, a separate **VAT Payment** entry is created for each rate. If the advance is only partially paid, the **VAT Payment** entries are generated proportionally.
- When the advance is fully paid, the **Advance Status** changes to **To Use**. If partially paid, the status remains **To Pay**. The advance letter can be used to a final invoice up to the paid amount, even if it isn't fully settled.
- The VAT document is posted using the document number from the number series specified in the **Advance Letter Invoice Nos.** field on the advance letter template.

## Post a VAT document manually

If the **Automatic Post VAT Document** field is set to **No**, no VAT document is created automatically when the advance letter is paid. The advance can still be applied to the final invoice.

If you want to post the VAT document later, you can trigger VAT document creation manually from the **Advance Letter Entries**.

To manually create a VAT document:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters**, and then select the related link.  
2. In the list of sales advance letters, select the relevant advance.  
3. Choose **Advance Letter Entries**, and then select the line where the **Entry Type** field contains **Payment**.  
4. Run the **Post Payment VAT** action. The **VAT Payment** entry (and related VAT and general ledger entries) will be posted using the same posting date as the original payment.

- If the **Auto Post VAT Document** field is still set to **No** when you post the final invoice, the advance won't automatically post for VAT. You must handle VAT posting manually. You can change this setting to **Yes** before you post the final invoice to enable automatic VAT posting.
- If the advance was used in the final invoice but VAT was not posted, you can still post it manually afterward.

### Manual VAT deduction from advance

To manually deduct VAT from an advance, follow these steps:

1. Choose the ![Lightbulb icon](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters**, and then select the related link.  
2. In the list of sales advance letters, select the relevant advance.  
3. Choose **Advance Letter Entries**, select an entry of type **Usage**, and then select the **Post Payment VAT Usage** action. This action posts the VAT deduction using the date and document number of the posted final invoice.

## Related information

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
