---
title: Print General Ledger Setup Information [CH]
description: Run the G/L Setup Information report in Business Central to review and verify the master data you configured before starting daily operations.
author: brentholtorf
ms.topic: install-set-up-deploy
ms.devlang: al
ms.search.keywords: G/L setup information, G/L setup, general setup information, Swiss version
ms.date: 04/29/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Print general ledger setup information in the Swiss version

Before you use [!INCLUDE[prod_short](../../includes/prod_short.md)] in the daily business, you can run the **G/L Setup Information** report to display the master data that you set up. For example, you can look over this master data so that you have a baseline to compare to, and then verify that you have set up posting groups correctly.  

## Print general ledger setup information  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Setup Information**, and then choose the related link.  
1. On the **Options** FastTab, in the **Setup Information** field, select the master data area as described in the following table.  

    |Option|Description|  
    |-------------------------------------|---------------------------------------|  
    |**G/L Setup - Company Data - Consolidation**|Displays tables for general ledger setup, company information, and business units.|  
    |**Posting Groups**|Displays customer posting group tables, vendor posting group tables, inventory posting group tables, and bank account posting group tables.|  
    |**Posting Matrix**|Displays general business posting group tables, general product posting group tables, and general posting group tables.|  
    |**VAT Setup**|Displays VAT business posting group tables, VAT product posting group tables, and VAT posting setup tables.|  
    |**Source Code - Reason Code**|Displays source tables, source code setup tables, and reason codes tables.|  
    |**Check Number Series**|Select to provide an overview of the use of number series so that you can identify number series that are problematic for the data export for the Grundsätze zum Datenzugriff und zur Prüfbarkeit digitaler Unterlagen (GDPdU). The report shows number series with one of the following issues:<br><br/>- The number series allows manual document numbers.<br/>- The number series isn't chronological.<br/>- The number series is used in more than one table or field.|  

1. Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## Related information

[Setting Up Finance](../../finance-setup-finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
