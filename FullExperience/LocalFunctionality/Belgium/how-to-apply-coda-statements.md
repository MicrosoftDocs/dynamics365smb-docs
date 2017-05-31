---
title: "How to: Apply CODA Statements"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "CODA, applying statements"
ms.assetid: 40a4e8df-0c03-4e83-a2cd-b26ebda9d6a3
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: Apply CODA Statements
After a CODA statement has been imported, the statement lines can be accessed from the **\($ N\_370 Bank Account Card $\)** window. The application status on each line will be blank because the statement amounts have not been applied to outstanding ledger entries.  
  
 Statement amounts can be applied to outstanding ledger entries by:  
  
-   Manually applying CODA statement lines.  
  
-   Automatically applying CODA statement amounts to the appropriate ledger entries and accounts. Automatic processing of CODA statement lines is recommended.  
  
### To manually apply the CODA statement lines  
  
1.  In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
  
2.  Select the bank account, and on the **Home** tab, in the **Process** group, choose **CODA Statements**.  
  
3.  Select the CODA statement, choose **Actions**, and then choose **Edit**.  
  
4.  In the **CODA Statement Lines** FastTab, for each statement line, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_2000041\_41 Account No. $\)**|Enter the number of the general ledger account, bank, customer, vendor, or fixed asset, which the bank account statement line is linked to.|  
    |**\($ T\_2000041\_6 Description $\)**|[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] automatically retrieves the description from the imported CODA file, but you can modify the contents of this field.|  
  
5.  Choose the **OK** button.  
  
### To automatically apply the CODA statement lines  
  
1.  In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
  
2.  Select the bank account, and on the **Home** tab, in the **Process** group, choose **CODA Statements**.  
  
3.  Select the CODA statement, choose **Actions**, and then choose **Edit**.  
  
4.  Choose **Actions**, point to **Functions**, and then choose **Process CODA Statement Lines**.  
  
5.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_2000059\_F\_1\_1 Default Posting $\)**|Select if you want the batch job to post statement amounts that cannot be linked to existing ledger entries. For more information, see [\($ T\_2000043 Transaction Coding $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-t_2000043-transaction-coding-$-.md).|  
    |**\($ B\_2000059\_F\_1\_3 Print List $\)**|Select to print a list of statement amounts that cannot be linked automatically.|  
  
6.  Choose the **OK** button.  
  
     When you start the batch job, statement amounts will be applied to existing ledger entries based on the transaction codes. For more information, see [How to: Set Up Bank Accounts for CODA](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-bank-accounts-for-coda.md).  
  
## See Also  
 [CODA Bank Statements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/coda-bank-statements.md)   
 [How to: Set Up Bank Accounts for CODA](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-bank-accounts-for-coda.md)   
 [How to: Set Up IBLC\-BLWI Transaction Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-iblc-blwi-transaction-codes.md)   
 [How to: Import CODA Statements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-import-coda-statements.md)   
 [How to: Create Financial Journals](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-create-financial-journals.md)   
 [How to: Automatically Transfer and Post CODA Statements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-automatically-transfer-and-post-coda-statements.md)   
 [How to: Manually Transfer and Post CODA Statements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-manually-transfer-and-post-coda-statements.md)