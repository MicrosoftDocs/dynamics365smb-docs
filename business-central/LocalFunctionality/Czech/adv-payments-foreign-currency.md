---
title: Advance in Foreign Currency
description: This section describes Advance Payments Localization for Czech extension functionality.
author: v-pejano

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, Advance Payments, Localization
ms.date: 10/01/2021
ms.reviewer: v-pejano
ms.author: v-pejano
---

# Advances in Foreign Currency

The Advance Payments application works with foreign currencies. However, the rule of a unified currency throughout the entire lifecycle of the advance must be followed, i.e., the advance, payment, invoice, and closing must all be posted in the same currency.

- Advance entries are always recorded in both foreign and local currencies.
- If automatic creation of an advance VAT document is set for a sales advance, VAT is automatically posted using the exchange rate used for the advance payment. For manually created VAT documents in purchase advances, the payment exchange rate is pre-filled in the dialog window.
- If the exchange rate differs between the payment and the final invoice, a new entry of type **VAT Rate** is created in the advance entries to align the total advance amount, base, and VAT amount in the local currency.

## Paying an Advance in Foreign Currency

1. Select the ![Lightbulb icon that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters**, and then select the related link.
2. Create a new sales advance letter for any customer.
3. In the **Currency Code** field on the **Invoice Details** tab, select e.g., EUR.
4. In the advance letter line, fill in the **VAT Prod. Posting Group** and the **Amount Including VAT**.
5. Release the advance using the **Release** function from the action bar.
6. Search for and open any **General Journal**.
7. In the journal line, set **Document Type = Payment**, and enter the customer number.
8. In the **Currency Code** field, select EUR and set the exchange rate.
9. In the **Advance Letter No.** field, select the number the advance invoice created in the previous steps.
10. Fill in the balancing account and post the journal.
11. An entry with **Entry Type = Payment** is created in the advance letter entries.

## Linking an Advance to an Invoice

1. Select the ![Lightbulb icon that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then select the related link.
2. Create a new sales invoice in EUR for the same customer, enter the exchange rate and invoice lines.
3. From the action bar, select **Link Advance Letter** and link the invoice with the advance (see the chapter *Using the Advance Invoice in the Final Invoice*).
4. Post the invoice.
5. If the exchange rate differs between the payment and the final invoice, a new entry of type **VAT Rate** is created in the advance entries to align the total advance amount in CZK and to adjust the base and VAT amounts in CZK.

![Linking the advance with the payment](Media/adv-payments-foreign-curr-connect.png)

## Revaluation of Advances at Year-End

Customer balances in foreign currencies must be revalued at year-end using the exchange rate issued by the Czech National Bank (CNB). The standard **Adjust Exchange Rates** function revalues only customer and vendor entries and creates detailed entries to adjust originally posted values. This includes the revaluation of advance payments. However, the advance invoices themselves are not affected by this standard function.

To reflect exchange rate adjustments in the advance entries (i.e., revalue VAT in local currency on advances), you need to run the follow-up report **Adjust Advance Letter Exchange Rates**. This function finds all customer detailed entries with Entry Type = Unrealized Gain or Unrealized Loss posted on the selected date (e.g., 12/31) and transfers them to the advance entries as entries of type **VAT Adjustment**. This adjusts the total advance amount in the local currency and the base and VAT amounts in local currency. Posting is made between the **advance letter account (VAT Posting Setup)** and the standard exchange rate difference account.

Advance adjustment will be applied retroactively as well – for example, if the advance was issued and paid in 2020 and then applied to an invoice in January 2021. If the adjustment is made after this posting, the system will create a retroactive adjustment as of 12/31/2020 and then reverse it as of the invoice date.

Using the year-end advance revaluation function is not mandatory. If it is not used, the VAT (in local currency) posted at the time of the advance payment will be used when posting the final invoice.
If **VAT Adjustment** entries exist, they will be used when posting the final invoices linked to the advance.

![Year-end revaluation of advances](Media/adv-payments-foreign-curr-end.png)

## See also

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
