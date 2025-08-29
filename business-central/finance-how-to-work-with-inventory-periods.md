---
title: Work with inventory periods
description: You can control the timeframe in which people can post post changes to inventory by defining inventory periods.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: inventory, periods
ms.search.form: 5828
ms.date: 07/29/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Work with inventory periods

Inventory periods define a period of time in which you can post changes to inventory. An inventory period is defined by the date on which it ends, or the ending date. When you close an inventory period, you can't post any changes to inventory, either expected or invoiced, before this ending date. You can't post any new values to inventory before the ending date. If you have open item entries in the closed period, meaning positive quantities that haven't yet been applied to outbound transactions, you can still apply outbound quantities to these entries, even if the period is closed.  

The following sections describe how to:

* Create inventory periods.  
* Close inventory periods.  
* Reopen inventory periods.  

## To create an inventory period

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Inventory Periods**, and then choose the related link.  
2. Create a new line.  
3. In the **Ending Date** field, enter the last date in the inventory period that you want to define. When the period is closed, you won't be able to post inventory changes before this date.  
4. Enter a descriptive name in the **Name** field. Choose the **OK** button.  

## To close inventory periods

The **Closed** field indicates whether or not the inventory period is closed to inventory value changes. You can't edit this field.  

You can close any inventory period, if the following is true:  

* There are no open outbound item ledger entries, meaning negative inventory, in that period.  
* The cost of all items has been adjusted using the **Adjust Cost – Item Entries** batch job.  

This means that all outbound transaction quantities, such as those from sales orders, outbound transfers, sales invoices, purchase returns, or purchase credit memos, must be applied to existing quantity in inventory.  

### To close an inventory period  

1. Before closing an inventory period, choose the **Adjust Cost – Item Entries** action to ensure that all cost adjustments are posted.

    Run the **Close Inventory Period – Test** report to determine if there are any open outbound item entries within the inventory period or any items whose cost hasn't yet been adjusted.  
2. Choose the **Test Report** action.  

    Run the **Post Inventory Cost to G/L** batch job to ensure that all costs are posted to the general ledger.  
3. Choose the **Post Inventory to G/L** action.  
4. On the **Inventory Periods** page, select the inventory period you want to close.  
5. Choose the **Close Period** action. After the inventory period has been closed, you can't post inventory changes before the ending date. The cost of all items must be adjusted with the **Adjust Cost – Item Entries** batch job before you close the inventory period.  
6. Choose the **Yes** button to confirm that you want to close the period, or choose **No** to cancel the closing.  
7. The inventory period is closed and a confirmation message is displayed when it's finished.  

## Reopening inventory periods  
After you have closed the inventory period, you can't delete the inventory period. You can, however, reopen it, if you would like to allow posting before the ending date of the inventory period. Reopening a period also reopens all inventory periods with ending dates later than the period you reopen.  

### To reopen an inventory period  
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Inventory Periods**, and then choose the related link.  
2. Select the inventory period you want to reopen.  
3. Choose the **Reopen Period** period action. Confirm that you want to reopen the period.  
4. All inventory periods with ending dates later than the period you selected are reopened.  

## Related information  
[Design Details: Inventory Periods](design-details-inventory-periods.md)    
[Finance](finance.md)    
[Inventory](inventory-manage-inventory.md)    
[Work with Financials](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
