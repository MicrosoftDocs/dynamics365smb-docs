---
title: Advance in a foreign currency
description: This section describes advance payments localization for the Czech extension.
author: v-pejano
ms.reviewer: v-pejano
ms.author: v-pejano
ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, Advance Payments, Localization
ms.date: 09/17/2025
ms.custom: bap-template
---

# Advances in a foreign currency

The Advance Payments application works with foreign currencies (FCY). However, you must use a unified currency throughout the entire process. For example, you must post the advance, payment, invoice, and closing in the same currency.

> [!NOTE]
> - Advance entries are always recorded in both foreign and local currencies.
> - If automatic creation of an advance VAT document is set for a sales advance, VAT is automatically posted using the exchange rate used for the advance payment. For manually created VAT documents in purchase advances, the payment exchange rate is pre-filled.
> - If the exchange rate differs between the payment and the final invoice, a new entry of type **VAT Rate** is created in the advance entries to align the total advance amount, base, and VAT amount in the local currency.

## Pay an advance in a foreign currency

1. Select the ![Lightbulb icon that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters**, and then select the related link.
2. Create a new sales advance letter for any customer.
3. In the **Currency Code** field on the **Invoice Details** tab, select the currency.
4. On the advance letter line, fill in the **VAT Prod. Posting Group** and the **Amount Including VAT** fields.
5. Release the advance using the **Release** function.
6. Search for and open any **General Journal**.
7. On a journal line, in the **Document Type** field, choose **Payment**, and, and then enter the customer number.
8. In the **Currency Code** field, select the currency and set the exchange rate.
9. In the **Advance Letter No.** field, select the number the advance invoice created in the previous steps.
10. Fill in the **Balancing Account**, and then post the journal.
11. An entry where the **Entry Type** is **Payment** is created in the advance letter entries.

## Link an advance to an invoice

1. Select the ![Lightbulb icon that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then select the related link.
2. Create a new sales invoice in EUR for the same customer, enter the exchange rate and invoice lines.
3. Select **Link Advance Letter**, and link the invoice with the advance.
4. Post the invoice.
5. If the exchange rate differs between the payment and the final invoice, a new entry of type **VAT Rate** is created in the advance entries to align the total advance amount in CZK and to adjust the base and VAT amounts in CZK.

![Linking the advance with the payment](Media/adv-payments-foreign-curr-connect.png)

## Revaluation of advances at year-end

You must revalue customer balances in FCY at year-end using the exchange rate issued by the Czech National Bank (CNB). The standard **Adjust Exchange Rates** function revalues only customer and vendor entries and creates detailed entries to adjust originally posted values. This includes the revaluation of advance payments. However, the advance invoices themselves aren't affected.

To reflect exchange rate adjustments in the advance entries (for example, revalue VAT in local currency on advances), run the **Adjust Advance Letter Exchange Rates** report. This function finds all customer detailed entries with an **Entry Type** of **Unrealized Gain** or **Unrealized Loss** posted on the selected date, for example, 12/31. The function also transfers the entries to the advance entries as entries of type **VAT Adjustment**. This transfer adjusts the total advance, base, and VAT amounts in LCY. Posting is made between the **advance letter account (VAT Posting Setup)** and the standard exchange rate difference account.

Advance adjustment also applies retroactively. For example, if you issued and paid the advance in 2024 and then applied to an invoice in January 2025. If you make the adjustment after this posting, [!INCLUDE [prod_short](../../includes/prod_short.md)] creates a retroactive adjustment as of 12/31/2024 and then reverses it as of the invoice date.

Using the year-end advance revaluation function isn't mandatory. If you don't use it, the VAT (in LCY) posted at the time of the advance payment is used when posting the final invoice.

If **VAT Adjustment** entries exist, they're used when posting the final invoices linked to the advance.

![Year-end revaluation of advances](Media/adv-payments-foreign-curr-end.png)

## Related information

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
