---
title: Posting date on value entries
description: Learn how the Adjust Cost - Item Entries batch job identifies and assigns a posting date to the value entries that the batch job is about to create.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 09/17/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design Details: Posting Date on Adjustment Value Entry

This article provides guidance for users of the Inventory Costing functionality in [!INCLUDE[prod_short](includes/prod_short.md)], and in particular for how the **Adjust Cost - Item Entries** batch job identifies and assigns a posting date to the value entries that the batch job is about to create.

## How posting dates are assigned

The **Adjust Cost – Item Entries** batch job assigns a posting date to the value entry it is about to create in the following steps:  

1. Initially the Posting Date of the entry to be created is the same date as the entry it adjusts.  

2. The Posting Date is validated against Inventory Periods and/or General Ledger Setup.  

3. Assignment of Posting Date; If the initial Posting Date is not within allowed posting date range the batch job will assign an allowed Posting Date from either General Ledger Setup or Inventory Period. If both Inventory Periods and allowed posting dates in General Ledger Setup are defined, the later date of the two will be assigned to the Adjustment Value Entry.  

Let’s review this process more in practice. Assume we have an Item Ledger Entry of Sale. The item was shipped on September 5, 2020 and it was invoiced the day after.  

#### Item Ledger Entry

|Entry No.  |Item No.  |Posting Date  |Entry Type  | Document No. |Location Code  |Quantity  |Cost Amount (Actual)  |Invoiced Quantity  |Remaining Quantity  |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|319     |A         |2020-09-05     |  Sale       |102033     |  Blue       | -1    |    -11     |-1     |    0     |

Below are the related value entries:

- **Entry No. 379** represents the shipment and carry the same Posting Date as the parent Item ledger Entry.  
- **Entry No. 381** represents the invoice.  
- **Entry No. 391** is an Adjustment of the invoicing Value Entry (Entry No. 381 above).  

|Entry No.  |Item No.  |Posting Date  |Item Ledger Entry Type  |Entry Type  |Document No.  |Item Ledger Entry No.  |Location Code  |Item Ledger Entry Quantity  |Invoiced Quantity  |Cost Amount (Actual)  |Cost Amount (Expected)  |Adjustment  |Applies-to Entry  |Source Code  |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|--------|---------|---------|---------|---------|
|379     |  A       |    2020-09-05     |    Sale     | Direct Cost   | 102033        |319     | Blue        | -1       |0         |  0       |     -10   |No   |0    |Sales          |
|381     |  A       |    2020-09-06     |    Sale     | Direct Cost   | 103022        |319     | Blue        |  0       |-1        |-10       |    10     | No  |0      |       Sales   |
|391     |  A       |    2020-09-10     |    Sale     | Direct Cost   | 103022        |319     | Blue        |  0       |0         |-1        |    0     |Yes   |    181   | INVTADJMT   |

To assign the posting date for **Entry No. 391** the following steps were applied:

1. The **Adjustment Value Entry** to be created (**Entry No. 391**) is assigned same **Posting Date** as the entry it adjusts.

2. The **Adjust Cost – Item Entries** batch job determines if the initial Posting Date of the Adjustment Value Entry is within allowed posting date range based upon Inventory Periods and/or General Ledger Setup.  

Let’s review the above mentioned Sale by adding setup of allowed posting date ranges.  
  
#### Inventory Periods

|Ending Date  |Name  |Closed  |
|---------|---------|---------|
|2020-01-31     |January 2020      |  Yes    |
|2020-02-28     |February 2020     |  Yes    |
|2020-03-31     |March 2020        |  Yes    |
|2020-04-30     |April 2020        |  Yes    |
|2020-05-31     |May   2020        |  Yes    |
|2020-06-30     |June   2020       |  Yes    |
|2020-07-31     |July  2020        |  Yes    |
|2020-08-31     |August   2020     |  Yes    |
|2020-09-30     |September   2020  |         |
|2020-10-31     |October   2020    |         |
|2020-11-30     |November   2020   |         |
|2020-12-31     |December   2020   |         |

The first allowed posting date is the first day in the first open period, which is September 1, 2020.  

#### General Ledger Setup

|Field|Value  |
|---------|---------|
|Allow Posting From:  |  2020-09-10      |
|Allow Posting To:    |  2020-09-30      |
|Register Time:       |         |
|Local Address Format:|   Post Code      |  

The first allowed posting date is the date stated in field **Allow Posting From**: September 10, 2020. If both Inventory Periods and allowed posting dates in **General Ledger Setup** are defined, the later date of the two will define the allowed posting date range.  

**Assignment of an allowed posting date**  

The initial assigned Posting Date was September 6 as illustrated in step 1. However, in the second step the Adjust Cost – Item entries batch job identifies that earliest allowed Posting Date is September 10 and thereby assigns September 10 to the Adjustment Value Entry (**Entry No. 391**), below.  


|Entry No.  |Item No.  |Posting Date  |Item Ledger Entry Type  |Entry Type  |Document No.  |Item Ledger Entry No.  |Location Code  |Item Ledger Entry Quantity  |Invoiced Quantity  |Cost Amount (Actual)  |Cost Amount (Expected)  |Adjustment  |Applies-to Entry  |Source Code  |
|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|379     |  A       |    2020-09-05     |    Sale     | Direct Cost   | 102033        |319     | Blue        | -1       |0         |  0       |     -10   |No   |0    |Sales          |
|381     |  A       |    2020-09-06     |    Sale     | Direct Cost   | 103022        |319     | Blue        |  0       |-1        |-10       |    10     | No  |0      |       Sales   |
|391     |  A       |    **2020-09-10**     |    Sale     | Direct Cost   | 103022        |319     | Blue        |  0       |0         |-1        |    0     |Yes   |    181   | INVTADJMT   |

## Common problems with the "Adjust Cost - Item entries"-batch job

There are two scenarios that the support team encounters frequently enough for them to warrant their own problem resolution articles.

### Error message: "Posting Date is not within your range of allowed posting dates…"

If you encounter this error you need to adjust the dates for which the user is allowed to post entries. To learn more, see [Error Message "Posting Date is not within your range of allowed posting dates"](design-details-inventory-adjustment-value-entry-allowed-posting-dates.md).

### Posting Date on Adjustment Value Entry versus Posting Date on entry causing the adjustment such as Revaluation or Item charge

To learn more, see [Posting Date on Adjustment Value Entry Compared to the Source Entry](design-details-inventory-adjustment-value-entry-source-entry.md).

## Related information  

[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Design Details: Item Application](design-details-item-application.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
