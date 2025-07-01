---
title: Apply CODA Statements [BE]
description: After a CODA statement is imported, you can view the statement lines on the Bank Account Card page.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Bank Account Card, CODA statements, statement lines, Belgian version
ms.search.form: 2000040
ms.date: 04/01/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Apply CODA statements in the Belgian version

After a CODA statement is imported, the statement lines can be accessed from the **Bank Account Card** page. The application status on each line is blank because the statement amounts haven't been applied to outstanding ledger entries.  

Statement amounts can be applied to outstanding ledger entries by:  

- Manually applying CODA statement lines.  
- Automatically applying CODA statement amounts to the appropriate ledger entries and accounts. Automatic processing of CODA statement lines is recommended.  

## Manually apply the CODA statement lines  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.  
1. Select the bank account, and then choose the **CODA Statements** action.  
1. Select the CODA statement, and then choose the **Edit** action.  
1. For each statement line, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Account No.**|Enter the number of the general ledger account, bank, customer, vendor, or fixed asset that the bank account statement line is linked to.|  
    |**Description**|[!INCLUDE[prod_short](../../includes/prod_short.md)] automatically retrieves the description from the imported CODA file, but you can modify the contents of this field.|  

1. Choose the **OK** button.  

## Automatically apply the CODA statement lines  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.  
1. Select the bank account, and then choose the **CODA Statements** action.  
1. Select the CODA statement, and then choose the **Edit** action.  
1. Choose the **Process CODA Statement Lines** action.  
1. Fill in the fields as described in the following table.  

   |Field|Description|  
   |---------------------------------|---------------------------------------|  
   |**Default Posting**|Select if you want the batch job to post statement amounts that can't be linked to existing ledger entries.|  
   |**Print List**|Select to print a list of statement amounts that can't be linked automatically.|  

1. Choose the **OK** button.  

   When you start the batch job, statement amounts are applied to existing ledger entries based on the transaction codes. Learn more in [Set up bank accounts for CODA](how-to-set-up-bank-accounts-for-coda.md).

## Related information

- [CODA Bank Statements](coda-bank-statements.md)
- [Set Up Bank Accounts for CODA](how-to-set-up-bank-accounts-for-coda.md)
- [Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md)
- [Import CODA Statements](how-to-import-coda-statements.md)
- [Create Financial Journals](how-to-create-financial-journals.md)
- [Automatically Transfer and Post CODA Statements](how-to-automatically-transfer-and-post-coda-statements.md)
- [Manually Transfer and Post CODA Statements](how-to-manually-transfer-and-post-coda-statements.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
