---
    title: About Posting Purchases | Microsoft Docs
    description: In the **Posting** group on a purchase document, you can choose between the following posting functions:
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
# About Posting Purchases
In the **Posting** group on a purchase document, you can choose between the following posting functions:  
  
-   **Post**  
  
-   **Preview Posting** for more information, see [Preview Posting Results](../FullExperience/how-to-preview-posting-results.md).  
  
-   **Post and Print**  
  
-   **Test Report**  
  
-   **Post Batch**  
  
 When you have completed all the lines and entered all the information on the purchase order, you can post it, that is, create a receipt and an invoice.  
  
 When a purchase order is posted, the vendor's account, the general ledger, and the item ledger entries are updated.  
  
 For each purchase order, a purchase entry is created in the G/L Entry table. An entry is also created in the vendor's account in the Vendor Ledger Entry table and a G/L entry is created in the relevant payables account. In addition, posting the order may result in a VAT entry and a G/L entry for the discount amount. Whether an entry for the discount is posted depends on the contents of the **Discount Posting** field of the **Purchases & Payables Setup** table.  
  
 For each purchase order line, an item ledger entry will be created in the Item Ledger Entry table (if the purchase lines contain item numbers) or a G/L entry will be created in the **G/L Entry** table (if the purchase lines contain a G/L account). If your location is set up to use bins, a warehouse entry will be created in the Warehouse Entry table.  
  
 In addition, purchase orders are always recorded in the [Purch. Recpt. Header](../FullExperience/($%20T_122%20Purch.%20Inv.%20Header%20$).md) tables.  
  
 Before you start to post, you can print a test report that contains all the information in the purchase order and indicates any errors there. To print the report, choose **Actions**, choose **Posting**, and then choose **Test Report**.  
  
> [!IMPORTANT]  
>  When you post an order, you can create both a receipt and an invoice. These can be done simultaneously or independently.  
>   
>  You can also create a partial receipt and a partial invoice by completing the Qty. to Receive and/or Qty. to Invoice fields on the individual purchase order lines before you post. Note that you cannot create an invoice for something that has not been received. That is, before you can invoice, you must have recorded a receipt, or you must choose to receive and invoice at the same time.  
  
 You can either post, or post and print. If you choose to post and print, a report is printed when the order is posted. You can also choose the **Post Batch** function, which lets you post several orders at the same time.  
  
 When the posting is completed, the posted purchase lines are removed from the order. A message tells you when the posting is completed. After this, you will be able to see the posted entries in the various windows that contain posted entries, such as **Vendor Ledger Entries**, **G/L Entries**, **Item Ledger Entries**, **Warehouse Entries**, **Purchase Receipt**, and **Purchase Invoice**.  
  
> [!CAUTION]  
>  The planning system will try to consolidate supplies, for example by increasing existing purchase order lines to include new demand for the same item and vendor.  
>   
>  If a purchase order line with a value in the **Job No.** field is increased by the planning system, then the combined purchase quantity will be posted as consumed by the related job and thereby cause erroneous job costing. You should therefore pay extra attention when posting purchase order lines that contain a job number. Alternatively, you can prevent the issue in the following ways:  
>   
>  -   Manually split the affected purchase order by creating a second purchase order line for the quantity that is not job-related.  
> -   Set affected items up with a reordering policy of **Order**, to ensure that the planning system always creates one supply per demand.  
> -   Set the **Planning Flexibility** field on purchase order lines to **None**, to specify that such supplies are newer modified by the planning system.  
  
## See Also  
 Purchase Order   
 [Post Purchase Orders](../FullExperience/how-to-post-purchase-orders.md)   
 [Post Purchase Invoices](../FullExperience/how-to-post-purchase-invoices.md)   
 [Preview Posting Results](../FullExperience/how-to-preview-posting-results.md)   
 Batch Post Purchase Orders