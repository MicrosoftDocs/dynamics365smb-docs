---
    title: How to Declare VAT-VIES Tax
    description: The VAT-VIES declaration report allows you to submit information about sales transactions with other European Union (EU) countries/regions to the customs and tax authorities' list system.
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
# Declare VAT-VIES Tax
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] includes the VAT-VIES declaration report, which you can use to submit information about sales transactions with other European Union (EU) countries/regions to the customs and tax authorities' list system. The report displays information in the same format that is used in the customs and tax authorities' declaration list.  

Depending on the volume of sales of goods or services to other EU countries/regions, you must submit monthly, bi-monthly, or quarterly declarations. If your company has sales of more than 100,000 euros per quarter, you must submit a monthly declaration. If your company has sales of less than 100,000 euros per quarter, you must submit a quarterly declaration. For more information, see the [BZSt website](https://go.microsoft.com/fwlink/?LinkId=204368).  

The report is based on the VAT Entry table.  

## To declare VAT-VIES tax  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT-Vies Declaration Tax – DE**, and then choose the related link.  
2.  On the **VAT-Vies Declaration Tax – DE** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Reporting Period**|Select the time period that the report applies to. This can be a month, a two-month period, a quarter, or the calendar year.|  
    |**Date of Signature**|Enter the date on which the VAT-VIES declaration is sent.|  
    |**Corrected Notification**|If selected, this field indicates that this is a corrected version of an already delivered VAT-VIES declaration.|  
    |**Show Amounts in Add. Reporting Currency**|If selected, the amounts of the report will be in the additional reporting currency. For more information, see Additional Reporting Currency.|  
    |**Change to monthly reporting**|If selected, your company has sales of more than 100,000 euros per quarter and you must migrate from a quarterly report to a monthly report. **Important:**  Only select this field the first time that you submit a monthly report.|  
    |**Revoke monthly reporting**|If selected, you want to switch from monthly reporting to another reporting period.<br /><br /> For example, if you have previously submitted monthly declarations but the EU sales are less than 100,000 euros per quarter, select this field and then select one of the quarters in the **Reporting Period** field.|  

3.  On the **VAT Entry** FastTab, select the appropriate filters.  

    > [!NOTE]  
    >  In order to run this report, you must select the **Posting Date** as a filter, and enter the posting date value.  

## See Also  
[VAT Reporting](vat-reporting.md)
