---
title: 'Walkthrough: Trace Serial and Lot Numbers'
description: This topic describes the actions that are needed to take to prevent selling a defective item, and also how to trace and recall items when needed.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.date: 11/10/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Walkthrough: Trace serial and lot numbers

<!-- [!INCLUDE[complete_sample_data](includes/complete_sample_data.md)]   -->

When product defects occur, the errors must be identified and affected items must be prevented from leaving the company. If defective items have already been shipped, you must trace who received them and, if you need to, recall the items.  

The first task of defects management is to investigate where the defective items came from and where they were used. This investigation is based on historic data and is made easier by searching through item tracking entries using the **Item Tracing** page.  

The second task of defects management is to determine whether the traced items are planned for in open documents, such as non-posted sales orders or consumption journals. Perform this work on the **Find entries** page. Use Find Entries to search related posted entries and open records for a serial or lot number.

## About this walkthrough

This walkthrough demonstrates how to identify which items are defective, which vendor supplied them, and where they are used so that those orders can be stopped or recalled.  

This walkthrough illustrates the following tasks:  

- Tracing usage to origin.  
- Tracing origin to usage.  
- Searching for all current records which hold the traced serial/lot number.  

## Roles in this walkthrough

This walkthrough demonstrates tasks that are performed by the following user roles:  

- Quality Controller  
- Warehouse Manager  
- Order Processor  
- Purchasing Agent  

## Prerequisites for the sample transactions

To complete this walkthrough, you will need:  

- A test company with manufacturing available. Don't use a production company for this walkthrough.
- The sample vendors Custom Metals Incorporated and Coolwood Technologies, and the sample customers Selangorian Ltd. and Cannon Group PLC.
- The units of measure, posting groups, and item tracking codes shown in the item tables. **LOTALL** must require lot-specific tracking, and **SNALL** must require serial-specific tracking.
- Routing **1000** and production BOM **1000**, with enough inventory for any other components in the BOM.
- Unused item numbers **2000** and **1002**, and unused tracking numbers **LOT1**, **LOT2**, and **SN1** through **SN4**.

> [!NOTE]
> Sample data varies by company and localization. Set up any missing records and valid posting combinations before you continue. Substitute equivalent records where needed and use them consistently throughout the walkthrough.
<!-- - To create new items and several business transactions by following the [Prepare Sample Data](walkthrough-tracing-serial-lot-numbers.md#prepare-sample-data).   -->

## Scenario for tracing a defective frame

Ricardo, the quality controller, is acting on a sales return of item 1002, Racing Bike. The customer, Selangorian Ltd., complained that the frame has cracked welding seams. Quality control engineers have confirmed that the racing frame of the returned bike is defective. The quality controller must now determine:  

- Which lot of racing frames was faulty.  
- On which purchase order the faulty lot was received.  

From the sales department, the quality controller knows that the returned racing bike, item 1002, had the serial number SN1. By using this basic information, they must determine where the finished racing bike was last used, and then they must trace backward to the earliest origin to establish which lot number the faulty component, the racing frame, came from.  

The results of this first item tracking task identify which racing frames were defective and which vendor supplied them. Afterward, but in the same overall tracking process, the quality controller must find all the sold racing bikes that contain racing frames from the faulty lot so that those orders can be stopped or recalled. Lastly, the quality controller must find any open documents where the faulty lot is used so that no additional transactions are made.  

The first two defects-management tasks are performed on the **Item Tracing** page. The last task is performed on the **Find entries** page in integration with the **Item Tracing** page.  

## Prepare sample data

You must create the following new items:  

- 2000, Racing Frame: lot-specific tracking, component of 1002  
- 1002, Racing Bike: serial number-specific tracking  

Then you must create various purchase, production, and sales transactions with the two items.  

### To create the items  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, and then choose the related link.  
1. Choose the **New** action.
1. In the **No.** field, enter `2000`, and then fill in the following fields.

    |Description|Base Unit of Measure|Gen. Prod. Posting Group|VAT Prod. Posting Group|Inventory Posting Group|Item Tracking Code|  
    |-----------|--------------------|------------------------|-----------------------|--------------------|------------------|  
    |Racing Frame|PCS|RAW MAT|VAT25|RAW MAT|LOTALL|  

    > [!NOTE]  
    >  To enter the base unit of measure, choose **New**, and then select **PCS** on the **Item Units of Measure** page.

1. All other fields have acceptable default data or don't need to be filled in.
1. Choose **OK** to create the first new item card, `2000`.
1. Select **New**.
1. In the **No.** field, enter `1002`, and then fill in the following fields.

    |Description|Base Unit of Measure|Gen. Prod. Posting Group|VAT Prod. Posting Group|Inventory Posting Group|Replenishment System|Item Tracking Code|  
    |-----------------|--------------------------|------------------------------|-----------------------------|-----------------------------|--------------------------|------------------------|  
    |Racing Bike|PCS|RETAIL|VAT25|FINISHED|Prod. Order|SNALL|  

    > [!NOTE]  
    >  To enter the base unit of measure, choose **New**, and then select **PCS** on the **Item Units of Measure** page.

### Define the racing bike manufacturing setup

1. Keep the item card for item **1002** open.

1. On the **Replenishment** FastTab, in the **Routing No.** field, enter **1000**.
1. Choose the **Production BOM No.** field, and then choose **Advanced**.
1. On the **Production BOM List** page, choose the first line, **1000**, and then choose the **Edit** action.
1. On the **Production BOM** page, change the value in the **Status** field to **Under Development**.
1. Go to an empty line, enter **2000** in the **No.** field, and then enter **1** in the **Quantity Per** field.
1. Change the value in the **Status** field back to **Certified**.
1. Choose the **OK** button to insert the production BOM on the item card and close the **Production BOM** page.

    Next, purchase racing frames from Custom Metals Incorporated.  

### To purchase components

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Orders**, and then choose the related link.  
1. Choose the **New** action.
1. Create a purchase order for vendor, Custom Metals Incorporated, by filling in the following line fields.

    |Item|Quantity|Lot No.|  
    |----|--------|-------|  
    |2000|10|LOT1|  

1. To enter the lot number, choose the **Item Tracking Lines** action.
1. On the **Item Tracking Lines** page, fill in the **Lot No.** and **Quantity (Base)** fields, and then close the page.
1. In the **Vendor Invoice No.** field, enter any value.
1. Select the **Post** action, select the **Receive and Invoice** option, and then choose the **OK** button.

### Purchase a second lot of components

Purchase racing frames from Coolwood Technologies.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Orders**, and then choose the related link.
1. Choose the **New** action.
1. Create a purchase order for vendor Coolwood Technologies by filling in the following line fields.

    |Item|Quantity|Lot No.|  
    |----------|--------------|-------------|  
    |2000|11|LOT2|  

1. To enter the lot number, on the **Lines** FastTab, in the **Line** group, select the **Item Tracking Lines** action.
1. On the **Item Tracking Lines** page, fill in the **Lot No.** and **Quantity (Base)** fields, and then close the page.
1. In the **Vendor Invoice No.** field, enter any value.
1. Select the **Post** action, select the **Receive and Invoice** option, and then choose the **OK** button.

    Next, produce two racing bikes, SN1 and SN2.  

### To produce end items

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Released Prod. Orders**, and then choose the related link.  
1. Choose the **New** action.
1. Create a new released production order by filling in the following fields.

    |Source No.|Quantity|
    |----------|--------|
    |1002|2|

1. Select **Refresh Production Order**, and then select **OK** to fill the line.
1. To enter the serial numbers, select **Item Tracking Lines**.
1. On **Item Tracking Lines**, enter two lines, and then close the page.

    |Serial No.|Quantity (Base)|
    |----------|---------------|
    |SN1|1|
    |SN2|1|

    Next, post consumption of racing frames from LOT1.  
1. On **Released Production Order**, select **Production Journal**.
1. On **Production Journal**, select the consumption line for item 2000, and then select **Item Tracking Lines**.
1. On **Item Tracking Lines**, enter **LOT1** in **Lot No.** and **2** in **Quantity (Base)**, and then close the page.
1. Keep all other default values on **Production Journal**, and then select **Post**.

### Produce the second pair of racing bikes

Produce two more racing bikes, SN3 and SN4.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Released Prod. Orders**, and then select the related link.
1. Choose the **New** action.
1. Create a new released production order by filling in the following fields on the header.

    |Source No.|Quantity|
    |----------|--------|
    |1002|2|

1. Select **Refresh Production Order** to fill the line.
1. Select **Item Tracking Lines**, enter the following two lines, and then close the page.

    |Serial No.|Quantity (Base)|
    |----------|---------------|
    |SN3|1|
    |SN4|1|

    Next, post more consumption of racing frames from LOT1.  
1. On **Released Production Order**, select **Production Journal**.
1. On **Production Journal**, select the consumption line for item 2000, and then select **Item Tracking Lines**.
1. On **Item Tracking Lines**, enter **LOT1** in **Lot No.** and **2** in **Quantity (Base)**, and then close the page.
1. Leave all other defaults on **Production Journal**, and then select **Post**.

    You have produced four racing bikes, SN1 to SN4, and consumed four of the ten racing frames from LOT1, two frames in each production order.  

1. Close **Production Journal** and the production orders.

    Next, sell racing bikes. First sell the racing bike with SN1 to Selangorian Ltd..  

### To sell the end items

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, and then choose the related link.  
1.  Choose **New**, and then create a sales order by filling in the following fields.

    |Customer|Item|Qty.|Serial No.|  
    |--------------|----------|----------|----------------|  
    |Selangorian Ltd.|1002|1|SN1|  

1. Choose **Item Tracking Lines**. Enter the serial number in **Serial No.** and **1** in **Quantity (Base)**, and then close the page.
1.  Choose **Post**, select the **Ship and Invoice** option, and then choose **OK**.

    Next, sell the racing bike with SN2 to The Cannon Group PLC.  

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, and then choose the related link.
1.  Choose **New**, and then create a sales order by filling in the following fields.

    |Customer|Item|Qty.|Serial No.|  
    |--------------|----------|----------|----------------|  
    |Cannon Group PLC.|1002|1|SN2|  

1. Choose **Item Tracking Lines**. Enter the serial number in **Serial No.** and **1** in **Quantity (Base)**, and then close the page.
1.  Choose **Post**, select the **Ship and Invoice** option, and then choose **OK**.

    Finally, sell some racing frames separately. The Cannon Group PLC. also orders five separate racing frames for their own assembly line.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, and then select the related link.  
1. Choose **New**, and then create a sales order by filling in the following fields.

    |Customer|Item|Qty.|Lot No.|
    |--------------|----------|----------|----------------|
    |Cannon Group PLC.|2000|5|LOT1|

1. On the **Lines** FastTab, choose **Item Tracking Lines**. Enter **LOT1** in **Lot No.** and **5** in **Quantity (Base)**, and then close the page.

    > [!NOTE]  
    >  Do not post the last sales order for five racing frames.  

    This completes the preparation of data to demonstrate the Item Tracing and Find Entries features.  

## Trace from usage to origin

 From the sales department, the quality controller knows that the returned racing bike, item 1002, has the serial number SN1. By using this basic information, they can determine where the finished racing bike was last used, in this case, on the sales shipment to Selangorian Ltd.. Then, the quality controller must trace backward to the earliest origin to establish which lot number the faulty racing frame came from and which vendor supplied it.  

### To determine which lot included the faulty frame and who supplied it

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Item Tracing**, and then choose the related link.  
1.  On the **Item Tracing** page, enter **SN1** in the **Serial No. Filter** field, and then enter **1002** in the **Item Filter** field.
1.  Set **Show Components** to **Item-tracked Only** and **Trace Method** to **Usage -> Origin**.
1.  Choose the **Trace** action.

    Note that one sales shipment header matches the search criteria. Before you continue the trace, verify that the shipment is the one that shipped the faulty racing bike to Selangorian Ltd.  

1.  Select the trace line, and then choose the **Show Document** action.

    Now continue to trace the origin of the sales shipment of the racing bike with number SN1.  
1.  Choose the + icon on the trace lines to gradually expand and trace backward in the chain of transactions that the sales shipment originates from.

    You can trace the following transaction history:  

    - The first posted document backward in the chain of transactions is the output posting of SN1 from the first released production order.  
    - The next posted document backward after that is the consumption posting from the first released production order. Here the quality controller sees that a racing frame from LOT1 was used.  
    - The lowest posted document in this chain is the posted purchase receipt on which racing frames with LOT1 entered inventory.  

    The quality controller has now established which lot of racing frames was faulty and they can search for the last trace line to see which vendor supplied them, namely Custom Metals Incorporated.  

    > [!NOTE]  
    >  Do not make any additional modifications to the trace result, as you will use it in the next section.  

     This completes the first defects-management task using the **Item Tracing** page. The quality controller must now determine whether other posted documents have processed racing frames from LOT1.  

## Trace from origin to usage

 The quality controller has established that the faulty racing frames came from LOT1. They must now find any other racing bikes that contain racing frames from the faulty lot so that those bikes can be stopped or recalled.  

 One way to prepare this trace task on the **Item Tracing** page is to manually enter LOT1 in the **Lot No. Filter** field and 2000 in the **Item Filter** field. However, this walkthrough will use the **Trace Opposite - from Line** function.  

### To find all usage of the faulty lot  

1.  On the **Item Tracing** page, select the purchase receipt line for item **2000** and **LOT1**, and then choose **Trace Opposite - from Line**.

    The trace result is now based on the filters of the trace line for the purchase receipt, LOT1 and item 2000, and the result is based on trace method **Origin -> Usage**.

    To obtain an overview of all usage of item 2000 with LOT1, continue to expand all trace lines.  

1.  Choose the **Expand All** action.

    Locate the output and sales shipment entries for **SN1** and **SN2**. The shipment for **SN1** is to Selangorian Ltd. The shipment for **SN2** is to Cannon Group PLC. Both bikes were produced in the first production order using frames from **LOT1**.

    The quality controller immediately informs the sales department so that they can initiate a recall of the defective racing bike from the customer, Cannon Group PLC.  

    The output entries also show that **SN3** and **SN4** were produced using racing frames from **LOT1** and aren't sold. The quality controller takes action to block these end items in inventory.

    This completes the second defects management task using the **Item Tracing** page for defects management. Since the **Item Tracing** page is based on posted entries only, the quality controller must continue to the **Find entries** page to make sure that LOT1 is not used in non-posted documents.  

## Find open records for a serial or lot number

 By using the **Item Tracing** page, the quality controller learned that LOT1 contained the faulty racing frames, which vendor supplied them, and in which posted transaction they used them. They must now determine whether LOT1 is in any open documents by opening **Find entries** from the trace result.

### To find all occurrences of LOT1 in non-posted records, such as open orders  

1.  On the **Item Tracing** page, select the first trace line, the purchase receipt of LOT1.  
1.  Choose the **Find entries** action.

    The **Find entries** page is preset with search filters based on the trace result for LOT1. The quality controller recognizes records related to documents already identified on the **Item Tracing** page.

    The result also includes an unposted **Sales Line**, so the quality controller proceeds to investigate.

1.  Select the **Sales Line** result, and then choose **Show**. Alternatively, choose the value in **No. of Entries**.

    Here the quality controller sees one open sales line for the faulty racing frames. They immediately suggest to the sales department that this order be canceled and a new production order, based on good racing frames, be initiated.  

 This completes the walkthrough of how to use the **Find entries** page for defects management in integration with the **Item Tracing** page.  

## Related information

[Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md)  
[Trace Item-Tracked Items](inventory-how-to-trace-item-tracked-items.md)  
[Find Entries](ui-find-entries.md)  
[Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
