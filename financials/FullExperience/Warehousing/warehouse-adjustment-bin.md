---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Warehouse Adjustment Bin
If you use directed put-away and pick for a warehouse, when you register differences in item quantity in bins in the warehouse item journal, the positive and negative adjustment quantities are registered in the adjustment bin. The quantities are not automatically posted to the item ledger. At appropriate intervals as defined by company policy, you must post the entries in the adjustment bin to the item ledger, so that the item ledger quantities correspond to the actual quantities of items in the warehouse. Some companies find it appropriate to post adjustments to the item ledger every day, while others may find it adequate to reconcile every week or every two weeks.  
  
 When you conduct a warehouse physical inventory, you also create quantities in the adjustment bin for all the differences between the calculated and physical inventory quantities. If you want to post the results of the particular warehouse physical inventory in the physical inventory ledger, however, and you want the posted results to be identifiable as the results of the particular count, you need to do two things:  
  
-   Before you conduct the physical inventory, run the Calculate Whse. Adjustment function in the item journal in Inventory for the items you want to count. If you do not do this, previous warehouse adjustments for a particular item will become part of the physical inventory record.  
  
-   Immediately after you register the results of the warehouse physical inventory, run the Calculate Inventory function in the physical inventory journal in the Inventory menu for the same items you counted in the warehouse physical inventory. The program calculates the physical inventory quantity for each item on the basis of the bin-by-bin registrations and also calculates, in the Quantity field, the necessary positive or negative adjustments to the item ledger. You can now post the exact results of this physical inventory.  
  
 Entries are made in the adjustment bin not only by the warehouse but also by postings in the item journal and other non-warehouse documents that concern inventory quantity. For example, when a purchaser receives a gift for the company, he posts the items to the item ledger. These items are automatically registered in the adjustment bin \(positive entry\). But the items are not available in the warehouse until a warehouse employee registers the item to an appropriate bin in the Whse. Item Journal and thereby creates a negative quantity in the adjustment bin. The entries regarding the gift in the adjustment bin thus cancel one another, and the gift is available for picking in the warehouse.  
  
 The other documents that create entries in the adjustment bin - purchase invoices, purchase credit memos, sales invoices, and sales credit memos - are normally not regarded in the warehouse because you cannot create a receipt or shipment for them. They are, however, documents that concern company inventory. For example, if you do not want the customer to return an item that was damaged upon delivery, but decide to issue a sales credit memo, the inventory loss must somehow be reflected in the item ledger, and the adjustment journal provides the means to do so. Another example is the posting of a purchase invoice, which creates a positive entry in the item ledger and in the adjustment bin at the same time.  
  
## See Also  
 [How to: Perform Warehouse Physical Inventories](../FullExperience/how-to-perform-warehouse-physical-inventories.md)   
 [How to: Register Quantity Adjustments in Warehouse Item Journals](../FullExperience/how-to-register-quantity-adjustments-in-warehouse-item-journals.md)   
 [How to: Post Quantity Adjustments for Bins](../FullExperience/how-to-post-quantity-adjustments-for-bins.md)