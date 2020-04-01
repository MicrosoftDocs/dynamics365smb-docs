---
title: Design Details - Item Application | Microsoft Docs
description: This topic describes where inventory quantity and value are recorded when you post an inventory transaction.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, items, ledger entries, posting, inventory
ms.date: 04/01/2020
ms.author: sgroespe

---
# Design Details: Item Application
When you post an inventory transaction, the quantity posting is recorded in the item ledger entries, the value posting in the value entries. For more information, see [Design Details: Inventory Posting](design-details-inventory-posting.md).  

In addition, an item application is made to link the cost recipient to its cost source to provide cost forwarding according to the costing method. For more information, see [Design Details: Costing Methods](design-details-costing-methods.md).  

[!INCLUDE[d365fin](includes/d365fin_md.md)] makes two types of item application.  

|Application type|Description|  
|----------------------|---------------------------------------|  
|Quantity application|Created for all inventory transactions|  
|Cost application|Created for inbound entries together with a quantity application as a result of user interaction in special processes.|  

Item applications can be made in the following ways.  

|Method|Description|Application type|  
|------------|---------------------------------------|----------------------|  
|Automatic|Occurs as general cost forwarding according to the costing method|Quantity application|  
|Fixed|Made by the user when:<br /><br /> -   Processing returns<br />-   Posting corrections<br />-   Undoing quantity postings<br />-   Creating drop shipments **Note:**  The fixed application can be  made either manually by entering an entry number in the **Appl.-from Item Entry** field or by using a function, such as the **Get Posted Document Lines to Reverse**.|Quantity application<br /><br /> Cost application **Note:**  Cost application only occurs in inbound transactions where the **Appl.-from Item Entry** field is filled to create a fixed application. See the next table.|  

Whether quantity applications or cost applications are made depends on the direction of the inventory transaction and whether the item application is made automatically or fixed, in connection with special processes.  

The following table shows, based on the central application fields on inventory transaction lines, how costs flow depending on the transaction direction. It also indicates when and why the item application is of type quantity or cost.  

||Appl.-to Item Entry field|Appl.-from Item Entry field|  
|-|--------------------------------|----------------------------------|  
|Application for outbound entry|The outbound entry pulls the cost from the open inbound entry.<br /><br /> **Quantity application**|Not supported|  
|Application for inbound entry|The inbound entry pushes the cost onto the open outbound entry.<br /><br /> The inbound entry is the cost source.<br /><br /> **Quantity application**|The inbound entry pulls the cost from the outbound entry. **Note:**  When making this fixed application, the inbound transaction is treated as a sales return. Therefore, the applied outbound entry remains open. <br /><br /> The inbound entry is NOT the cost source.<br /><br /> **Cost application**|  

> [!IMPORTANT]  
>  A sales return is NOT considered a cost source when fixed applied.  
>   
>  The sales entry remains open until the real source is posted.  

An item application entry records the following information.  

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Item Ledger Entry No.**|The number of the item ledger entry for the transaction that this application entry is created for.|  
|**Inbound Item Entry No.**|The item ledger entry number of the inventory increase to which the transaction should be linked, if applicable.|  
|**Outbound Item Entry No.**|The item ledger entry number of the inventory decrease to which the transaction should be linked, if applicable.|  
|**Quantity**|The quantity being applied.|  
|**Posting Date**|The posting date of the transaction.|  

## Inventory Increase  
When you post an inventory increase, then a simple item application entry is recorded without an application to an outbound entry.  

### Example  
The following table shows the item application entry that is created when you post a purchase receipt of 10 units.  

|Posting Date|Inbound Item Entry No.|Outbound Item Entry No.|Quantity|Item Ledger Entry No.|  
|------------------|----------------------------------------------|-----------------------------------------------|--------------|---------------------------------------------|  
|01-01-20|1|0|10|1|  

## Inventory Decrease  
When you post an inventory decrease, an item application entry is created that links the inventory decrease to an inventory increase. This link is created by using the item’s costing method as a guideline. For items using FIFO, Standard, and Average costing methods, the linking is based on the first-in-first-out principle. The inventory decrease is applied to the inventory increase with the earliest posting date. For items using the LIFO costing method, the linking is based on the last-in-first-out principle. The inventory decrease is applied to the inventory increase with the most recent posting date.  

In the  **Item Ledger Entry** table, the **Remaining Quantity** field shows the quantity that has not yet been applied. If the remaining quantity is more than 0, then the **Open** check box is selected.  

### Example  
The following example shows the item application entry that is created when you post a sales shipment of 5 units of the items that were received in the previous example. The first item application entry is the purchase receipt. The second application entry is the sales shipment.  

The following table shows the two item application entries that result from the inventory increase and the inventory decrease, respectively.  

|Posting Date|Inbound Item Entry No.|Outbound Item Entry No.|Quantity|Item Ledger Entry No.|  
|------------------|----------------------------------------------|-----------------------------------------------|--------------|---------------------------------------------|  
|01-01-20|1|0|10|1|  
|01-03-20|1|2|-5|2|  

## Fixed Application  
You make a fixed application when you specify that the cost of an inventory increase should apply to a specific inventory decrease, or vice versa. The fixed application affects the remaining quantities of the entries, but the fixed application also reverses the exact cost of the original entry that you are applying to, or from.  

To make a fixed application, you use the **Appl.-to Item Entry** field or the **Appl.-from Item Entry** field in the document lines to specify the item ledger entry that you want the transaction line to apply to, or from. For example, you might make a fixed application when you want to create a cost application that specifies that a sales return should apply to a specific sales shipment to reverse the cost of the sales shipment. In this case, [!INCLUDE[d365fin](includes/d365fin_md.md)] ignores the costing method and applies the inventory decrease, or increase, for a sales return, to the item ledger entry that you specify. The advantage of making a fixed application is that the cost of the original transaction is passed to the new transaction.  

### Example – Fixed Application in Purchase Return  
The following example, which illustrates the effect of fixed application of a purchase return of an item using the FIFO costing method, is based on the following scenario:  

1. In entry 1, the user posts a purchase at a cost of LCY 10.00.  
2. In entry 2, the user posts a purchase at a cost of LCY 20.00.  
3. In entry 3, the user posts a purchase return. The user makes a fixed application to the second purchase by entering the item ledger entry number in the **Appl.-to Item Entry** field on the purchase return order line.  

The following table shows item ledger entries resulting from the scenario.  

|**Posting Date**|**Item Ledger Entry Type**|**Quantity**|**Cost Amount (Actual)**|**Item Ledger Entry No.**|  
|----------------------|---------------------------------------------------|------------------|----------------------------------------------------|---------------------------------------------------|  
|01-04-20|Purchase|10|10.00|1|  
|01-05-20|Purchase|10|20.00|2|  
|01-06-20|Purchase (Return)|-10|-20.00|3|  

Because a fixed application is made from the purchase return to the second purchase entry, the items are returned at the correct cost. If the user had not performed the fixed application, then the returned item would be incorrectly valued at LCY 10.00 because the return would have been applied to the first purchase entry according to the FIFO principle.  

The following table shows the item application entry that results from the fixed application.  

|Posting Date|Inbound Item Entry No.|Outbound Item Entry No.|Quantity|Item Ledger Entry No.|  
|------------------|----------------------------------------------|-----------------------------------------------|--------------|---------------------------------------------|  
|01-06-20|2|3|10|3|  

The cost of the second purchase, LCY 20.00, is passed correctly to the purchase return.  

### Example – Fixed Application with Average Cost  
The following example, which illustrates the effect of fixed application, is based on the following scenario for an item that uses the Average costing method:  

1. In entry numbers 1 and 2, the user posts two purchase invoices. The second invoice has the incorrect direct unit cost of LCY 1000.00.  
2. In entry number 3, the user posts a purchase credit memo, with a fixed application applied to the purchase entry with the wrong direct unit cost. The sum of the **Cost Amount (Actual)** field for the two fixed applied value entries becomes 0.00  
3. In entry number 4, the user posts another purchase invoice with the correct direct unit cost of LCY 100.00  
4. In entry number 5, the user posts a sales invoice.  
5. The inventory quantity is 0, and the inventory value is also 0.00  

The following table shows the result of the scenario on the item’s value entries.  

|Posting Date|Item Ledger Entry Type|Valued Quantity|Cost Amount (Actual)|Appl.-to Item Entry|Valued by Average Cost|Item Ledger Entry No.|Entry No.|  
|-------------------------------------|-----------------------------------------------|-----------------------------------------|------------------------------------------------|--------------------------------------------|-------------------------------------------------|-----------------------------------------------|----------------------------------|  
|01-01-20|Purchase|1|200.00||No|1|1|  
|01-01-20|Purchase|1|1000.00||No|2|2|  
|01-01-20|Purchase|-1|-1000|2|No|3|3|  
|01-01-20|Purchase|1|100.00||No|4|4|  
|01-01-20|Sale|-2|-300.00||Yes|5|5|  

If the user had not made the fixed application between the purchase credit memo and the purchase with the incorrect direct unit cost (step 2 in the previous scenario), then the cost would have been adjusted differently.  

The following table shows the result on the item’s value entries if step 2 in the previous scenario is performed without a fixed application.  

|Posting Date|Item Ledger Entry Type|Valued Quantity|Cost Amount (Actual)|Appl.-to Item Entry|Valued by Average Cost|Item Ledger Entry No.|Entry No.|  
|-------------------------------------|-----------------------------------------------|-----------------------------------------|------------------------------------------------|--------------------------------------------|-------------------------------------------------|-----------------------------------------------|----------------------------------|  
|01-01-20|Purchase|1|200.00||No|1|1|  
|01-01-20|Purchase|1|1000.00||No|2|2|  
|01-01-20|Purchase|-1|433,33||Yes|3|3|  
|01-01-20|Purchase|1|100.00||No|4|4|  
|01-01-20|Sale|-2|866,67||Yes|5|5|  

In entry number 3, the value in the **Cost Amount (Actual)** field is valued by average and therefore includes the erroneous posting of 1000.00. Accordingly, it becomes -433,33, which is an inflated cost amount. The calculation is 1300 / 3 = .-433,33.  

In entry number 5, the value of the **Cost Amount (Actual)** field for this entry is also inaccurate for the same reason.  

> [!NOTE]  
>  If you create a fixed application for an inventory decrease for an item that uses the Average costing method, then the decrease will not receive the average cost for the item as usual, but will instead receive the cost of the inventory increase that you specified. That inventory decrease is then no longer part of the average cost calculation.  

### Example – Fixed Application in Sales Return  
Fixed applications are also a very good means of reversing cost exactly, such as with sales returns.  

The following example, which illustrates how a fixed application ensures exact cost reversal, is based on the following scenario:  

1.  The user posts a purchase invoice.  
2.  The user posts a sales invoice.  
3.  The user posts a sales credit memo for the returned item, which applies to the sales entry, to reverse the cost correctly.  
4.  A freight cost, related to the purchase order that was posted earlier, arrives. The user posts it as an item charge.  

The following table shows the result of scenario steps 1 through 3 on the item’s value entries.  

|Posting Date|Item Ledger Entry Type|Valued Quantity|Cost Amount (Actual)|Appl.-from Item Entry|Item Ledger Entry No.|Entry No.|  
|-------------------------------------|-----------------------------------------------|-----------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------------|----------------------------------|  
|01-01-20|Purchase|1|1000.00||1|1|  
|02-01-20|Sale|-1|1000.00||2|2|  
|03-01-20|Sale (Credit Memo)|1|1000|2|3|3|  

The following table shows the value entry resulting from scenario step 4, posting the item charge.  

|Posting Date|Item Ledger Entry Type|Valued Quantity|Cost Amount (Actual)|Appl.-from Item Entry|Item Ledger Entry No.|Entry No.|  
|-------------------------------------|-----------------------------------------------|-----------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------------|----------------------------------|  
|04-01-20|(Item Charge)|1|100.00||1|4|  

The following table shows the effect of the exact cost reversal on the item’s value entries.  

|Posting Date|Item Ledger Entry Type|Valued Quantity|Cost Amount (Actual)|Appl.-from Item Entry|Item Ledger Entry No.|Entry No.|  
|-------------------------------------|-----------------------------------------------|-----------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------------|----------------------------------|  
|01-01-20|Purchase|1|1000.00||1|1|  
|02-01-20|Sale|-1|1100.00||2|2|  
|03-01-20|Sale (Credit Memo)|1|1100.00|2|3|3|  
|04-01-20|(Item Charge)|1|100.00||1|4|  

When you run the **Adjust Cost - Item Entries** batch job, the increased cost of the purchase entry, due to the item charge, is forwarded to the sales entry (entry number 2). The sales entry then forwards this increased cost to the sales credit entry (entry number 3). The final result is that the cost is correctly reversed.  

> [!NOTE]  
>  If you are working with returns or credit memos and you have set up the **Exact Cost Reversing Mandatory** field in either the **Purchases & Payables Setup** page or the **Sales & Receivables Setup** page, as appropriate for your situation, then [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically fills the various application entry fields when you use the **Copy from Document** function. If you use the **Get Posted Document Lines to Reverse** function, then the fields are always filled automatically.  

> [!NOTE]  
>  If you post a transaction with a fixed application, and the item ledger entry that you are applying to is closed, meaning that the remaining quantity is zero, then the old application is automatically undone and reapplies the item ledger entry using the fixed application that you specified.  

## Transfer Application  
When an item is transferred from one location to another, inside the company inventory, then an application is created between the two transfer entries. Valuing a transfer entry depends on the costing method. For items using the Average costing method, valuation is made using the average cost in the average cost period in which the valuation date of the transfer occurs. For items using other costing methods, valuation is made by tracing back to the cost of the original inventory increase.  

### Example – Average Costing Method  
The following example, which illustrates how transfer entries are applied, is based on the following scenario for an item using Average costing method and an average cost period of Day.  

1. The user purchases the item at a cost of LCY 10.00.  
2. The user purchases the item again at a cost of LCY 20.00.  
3. The user transfers the item from BLUE to RED location.  

The following table shows the effect of the transfer on the item’s value entries.  

|Posting Date|Item Ledger Entry Type|Location Code|Valued Quantity|Cost Amount (Actual)|Entry No.|  
|-------------------------------------|-----------------------------------------------|--------------------------------------|-----------------------------------------|------------------------------------------------|----------------------------------|  
|01-01-20|Purchase|BLUE|1|10.00|1|  
|01-01-20|Purchase|BLUE|1|20.00|2|  
|02-01-20|Transfer|BLUE|-1|15.00|3|  
|02-01-20|Transfer|RED|1|15.00|4|  

### Example – Standard Costing Method  
The following example, which illustrates how transfer entries are applied, is based on the following scenario for an item using Standard costing method and an average cost period of Day.  

1. The user purchases the item at a standard cost of LCY 10.00.  
2. The user transfers the item from BLUE to RED location at a standard cost of LCY 12.00.  

The following table shows the effect of the transfer on the item’s value entries.  

|Posting Date|Item Ledger Entry Type|Location Code|Valued Quantity|Cost Amount (Actual)|Entry No.|  
|-------------------------------------|-----------------------------------------------|--------------------------------------|-----------------------------------------|------------------------------------------------|----------------------------------|  
|01-01-20|Purchase|BLUE|1|10.00|1|  
|02-01-20|Transfer|BLUE|-1|10.00|2|  
|02-01-20|Transfer|RED|1|10.00|3|  

Since the value of the original inventory increase is LCY 10.00, the transfer is valued at that cost, not at LCY 12.00.  

## Reapplication  
Because of the way an item’s unit cost is calculated, an incorrect item application could lead to a skewed average cost and unit cost. The following scenarios may cause incorrect item applications, which require that you undo item applications and reapply item ledger entries:  

* You have forgotten to make a fixed application.  
* You have made an incorrect fixed application.  
* You want to overrule the application created automatically when posting, according to the item’s costing method.  
* You have to return an item to which a sale has already been manually applied, without using the **Get Posted Document Lines to Reverse** function, and you must therefore undo the application.  

[!INCLUDE[d365fin](includes/d365fin_md.md)] offers a feature for analyzing and correcting item applications. This work is performed on the **Application Worksheet** page.  

## See Also  
[Design Details: Known Item Application Issue](design-details-inventory-zero-level-open-item-ledger-entries.md)  
[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Design Details: Costing Methods](design-details-costing-methods.md)  
[Design Details: Average Cost](design-details-average-cost.md)   
[Design Details: Cost Adjustment](design-details-cost-adjustment.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
