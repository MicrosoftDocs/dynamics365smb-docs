---
    title: How to: Use Filters to Get Source Documents | Microsoft Docs
    description: From a new or an open warehouse receipt or warehouse shipment, you can use the **Filters to Get Source Docs.** window to retrieve the released source document lines that define which items to receive or ship.
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
# How to: Use Filters to Get Source Documents
From a new or an open warehouse receipt or warehouse shipment, you can use the **Filters to Get Source Docs.** window to retrieve the released source document lines that define which items to receive or ship.  
  
### To use filters to get source documents  
  
1.  Open a warehouse receipt or warehouse shipment, or create a new one.  
  
2.  Fill in the **General** FastTab for the receipt or shipment.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Use Filters to Get Src. Docs.**.  
  
4.  To set up a new filter, enter a descriptive code in the **Code** field, and then click **Modify**.  
  
     The **Source Document Filter Card** window appears. The caption of the window includes **Inbound** if you are using the filter function to get receipt lines, or **Outbound** if you are preparing a shipment.  
  
5.  Define the type of source document lines that you want to retrieve by filling in the relevant filter fields.  
  
     For information about the filters, press F1 in each field to read the field description.  
  
6.  Click **Run.**  
  
 All released source document lines that fulfill the filter criteria are now inserted in **Warehouse Receipt** or **Warehouse Shipment** window from which you activated the filter function.  
  
 For information about releasing outbound source documents for shipment, see [How to: Pick Items for Warehouse Shipment](../how-to-pick-items-for-warehouse-shipment.md).  
  
 The filter combinations that you define are saved in the **Filters to Get Source Docs.** window until the next time you need it. You can make an unlimited number of filter combinations.  
  
 You can change the criteria at any time by clicking **Modify**.  
  
## See Also  
 Filters to Get Source Docs.   
 Source Document Filter Card   
 Warehouse Receipt   
 Warehouse Shipment   
 Warehouse Source Filter   
 [How to: Pick Items for Warehouse Shipment](../how-to-pick-items-for-warehouse-shipment.md)   
 [How to: Receive Items](../how-to-receive-items.md)   
 [Shipping](../Shipping.md)