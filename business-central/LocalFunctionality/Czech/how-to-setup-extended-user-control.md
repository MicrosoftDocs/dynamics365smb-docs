---
title: Set up extended user control [CZ]
description: Most companies in the Czech Republic require enhancements to user setup and control to meet local business needs.
author: v-pejano
ms-service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 03/30/2026
ms.reviewer: v-soumramani
ms.author: v-jurxova
---

# Set up extended user control in the Czech version

This feature in User Setup in combination with new User Setup Lines table allows setting and providing the following control:

- Assigning user to Employee No.
- Set Cash Resp. Ctr. Filter for Cash desk operations
- Check Document Date at posting against work date or system date
- Check Posting Date at posting against work date or system date
- Check access to Payment Orders – checks allowed Bank Accounts for payment orders (set in lines)
- Check access to Bank Statements – checks allowed Bank Accounts for bank statements (set in lines)
- Check Bank Accounts allowed for posting (set in lines)
- Check access to Journal Templates – check allowed Journal Templates for all Journal types (set in lines)
- Check Dimension Values allowed for posting (set in lines)
- Check Location Code allowed for posting separately for quantity increase and quantity decrease (set in lines)
- Check Location Code allowed for document release separately for quantity increase and quantity decrease (set in lines)
- Check the usage of Whse. Net Change Templates at posting in Item Journals
- Allow Posting to Closed Period
- Allow Complete Job
- Allow Item Un-apply functionality
- Allow VAT Date Changing
- Allow External Document No. Changing
- Allow Original VAT Date Changing

The User Setup page has been updated so that all links to extended user control functionality are grouped under a new action group called User Check. This group dynamically appears or hides based on the value of the User Checks Allowed field in General Ledger Setup.

Fields related to user controls on the User Setup page also dynamically appear or hide depending on the global functionality setting in General Ledger Setup.

The User Setup Card page is improved to provide clearer placement of links to functionality settings.

## Related information

- [Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
