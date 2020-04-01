---
    title: How to Print General Ledger Setup Information
    description: Before you use Business Central in the daily business, you can run the G/L Setup Information report to display the master data that you have set up.

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
# Print General Ledger Setup Information
Before you use [!INCLUDE[d365fin](../../includes/d365fin_md.md)] in the daily business, you can run the **G/L Setup Information** report to display the master data that you have set up. You can look over this master data so that you have a baseline to compare to, and then verify that you have set up posting groups correctly, for example.  

## To print general ledger setup information  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Setup Information**, and then choose the related link.  
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
