---
    title: How to: Undo Service Shipments | Microsoft Docs
    description: You can cancel a service shipment that has been posted by mistake or contains some erroneous information.
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
# How to: Undo Service Shipments
You can cancel a service shipment that has been posted by mistake or contains some erroneous information.  
  
### To undo a service shipment  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Service Shipments**, and then choose the related link.  
  
2.  Open the relevant posted service shipment.  
  
3.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Shipment**, and then choose **Service Shipment Lines**. The **Posted Service Shipment Lines** window opens.  
  
4.  Select the relevant line.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Undo Shipment**.  
  
 A balancing service shipment line is inserted with negative corresponding values in the **Quantity Invoiced** and **Quantity** fields. Relevant ledger entries are also generated.  
  
> [!NOTE]  
>  You will not be able to undo a service shipment that has already been invoiced.  
  
## See Also  
 [How to: Undo Service Consumption](../how-to-undo-service-consumption.md)   
 [How to: Register Service Operations](../how-to-register-service-operations.md)