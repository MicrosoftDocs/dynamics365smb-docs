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
# How to: Process Purchase Returns
Purchase returns are used to ensure that your company is compensated for incorrect or damaged items that you receive from your vendors.  
  
 In cases where a company or its customers are dissatisfied with an order they received from a vendor, they can expect their vendor to compensate them in different ways. The terms of a compensation agreement reached between the company and the vendor will often depend on the reason for the return and the company-vendor relationship. For example, the parties may agree that in case of wrongly ordered\/delivered items the company returns the item to the vendor against receiving a credit and receives a replacement item instead. In other situations, for example, if a company receives a damaged item, the company may require a price deduction against the original purchase order price. The same may be applied when a company provided a sales allowance for their own customers and now wants to recover costs by requesting a purchase allowance from their vendor. Meanwhile, where the purchased item has a warranty, the company may ask the vendor to repair the malfunctioning or broken item. For more information, see [About Returns Management](../FullExperience/about-returns-management.md).  
  
 The purchase return order is the central document that allows you to register a compensation agreement settled with the vendor. From here, you can access other purchase-related documents, and enter and maintain the return-related information concerning the vendor, the method of compensation, and the items in question.  
  
 The following are the standard steps in creating a basic purchase return order. A basic return order is created when you want to return an item to a vendor for credit. Additional return options are described below.  
  
### To process a basic purchase return  
  
1.  Create a purchase return order. For more information, see [How to: Create Purchase Return Orders](../FullExperience/how-to-create-purchase-return-orders.md).  
  
2.  On the **Invoicing** FastTab, you can apply the return order to the associated purchase invoice by filling in the **Applies-to Doc. Type** and **Applies-to Doc. No.** fields.  
  
3.  Post the purchase return order. On the **Home** tab, in the **Process** group, choose **Post**.  
  
4.  Select **Ship and Invoice** to create a posted purchase credit memo is created.  
  
 If the associated invoice was not applied earlier in the process, this application can take place after posting.  
  
### Additional Return Options  
  
-   If you want to revalue inventory using the unit cost that is connected to the original purchase entry, assign Exact Cost Reversing.  
  
    -   You may need to create a purchase allowance if you and your vendor agree to accept compensation for a returned item in the form of a deduction from the original purchase order cost.  
  
    -   You may need to create a replacement purchase order if your vendor agrees to replace a returned item. The replacement item can be the same or it can be different.  
  
    -   In some cases, you may want to return a specific serialized item or lot, for instance, if a particular item or lot is defective or has been recalled. For these situations, you can to find the item using the serial or lot number, and then receive that specific item or lot return. Follow these steps:  
  
        1.  Locate the serial\/lot numbers from the vendor.  
  
        2.  Create a purchase return order.  
  
        3.  Select the line that you want to select serial\/lot numbers for.  
  
        4.  Choose the **Actions** button, choose **Line,** and then choose **Item Tracking Lines**.  
  
        5.  In the **Item Tracking Lines** window, in the **Lot No.** or **Serial No.** field, select a value from the **Item Tracking Summary** window.  
  
    -   You can create all return-related documents at the same time from the **Sales Return Order** window. Alternatively, you can create all the documents, including replacement purchase orders, sales return orders, and sales orders, individually.  
  
-   The following options can be used for items that have been received but not yet invoiced:  
  
    -   There may be times when you need to return several items that are covered by different purchase return orders to your vendor. Once the items have been shipped and before you invoice, you can use the **Get Return Shipment Lines** function to create one purchase credit memo for all of the shipped items.  
  
    -   If a return order has been shipped but the item is subsequently rejected, you must create a corrective purchase invoice to complete the return order transaction.  
  
## See Also  
 [How to: Create Purchase Credit Memos](../FullExperience/how-to-create-purchase-credit-memos.md)   
 Create Return-Related Documents   
 [How to: Create a Restock Charge](../FullExperience/how-to-create-a-restock-charge.md)   
 [How to: Assign Exact Cost Reversing in Sales](../FullExperience/how-to-assign-exact-cost-reversing-in-sales.md)   
 [How to: Create Replacement Purchase Orders](../FullExperience/how-to-create-replacement-purchase-orders.md)   
 [How to: Create and Post Purchase Allowances](../FullExperience/how-to-create-and-post-purchase-allowances.md)   
 [How to: Get Return Shipment Lines for Item Charges](../FullExperience/how-to-get-return-shipment-lines-for-item-charges.md)   
 [How to: Correct Purchase Invoices with Purchase Credit Memos](../FullExperience/how-to-correct-purchase-invoices-with-purchase-credit-memos.md)