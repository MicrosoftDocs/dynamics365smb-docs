---
title: Setting Up Text-to-Account Mapping for Recurring Payments | Microsoft Docs
description: Link text on payments with specific accounts, so that payments are posted to the accounts when you post the payment reconciliation journal.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account linking, direct payment posting, automatic payment processing, reconcile payment, recurring expense, recurring cash receipt
ms.date: 04/01/2020
ms.author: sgroespe

---
# Map Text on Recurring Payments to Accounts for Automatic Reconciliation
On the **Text-to-Account Mapping** page, which you open from the **Payment Reconciliation Journal** page, you can set up mappings between text on payments and specific debit, credit, and balancing accounts so that such payments are posted to the specified accounts when you post the payment reconciliation journal.

Similar functionality exists to reconcile excess amounts on payment reconciliation journal lines on an ad-hoc basis. For more information, see [Reconcile Payments that Cannot be Applied Automatically](receivables-how-reconcile-payments-cannot-apply-auto.md).

Payments posted based on text-to-account mapping are not applied to open entries, but are merely posted to the specified accounts in addition to creating bank account ledger entries. Accordingly, text-to-account mapping is suited for recurring cash receipts or expenses, such as frequent purchases of car fuel or bank fees and interest, that regularly occur on the bank statement and do not need a related business document. For more information, see the “Example - Text-to-Account Mapping for Fuel Expense” section in this topic.

> [!NOTE]  
>   Payments on reconciliation journal lines are only set to posting according to text-to-account mapping if the automatic application function can only provide a match confidence of **Low** or **Medium**. If the automatic application function provides a match confidence of High, then the payment is automatically applied to one or more open entries, and the payment is not posted to the accounts specified on the **Text-to-Account Mapping** page. In other words, a match confidence of **High** overrules a text-to-account mapping.

On a payment reconciliation journal line where the payment has been set to posting according to text-to-account mapping, the **Match Confidence** field contains **High - Text-to-Account Mapping**, and the **Account Type** and **Account No.** fields contain the mapped accounts.

## To map text on recurring payments to accounts for automatic reconciliation
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Reconciliation Journals**, and then choose the related link.
2. Open a payment reconciliation journal. For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).
3. Choose the **Map Text to Account** action. The **Text-to-Account Mapping** page opens.
4. In the **Mapping Text** field, enter any text that occurs on payments that you want to post to specified accounts without applying to an open entry. You can enter up to 50 characters.

    > [!NOTE]  
    >   If no other payments exist with the mapping text in question, then the text-to-account mapping will occur even when only a part of the text on the payment exists as a mapping text.
5. In the **Vendor No.** field, enter the vendor that the payments will be posted to.
6. In the **Bal. Source Type** field, specify if the payment will be posted to a general ledger account or to a customer or vendor account.
7. In the **Bal. Source No.** field, specify the account that the payment will be posted to, depending on your selection in the **Bal. Source Type** field.

    > [!NOTE]
    > Do not use the **Debit Acc. No.** and **Credit Acc. No.** fields in connection with payment reconciliation. They are used for incoming documents only. For more information, see [Use OCR to Turn PDF and Image Files into Electronic Documents](across-how-use-ocr-pdf-images-files.md).

8. Repeat steps 3 through 7 for all text on payments that you want to map to accounts for direct posting without application.

Next time you import a bank statement file or choose the **Apply Automatically** action on the **Payment Reconciliation Journal** page, journal lines for the payments that contain the specified mapping text will contain the mapped accounts in the **Account Type** and **Account No.** fields. The **Match Confidence** field will contain **High - Text-to-Account Mapping**. This is on the condition that the automatic application function can only provide a match confidence of **Low** or **Medium**.

## Example: Text-to-Account Mapping for Fuel Expense
To always post fuel expenses incurred at Shell gas stations to the general ledger account for gasoline (account 8510), fill a line on the **Text-to-Account Mapping** page as follows.

| Mapping Text | Debit Acc. No. | Credit Acc. No. | Bal. Source Type | Bal. Source No. |
| --- | --- | --- | --- | --- |
| Shell |BLANK |8510 |G/L Account |BLANK |

## See Also
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
