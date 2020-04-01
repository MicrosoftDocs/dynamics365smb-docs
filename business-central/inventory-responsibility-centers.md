---
    title: How to Work with Responsibility Centers | Microsoft Docs
    description: Responsibility centers providing the ability to handle administrative centers. A responsibility center can be a cost center, a profit center, an investment center, or other company-defined administrative center.
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
# Work with Responsibility Centers
Responsibility centers provide the ability to handle administrative centers. A responsibility center can be a cost center, a profit center, an investment center, or other company-defined administrative center. Examples of responsibility centers are a sales office, a purchasing department for several locations, and a plant planning office. Using this functionality, for example, companies can set up user-specific views of sales and purchase documents related exclusively to a particular responsibility center.  

Using multiple locations together with responsibility centers provides the ability to manage business operations in the most flexible, yet optimal way.

Multiple locations allows companies to manage their inventory in multiple locations using one database. Two concepts, locations and stockkeeping units, are the cornerstones of this granule. A location is defined as a place that handles physical placement and quantities of items. The concept is broad enough to include locations such as plants or production facilities as well as distribution centers, warehouses, showrooms and service vehicles. A stockkeeping unit is defined as an item at a specific location and/or as a variant. Using stockkeeping units, companies with multiple locations are able to add replenishment information, addresses, and some financial posting information at the location level. As a result, they have the ability to replenish variants of the same item for each location as well as to order items for each location on the basis of location-specific replenishment information.  

Responsibility centers extends the multiple locations functionality by providing users the ability to handle administrative centers. A responsibility center can be a cost center, a profit center, an investment center, or other company-defined administrative center. Examples of responsibility centers are a sales office, a purchasing department for several locations, and a plant planning office. Using this functionality, for example, companies can set up user-specific views of sales and purchase documents related exclusively to a particular responsibility center.

## To set up a responsibility center  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Responsibility Centers**, and then choose the related link.  
2.  Choose the **New** action.  
3.  Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    If you are using responsibility centers to administer your company, it can be useful to have a default responsibility center for your company.
4. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.
5. In the **Responsibility Center** field, enter a responsibility center code.

This code will be used on all purchase, sales, or service documents, if the user, customer, or vendor has no default responsibility center. On any sales, purchase, or service document, you can enter another responsibility center than the default.

> [!NOTE]  
>  When you enter a responsibility center code on a document, it affects the address, dimensions, and prices on the document.  

## To assign responsibility centers to users  
You can set up users so that in their daily routines application retrieves only the documents relevant for their particular work areas. Users are usually associated with one responsibility center and work only with documents related to specific application areas at that particular center.  

To set this up, you assign responsibility centers to users in three functional areas: Purchases, Sales, and Service Management.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Setup**, and then choose the related link.  
2.  On the **User Setup** page, select the user you want to assign a responsibility center to. If the user not is on the list, you must enter a user ID in the **User ID** field.  
3.  In the **Sales Resp. Ctr. Filter** field, enter the responsibility center where the user will have tasks related to sales.  
4.  In the **Purchase Resp. Ctr. Filter** field, enter the responsibility center where the user will have tasks related to purchasing.  
5.  In the **Service Resp. Ctr. Filter** field, enter the responsibility center where the user will have tasks related to service management.  

> [!NOTE]  
>  Users will still be able to view all posted documents and ledger entries, not just those related to their own responsibility center.

## See Also  
[Setting Up Inventory](inventory-setup-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)
[Inventory](inventory-manage-inventory.md)[Warehouse Management](warehouse-manage-warehouse.md)  
[Warehouse Management](warehouse-manage-warehouse.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
