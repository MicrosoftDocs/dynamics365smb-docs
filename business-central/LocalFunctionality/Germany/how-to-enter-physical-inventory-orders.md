---
    title: How to Enter Physical Inventory Orders
    description: A physical inventory order is a complete document that consists of a physical inventory order header and some physical inventory order lines. The information on a physical inventory header describes how to take the physical inventory.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Enter Physical Inventory Orders
A physical inventory order is a complete document that consists of a physical inventory order header and some physical inventory order lines. The information on a physical inventory header describes how to take the physical inventory. You can fill in the header manually. You can create a physical inventory order and relate it to one or more physical inventory recordings.  

The physical inventory order lines contain the information about the items and their locations. You can create the physical inventory order lines manually, or you can let the program automatically create physical inventory order lines for you. You can do this by using batch jobs.  

Before you can create physical inventory orders you have to set up properties for physical inventory. For more information, see [Set Up Physical Inventory Documents](how-to-set-up-physical-inventory-documents.md).  

## To create a physical inventory order  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Phys. Inventory Order**, and then choose the related link.  
2.  Choose the **New** action.  
3.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Description**|Sets a description for the physical inventory order.|  
    |**Location Code**|Sets location code for the item in the order line.|  
    |**Person Responsible**|Select the code for the person responsible for taking the inventory.<br /><br /> Optionally, you can add this information later.|  
    |**Order Date**|Sets the creation date for the physical inventory order.|  
    |**Posting Date**|Sets the posting date for the physical inventory order.|  

You can add lines to the physical inventory order manually, or [!INCLUDE[d365fin](../../includes/d365fin_md.md)] can create new physical inventory order lines automatically. To create new physical inventory order lines automatically, you have two possibilities:  

- You can create new physical inventory order lines based on inventory items and item ledger entries.  
- You can create new physical inventory order lines based on existing or posted physical inventory orders by using the copy function.  

Both batch jobs will check if there is already a line with the same values in the following fields on a physical inventory order line: Item No., Variant Code, Location Code, and Bin Code. In this case the new line is not inserted automatically to avoid duplicate lines.  

## To automatically add physical inventory order lines from inventory  

1.  In the **Phys. Inventory Order** window, choose the **Calculate Lines** action.  
2.  In the **Calc. Phys. Invt. Order Lines** window, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Calculate Qty. Expected**|Select to calculate and insert the quantity expected data for newly created physical inventory order lines.|  
    |**Items Not on Inventory**|Select to insert physical inventory order lines for items that have a value of zero in the **Quantity Expected** field.|  

3.  Optionally, on the **Item** FastTab, select the appropriate filters, and then choose the **OK** button.  
4.  When the batch job completes, choose the **OK** button.  

## To automatically add physical inventory order lines by copying documents  

1.  In the **Phys. Inventory Order** window, choose the **Copy Document** action.  
2.  In the **Copy Phys. Invt. Order** window, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Document Type**|Specify the type of document to copy.|  
    |**Document No.**|Specify the document to copy.|  
    |**Calculate Qty. Expected**|Select to calculate and insert the quantity expected data for newly created physical inventory order lines.|  

3.  When the batch job completes, choose the **OK** button.  

You can run the batch job more than once. If there are already existing lines for the physical inventory order, the program will append the new lines at the end.  

For each physical inventory order, you can create one or more physical inventory recordings. There you can document the physical count. For more information, see [Create a Physical Inventory Recording](how-to-create-a-physical-inventory-recording.md).  

You can compare and document the expected quantities from the physical inventory order lines with the (counted) quantities from the physical inventory recording lines. You can post the physical inventory differences.  

## See Also  
 [Physical Inventory Documents](physical-inventory-documents.md)   
 [Enter Dimensions for Physical Inventory Orders](how-to-enter-dimensions-for-physical-inventory-orders.md)   
 [View Duplicate Physical Inventory Order Lines](how-to-view-duplicate-physical-inventory-order-lines.md)   
 [Create a Physical Inventory Recording](how-to-create-a-physical-inventory-recording.md)   
 [Calculate Quantity On Hand for a Physical Inventory Order](how-to-calculate-quantity-on-hand-for-a-physical-inventory-order.md)   
 [Post Physical Inventory Orders](how-to-post-physical-inventory-orders.md)
