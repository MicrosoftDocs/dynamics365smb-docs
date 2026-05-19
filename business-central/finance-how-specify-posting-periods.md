---
title: Specify posting periods
description: You specify posting periods (posting start and end dates) to set up when users can post to the general ledger.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: user setup
ms.search.form: 118_Primary,
ms.date: 03/18/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Specify posting periods

Use posting periods to specify when users can post to the general ledger.  

## To specify fixed dates for posting periods

1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Ledger Setup**, and then choose the related link.  
2. On the **General Ledger Setup** page, define the period by entering dates in the **Allow Posting From** and **Allow Posting To** fields.  

> [!NOTE]  
> These posting periods apply to the company and to all users. To allow for exceptions, you can define different posting periods for specific users on the **User Setup** page. These posting periods overrule the periods specified on the **General Ledger Setup** page. To learn more, go to [Set up time constraints for users](ui-define-granular-permissions.md#set-up-time-constraints-for-users).

### Video guidance for fixed dates

When you're closing an accounting period, you might want to prevent new posts from coming in, or allow only certain people to post transactions. The following video shows how to control when, and who, can post transactions to your general ledger.

> [!VIDEO https://learn-video.azurefd.net/vod/player?id=c53fd593-9cb6-4244-a21f-8fea6a602b4e]

## Dynamically calculate posting periods

You can use date formulas to control the range of allowed posting dates in **General Ledger Setup**, **User Setup**, and **General Journal Templates**. Instead of entering fixed dates that you must update every period, you enter a date formula and [!INCLUDE [prod_short](includes/prod_short.md)] calculates the period in which you allow posting based on your current work date.

> [!NOTE]
> Date formulas are evaluated against the work date, which users can change on their **My Settings** page. The calculated posting period shifts when a user changes their work date, making date formulas less restrictive than the old fixed-date approach, where an administrator set explicit boundaries that no user could shift on their own.
>
> Use fixed dates when you need strict, administrator-controlled boundaries that users can't influence. Use date formulas when the benefit of automatic, maintenance-free period management outweighs the reduced restrictiveness from adjustable work dates. You can also combine both approaches, and use a fixed date for one boundary and a formula for the other.

The **Allow Posting From Date Formula** and **Allow Posting To Date Formula** fields are available on:

- **General Ledger Setup** (Though you might need to choose **Show more** to view them.)
- **User Setup**  
- **General Journal Templates**

### How posting date formulas work

[!INCLUDE [prod_short](includes/prod_short.md)] evaluates your date formula against the work date each time a posting date is validated. The following table shows various examples.

| Scenario | Allow Posting From Date Formula | Allow Posting To Date Formula | Work Date | Resulting Range |
|---|---|---|---|---|
| Current month only | `-CM` | `CM` | Mar 17, 2026 | Mar 1 - Mar 31 |
| Rolling 30-day window | `-30D` | `0D` | Mar 17, 2026 | Feb 15 - Mar 17 |
| One month back, one week forward | `-1M` | `1W` | Mar 17, 2026 | Feb 17 - Mar 24 |
| Previous month close | `-1M-CM` | `-CM-1D` | Mar 17, 2026 | Feb 1 - Feb 28 |
| Today only | `0D` | `0D` | Mar 17, 2026 | Mar 17 – Mar 17 |

To learn more about date formulas, go to [Use date formulas](ui-enter-date-ranges.md#use-date-formulas).

### Priority of posting date checks

[!INCLUDE [prod_short](includes/prod_short.md)] evaluates posting date restrictions in this order:

1. User Setup page
2. General Ledger Setup page
3. General Journal Template page (when the **Journal Templ. Name Mandatory** toggle is enabled on the **General Posting Setup** page).

### Using formulas together with fixed dates

For each boundary (From or To), you can choose either a fixed date or a date formula. When you enter a formula, the corresponding fixed date is cleared. When you enter a fixed date, the formula field is cleared. You can mix a fixed date for one boundary and a formula for the other.

## Related information

[Finance](finance.md)  
[Completing Period-End Processes](year-how-complete-period-end-processes.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
