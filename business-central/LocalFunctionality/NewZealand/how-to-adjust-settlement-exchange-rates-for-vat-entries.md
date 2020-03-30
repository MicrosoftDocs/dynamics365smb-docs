---
    title: How to Adjust Settlement Exchange Rates for VAT Entries
    description: Describes how to settle VAT entries according to the government exchange rate.
    services: project-madeira 
    documentationcenter: ''
    author: bholtorf
    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Adjust Settlement Exchange Rates for VAT Entries
You can use the **Adjust Settlement Exch. Rates** batch job to settle VAT entries according to the government exchange rate as defined in the **Currency Exchange Rate** table.  

## To adjust settlement exchange rates for VAT  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Adjust Settlement Exch. Rates**, and then choose the related link.  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Settlement Period**|Specifies the start date of the settlement period.|  
    |**Ending Date**|Specifies the end date of the settlement period.|  
    |**Posting Description**|Specifies the posting description.|  
    |**Document No.**|Specifies the document number for which you want to settle VAT entries.|  
    |**Posting Date**|Specifies the posting date of the document.|  
    |**Use Daily Settlement Exch. Rate**|Select if you want to use the daily settlement exchange rate.|  

3.  Choose the **OK** button.  

The VAT entries are adjusted and you can view them in the **VAT Register** report.

## See Also
[New Zealand Local Functionality]new-zealand-local-functionality.md()