---
    title: How to Create the TORG-29 Goods Report | Microsoft Docs
    description: The TORG-29 report shows the item documents that you can use to submit for receipts and shipments for a location.
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
# How to: Create the TORG-29 Goods Report
The TORG-29 report shows the item documents that you can use to submit for receipts and shipments for a location.  
  
 When you run the report for a location, the **Last Goods Report No.** and **Last Goods Report Date** fields in the **Location Card** window are updated to ensure consistent reporting.  
  
### To create the TORG-29 report  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Report TORG-29**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Location Code**|Specifies the location that the report is for.|  
    |**Report No.**|Specifies the number of times that the report has printed based on the value of the **Last Goods Report No.** field in the **Location Card** window.|  
    |**Responsible Employee**|Specifies the employee who is responsible for the validity of the data in the report.|  
    |**Report Acceptor**|Specifies the employee who is responsible for accepting the report.|  
    |**Report Date**|Specifies the date of the report.|  
    |**Start Date**|Specifies the start date for the report.|  
    |**End Date**|Specifies the start date for the report.|  
    |**Operation Type**|Optionally, specifies the type of operation. This information will be included in the report.|  
    |**Attaches No.**|Specifies the number of attachments to the report.|  
    |**Receipt Detailing**|Specifies what the detailed information for each entry is based on.<br /><br /> If you select **Document**, amounts are totaled for each document. If you select **Item**, the amount and quantity are totaled for each item. If you select **Operation**, the amount and quantity are included in a single transaction.|  
    |**Shipment Detailing**|Specifies what the detailed information for each entry is based on.<br /><br /> If you select **Total Amount**, the report summarizes amounts in a single line. If you select **Document**, amounts are totaled for each document. If you select **Item**, the amount and quantity are totaled for each item. If you select **Operation**, the amount and quantity are included in a single transaction.|  
    |**Amount Type**|Specifies what the amounts are based on, cost or sales price.<br /><br /> If you set this field to **Sales Price**, the **Sales Type**, **Show Cost Amount for Receipts**, and **Show Cost Amounts for Shipment** fields become available.|  
    |**Sales Type**|Specifies the type of price list.<br /><br /> If you select **Customer Price List**  or **Campaign**, you can select the price list in the **Sales Code** field. If you select **All Customers**, a unified price list is used.|  
    |**Sales Code**|Specifies the price list. Depending on the selection in the **Sales Type** field, you can specify either a customer price group or a campaign number.|  
    |**Show Cost Amount for Receipts**|Specifies if each receipt line must be divided into two lines. If selected, the first line for a receipt represents item cost, and the second line represents the sales margin.|  
    |**Show Cost Amounts for Shipment**|Specifies if each shipment line must be divided into two lines. If selected, the first line for a receipt represents the item cost, and the second line represents the sales margin.|  
  
3.  Choose the **Print** button.  
  
## See Also  
 [Inventory Setup](inventory-setup.md)   
 Item Report TORG-29   
 Items Receipt Act TORG-1   
 Receipt Deviations TORG-2   
 Transfer Order TORG-13