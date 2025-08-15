---
title: Design details accounts in the general ledger
description: To reconcile inventory and capacity ledger entries with the general ledger, the related value entries post to different accounts in the general ledger.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords:
ms.date: 07/01/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Design details: accounts in the general ledger

To reconcile inventory and capacity ledger entries with the general ledger, the related value entries are posted to different accounts in the general ledger. For more information, see [Design Details: Reconciliation with the General Ledger](design-details-reconciliation-with-the-general-ledger.md).  

## From the Inventory Ledger  

The following table shows the relationship between different types of inventory value entries and the accounts and balancing accounts in the general ledger.  

|**Item Ledger Entry Type**|**Value Entry Type**|**Variance Type**|**Expected Cost**|**Account**|**Balancing Account**|  
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
|Positive Adjmt., Negative Adjmt., Transfer|Direct Cost||No|Inventory|Inventory Adjmt.|  
|Positive Adjmt., Negative Adjmt., Transfer|Revaluation||No|Inventory|Inventory Adjmt.|  
|Positive Adjmt., Negative Adjmt., Transfer|Rounding||No|Inventory|Inventory Adjmt.|  
|(Production) Consumption|Direct Cost||No|Inventory|WIP|  
|(Production) Consumption|Revaluation||No|Inventory|Inventory Adjmt.|  
|(Production) Consumption|Rounding||No|Inventory|Inventory Adjmt.|  
|Assembly Consumption|Direct Cost||No|Inventory|Inventory Adjmt.|  
|Assembly Consumption|Direct Cost||No|Direct Cost Applied|Inventory Adjmt.|  
|Assembly Consumption|Indirect Cost||No|Overhead Applied|Inventory Adjmt.|  
|(Production) Output|Direct Cost||Yes|Inventory  (Interim)|WIP|  
|(Production) Output|Direct Cost||No|Inventory|WIP|  
|(Production) Output|Indirect Cost||No|Inventory|Overhead Applied|  
|(Production) Output|Direct Cost - Non Inventory||No|Inventory|Direct Cost Non-Inventory Applied Account|
|(Production) Output|Variance|Material|No|Inventory|Material Variance|  
|(Production) Output|Variance|Capacity|No|Inventory|Capacity Variance|  
|(Production) Output|Variance|Subcontracted|No|Inventory|Subcontracted Variance|  
|(Production) Output|Variance|Capacity Overhead|No|Inventory|Cap. Overhead Variance|  
|(Production) Output|Variance|Manufacturing Overhead|No|Inventory|Mfg. Overhead Variance|  
|(Production) Output|Variance|Material-Non Inventory|No|Inventory|Material Non-Inventory Variance Account|
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

## Assembly costs are always actual  

 As the table shows, assembly postings aren't represented in interim accounts. They're excluded because the concept of work in process (WIP) doesn't apply in assembly output posting, unlike in production output posting. Assembly costs are only posted as actual cost, never as expected cost.  

 For more information, see [Design Details: Assembly Order Posting](design-details-assembly-order-posting.md).  

## Calculating the amount to post to the general ledger  

 The following fields in the **Value Entry** table are used to calculate the expected cost amount that is posted to the general ledger:  

- Cost Amount (Actual)  
- Cost Posted to G/L  
- Cost Amount (Expected)  
- Expected Cost Posted to G/L  

The following table shows how the amounts to post to the general ledger are calculated for the two different cost types.  

|Cost Type|Calculation|  
|---------------|-----------------|  
|Actual Cost|Cost Amount (Actual) – Cost Posted to G/L|  
|Expected Cost|Cost Amount (Expected) –  Expected Cost Posted to G/L|  

## Examples

The tables in the following sections explain the accounts in more detail. They show the posting setups that include the accounts, and how the records are used.

### Assembly output

|Account  |Balancing account  |
|---------|---------|
|Page: Inventory Posting Setup<br>Field: Inventory Account<br><br>* The Inventory Posting Group comes from the assembly item.<br>* The Location Code comes from the assembly order.     |Page: General Posting Setup<br>Field: Inventory Adjustment Account<br><br>* The General Business Posting Group comes from the assembly order.<br>* The General Product Posting Group comes from the assembly item.          |
||Page: Inventory Posting Setup<br>Fields: Material Variance, Capacity Variance Account, Capacity Overhead Variance Account, Manufacturing Overhead Variance Account<br><br> * The Inventory Posting Group comes from the assembly item.<br> * The Location Code comes from the assembly order.|

### Assembly consumption

|Account  |Balancing account  |
|---------|---------|
|Page: General Posting Setup<br>Field: Inventory Adjmt. Account<br><br>* The General Business Posting Group comes from the assembly order.<br>* The General Product Posting Group comes from the component.|Page: Inventory Posting Setup<br>Field: Inventory Account<br><br>* The Inventory Posting Group comes from the component.<br>* The Location Code comes from the assembly order line.| 

|Account  |Balancing account  |
|---------|---------|
|Page: General Posting Setup<br>Field: Inventory Adjmt. Account<br><br>* The General Business Posting Group comes from the assembly order.<br>* The General Product Posting Group comes from the resource.|Page: General Posting Setup<br>Field: Direct Cost Applied Account<br>Field: Overhead Applied Account<br><br>* The General Business Posting Group comes from the assembly order.<br>* The General Product Posting Group comes from the resource.|

### Production output

|Account  |Balancing account  |
|---------|---------|
|Page: Inventory Posting Setup<br>Field: Inventory Account<br><br>* The Inventory Posting Group comes from the finished item.<br>* The Location Code comes from the production order line.|Page: Inventory Posting Setup<br>Field: WIP Account<br><br>* The Inventory Posting Group comes from the finished item.<br>* The Location Code comes from the production order line.<br><br>Page: General Posting Setup<br>Field: Direct Cost Non-Invent. Applied Account<br><br>* The General Business Posting Group comes from the production order.<br>* The General Product Posting Group comes from the finished item.<br><br>Page: General Posting Setup<br>Field: Overhead Applied Account<br><br>* The General Business Posting Group comes from the production order.<br>* The General Product Posting Group comes from the finished item.<br><br>Page: Inventory Posting Setup<br>Fields: Material Variance Account, Capacity Variance Account, Cap. Overhead Variance Account, Mfg. Overhead Variance Account, Subcontracted Variance Account, Material Non-Inventory Variance Account<br><br>* The Inventory Posting group comes from the finished item.<br>* The Location Code comes from the production order line.|

### Production consumption

|Account  |Balancing account  |
|---------|---------|
|Page: Inventory Posting Setup<br>Field: WIP Account<br><br>* The Inventory Posting Group comes from the finished item.<br>* The Location Code comes from the production order line.|Page: Inventory Posting Setup<br>Field: Inventory Account<br><br>* The Inventory Posting Group comes from the component.<br>* The Location Code comes from the assembly order line.|

|Account  |Balancing account  |
|---------|---------|
|Page: Inventory Posting Setup<br>Field: WIP Account<br><br>* The Inventory Posting Group comes from the finished item.<br>* The Location Code is blank.|Page: General Posting Setup<br>Fields: Direct Cost Applied Account, Overhead Applied Account<br><br>* The General Business Posting Group comes from the production order.<br>* The General Product Posting Group comes from the work center.<br><br>Page General Posting Setup<br>Fields: Direct Cost Applied Account, Overhead Applied Account<br><br>* The General Business Posting Group comes from the subcontracting vendor.<br>* The General Product Posting Group comes from the work center.|

## Related information  

[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Design Details: Inventory Posting](design-details-inventory-posting.md)  
[Design Details: Expected Cost Posting](design-details-expected-cost-posting.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
