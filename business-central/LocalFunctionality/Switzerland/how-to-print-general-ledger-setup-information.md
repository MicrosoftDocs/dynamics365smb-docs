---
    title: Print General Ledger Setup Information [CH]
    description: Before you use Business Central in your daily business, you can run the G/L Setup Information report to display the master data that you have set up.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/25/2021
    ms.author: bholtorf
---
# Print General Ledger Setup Information in the Swiss Version
Before you use [!INCLUDE[prod_short](../../includes/prod_short.md)] in the daily business, you can run the **G/L Setup Information** report to display the master data that you have set up. You can look over this master data so that you have a baseline to compare to, and then verify that you have set up posting groups correctly, for example.  

## To print general ledger setup information  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Setup Information**, and then choose the related link.  
2.  On the **Options** FastTab, in the **Setup Information** field, select the master data area as described in the following table.  

    |Option|Description|  
    |-------------------------------------|---------------------------------------|  
    |**G/L Setup - Company Data - Consolidation**|Displays tables for general ledger setup, company information, and business units.|  
    |**Posting Groups**|Displays customer posting group tables, vendor posting group tables, inventory posting group tables, and bank account posting group tables.|  
    |**Posting Matrix**|Displays general business posting group tables, general product posting group tables, and general posting group tables.|  
    |**VAT Setup**|Displays VAT business posting group tables, VAT product posting group tables, and VAT posting setup tables.|  
    |**Source Code - Reason Code**|Displays source tables, source code setup tables, and reason codes tables.|  
    |**Check Number Series**|Select to provide an overview of the use of number series so that you can identify number series that are problematic for the data export for the Grundsätze zum Datenzugriff und zur Prüfbarkeit digitaler Unterlagen (GDPdU). The report will show number series with one of the following issues:<br /><br /> -   The number series allows manual document numbers.<br />-   The number series is not chronological.<br />-   The number series is used in more than one table or field.|  

3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## See Also  
[Setting Up Finance](../../finance-setup-finance.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]