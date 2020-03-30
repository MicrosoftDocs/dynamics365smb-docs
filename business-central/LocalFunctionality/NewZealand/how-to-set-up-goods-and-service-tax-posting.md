---
    title: How to Set Up Goods and Service Tax Posting
    description: Describes how to set up posting for goods and services tax (GST) in New Zealand.
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
# Set Up Goods and Service Tax Posting
Goods and services tax (GST) is the tax that is applied on most goods and services. The GST that is paid and received during a period is reported in the Business Activity Statement (BAS) that has to be submitted to the tax authority.  

To set up posting details for GST, you must define the posting groups, rate of GST, and the accounts to which GST is to be posted. You can set up this information for a particular combination business posting groups and product posting groups.  

## To set up goods and sales tax posting  
1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Posting Setup**, and then choose the related link.  
2. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**VAT Bus. Posting Group**|Specifies the VAT business posting group code.|  
    |**VAT Prod. Posting Group**|Specifies the VAT product posting group code.|  
    |**VAT Identifier**|Specifies the code that is used to group similar VAT setups with similar attributes.<br /><br /> For example, you can group a number of VAT posting setups that have a common VAT percentage.|  
    |**VAT %**|Specifies the VAT rate.|  
    |**VAT Calculation Type**|Specifies the method that is used to calculate the purchase or sale of items.|  
    |**Sales VAT Account**|Specifies the number of the general ledger account to which you want to post the sales VAT.<br /><br /> If you have selected the **Reverse Charge VAT** option in the **VAT Calculation Type** field, then do not enter a value in this field.|  
    |**Purchase VAT Account**|Specifies the number of the general ledger account to which you want to post the purchase VAT.|  
    |**Reverse Chrg. VAT Acc.**|Specifies the number of the general ledger account to which you want to post the reverse charge VAT.<br /><br /> You can enter a value in this field only if you have selected the **Reverse Charge VAT** option in the **VAT Calculation Type** field.|  

3.  Choose the **OK** button.  

## See Also  
[Print Goods and Service Tax Settlement Reports](how-to-print-goods-and-service-tax-settlement-reports.md)
