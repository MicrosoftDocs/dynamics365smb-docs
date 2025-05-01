---
author: brentholtorf
ms.topic: include
ms.date: 03/28/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

## Set up WHT posting groups

To use withholding tax, you must set up the business posting groups and product posting groups for withholding tax so that the correct WHT calculations are made for each vendor.  

> [!NOTE]  
> As a prerequisite, you must set up source codes for WHT settlement on the **Source Code Setup** page. Learn more in [Setting Up Source Codes and Reason Codes for Audit Trails](../../../finance-setup-trail-codes.md).  

The following procedure describes how to set up product posting groups for WHT, but the same steps also apply to setting up business posting groups for WHT.  

### Set up a product posting group for withholding tax  

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **WHT Product Posting Group**, and then choose the related link.  
1. Fill in the fields as described in the following table.  

   |Field|Description|  
   |---------------------------------|---------------------------------------|  
   |**Code**|Specify the code for the product posting group. You can enter a maximum of 10 alphanumeric characters.|  
   |**Description**|Specify the description for the product posting group. You can enter a maximum of 50 alphanumeric characters.|  

1. Choose the **OK** button.  

Finally, you must set up how these posting groups must be used when documents are posted.  

### Set up posting for withholding tax  

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **WHT Posting Setup**, and then choose the related link.  

1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**WHT Business Posting Group**|Specifies the business posting group code for withholding tax.|  
    |**WHT Product Posting Group**|Specifies the product posting group code for withholding tax.|  
    |**WHT Calculation Rule**|Specifies the calculation rule for WHT, which is used with the amount specified in the **WHT Minimum Invoice Amount** field. This helps identify the transactions for which WHT isn't deducted.<br/><br/> For example, if you select the **Less than** option here and enter 100 in the **WHT Minimum Invoice Amount** field, then WHT isn't deducted for those transactions with an amount less than 100.|  
    |**WHT Minimum Invoice Amount**|Specifies the threshold amount that is below which WHT isn't deducted.|  
    |**WHT %**|Specifies the WHT rate. You must enter the rate without the percent sign.|  
    |**Realized WHT Type**|Specifies the mode of WHT calculation for purchases or sales of items.|  
    |**Prepaid WHT Account Code**|Specifies the general ledger account number to which sales WHT is to be posted.|  
    |**Payable WHT Account Code**|Specifies the general ledger account number to which purchase WHT is to be posted.|  
    |**WHT Report**|Specifies the withholding tax report type.|  
    |**Bal. Prepaid Account Type**|Specifies the type of balancing account for sales WHT transactions.|  
    |**Bal. Prepaid Account No.**|Specifies the account number or bank name for sales WHT transactions, based on the type selected in the **Bal. Prepaid Account Type** field.|  
    |**Bal. Payable Account Type**|Specifies the type of balancing account for purchase WHT transactions.|  
    |**Bal. Payable Account No.**|Specifies the account number or bank name for purchase WHT transactions. This is based on the type selected in the **Bal. Payable Account Type** field.|  
    |**WHT Report Line No. Series**|Specifies the number series for the WHT report line.|  
    |**Revenue Type**|Specifies the type of revenue.|  
    |**Purch. WHT Adj. Account No.**|Specifies the account number on which to post purchase credit memo adjustments.|  
    |**Sales WHT Adj. Account No.**|Specifies the account number on which to post sales credit memo adjustments.|  
    |**Sequence**|Specifies the sequence in which the withholding tax posting setup information must be displayed in reports.|  

1. Choose the **OK** button.  
