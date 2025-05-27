---
title: How to Limit the Posting Period [BE]
description: Understand the methods to limit the posting period at three distinct levels - company-wide, user-specific, and template-based.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: limit posting period, posting period, sales journal, purchase journal, Belgian version
ms.date: 04/02/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Limit the posting period in the Belgian version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can limit the period by which posting is permitted on three different levels: **by company**, **by user**, and **by template**.  

Limiting posting periods can be useful when a company closes its sales journal at the end of each month. This keeps salespeople from registering sales documents from the previous month. At the same time, the purchase journal may stay open to register incoming purchase invoices from the previous month.  

When you post on the **General Journal Templates** page, the contents of the **Allow Posting From** field and **Allow Posting To** field are checked for a date interval. The date interval indicates when you can post to a journal template. If the field is blank, the **User Setup** page is checked for a date interval for the current user. If the **User Setup** page doesn't contain an interval, the **Allow Posting From** field and the **Allow Posting To** field on the **General Ledger Setup** page is checked for a date interval at the company level.  

## Limit posting periods by company  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
1. To specify the start of the period, choose the **Allow Posting From** field, and then enter the earliest date on which posting to the company is enabled.  
1. To specify the end of the period, choose the **Allow Posting To** field, and then enter the last date on which posting to the company is enabled.  

## Limit posting periods by user  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Setup**, and then choose the related link.  
1. To specify the start of the period, choose the **Allow Posting From** field, and then enter the earliest date on which the user can post to the company.  
1. To specify the end of the period, choose the **Allow Posting To** field, and then enter the last date the user will be able to post to the company.  

## Limit posting periods by template  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journal Templates**, and then choose the related link.  
1. To specify the start of the period, choose the **Allow Posting From** field, and then enter the earliest date on which the user can post to the company.  
1. To specify the end of the period, choose the **Allow Posting To** field, and then enter the last date the user will be able to post to the company.  

## Related information

- [Belgium Local Functionality](belgium-local-functionality.md)
- [Specify Posting Periods](../../finance-how-specify-posting-periods.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
