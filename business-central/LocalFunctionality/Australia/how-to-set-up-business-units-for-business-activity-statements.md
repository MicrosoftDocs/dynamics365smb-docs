---
title: Set Up Business Units for Business Activity Statements (AU)
description: Describes how to consolidate the financial statements of various companies into one financial statement.
author: brentholtorf
    
ms.topic: conceptual
ms.devlang: al
ms.search.keywords:
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Set Up Business Units for Business Activity Statements in the Australian Version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can consolidate the financial statements of various companies into one financial statement.  

You must set up a consolidation company to perform the consolidation. In this company, the total amounts for all accounts in the group, from both the parent company and subsidiaries, are added together. You must also indicate the general ledger accounts in the consolidated company to which the total should be transferred.  

You can use the **BAS Business Units** page to set up the following:  

- Parent company  
- Subsidiaries  
- Affiliates  

You must provide information on the **General Ledger Setup** page before you can set up business units.  

## To set up a general ledger for a business activity statement  
1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
2. Fill in the required fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**BAS to be Lodged as a Group**|Select if you are logging a business activity statement for a group of companies.|  
    |**BAS Group Company**|Select if this company is the main company in the group of companies for which you are logging a group business activity statement.|  

3.  Choose the **OK** button.  

## To set a business unit for a business activity statement  
1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **BAS Business Units**, and then choose the related link.  
2. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Company Name**|Specify the name of the company that will be added to the group company's business activity statement.|  
    |**Document No.**|Specify the BAS document number that has to be consolidated. This field is associated with the **BAS Version** field.|  
    |**BAS Version**|Specify the BAS version number in which the transaction was included. This field is associated with the **Document No.** field.|  

3. Choose the **OK** button.  

## See Also  
[Australian Local Functionality](australia-local-functionality.md)   



[!INCLUDE[footer-include](../../includes/footer-banner.md)]