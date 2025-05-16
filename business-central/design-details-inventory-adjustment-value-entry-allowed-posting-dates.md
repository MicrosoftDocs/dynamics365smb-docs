---
title: Error Message "Posting Date is not within your range of allowed posting dates"
description: Resolve the error behind the message "Posting date is not within your range of allowed posting dates" when running the Adjust Cost - Item Entries batch job.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords:
ms.date: 05/24/2024
ms.service: dynamics-365-business-central
---

# Error message: "Posting Date is not within your range of allowed posting dates…"

When you use the **Adjust Cost - Item Entries** batch job, you might run into the following error message:

**Posting date is not within your range of allowed posting dates**

This message indicates that you aren't allowed to post entries for the date you entered. You can get around this issue by changing your user setup.

## Change the user setup  

|User ID  |Allow Posting From  | Allow Posting To  |
|---------|---------|--------|
|EUROPE  |  2020-09-11      |2020-09-30      |

In this case, you're allowed to post in the date range from September 11 to September 30. However, you aren't allowed to post the adjustment value entry with a September 10 posting date.  

### Overview of the posting date setup

#### Inventory Periods

|Ending Date  |Name  |Closed  |
|---------|---------|---------|
|2020-01-31     |January 2020      |  Yes    |
|2020-02-28     |February 2020     |  Yes    |
|2020-03-31     |March 2020        |  Yes    |
|2020-04-30     |April 2020        |  Yes    |
|2020-05-31     |May   2020        |  Yes    |
|2020-06-30     |June   2020       |  Yes    |
|2020-07-31     |July  2020        |   Yes   |
|2020-08-31     |August   2020     |   Yes   |
|2020-09-30     |September   2020  |         |
|2020-10-31     |October   2020    |         |
|2020-11-30     |November   2020   |         |
|2020-12-31     |December   2020   |         |  

#### General Ledger Setup

|Field|Value|
|---------|---------|
|Allow Posting From:  |  2020-09-10      |
|Allow Posting To:    |  2020-09-30      |
|Register Time:       |         |
|Local Address Format:|   Post Code      |  

#### User Setup

|User ID  |Allow Posting From  | Allow Posting To  |
|---------|---------|--------|
|USERNAME |  2020-09-10      |2020-09-30      |

Assigning a wider date range where you allow posting on the **Inventory Period** or **General Ledger Setup** pages lets you avoid the conflict that causes the error message. For example, the wider range lets you post the adjustment value entry with a September 10 posting date.
  
## Related information  

[Design Details: Posting Date on Adjustment Value Entry](design-details-inventory-adjustment-value-entry-posting-date.md)  
[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Design Details: Item Application](design-details-item-application.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
