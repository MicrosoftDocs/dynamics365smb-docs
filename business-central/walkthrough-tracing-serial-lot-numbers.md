---
    title: Walkthrough - Tracing Serial-Lot Numbers | Microsoft Docs
    description: When product defects occur, the errors must be identified and affected items must be prevented from leaving the company. If defective items have already been shipped, you must trace who received them and, if you need to, recall the items.
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
# Walkthrough: Tracing Serial/Lot Numbers

**Note**: This walkthrough must be performed on a demonstration company with the **Full Evaluation - Complete Sample Data** option, which is available in the Sandbox environment. For more information, see [Creating a Sandbox Environment](across-how-create-sandbox-environment.md).

When product defects occur, the errors must be identified and affected items must be prevented from leaving the company. If defective items have already been shipped, you must trace who received them and, if you need to, recall the items.  

The first task of defects management is to investigate where the defective items came from and where they were used. This investigation is based on historic data and is made easier by searching through item tracking entries using the **Item Tracing** page.  

The second task of defects management is to determine whether the traced items are planned for in open documents, such as non-posted sales orders or consumption journals. This work is performed on the **Navigate** page. You can use the Navigate feature to search all kinds of database records.  

## About This Walkthrough  
This walkthrough demonstrates how to identify which items are defective, which vendor supplied them, and where they are used so that those orders can be stopped or recalled.  

This walkthrough illustrates the following tasks:  

-   Tracing usage to origin.  
-   Tracing origin to usage.  
-   Searching for all current records which hold the traced serial/lot number.  

## Roles  
This walkthrough demonstrates tasks that are performed by the following user roles:  

-   Quality Controller  
-   Warehouse Manager  
-   Order Processor  
-   Purchasing Agent  

## Prerequisites  
To complete this walkthrough, you will need:  

-   The [!INCLUDE[d365fin](includes/d365fin_md.md)] company.  
-   To create new items and several business transactions by following the [Prepare Sample Data](walkthrough-tracing-serial-lot-numbers.md#prepare-sample-data)..  

## Story  
Ricardo, the quality controller, is acting on a sales return of item 1002, Racing Bike. The customer, Selangorian Ltd., complained that the frame has cracked welding seams. Quality control engineers have confirmed that the racing frame of the returned bike is defective. The quality controller must now determine:  

-   Which lot of racing frames was faulty.  
-   On which purchase order the faulty lot was received.  

From the sales department, the quality controller knows that the returned racing bike, item 1002, had the serial number SN1. By using this basic information, he must determine where the finished racing bike was last used, and then he must trace backward to the earliest origin to establish which lot number the faulty component, the racing frame, came from.  

The results of this first item tracking task identify which racing frames were defective and which vendor supplied them. Afterward, but in the same overall tracking process, the quality controller must find all the sold racing bikes that contain racing frames from the faulty lot so that those orders can be stopped or recalled. Lastly, the quality controller must find any open documents where the faulty lot is used so that no additional transactions are made.  

The first two defects-management tasks are performed on the **Item Tracing** page. The last task is performed on the **Navigate** page in integration with the **Item Tracing** page.  

## Prepare Sample Data  
You must create the following new items:  

-   2000, Racing Frame: lot-specific tracking, component of 1002  
-   1002, Racing Bike: serial number-specific tracking  

Then you must create various purchase, production, and sales transactions with the two items.  

### To create the items  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2.  Choose the **New** action.  
3.  In the **No.** field, enter **2000**, and then proceed to fill in the following fields.  

    |Description|Base Unit of Measure|Gen. Prod. Posting Group|VAT Prod. Posting Group|Inventory Posting Group|Item Tracking Code|  
    |-----------------|--------------------------|------------------------------|-----------------------------|-----------------------------|------------------------|  
    |Racing Frame|PCS|RAW MAT|VAT25|RAW MAT|LOTALL|  

    > [!NOTE]  
    >  To enter the base unit of measure, choose the **New** button, and then select **PSC** on the **Item Units of Measure** page.  

4.  All other fields have acceptable default data or do not have to be filled in.  
5.  Choose the **OK** button to create the first new item card, 2000.  
6.  Choose **New**.  
7.  In the **No.** field, enter **1002**, and then proceed to fill in the following fields.  

    |Description|Base Unit of Measure|Gen. Prod. Posting Group|VAT Prod. Posting Group|Inventory Posting Group|Replenishment System|Item Tracking Code|  
    |-----------------|--------------------------|------------------------------|-----------------------------|-----------------------------|--------------------------|------------------------|  
    |Racing Bike|PCS|RETAIL|VAT25|FINISHED|Prod. Order|SNALL|  

    > [!NOTE]  
    >  To enter the base unit of measure, choose the **New** button, and then select **PSC** on the **Item Units of Measure** page.  

    Next, define the item's manufacturing setup.

9. On the **Replenishment** FastTab, in the **Routing No.** field, enter **1000**.  
10. Choose the **Production BOM No.** field, and then choose **Advanced**.  
11. On the **Production BOM List** page, choose the first line, **1000**, and then choose the **Edit** action.  
12. On the **Production BOM** page, change the value in the **Status** field to **Under Development**.  
13. Go to an empty line, enter **2000** in the **No.** field, and then enter **1** in the **Quantity Per** field.  
14. Change the value in the **Status** field back to **Certified**.  
15. Choose the **OK** button to insert the production BOM on the item card and close the **Production BOM** page.  

    Next, purchase racing frames from Custom Metals Incorporated.  

### To purchase components  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
2.  Choose the **New** action.  
3.  Create a purchase order for vendor, Custom Metals Incorporated, by filling in the following line fields.  

    |Item|Quantity|Lot No.|  
    |----------|--------------|-------------|  
    |2000|10|LOT1|  

4.  To enter the lot number, choose the **Item Tracking Lines** action.  
5.  On the **Item Tracking Lines** page, fill in the **Lot No.** and **Quantity (Base)** fields, and then close the page.  
6.  In the **Vendor Invoice No.** field, enter any value.  
7.  Choose the **Post** action, select the **Receive and Invoice** option, and then choose the **OK** button.  

    Next, purchase racing frames from Coolwood Technologies.  
8.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
9. Choose the **New** action.
10. Create a purchase order for vendor, Coolwood Technologies, by filling in the following line fields.  

    |Item|Quantity|Lot No.|  
    |----------|--------------|-------------|  
    |2000|11|LOT2|  

11. To enter the lot number, on the **Lines** FastTab, in the **Line** group, choose the **Item Tracking Lines** action.  
12. On the **Item Tracking Lines** page, fill in the **Lot No.** and **Quantity (Base)** fields, and then close the page.  
13. In the **Vendor Invoice No.** field, enter any value.  
14. Choose the **Post** action, select the **Receive and Invoice** option, and then choose the **OK** button.  

    Next, produce two racing bikes, SN1 and SN2.  

### To produce end items  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Prod. Orders**, and then choose the related link.  
2.  Choose the **New** group.  
3.  Create a new released production order by filling in the following fields.  

    |-|-|-|  
    |Source No.|Quantity|Serial No.|  
    |1002|2|SN1|  
    |1002|2|SN2|  

4.  Choose the **Refresh Production Order** action, and then choose the **OK** button to fill the line.  
5.  To enter the serial numbers, choose the **Item Tracking Lines** action.  
6.  On the **Item Tracking Lines** page, fill in the **Serial No.** and **Quantity (Base)** fields, and then close the page.  

    Next, post consumption of racing frames from LOT1.  
7.  On the **Released Production Order** page, choose the **Production Journal** action.  
8.  On the **Production Journal** page, select the consumption line for item 2000, choose the **Item Tracking Lines** action.
9. On the **Item Tracking Lines** page, choose the **Lot No.** field, choose **LOT1**, and then choose the **OK** button.  
10. Leave all other defaults on the **Production Journal** page, and then choose the **Post** action.  

    Next, produce two more racing bikes, SN3 and SN4.  

11. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Prod. Orders**, and then choose the related link.  
12. Choose the **New** action.  
13. Create a new released production order by filling in the following fields on the header.  

    |Source No.|Quantity|Serial No.|  
    |----------------|--------------|----------------|  
    |1002|2|SN3|  
    |1002|2|SN4|  

14. Choose the **Refresh Production Order** action to fill the line.  
15. To enter the serial numbers, choose the **Item Tracking Lines** action, and then the numbers on two lines in the **Serial No.** field on the **Item Tracking Lines** page.  

    Next, post more consumption of racing frames from LOT1.  
16. On the **Released Production Order** page, choose the **Production Journal** action.  
17. On the **Production Journal** page, select the consumption line for item 2000, choose the **Item Tracking Lines** action.
18. On the **Item Tracking Lines** page, choose the **Lot No.** field, choose **LOT1**, and then choose the **OK** button.  
19. Leave all other defaults on the **Production Journal** page, and then choose the **Post** action.  

    You have produced four racing bikes, SN1 to SN4, and consumed four of the ten racing frames from LOT1, two frames in each production order.  

20. Close the production journal and the production orders.  

    Next, sell racing bikes. First sell the racing bike with SN1 to Selangorian Ltd..  

### To sell the end items  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2.  Choose the **New** action, and then, create a sales order by filling in the following fields.  

    |Customer|Item|Qty.|Serial No.|  
    |--------------|----------|----------|----------------|  
    |Selangorian Ltd.|1002|1|SN1|  

3.  To enter the serial number, choose the **Item Tracking Lines** action, and then the number in the **Serial No.** field on the **Item Tracking Lines** page.  
4.  Choose the **Post** action, select the **Ship and Invoice** option, and then choose the **OK** button.  

    Next, sell the racing bike with SN2 to The Cannon Group PLC.  

5.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
6.  Choose the **New** action, and then, create a sales order by filling in the following fields.  

    |Customer|Item|Qty.|Serial No.|  
    |--------------|----------|----------|----------------|  
    |Cannon Group PLC.|1002|1|SN2|  

7.  To enter the serial number, choose the **Item Tracking Lines** action, and then the number in the **Serial No.** field on the **Item Tracking Lines** page.  
8.  Choose the **Post** action, select the **Ship and Invoice** option, and then choose the **OK** button.  

    Finally, sell some racing frames separately. The Cannon Group PLC. also orders four separate racing frames for their own assembly line.  

9. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
10. Choose the **New** action, and then, create a sales order by filling in the following fields.  

    |Customer|Item|Qty.|Serial No.|  
    |--------------|----------|----------|----------------|  
    |Cannon Group PLC.|2000|5|LOT1|  

11. To enter the serial number, on the **Lines** FastTab, in the **Line** group, choose the **Item Tracking Lines** action, and then the number in the **Serial No.** field on the **Item Tracking Lines** page.  

    > [!NOTE]  
    >  Do not post the last sales order for five racing frames.  

    This completes the preparation of data to demonstrate the Item Tracing and Navigate features.  

## Tracing from Usage to Origin  
 From the sales department, the quality controller knows that the returned racing bike, item 1002, has the serial number SN1. By using this basic information, he can determine where the finished racing bike was last used, in this case, on the sales shipment to Selangorian Ltd.. Then, the quality controller must trace backward to the earliest origin to establish which lot number the faulty racing frame came from and which vendor supplied it.  

### To determine which lot included the faulty frame and who supplied it  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Tracing**, and then choose the related link.  
2.  On the **Item Tracing** page, enter **SN1** in the **Serial No. Filter** field, and then enter **1002** in the **Item Filter** field.  
3.  Keep the default setting of **Item-Tracked Only** in the **Show Components** field, and keep the default trace method of **Usage – Origin** in the **Trace Method**.  
4.  Choose the **Trace** action.  

    Note that one sales shipment header matches the search criteria. Before you continue the trace, verify that the shipment is the one that shipped the faulty racing bike to Selangorian Ltd.  

5.  Select the trace line, and then choose the **Show Document** action.  

    Now continue to trace the origin of the sales shipment of the racing bike with number SN1.  
6.  Choose the + icon on the trace lines to gradually expand and trace backward in the chain of transactions that the sales shipment originates from.  

    You can trace the following transaction history:  

    -   The first posted document backward in the chain of transactions is the output posting of SN1 from the first released production order.  
    -   The next posted document backward after that is the consumption posting from the first released production order. Here the quality controller sees that a racing frame from LOT1 was used.  
    -   The lowest posted document in this chain is the posted purchase receipt on which racing frames with LOT1 entered inventory.  

    The quality controller has now established which lot of racing frames was faulty and he can search for the last trace line to see which vendor supplied them, namely Custom Metals Incorporated.  

    > [!NOTE]  
    >  Do not make any additional modifications to the trace result, as you will use it in the next section.  

     This completes the first defects-management task using the **Item Tracing** page. The quality controller must now determine whether other posted documents have processed racing frames from LOT1.  

## Tracing from Origin to Usage  
 The quality controller has established that the faulty racing frames came from LOT1. He must now find any other racing bikes that contain racing frames from the faulty lot so that those bikes can be stopped or recalled.  

 One way to prepare this trace task on the **Item Tracing** page is to manually enter LOT1 in the **Lot No. Filter** field and 2000 in the **Item Filter** field. However, this walkthrough will use the **Trace Opposite - from Line** function.  

### To find all usage of the faulty lot  

1.  On the **Item Tracing** page, select the line of the purchase receipt, the last trace line, and then choose **Trace Opposite – from Line**.  

    The trace result is now based on the filters of the trace line for the purchase receipt, LOT1 and item 2000, and the result is based on trace method **Origin - Usage**.  

    To obtain an overview of all usage of item 2000 with LOT1, continue to expand all trace lines.  

2.  Choose the **Expand All** action.  

    The first four trace lines refer to the sales shipment to Selangorian Ltd., which is already resolved. The last line indicates that one more racing bike, SN2, was produced in the same released production order and then sold and shipped on another sales shipment.  

    The quality controller immediately informs the sales department so that they can initiate a recall of the defective racing bike from the customer, Cannon Group PLC.  

    At the same time, he can see from the last three trace lines that another two items, SN3 and SN4, have been produced based on racing frames from LOT1. He takes action to block these end items in inventory.  

    This completes the second defects management task using the **Item Tracing** page for defects management. Since the **Item Tracing** page is based on posted entries only, the quality controller must continue to the **Navigate** page to make sure that LOT1 is not used in non-posted documents.  

## Finding All Records of a Serial/Lot Number  
 With the **Item Tracing** page, the quality controller learned that LOT1 contained the faulty racing frames, which vendor supplied them, and in which posted transaction they have been used. He must now determine whether LOT1 is in any open documents by integrating from the trace result to the **Navigate** page where he can perform a search through all database records.  

### To find all occurrences of LOT1 in non-posted records, such as open orders  

1.  On the **Item Tracing** page, select the first trace line, the purchase receipt of LOT1.  
2.  Choose the **Navigate** action.  

    The **Navigate** page is preset with search filters based on the trace result for LOT1. The quality controller recognizes most of the records as pertaining to documents already identified on the **Item Tracing** page. For example, the last Navigate line of type Production Order refers to the two released production orders that consumed racing frames from LOT1.  

    However, the second Navigate line of type **Sales Line** is a non-posted document line, so the quality controller proceeds to investigate.  

3.  To open the sales line record, select the second Navigate line, choose the **Show** action. Alternatively, choose the value in the **No. of Records** field.  

    Here the quality controller sees one open sales line for the faulty racing frames. He immediately suggests to the sales department that this order be canceled and a new production order, based on good racing frames, be initiated.  

 This completes the walkthrough of how to use the **Navigate** page for defects management in integration with the **Item Tracing** page.  

## See Also
[Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md)  
[Trace Item-Tracked Items](inventory-how-to-trace-item-tracked-items.md)  
[Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)  
