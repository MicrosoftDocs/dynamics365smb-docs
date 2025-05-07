---
title: Setting up customer prepayments in Russia
description: Russian enhancements include prepayments from customers.
author: DianaMalina


ms.topic: how-to
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Set Up Customer Prepayments

Prepayments are advance payments on sales orders that are received, invoiced, and posted before the final invoice is issued. For example, you may require a deposit before you manufacture and ship an item to a customer. Prepayments let you invoice and collect advance payments from customers and post the payments against the correct invoices and accounts.

## To set up customer prepayments

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.

2. On the **Numbering** FastTab, verify that the number series for the **Posted Prepmt. Inv. Nos.** is the same as the **Posted Invoice Nos.**. Also verify that the number series for the **Posted Prepmt. Cr. Memo Nos.** is the same as the **Posted Credit Memo Nos.**.

3. On the **Prepayment** FastTab, enter the following information.

   | Field                             | Description                                                  |
   | :-------------------------------- | :----------------------------------------------------------- |
   | **Use Prepayment Account**        | Select to post prepayments using the subaccount specified in the **Prepayment Account** field in the **Customer Posting Groups** window. |
   | **Create Prepayment Invoice**     | Select to create an invoice for the prepayment. If this field is not selected, an invoice for the prepayment will not be created. |
   | **Posted Prepayment Nos.**        | Enter the code of the number series that you want to use for prepayment invoices. |
   | **Posted PD Doc. Nos.**           | Enter the code of the number series that you want to use for prepayment documents. |
   | **PD Doc. Nos. Type**             | Select if you want to use a number series or symbol to identify prepayment documents. |
   | **Symbol for PD Doc.**            | Enter a symbol to be printed on prepayment documents.        |
   | **PD Gains Condition Dim Value**  | Enter the code for the dimension that is used to generate conditional prepayment gains. |
   | **PD Losses Condition Dim Value** | Enter the code for the dimension that is used to generate conditional prepayment losses. |
   | **PD Gains Kind Dim Value**       | Enter the code for the dimension that is used to generate payment in kind prepayment gains. |
   | **PD Losses Kind Dim Value**      | Enter the code for the dimension that is used to generate payment in kind prepayment gains. |

4. Open the **Customer Posting Groups** window.

5. In the **Prepayment Account** field, specify the general ledger accounts that you want to use for posting customer prepayments.

6. Choose the **Close** button to close the window and save your entries.

You can now invoice and collect advance payments from customers and post the payments to the correct invoices and accounts.

## Related information

[Invoicing Prepayments](../../finance-invoice-prepayments.md)  
[Walkthrough: Setting Up and Invoicing Sales Prepayments](../../walkthrough-setting-up-and-invoicing-sales-prepayments.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
