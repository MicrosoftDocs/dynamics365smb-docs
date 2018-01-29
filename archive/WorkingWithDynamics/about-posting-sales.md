---
    title: About Posting Sales | Microsoft Docs
    description: In the **Posting** group on a sales document, you can choose between the following posting functions:
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
# About Posting Sales
In the **Posting** group on a sales document, you can choose between the following posting functions:  
  
-   **Post**  
  
-   **Test Report**  
  
-   **Post and Send** for more information, see [Set Up Document Sending Profiles](../FullExperience/how-to-set-up-document-sending-profiles.md).  
  
-   **Post and Print**  
  
-   **Post and Email** For more information, see [Send Documents by Email](../FullExperience/how-to-send-documents-by-email.md).  
  
-   **Post Batch**  
  
-   **Preview Posting** for more information, see [Preview Posting Results](../FullExperience/how-to-preview-posting-results.md).  
  
 When you have completed all the lines and entered all the information on the sales order, you can post it. This creates a shipment and an invoice.  
  
 When a sales order is posted, the customer's account, the general ledger, and the item ledger entries are updated.  
  
 For each sales order, a sales entry is created in the G/L Entry table. An entry is also created in the customer's account in the Cust. Ledger Entry table and a general ledger entry is created in the relevant receivables account. In addition, posting the order may result in a VAT entry and a general ledger entry for the discount amount. Whether an entry for the discount is posted depends on the contents of the **Discount Posting** field in the **Sales & Receivables Setup** table.  
  
 For each sales order line, an item ledger entry will be created in the Item Ledger Entry table (if the sales lines contain item numbers) or a general ledger entry will be created in the **G/L Entry** table (if the sales lines contain a general ledger account). If your location is set up to use bins and you have set a bin code on the sales order line, a warehouse entry will be created in the Warehouse Entry.  
  
 In addition to this, sales orders are always recorded in the [Sales Shipment Header](../FullExperience/($%20T_112%20Sales%20Invoice%20Header%20$).md) tables.  
  
> [!IMPORTANT]  
>  When you post an order, you can create both a shipment and an invoice. These can be done at the same time or independently.  
>   
>  You can also create a partial shipment and a partial invoice by completing the Qty. to Ship or Qty. to Invoice fields on the individual sales order lines before you post. Note that you cannot create an invoice for something that is not shipped. That is, before you can invoice, you must have recorded a shipment, or you must choose to ship and invoice at the same time.  
  
 When the posting is completed, the posted sales lines are removed from the order. A message tells you when the posting is completed. After this, you will be able to see the posted entries in the various windows that contain posted entries, such as **Cust. Ledger Entries**, **G/L Entries**, **Item Ledger Entries**, **Warehouse Entries**, **Posted Sales Shipment**, and **Posted Sales Invoice**.  
  
## See Also  
 Sales Order   
 [Post Sales Orders](../FullExperience/how-to-post-sales-orders.md)   
 Batch Post Sales Orders   
 [Preview Posting Results](../FullExperience/how-to-preview-posting-results.md)