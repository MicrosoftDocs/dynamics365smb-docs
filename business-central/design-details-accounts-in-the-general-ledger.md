---
    title: Design Details - Accounts in the General Ledger | Microsoft Docs
    description: To reconcile inventory and capacity ledger entries with the general ledger, the related value entries are posted to different accounts in the general ledger.
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
# Design Details: Accounts in the General Ledger
To reconcile inventory and capacity ledger entries with the general ledger, the related value entries are posted to different accounts in the general ledger. For more information, see [Design Details: Reconciliation with the General Ledger](design-details-reconciliation-with-the-general-ledger.md).  

## From the Inventory Ledger  
The following table shows the relationship between different types of inventory value entries and the accounts and balancing accounts in the general ledger.  

|**Item Ledger Entry Type**|**Value Entry Ttype**|**Variance Type**|**Expected Cost**|**Account**|**Balancing Account**|  
|--------------------------------|--------------------------|-----------------------|-----------------------|-----------------|---------------------------|  
|Purchase|Direct Cost||Yes|Inventory  (Interim)|Invt. Accrual Acc. (Interim)|  
|Purchase|Direct Cost||No|Inventory|Direct Cost Applied|  
|Purchase|Indirect Cost||No|Inventory|Overhead Applied|  
|Purchase|Variance|Purchase|No|Inventory|Purchase Variance|  
|Purchase|Revaluation||No|Inventory|Inventory Adjmt.|  
|Purchase|Rounding||No|Inventory|Inventory Adjmt.|  
|Sale|Direct Cost||Yes|Inventory  (Interim)|COGS (Interim)|  
|Sale|Direct Cost||No|Inventory|COGS|  
|Sale|Revaluation||No|Inventory|Inventory Adjmt.|  
|Sale|Rounding||No|Inventory|Inventory Adjmt.|  
|Positive Adjmt.,Negative Adjmt., Transfer|Direct Cost||No|Inventory|Inventory Adjmt.|  
|Positive Adjmt.,Negative Adjmt., Transfer|Revaluation||No|Inventory|Inventory Adjmt.|  
|Positive Adjmt.,Negative Adjmt., Transfer|Rounding||No|Inventory|Inventory Adjmt.|  
|(Production) Consumption|Direct Cost||No|Inventory|WIP|  
|(Production) Consumption|Revaluation||No|Inventory|Inventory Adjmt.|  
|(Production) Consumption|Rounding||No|Inventory|Inventory Adjmt.|  
|Assembly Consumption|Direct Cost||No|Inventory|Inventory Adjmt.|  
|Assembly Consumption|Direct Cost||No|Direct Cost Applied|Inventory Adjmt.|  
|Assembly Consumption|Indirect Cost||No|Overhead Applied|Inventory Adjmt.|  
|(Production) Output|Direct Cost||Yes|Inventory  (Interim)|WIP|  
|(Production) Output|Direct Cost||No|Inventory|WIP|  
|(Production) Output|Indirect Cost||No|Inventory|Overhead Applied|  
|(Production) Output|Variance|Material|No|Inventory|Material Variance|  
|(Production) Output|Variance|Capacity|No|Inventory|Capacity Variance|  
|(Production) Output|Variance|Subcontracted|No|Inventory|Subcontracted Variance|  
|(Production) Output|Variance|Capacity Overhead|No|Inventory|Cap. Overhead Variance|  
|(Production) Output|Variance|Manufacturing Overhead|No|Inventory|Mfg. Overhead Variance|  
|(Production) Output|Revaluation||No|Inventory|Inventory Adjmt.|  
|(Production) Output|Rounding||No|Inventory|Inventory Adjmt.|  
|Assembly Output|Direct Cost||No|Inventory|Inventory Adjmt.|  
|Assembly Output|Revaluation||No|Inventory|Inventory Adjmt.|  
|Assembly Output|Indirect Cost||No|Inventory|Overhead Applied|  
|Assembly Output|Variance|Material|No|Inventory|Material Variance|  
|Assembly Output|Variance|Capacity|No|Inventory|Capacity Variance|  
|Assembly Output|Variance|Capacity Overhead|No|Inventory|Cap. Overhead Variance|  
|Assembly Output|Variance|Manufacturing Overhead|No|Inventory|Mfg. Overhead Variance|  
|Assembly Output|Rounding||No|Inventory|Inventory Adjmt.|  

## From the Capacity Ledger  
 The following table shows the relationship between different types of capacity value entries and the accounts and balancing accounts in the general ledger. Capacity ledger entries represent labor time consumed in assembly or production work.  

|**Work Type**|**Capacity Ledger Entry Type**|**Value Entry Type**|**Account**|**Balancing Account**|  
|-------------------|------------------------------------|--------------------------|-----------------|---------------------------|  
|Assembly|Resource|Direct Cost|Direct Cost Applied|Inventory Adjmt.|  
|Assembly|Resource|Indirect Cost|Overhead Applied|Inventory Adjmt.|  
|Production|Machine Center/Work Center|Direct Cost|WIP Account|Direct Cost Applied|  
|Production|Machine Center/Work Center|Indirect Cost|WIP Account|Overhead Applied|  

## Assembly Costs are Always Actual  
 As shown in the table above, assembly postings are not represented in interim accounts. This is because the concept of work in process (WIP) does not apply in assembly output posting, unlike in production output posting. Assembly costs are only posted as actual cost, never as expected cost.  

 For more information, see [Design Details: Assembly Order Posting](design-details-assembly-order-posting.md).  

## Calculating the Amount to Post to the General Ledger  
 The following fields in the **Value Entry** table are used to calculate the expected cost amount that is posted to the general ledger:  

-   Cost Amount (Actual)  
-   Cost Posted to G/L  
-   Cost Amount (Expected)  
-   Expected Cost Posted to G/L  

The following table shows how the amounts to post to the general ledger are calculated for the two different cost types.  

|Cost Type|Calculation|  
|---------------|-----------------|  
|Actual Cost|Cost Amount (Actual) – Cost Posted to G/L|  
|Expected Cost|Cost Amount (Expected) –  Expected Cost Posted to G/L|  

## See Also  
 [Design Details: Inventory Costing](design-details-inventory-costing.md)   
 [Design Details: Inventory Posting](design-details-inventory-posting.md)   
 [Design Details: Expected Cost Posting](design-details-expected-cost-posting.md)  
 [Managing Inventory Costs](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
