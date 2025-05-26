---
title: Subcontract manufacturing
description: This article gives an extended overview of the extended functionality of subcontracting, including work center fields and routing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: 99000886,
ms.date: 06/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Subcontract manufacturing

Subcontracting selected operations to vendor is common in many manufacturing companies. Subcontracting can be a rare occurrence or can be an integral part of all production processes.

[!INCLUDE[prod_short](includes/prod_short.md)] provides several tools for managing subcontract work:  

- Work Centers with assigned vendor: This feature enables you to set up a work center that is associated with a vendor (subcontractor). This work center is called a subcontract work center. You can specify a subcontract work center on a routing operation, which allows you to easily process the subcontracted activity. In addition, the cost of the operation can be designated at the routing or the work center level.  
- Work Center cost based on units or time: This feature enables you to specify whether costs associated with the work center are based on the production time or a flat charge per unit. Although subcontractors commonly use a flat charge per unit to charge for their services, the application can handle both options (production time and flat charge per unit).  
- Subcontracting Worksheet: This feature allows you to find the production orders with material ready to send to a subcontractor and to automatically create purchase orders for subcontract operations from production order routings. The application automatically posts the purchase order charges to the production order during the posting of the purchase order. Only production orders with a status of released can be accessed and used from a subcontracting worksheet.  

## Subcontract work centers  

Subcontract Work Centers are set up the same as regular work centers with additional information. They're assigned to routings in the same manner as other work centers.  

### Subcontract work center fields  

This **Subcontractor No.** field designates the work center as a subcontract work center. You can enter the number of a subcontractor who supplies the work center. This field can be used to administer work centers, which aren't in-house but perform processing under contract.  

If you subcontract with the vendor for a different rate for each process, then select the **Specific Unit Cost** field. This setting lets you set up a cost on each routing line and saves the time of reentering each purchase order. The cost on the routing line is used in processing instead of the cost on the work center cost fields. Selecting the **Specific Unit Cost** field calculates costs for the vendor by the routing operation.  

If you subcontract at a single rate per vendor, leave the **Specific Unit Cost** field blank. The costs are set up by filling in **Direct Unit Cost**, **Indirect Cost %**, and **Overhead Rate** fields.  

### Routings that use subcontract work centers

Subcontract work centers can be used for operations on routings in the same way as regular work centers.  

You can set up a routing that uses an outside work center as a standard operational step. Alternatively, you can modify the routing for a particular production order to include an outside operation. This might be needed in an emergency such as a server not working correctly, or during a temporary period of higher demand where work you normally do in-house must be sent to a subcontractor.  

For more information, see [Create Routings](production-how-to-create-routings.md).  

## Calculate subcontracting worksheets and create subcontract purchase orders  

After you calculate the subcontracting worksheet, the relevant document is created. In this case, a purchase order.  

The **Subcontracting Worksheet** page functions like the **Planning Worksheet** by calculating the needed supply, in this case purchase orders, which you review in the worksheet and then create with the **Carry Out Action Message** function.  

> [!NOTE]  
> Only production orders with status **Released** can be accessed and used from a subcontracting worksheet.  

### To calculate the subcontracting worksheet  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Worksheet**, and then choose the related link.  
2. To calculate the worksheet, choose the **Calculate Subcontracts** action.  
3. On the **Calculate Subcontracts** page, set filters for the subcontracted operations, or the work centers where they're performed, to calculate only the relevant production orders.  
4. Choose the **OK** button.  

    Review the lines on the **Subcontracting Worksheet** page. The information in this worksheet comes from the production order and production order routing lines and flows to the purchase order when that document is created. You can delete a row from the worksheet without affecting the original information, just as you can with the other worksheets. The information will reappear the next time you run the **Calculate Subcontracts** function.  

### To create the subcontract purchase order  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Worksheet**, and then choose the related link.  
2. Choose the **Carry Out Action Message** action.  
3. Select the **Print Orders** field to print the purchase order as it is created.  
4. Choose the **OK** button.  

If all subcontracted operations are sent to the same vendor location, then only one purchase order is created.  

The worksheet line that was turned into a purchase order is deleted from the worksheet. After a purchase order is created, it won't appear in the worksheet again.  

## Posting subcontract purchase orders  

After the Subcontractor Purchase Orders are created, they can be posted. Receiving the order posts a Capacity Ledger Entry to the production order and invoicing the order posts the direct cost of the purchase order to the production order.  

## To post a subcontract purchase order
 
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then select the related link.  
2. Open a purchase order that is created from the subcontracting worksheet.  

    On the purchase order lines, you see the same information that was in the worksheet. The **Prod. Order No.**, **Prod. Order Line No.**, **Operation No.**, and **Work Center No.** fields are filled in with the information from the source production order.  

3. Choose the **Post** action.  

When the purchase is posted as received, an output journal entry is automatically posted for the production order if the subcontract operation is the last operation on the production order routing.  

> [!CAUTION]  
> Posting output automatically for an ongoing production order when subcontracted items are received may not be desired. Reasons for this could be that the expected output quantity that is posted may be different from the actual quantity and that the posting date of the automatic output is misleading.  
>
> To avoid that the expected output of a production order is posted when subcontract purchases are received, make sure the subcontracted operation is not the last one. Alternatively, insert a new last operation for the final output quantity.  

When the purchase order is posted as invoiced, then the direct cost of the purchase order is posted to the production.  

> [!NOTE]  
> Expected costs are only managed for item transactions. Expected costs are not for immaterial transaction types, such as capacity posted via subcontract purchase orders. Don't be confused by the fact that posting a receipt might trigger posting of output. These transactions are separate and the expected cost of output is calculated independently.  

## Related information  

[Manufacturing](production-manage-manufacturing.md)    
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)      
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
