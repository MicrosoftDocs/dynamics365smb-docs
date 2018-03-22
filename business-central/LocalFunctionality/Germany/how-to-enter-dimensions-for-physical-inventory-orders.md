---
    title: How to Enter Dimensions for Physical Inventory Orders
    description: After you have created a physical inventory order, you can enter dimensions for this order.
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
# Enter Dimensions for Physical Inventory Orders
After you have created a physical inventory order, you can enter dimensions for this order.  

The application distinguishes between the dimensions for the physical inventory order header and the dimensions for the physical inventory order lines. The dimensions of the physical inventory header are a pattern for the dimensions of the physical inventory order lines. Every time you create a new physical inventory order line manually or automatically, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] will transfer the dimensions from the header to the new line.  

That is why you should create the physical inventory order lines first after complete entering the dimensions for the physical inventory order header. You can manually change the dimensions for every physical inventory order line. For posting, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] will use the dimensions of the physical inventory order line.  

## To enter dimensions for a physical inventory order  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Phys. Inventory Order**, and then choose the related link.  
2.  Select the physical inventory order that you want to create an inventory recording for, and then choose the **Edit** action.  
3.  Choose the **Dimensions** action.  
4.  In the **Edit Dimension Set Entries** window, enter the dimensions for the inventory order header.  
5.  Create a new physical inventory order line and enter the item number.  
6.  Choose the **Line** action, and then choose the **Dimensions** action.  
7.  In the **Edit Dimension Set Entries** window, optionally, enter the dimensions for the inventory order line.  

## See Also  
 [Enter Physical Inventory Orders](how-to-enter-physical-inventory-orders.md)   
 [Post Physical Inventory Orders](how-to-post-physical-inventory-orders.md)   
 [Dimension Set Entries Overview](../../design-details-dimension-set-entries-overview.md)
