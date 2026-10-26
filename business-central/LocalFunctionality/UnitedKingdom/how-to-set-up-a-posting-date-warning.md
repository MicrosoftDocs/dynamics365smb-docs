---
title: Set Up a Posting Date Warning in the United Kingdom
description: Learn to set up the warning message displayed when posting sales and purchase documents with a posting date different from the work date.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: jswymer
ms.topic: how-to
ms.search.keywords: set up warning message, posting sales, posting purchase, posting date, work date
ms.search.form: 459, 460
ms.date: 10/23/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai-usage: ai-assisted
---

# Set up a posting date warning in the British version

You can show a confirmation when you post a sales or purchase document with a posting date that differs from the work date. During batch posting, the check stops posting the affected document instead of asking for confirmation. Set up the check separately on the **Sales & Receivables Setup** and **Purchases & Payables Setup** pages.

When you enable the posting date check feature, the UK extension turns on **Posting Date Check on Posting** for newly created sales and purchase setup records. Check the setting on existing setup records before you rely on the warning.

## Set up a posting date warning for sales and purchases  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Sales & Receivables Setup** or **Purchases & Payables Setup**, and then choose the related link.
1. On the **Sales & Receivables Setup** page or the **Purchases & Payables Setup** page, on the **General** FastTab, turn on the **Posting Date Check on Posting** toggle.
1. Choose the **OK** button.  

    > [!NOTE]  
    > The check is skipped when you select **Replace Posting Date** during batch posting. It is also skipped in sessions that don't allow a user interface.

## Related information

[United Kingdom Local Functionality](united-kingdom-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
