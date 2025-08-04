---
title: Financial Information Quick Start
description: Get your company ready for business by setting up the financial information in Business Central.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: quickstart
ms.search.form: 
ms.date: 08/25/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Financial Information Quick Start

After entering basic company information in [!INCLUDE[prod_short](includes/prod_short.md)], one of the next steps is completing the financial section. You do this not only to receive or make payments, but also to properly manage and report your business' numbers.

## The chart of accounts

The chart of accounts (COA) offers an overview of the company's finances, listing accounts in structured groups such as assets, liabilities, income, cost of goods sold, and expenses. [!INCLUDE[prod_short](includes/prod_short.md)] includes a standard chart of accounts you can customize to your business' accounting practices.

## Set up the chart of accounts

The following video shows how to set up the chart of accounts in [!INCLUDE[prod_short](includes/prod_short.md)].

<br /><br />

> [!Video https://learn-video.azurefd.net/vod/player?id=944c65b0-9b0f-4d35-b330-de2fad57143a]

### Add an account to the chart of accounts

To add an account not included by default in [!INCLUDE[prod_short](includes/prod_short.md)]—for example, gardening services—just follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, then choose the related link.
2. Choose the **New** action to open the **G/L Account Card** page.
3. Enter the following data in the corresponding fields on the **General** FastTab. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

   | Field | Data |
   | --- | --- |
   | **No.** | 61250 |
   | **Name** | Gardening services |
   | **Income/Balance** | Income Statement |
   | **Account Category** | Expense |
   | **Account Subcategory** | Repairs and Maintenance Expense |
   | **Debit/Credit** | Both |
   | **Account Type** | Posting |

4. On the **Posting** FastTab, enter the following data:

   | Field | Data |
   | --- | --- |
   | **Gen. Posting Type** | Purchase |
   | **Gen. Bus. Posting Group** | Domestic |
   | **Gen. Prod. Posting Group** | Services |

5. Fill in the remaining fields on the **G/L Account Card** page as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### Get an overview of the chart of accounts

If you need a more compact view of the chart of accounts, without columns for posting groups, posting type, or cost type, for example, the **Chart of Accounts Overview** lists the main information for each account in a smaller table. Additionally, you can collapse or expand groups to hide the accounts inside them.

To display the overview, choose the **Chart of Accounts Overview** action on the **Chart of Accounts** page, or search for the feature using ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do").

Learn more about the chart of accounts and the general ledger at [Understanding the General Ledger and the Chart of Accounts](finance-general-ledger.md).

## Set up bank accounts

Bank accounts in [!INCLUDE[prod_short](includes/prod_short.md)] register banking transactions and are associated with entries in the chart of accounts. The following video shows how to set up bank accounts.

<br /><br />

> [!Video https://learn-video.azurefd.net/vod/player?id=047a5a25-1f7d-423d-b96d-c4ea45042779]

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, then choose the related link.
2. On the **Bank Accounts** page, choose the **New** action.
3. In the **No.** field, an identifier such as *B010* will be entered automatically if there's a numbered series list set for bank accounts. If not, enter a unique combination.

   The field is different from the **Bank Account No.** field also available in the **General** FastTab.
4. Fill in the fields on the **Bank Account Card** page as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Related information

[Set Up the Chart of Accounts](finance-setup-chart-accounts.md)  
[Set Up Bank Accounts](bank-how-setup-bank-accounts.md)  
[Run and Print Reports](ui-work-report.md)  
[Business Central Quick Starts](quick-start-business-central.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
