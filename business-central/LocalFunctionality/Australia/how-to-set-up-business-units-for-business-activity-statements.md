---
title: Set Up Business Units for Business Activity Statements (AU)
description: Learn how to consolidate the financial statements of various companies into one financial statement.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: consolidate financial statements, business activity statements, financial statement, Australian version, financial statement consolidation, set up general ledger, set up business units
ms.date: 03/26/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up business units for business activity statements in the Australian version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can consolidate the financial statements of various companies into one financial statement.  

You must set up a consolidation company to perform the consolidation. In this company, the total amounts for all accounts in the group, from both the parent company and subsidiaries, are added together. You must also indicate the general ledger accounts in the consolidated company to which the total should be transferred.  

You can use the **BAS Business Units** page to set up the following:  

- Parent company  
- Subsidiaries  
- Affiliates  

You must provide information on the **General Ledger Setup** page before you can set up business units.  

## Set up a general ledger for a business activity statement

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
1. Fill in the required fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**BAS to be Lodged as a Group**|Select if you're logging a business activity statement for a group of companies.|  
    |**BAS Group Company**|Select if this company is the main company in the group of companies for which you're logging a group business activity statement.|  

1. Choose the **OK** button.  

## Set up a business unit for a business activity statement

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **BAS Business Units**, and then choose the related link.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Company Name**|Specify the name of the company that is added to the group company's business activity statement.|  
    |**Document No.**|Specify the BAS document number that must be consolidated. This field is associated with the **BAS Version** field.|  
    |**BAS Version**|Specify the BAS version number in which the transaction was included. This field is associated with the **Document No.** field.|  

1. Choose the **OK** button.  

## Related information

[Australian Local Functionality](australia-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
