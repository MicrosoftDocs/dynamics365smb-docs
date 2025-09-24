---
title: Register consumption output for a production order
description: This article explains how to register consumption and output for a released production order line.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 5510,
ms.date: 04/08/2025
ms.service: dynamics-365-business-central

---
# Register consumption and output for a released production order

Use the **Production Journal** page to register consumption output for a released production order. The journal combines the functions of the separate consumption journal and output journals into one journal. You open the combined journal from a released production order. Its purpose is to manually post the consumption of components, the quantity of end items produced, and the time spent on operations. The values post to ledger entries under the released production order. Consumption quantities post as negative item ledger entries, output quantities post as positive ledger entries, and time spent posts as capacity ledger entries. The posted values also display at the bottom of the journal as actual quantities.  

> [!NOTE]  
> Because consumption data is processed together with output data, this journal displays linked components and operations in a logical process structure. Components are indented under their respective operation. This linking requires that you use routing link codes. To learn more about routing links, go to [To create routing links](production-how-to-create-routings.md#to-create-routing-links).  

> [!NOTE]  
> Components without routing link codes list first in the journal.  

## To register consumption and output  

1. [!INCLUDE[open-search](includes/open-search.md)] enter **Released Prod. Orders**, and then choose the related link.  
2. Open a released production order line that's ready to register. On the **Lines** FastTab, choose the **Line** action, and then choose the **Production Journal** action.  

    The **Production Journal** page shows journal lines for the production order line according to the **Prod. Order Component** and **Prod. Order Routing** pages. These lines come from the production BOM and routing assigned to the item that is being produced. To learn more, go to [Create Production BOMs](production-how-to-create-routings.md).  

3. In the **Posting Date** field, enter a posting date that applies to all lines. The work date is entered by default. The field is meant as a quick way to align posting dates on all lines, if relevant.  

    > [!NOTE]  
    > Posting dates on individual lines override this field.  

4. In the **Flushing Method Filter** field, you can choose to also view consumption and output that is posted automatically according to the flushing methods defined for the item and resource respectively. To learn more, go to [Enable Flushing of Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).

5. Enter the consumption and output quantities.  
  
    On each type of line in the journal, only the relevant fields are shown. Other fields are blank and you can't edit them.  

    When you open the journal, it shows the quantities to post. If nothing is posted so far, all quantity fields show the expected quantities from the production order. If partial postings were done, the quantity fields on the lines show the remaining quantities. The quantities and times already posted for the order display at the bottom of the journal as actual entries.  

    > [!TIP]
    > For the quantities in the **Output Quantity** field, you can specify which values to preset when you first open the journal. On the **Manufacturing Setup** page, on the **General** FastTab, enter the value in the **Preset Output Quantity** field.

    > [!NOTE]  
    > Only the output quantity on the last journal line of entry type **Output** adjusts the inventory level when posting the journal. Therefore, don't post the journal with the expected output quantity preset on the last output line until all end items are produced.  

6. Select the **Finished** field of output lines to indicate that the operation is finished. This field is related to the **Routing Status** field on a production order routing line.  
7. Choose the **Post** action to register the quantities and then close the journal.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

    If values remain to be posted, the journal contains the remaining values the next time you open it. Posted values show as actual values in the bottom of the journal.  

    > [!NOTE]  
    > If an item that's being consumed is blocked, the journal doesn't post consumption quantities for it. If a machine or work center is blocked, the journal doesn't post output quantities or process times for the output line.  

    > [!NOTE]  
    > If you close the journal without posting, the changes are lost.  

> [!WARNING]  
> Only one person can use the **Production Journal** page at a time. For example, User 2 opens the page and enters data when User 1 is already working on the page. User 2 might lose their data when User 1 closes the page.  

## Related information  

[Cancel production orders that have consumption](production-cancel-production-orders-that-have-consumption.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
