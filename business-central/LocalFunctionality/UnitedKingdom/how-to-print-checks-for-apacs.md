---
title: Print Checks for APACS
description: The APACS specification sets the standard layout for fields on checks in the UK. The Check report uses the APACS specification.
author: brentholtorf 
ms.topic: how-to
ms.devlang: al
ms.search.keywords: APACS, checks, Check report
ms.search.form: 256
ms.date: 02/18/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Print Checks for APACS

The Association for Payment Clearing Services (APACS) specification defines a standard layout for fields on checks. The **Check** report uses this specification.  

## Print checks for APACS  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.  
1. Choose the **Preview Check** action to preview the check or choose the **Print Check** action to print the check.  
1. On the **Options** FastTab, fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Bank Account**|Specifies bank account code.|  
    |**Last Check No.**|Specifies the last check number that was specified on the **Bank Account Card** page.|  
    |**One Check per Vendor per Document No.**|Select to print only one check per vendor for each document number.|  
    |**Reprint Checks**|Select to reprint canceled checks.|  
    |**Test Print**|Select to print checks on blank paper before printing them on check forms.|  
    |**Preprinted Stub**|Select to use check forms with preprinted stubs.|  

1. Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## Related information

[United Kingdom Local Functionality](united-kingdom-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
