---
author: brentholtorf
ms.topic: include
ms.date: 03/28/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

To set up posting details for GST, you must define the posting groups, rate of GST, and the accounts to which GST is to be posted. You can set up this information for a particular combination of business posting groups and product posting groups.

You must set up GST posting before you generate the BAS report.  

## Set up goods and sales tax posting

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.  
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**VAT Bus. Posting Group**|Specifies the VAT business posting group code.|  
    |**VAT Prod. Posting Group**|Specifies the VAT product posting group code.|  
    |**VAT Identifier**|Specifies the code that is used to group similar VAT setups with similar attributes.<br/><br/>For example, you can group many VAT posting setups that have a common VAT percentage.|  
    |**VAT %**|Specifies the VAT rate.|  
    |**VAT Calculation Type**|Specifies the method that is used to calculate the purchase or sale of items.|  
    |**Sales VAT Account**|Specifies the number of the general ledger account to which you want to post the sales VAT.<br/><br/> If you select the **Reverse Charge VAT** option in the **VAT Calculation Type** field, then don't enter a value in this field.|  
    |**Purchase VAT Account**|Specifies the number of the general ledger account to which you want to post the purchase VAT.|  
    |**Reverse Chrg. VAT Acc.**|Specifies the number of the general ledger account to which you want to post the reverse charge VAT.<br/><br/> You can enter a value in this field only if you select the **Reverse Charge VAT** option in the **VAT Calculation Type** field.|  

1. Choose the **OK** button.  
