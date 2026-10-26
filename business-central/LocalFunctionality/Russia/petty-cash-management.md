---
title: Petty cash management in Russia
description: Russian localization provides enhanced features for managing petty cash transactions.
author: DianaMalina
ms.topic: article
ms.search.keywords: cash management, petty cash management, Cash order journal, Cash receipt Journal, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Petty cash management

The petty cash management feature enables you to:

- Create multiple cash account cards.
- Create ingoing and outgoing cash order documents with the following specifications:
  - Number them using special numbering rules.
  - Generate the documents in the configured report format.
  - Post the documents.
- Void posted cash documents (checks).
- Generate the following reports:
  - Cash Order Journal CO-3
  - Cash Report CO-4.

## Cash order journal

To use cash orders, create a general journal template with the **Cash Order Payments** type. There can be several cash accounts in the company, and several cash points, such as cashiers, for each cash account. For each cash account, create a cash account card.

For each cash point, create a General Journal batch. The value of the **Balance Account Type** field of the batch line should be chosen as Bank Account, and the appropriate cash account should be entered in the **Balance Account Number** field.

The journal uses **Credit Amount** for an ingoing cash order and **Debit Amount** for an outgoing cash order. Use **Preview Cash Order** to open the corresponding cash order card.

### Create an ingoing cash order

1. Search for **Cash Order Journal**, and open the page.
1. Choose the batch for the cash point, and create or select an ingoing journal line.
1. Choose **Preview Cash Order**. The **Ingoing Cash Order** card contains the fields listed in the following table.

   | Field | Description |
   |--|--|
   | **Posting Date** | Enter the **Posting Date** field in general journals. |
   | **Document Type** | Specifies **Payment** or **Refund**. For a customer or vendor, the document type is assigned from the account type and amount. |
   | **Prepayment** | In some cases, the financial posting of payments is different in relation to the date of payment, depending on whether if it is before or after the appropriate invoice financial posting. This field should be selected in case of prepayment. |
   | **Document No.** | Enter the **Document Number** field in general journals.   If the value of the **Bank Payment Type** field is Computer Check, then the value of the **Document Number** field is automatically filled in after printing the ingoing cash order. The field is filled in with the next number from the number series that is specified in the **Debit Cash Order Number Series** field in the appropriate cash card. In this case, if you use the Void Check Print function on the card, clear the field.   The document number of the posted ingoing cash order is equal to the document number of the unposted ingoing cash order. |
   | **Account Type** | Enter the **Account Type** field in general journals. This is the type of the object that is the posting source of a cash payment. |
   | **Account Code** | Enter the **Account Code** field in general journals. This is the account code of the object that is the posting source of a cash payment. |
   | **Currency Code** | Enter the **Currency Code** field in general journals. |
   | **Amount** | Enter the receipt amount. This value is the journal line's **Credit Amount**. A positive amount is an inflow to the cash account. |
   | **Bank Payment Type** | Enter the **Bank Payment Type** field in general journals. If the value is Computer Check, the order can't be posted before printing. |
   | **From to** | Enter the **Description** field in general journals. It's used in the printing window of an order as a payment source description. |
   | **Reason**, **Supplement**, **Including** | These fields are transferred to Check Ledger entries during posting and used in printing windows of posted and unposted ingoing cash orders. They can be filled in manually or with the Text Codes functionality. |
   | **Debit Account** | Shows the G/L account from the cash bank account's bank account posting group. This field isn't editable. |
   | **Credit Account** | Shows the corresponding G/L account for the source account. For a customer or vendor, the account comes from the posting group, including the prepayment account when applicable. This field isn't editable. |
   | **Reason Code**, **Applies-to Doc. Type**, **Applies-to Doc. No**.,  **Global Dimension 1 Code**, **Global Dimension 2 Code** | Enter these fields in general journals. |

1. Choose **Print** if required by the **Bank Payment Type**. Choose **Post**, or press <kbd>F9</kbd>, to post the cash order.

### Create an outgoing cash order

Create or select an outgoing line in **Cash Order Journal**, and choose **Preview Cash Order**. The **Outgoing Cash Order** card contains the following fields. Use **Print** and **Post** on the card as for an ingoing cash order.

| Field | Definition |
|--|--|
| **Posting Date** | Enter the **Posting Date** field in general journals. |
| **Document Type** | Specifies **Payment** or **Refund**. For a customer or vendor, the document type is assigned from the account type and amount. |
| **Prepayment** | In some cases, the financial posting of payments is different in relation to the date of payment, depending on whether if it is before or after the appropriate invoice financial posting. This field should be selected in case of prepayment. |
| **Document No.** | Enter the **Document Number** field in general journals. If the value of the **Bank Payment Type** field is Computer Check, then the value of the **Document Number.** field is automatically filled in after printing the outgoing cash order. The field is filled in with the next number from the number series that is specified in the **Credit Cash Order No. Series** field in the appropriate cash card. In this case, if you use the Void Check Print function on the card, the field is cleared.   The document number of a posted outgoing cash order is equal to the document number of the unposted outgoing cash order. |
| **Account Type** | Enter the **Account Type** field in general journals. This is the type of the object that is the posting source of a cash payment. |
| **Account Code** | Enter the **Account Code** field in general journals. This is the account code of the object that is the posting source of a cash payment. |
| **Posting Group** | Enter the **Posting Group** field in general journals. It's automatically filled. This field isn't editable. |
| **Currency Code** | Enter the **Currency Code** field in general journals. |
| **Amount** | Enter the payment amount. This value is the journal line's **Debit Amount**. A positive amount is an outflow from the cash account. |
| **Bank Payment Type** | Enter the **Bank Payment Type** field in general journals. |
| **Give to** | Enter a description of the payment recipient. This value is the journal line's **Description**. |
| **Reason**, **Supplement**, **Per** | These fields are transferred to check ledger entries during posting and used in reports for posted and unposted outgoing cash orders. Fill them in manually or use text codes. |
| **Analytic Code** | Shows the source **Account No.** This field isn't editable. |
| **Debit Account** | Shows the corresponding G/L account for the source account. For a customer or vendor, the account comes from the posting group, including the prepayment account when applicable. This field isn't editable. |
| **Credit Account** | Shows the G/L account from the cash bank account's bank account posting group. This field isn't editable. |
| **Reason Code**, **Applies-to Doc. Type**, **Applies-to Doc. No.**,  **Global Dimension 1 Code**, **Global Dimension 2 Code** | Enter these fields in general journals. |

## Cash order journal CO-3 report

The **Cash Order Journal CO-3** report lists posted ingoing and outgoing cash orders for a reporting period. For more information, see [Print the Cash Order Journal CO-3 Report](how-to-print-the-cash-order-journal-co-3-report.md).

## Cash Report CO-4

The **Cash Report CO-4** report shows daily cash transactions. Confirm the applicable reporting requirements and template with your accounting adviser. For more information, see [Print the Cash Report CO-4 Report](how-to-print-the-cash-report-co-4-report.md).

## Related information

- [Bank Management](bank-management.md)  
- [Create Cash Account Cards](how-to-create-cash-account-cards.md)  
- [Print the Cash Order Journal CO-3 Report](how-to-print-the-cash-order-journal-co-3-report.md)  
- [Print the Cash Report CO-4 Report](how-to-print-the-cash-report-co-4-report.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
