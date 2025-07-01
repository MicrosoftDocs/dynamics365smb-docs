---
title: Automatically transfer and post CODA statements [BE]
description: After all CODA statement lines are applied and processed, you can transfer them to a financial journal.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: CODA, CODA statements, financial journal, Belgian version
ms.search.form: 2000040
ms.date: 04/02/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Automatically transfer and post CODA statements in the Belgian version

After you apply and processed all CODA statement lines, you can transfer the CODA statement lines to a financial journal.  

After transferring the statement lines, you can post the lines in a corresponding general journal. If no such general journal exists, you can't transfer the lines. You can create a journal to handle CODA statements. Learn more in [Create Financial Journals](how-to-create-financial-journals.md).  

Alternatively, you can manually transfer and post CODA statements. Learn more in [Manually Transfer and Post CODA Statements](how-to-manually-transfer-and-post-coda-statements.md).  

## Automatically transfer statement lines  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.  
1. Select the bank account, and then choose the **CODA Statements** action.  
1. Select the CODA statement, and then choose the **Edit** action.  
1. Choose the **Transfer to General Ledger** action.  
1. Choose the **Yes** button.  

The batch job now transfers the CODA statement lines to the financial journal.  

After transferring the statement lines to the journal, you can post the statement lines in the corresponding financial journal.  

## Related information

- [CODA Bank Statements](coda-bank-statements.md)
- [Import CODA Statements](how-to-import-coda-statements.md)
- [Apply CODA Statements](how-to-apply-coda-statements.md)
- [Create Financial Journals](how-to-create-financial-journals.md)
- [Manually Transfer and Post CODA Statements](how-to-manually-transfer-and-post-coda-statements.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
