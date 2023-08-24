---
    title: Create Electronic VAT Transactions Report [IT]
    description: You must create a list of transactions that include VAT with amounts over the current threshold on or before the specified occurrence date. 
    services: project-madeira 
    documentationcenter: ''
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/29/2021
    ms.author: bholtorf

---
# Create Electronic VAT Transactions Reports in the Italian Version
You must create a list of transactions that include VAT with amounts over the current threshold on or before the specified occurrence date. You submit this report to the tax authorities.  

## To create a VAT transactions report  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Report**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |-------------------------------------|---------------------------------------|  
    |**Without Contract**|The VAT entries that resulted in this line are not associated with a contract.|  
    |**Contract**|The VAT entries that resulted in this line are associated with a contract.|  
    |**Other**|The VAT entries that resulted in this line are not associated with a special contract, such as ongoing maintenance or other exceptions.|  

    > [!TIP]  
    >  In [!INCLUDE[prod_short](../../includes/prod_short.md)], the contract that the tax authorities are looking for can be blanket orders or service contracts. To identify if the VAT report line belongs to a blanket order or service contract, you can drill down to see the underlying VAT entries from the **Amount** field.  

Credit memos are included in the VAT transaction report if the customer or vendor is from a country/region that is outside the EU and not excluded. For more information, see [Italian VAT](italian-vat.md).  

Now that you have created the VAT report, you must submit it to the tax authorities. For more information, see [Export VAT Transactions Reports](how-to-export-vat-transactions-reports.md).  

## See Also  
 [Italian VAT](italian-vat.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]