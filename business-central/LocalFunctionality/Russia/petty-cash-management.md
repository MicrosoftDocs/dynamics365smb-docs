---
title: Petty cash management in Russia
description: Russian localization provides enhanced features for managing petty cash transactions.
author: DianaMalina
ms.topic: article
ms.search.keywords: cash management, petty cash management, Cash order journal, Cash receipt Journal, Russia
ms.date: 07/18/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Petty cash management

The petty cash management feature enables you to:

- Create multiple cash account cards.
- Create ingoing and outgoing cash order documents with the following specifications:
  - Number them using special numbering rules.
  - Create printing windows of the documents in the required format.
  - Post the documents.
- Void posted cash documents (checks).
- Print the following required reports:
  - Cash Order Journal CO-3
  - Cash Report CO-4.

## Cash order journal

To use the ingoing cash order feature, create one general journal template with the Cash Order Payment type. There can be several cash accounts in the company, and several cash points (for example cashiers) for each cash account. For each cash account, you must create a cash account with the Cash Account Card feature.

For each cash point, create a General Journal batch. The value of the **Balance Account Type** field of the batch line should be chosen as Bank Account, and the appropriate cash account should be entered in the **Balance Account Number** field.

The following procedure shows how to access the **Cash Order Journal** window.

1. In **Financial Management**, choose **Cash Management**, and then choose **Cash Order Journal**.

1. To create a new  cash order, or to work with an existing unposted cash order, choose the correct batch name (and accordingly the cash point). This field is required and matches the **Batch Name** field in financial journals. The **Cash Order Journal** window contains the fields listed in the following table.

   | Field | Description |
   |--|--|
   | **Posting Date** | Enter the **Posting Date** field in general journals. |
   | **Document Type** | Enter the **Document Type** field in general journals. The options are:   -    -   Payment -   Refund   If the value of the **Account Type** field is Client or Vendor, then the **Document Type** field isn't editable, and is automatically filled in depending on the value in the **Account Type** field and the sign of the amount in the **Income** field. |
   | **Prepayment** | In some cases, the financial posting of payments is different in relation to the date of payment, depending on whether if it is before or after the appropriate invoice financial posting. This field should be selected in case of prepayment. |
   | **Document No.** | Enter the **Document Number** field in general journals.   If the value of the **Bank Payment Type** field is Computer Check, then the value of the **Document Number** field is automatically filled in after printing the ingoing cash order. The field is filled in with the next number from the number series that is specified in the **Debit Cash Order Number Series** field in the appropriate cash card. In this case, if you use the Void Check Print function on the card, clear the field.   The document number of the posted ingoing cash order is equal to the document number of the unposted ingoing cash order. |
   | **Account Type** | Enter the **Account Type** field in general journals. This is the type of the object that is the posting source of a cash payment. |
   | **Account Code** | Enter the **Account Code** field in general journals. This is the account code of the object that is the posting source of a cash payment. |
   | **Currency Code** | Enter the **Currency Code** field in general journals. |
   | **Income** | Enter the amount of the payment. Enter the **Credit Amount** field in general journals. If it's positive, then it's an income to the cash account. |
   | **Bank Payment Type** | Enter the **Bank Payment Type** field in general journals. If the value is Computer Check, the order can't be posted before printing. |
   | **From to** | Enter the **Description** field in general journals. It's used in the printing window of an order as a payment source description. |
   | **Reason**, **Supplement**, **Including** | These fields are transferred to Check Ledger entries during posting and used in printing windows of posted and unposted ingoing cash orders. They can be filled in manually or with the Text Codes functionality. |
   | **Debit Account** | This field indicates the general ledger account that is debited as a result of order posting. It's automatically shown according to the posting group's setup of the account (or balance account if the Income field contains a negative value). It's also used in the printing window. This field isn't editable. |
   | **Credit Account** | This field indicates the general ledger account that is credited as a result of order posting. It's automatically shown according to the posting group's setup of the balance account (or account if the **Income** field contains a negative value). It's used in printing windows. This field isn't editable. |
   | **Reason Code**, **Applies-to Doc. Type**, **Applies-to Doc. No**.,  **Global Dimension 1 Code**, **Global Dimension 2 Code** | Enter these fields in general journals. |

1. Choose **Posting** from the **Posting** button (Hot Key F11) to make posting to ledger entries similar to standard posting from payment journals and cash receipt journals.

## Cash receipt Journal

The Cash Order Journal window contains the fields listed in the following table.

| Field | Definition |
|--|--|
| **Posting Date** | Enter the **Posting Date** field in general journals. |
| **Document Type** | Enter the **Document Type** field in general journals. The options are:   -   **Payment** -   **Refund**   If the value of the **Account Type** field is Client or Vendor, then the **Document Type** field isn't editable and is automatically filled in depending on the **Account Type** field and the sign of the value in the **Expenses** field. |
| **Prepayment** | In some cases, the financial posting of payments is different in relation to the date of payment, depending on whether if it is before or after the appropriate invoice financial posting. This field should be selected in case of prepayment. |
| **Document No.** | Enter the **Document Number** field in general journals. If the value of the **Bank Payment Type** field is Computer Check, then the value of the **Document Number.** field is automatically filled in after printing the outgoing cash order. The field is filled in with the next number from the number series that is specified in the **Credit Cash Order No. Series** field in the appropriate cash card. In this case, if you use the Void Check Print function on the card, the field is cleared.   The document number of a posted outgoing cash order is equal to the document number of the unposted outgoing cash order. |
| **Account Type** | Enter the **Account Type** field in general journals. This is the type of the object that is the posting source of a cash payment. |
| **Account Code** | Enter the **Account Code** field in general journals. This is the account code of the object that is the posting source of a cash payment. |
| **Posting Group** | Enter the **Posting Group** field in general journals. It's automatically filled. This field isn't editable. |
| **Currency Code** | Enter the **Currency Code** field in general journals. |
| **Expenses** | Enter the amount of the payment. Enter the **Debit Amount** field in general journals. If it's positive, then it's an expense from the cash account. |
| **Bank Payment Type** | Enter the **Bank Payment Type** field in general journals. |
| **Given** | Enter the **Description** field in general journals. It's used in the printing window of an order as a payment recipient description. |
| **Reason**, **Supplement**, **Per** | These fields are transferred to Check Ledger entries during posting and used in printing windows of posted and unposted ingoing cash orders. They can be filled in manually or with the Text Codes. |
| **Analitic Code** | This field isn't editable. This field is equal to the value of the **Account Number** field. |
| **Debit Account** | This field indicates the general ledger account that is debited as a result of order posting. It's automatically shown according to the posting group's setup of the account (or balance account if the Income field contains a negative value). It's also used in the printing window. This field isn't editable. |
| **Credit Account** | This field indicates the general ledger account that is credited as a result of order posting. It's automatically shown according to the posting group's setup of the balance account (or account if the Income field contains a negative value). It's used in printing windows. This field isn't editable. |
| **Reason Code**, **Applies-to Doc. Type**, **Applies-to Doc. No.**,  **Global Dimension 1 Code**, **Global Dimension 2 Code** | Enter these fields in general journals. |

The functions executed from the window are the same as those for the **Cash receipt Journal** window.

## Cash Order Journal CO-3 Report

The **Cash Order Journal CO-3** report shows the register of posted ingoing and outgoing cash orders during some reporting period in the unified standard printing window that is certified by Russian accounting legislation. For more information, see [Print the Cash Order Journal CO-3 Report](How-to-Print-the-Cash-Order-Journal-CO-3-Report.md).

## Cash Report CO-4

The **Cash Report CO-4** report shows mandatory daily cash transactions in standard format as required by Russian accounting legislation. For more information, see[Print the Cash Report CO-4 Report](How-to-Print-the-Cash-Report-CO-4-Report.md).

## Related information

- [Bank Management](Bank-Management.md)  
- [Create Cash Account Cards](How-to-Create-Cash-Account-Cards.md)  
- [Print the Cash Order Journal CO-3 Report](How-to-Print-the-Cash-Order-Journal-CO-3-Report.md)  
- [Print the Cash Report CO-4 Report](How-to-Print-the-Cash-Report-CO-4-Report.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
