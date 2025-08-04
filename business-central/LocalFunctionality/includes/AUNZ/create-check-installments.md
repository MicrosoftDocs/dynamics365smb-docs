---
author: brentholtorf
ms.topic: include
ms.date: 03/28/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

You can create check installments for post-dated checks. You can define the number of installments that a payment is divided into, the percent of interest, and the period in which the checks are created.

## Create a check installment

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Post Dated checks-Purchases**, and then choose the relevant link.  
1. Choose the relevant check, and then choose the **Edit** action.  
1. On the **Post Dated Checks-Purchase** page, choose the **Create Check Installments** action.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**No. of Installments**|Specifies the number of installments into which the post-dated check is divided.|  
    |**Interest %**|Specifies the percent of interest.|  
    |**Period Length**|Specifies the period for which the installments are created. For example, if you want to divide the check into monthly installments, enter **1M**.|  
    |**Start Document No.**|Specifies the starting number of the document. Based on the number of installments specified, the consecutive numbers are allocated to the documents created.|  

1. Choose the **OK** button.  

   The installment checks are created and displayed on the **Post Dated Checks-Purchases** page.
