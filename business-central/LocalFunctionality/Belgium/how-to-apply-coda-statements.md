---
    title: How to Apply CODA Statements
    description: After a CODA statement has been imported, the statement lines can be accessed from the Bank Account Card page. The application status on each line will be blank because the statement amounts have not been applied to outstanding ledger entries.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Apply CODA Statements
After a CODA statement has been imported, the statement lines can be accessed from the **Bank Account Card** page. The application status on each line will be blank because the statement amounts have not been applied to outstanding ledger entries.  

Statement amounts can be applied to outstanding ledger entries by:  

-   Manually applying CODA statement lines.  
-   Automatically applying CODA statement amounts to the appropriate ledger entries and accounts. Automatic processing of CODA statement lines is recommended.  

## To manually apply the CODA statement lines  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Accounts**, and then choose the related link.  
2.  Select the bank account, and then choose the **CODA Statements** action.  
3.  Select the CODA statement, and then choose the **Edit** action.  
4.  For each statement line, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Account No.**|Enter the number of the general ledger account, bank, customer, vendor, or fixed asset that the bank account statement line is linked to.|  
    |**Description**|[!INCLUDE[d365fin](../../includes/d365fin_md.md)] automatically retrieves the description from the imported CODA file, but you can modify the contents of this field.|  

5.  Choose the **OK** button.  

## To automatically apply the CODA statement lines  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Accounts**, and then choose the related link.  
2.  Select the bank account, and then choose the **CODA Statements** action.  
3.  Select the CODA statement, and then choose the **Edit** action.  
4.  Choose the **Process CODA Statement Lines** action.  
5.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Default Posting**|Select if you want the batch job to post statement amounts that cannot be linked to existing ledger entries.|  
    |**Print List**|Select to print a list of statement amounts that cannot be linked automatically.|  

6.  Choose the **OK** button.  

    When you start the batch job, statement amounts will be applied to existing ledger entries based on the transaction codes. For more information, see [Set Up Bank Accounts for CODA](how-to-set-up-bank-accounts-for-coda.md).

## See Also  
 [CODA Bank Statements](coda-bank-statements.md)   
 [Set Up Bank Accounts for CODA](how-to-set-up-bank-accounts-for-coda.md)   
 [Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md)   
 [Import CODA Statements](how-to-import-coda-statements.md)   
 [Create Financial Journals](how-to-create-financial-journals.md)   
 [Automatically Transfer and Post CODA Statements](how-to-automatically-transfer-and-post-coda-statements.md)   
 [Manually Transfer and Post CODA Statements](how-to-manually-transfer-and-post-coda-statements.md)
