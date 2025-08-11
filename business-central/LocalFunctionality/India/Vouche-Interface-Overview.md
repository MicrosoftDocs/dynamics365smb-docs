---
title: Overview on Voucher Interface
description: Provides an overview of the Voucher Interface feature for Indian localization in Business Central.
author: v-debapd
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English, voucher interface
ms.date: 06/30/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Overview of voucher interface

Business Central has included Voucher Interface Feature to Indian Localization.

Feature required to provide the voucher interface as per Indian business requirements to record the day-to-day transactions in following vouchers:

- Journal Voucher - Entries, which aren't affecting the Cash Account or the Bank account are termed as Journal Vouchers
- Bank Receipt Voucher - Used for transactions that debit the Bank Account.
- Bank Payment Voucher - Used for transactions that credit the Bank Account.
- Cash Receipt Voucher - Used for transactions that debit the Cash Account.
- Cash Payment Voucher - Used for transactions that credit the Cash Account.
- Contra Voucher - Entries, which are affecting the Cash and Bank Account together, are termed as Contra Vouchers. For example, Withdrawal from bank.

## Set up voucher interface

### The following setups are required for voucher interface

- [General Journal Template](vouche-interface-overview.md#set-up-general-journal-template)
- [General Journal Batch](vouche-interface-overview.md#set-up-general-journal-batch)
- [General Voucher Setup](vouche-interface-overview.md#set-up-voucher-setup)

## Set up general journal template

Journals are used for different types or groups of entries, such as purchases, payments, sales, and receivables. Each journal type is set up with its own journal template. Journal templates provide the basic journal structure where business users can specify default information for all batches created using the template.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal Template**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Name**|Specifies unique identifier for the template.|  
    |**Description**|Specify the short description for the template.|
    |**Type**|Specifies the structure and functions of the journal page.|
    |**Recurring**|Specifies  if the journal is to be used to make recurring entries. Each journal type can be used for recurring purposes|
    |**Bal. Account Type**|Identifies the default balancing account type for all journal lines in all batches created under this template.|
    |**Bal. Account No.**|Identifies the default balancing account number for all journal lines in all batches created under this template.|
    |**No. Series**|Identifies the default number series used to assign document numbers to journal lines in journal batches created using this template.|
    |**Posting No. Series**|Identifies the document number used to assign to ledger entries posted from journal batches created using this template.|
    |**Source Code**|Identifies the point of origin for an entry and forms the basis for the audit trail. It's filled in automatically when selecting the Type of the General Journal template. It's assigned to all journal batches created from this template.|
    |**Reason Code**|Describes why an entry was made and can be used for the audit trail. Reason codes also provide opportunities for problem patterns analysis. The selected reason code is assigned as a default to all journal batches created from this template.|
    |**Force Doc. Balance**|Specifies whether entries posted in this general journal template must balance by document number and document type. If this field is empty, the program balances the journal by date only.|
    |**Increment Batch Name**|Specifies if batch name using this template are automatically incremented|

## Set up general journal batch

Journal batches are created based on the journal templates. All journal batches created from a specific template have the same structure, default settings, and information defined in the template. However, since these settings are defaults, business users can change them for a specific journal batch.

Batches are typically used to separate one user's entries from another. For example, User-A and User-B both work on general journal entries. User-A typically makes entries and posts them later when they're approved. To keep User-B's entries from becoming mixed with User-A's entries, separate batches can be assigned to the two users.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal Template**, and then choose the related link.
1. general Journal Template > Navigate > Template > Batches
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Name**|Specifies unique identifier for the batch.| 
    |**Description**|Specify the short description for the batch.|
    |**Bal. Account Type**|Identifies the default balancing account type for all journal lines in all batches created under this batch.|
    |**Bal. Account No.**|Identifies the default balancing account number for all journal lines in all batches created under this batch.|
    |**Location Code**|Specifies the default location code for the batch.|
    |**No. Series**|Identifies the default number series used to assign document numbers to journal lines in journal batches created using this batch.|
    |**Posting No. Series**|Identifies the document number used to assign to ledger entries posted from journal batches created using this batch.|
    |**Reason Code**|Describes why an entry was made and can be used for the audit trail. Reason codes also provide opportunities for problem patterns analysis. The selected reason code is assigned as a default to all journal batches created from this batch.|
    |**Suggest Balancing Amount**|Specifies the amount field on journal lines for the same document number is automatically pre filled with the value, which is required to balance the document.|

## Set up voucher setup

Voucher setup is done to define the type of voucher, related transaction direction, and default account number. Voucher setup can be defined from company information and location.

- Voucher setup on company information

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Company Information**, and then choose the related link.
  1. Company Information > Voucher Setup
  1. Fill in the fields as described in the following table.

       |Field|Description|  
       |---------------------------------|---------------------------------------|
       |**Type**|Specifies the structure and functions of the journal page, that is, Cash Receipt Voucher, Bank Payment Voucher, etc.|
       |**Posting No. Series**|Identifies the document number used to assign to ledger entries posted from journal batches created using this type.|
       |**Transaction Direction**|Specifies the direction of the transaction, if debit then select the type and account number in **Debit Account** else in **Credit Account**.|

- Voucher setup on location

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Locations**, and then choose the related link.
  1. Locations -> Process -> Voucher Setup
  1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Type**|Specifies the structure and functions of the journal page, that is, Cash Receipt Voucher, Bank Payment Voucher, etc.|
    |**Posting No. Series**|Identifies the document number used to assign to ledger entries posted from journal batches created using this type.|
    |**Transaction Direction**|Specifies the direction of the transaction, if debit then select the type and account number in **Debit Account** else in **Credit Account**.|

## Related information

[Voucher Interface Transaction](Voucher-Interface-Transactions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
