---
title: Design Details - Expected Cost Posting
description: Expected costs represent the estimation of, for example, a purchased item’s cost that you record before you receive the invoice for the item.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 07/20/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design Details: Expected Cost Posting
Expected costs represent the estimation of, for example, a purchased item’s cost that you record before you receive the invoice for the item.  

 You can post expected cost to inventory and to the general ledger. When you post a quantity that is only received or shipped but not invoiced, then a value entry is created with the expected cost. This expected cost affects the inventory value, but is not posted to the general ledger unless you set up the system up to do so.  

> [!NOTE]  
>  Expected costs are only managed for item transactions. Expected costs are not for immaterial transaction types, such as capacity and item charges.  

 If only the quantity part of an inventory increase has been posted, then the inventory value in the general ledger does not change unless you have selected the **Expected Cost Posting to G/L** check box on the **Inventory Setup** page. In that case, the expected cost is posted to interim accounts at the time of receipt. After the receipt has been fully invoiced, the interim accounts are then balanced and the actual cost is posted to the inventory account.  

 To support reconciliation and traceability work, the invoiced value entry shows the expected cost amount that has been posted to balance the interim accounts.  

## Prerequisites for posting expected costs

To make it possible to post expected costs you need to do the following:
1. On the **Inventory Setup** page, select the **Automatic Cost Posting** check box and the **Expected Cost Posting to G/L** check box.
2. Set up which interim accounts to use during the expected cost posting process.  

  On the **Inventory Posting Setup** page, verify the **Inventory Account** and the **Inventory Account (Interim)** fields for the **Location Code and Invt. Posting Group Code** of the item you will be purchasing. To learn more about these accounts see [Design Details - Accounts in the General Ledger](design-details-accounts-in-the-general-ledger.md).
3. On the **General Posting Setup** page, verify the **Invt. Accrual Acc. (Interim)** field for the **Gen. Bus. Posting Group** and the **Gen. Prod. Posting Group** you will be using.
4. When you create a purchase order the default is that the **Vendor Invoice No.** field is required. You need to turn that off on the **Purchase & Payables Setup** page, by unselecting the **Ext. Doc. No. Mandatory** field.

## Example  

> [!NOTE]  
> The account numbers used in this example are there for reference only, and will be different in your system. Set them up as directed in the Prerequisites above.

You post a purchase order as received. The expected cost is LCY 95.00.  

 **Value Entries**  

|Posting Date|Entry Type|Cost Amount (Expected)|Expected Cost Posted to G/L|Expected Cost|Item Ledger Entry No.|Entry No.|  
|------------------|----------------|------------------------------|----------------------------------|-------------------|---------------------------|---------------|  
|01-01-20|Direct Cost|95.00|95.00|Yes|1|1|  

 **Relation Entries in the G/L – Item Ledger Relation Table**  

|G/L Entry No.|Value Entry No.|G/L Register No.|  
|--------------------|---------------------|-----------------------|  
|1|1|1|  
|2|1|1|  

 **General Ledger Entries**  

|Posting Date|G/L Account|Account No. (En-US Demo)|Amount|Entry No.|  
|------------------|------------------|---------------------------------|------------|---------------|  
|01-01-20|Inventory Accrual Account (Interim)|5530|-95.00|2|  
|01-01-20|Inventory Account (Interim)|2131|95.00|1|  

 At a later date, you post the purchase order as invoiced. The invoiced cost is LCY 100.00.  

 **Value Entries**  

|Posting Date|Cost Amount (Actual)|Cost Amount (Expected)|Cost Posted to G/L|Expected Cost|Item Ledger Entry No.|Entry No.|  
|------------------|----------------------------|------------------------------|-------------------------|-------------------|---------------------------|---------------|  
|01-15-20|100.00|-95.00|100.00|No|1|2|  

 **Relation Entries in the G/L – Item Ledger Relation Table**  

|G/L Entry No.|Value Entry No.|G/L Register No.|  
|--------------------|---------------------|-----------------------|  
|3|2|2|  
|4|2|2|  
|5|2|2|  
|6|2|2|  

 **General Ledger Entries**  

|Posting Date|G/L Account|Account No. (Examples only!)|Amount|Entry No.|  
|------------------|------------------|---------------------------------|------------|---------------|  
|01-15-20|Inventory Accrual Account (Interim)|5530|95.00|4|  
|01-15-20|Inventory Account (Interim)|2131|-95.00|3|  
|01-15-20|Direct Cost Applied Account|7291|-100|6|  
|01-15-20|Inventory Account|2130|100|5|  

## Related information
 [Design Details: Inventory Costing](design-details-inventory-costing.md)   
 [Design Details: Cost Adjustment](design-details-cost-adjustment.md)   
 [Design Details: Reconciliation with the General Ledger](design-details-reconciliation-with-the-general-ledger.md)   
 [Design Details: Inventory Posting](design-details-inventory-posting.md)   
 [Design Details: Variance](design-details-variance.md)  
 [Managing Inventory Costs](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
