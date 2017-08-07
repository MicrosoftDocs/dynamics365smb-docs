---
    title: How to: Replace Service Items | Microsoft Docs
    description: If you cannot repair a service item, you may have to replace the service item either temporarily or permanently.
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
# How to: Replace Service Items
If you cannot repair a service item, you may have to replace the service item either temporarily or permanently.  
  
### To replace a service item  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Tasks**, and then choose the related link.  
  
2.  Open the relevant service order and select the line that includes the relevant service item. On the **Lines** toolbar, on the **Line** menu, choose **Service Item Worksheet**.  
  
3.  Enter a new service line.  
  
4.  In the **Type** field, select **Item**.  
  
5.  In the **No.** field, select the item that you want to replace the service item with. The item should be the one linked to the service item. The same item number as the service item you are replacing is assigned, and the replaced service item is marked as defective.  
  
6.  Press Enter. The **Service Item Replacement** window opens.  
  
7.  Fill in the relevant fields.  
  
     If you replace a complex service item that contains components, you select in the **Copy Components From** field either **Item BOM**, **Old Service Item**, or **Old Service Item w/o Serial No**.  
  
8.  Choose the **OK** button to replace the service item.  
  
 The new item is not registered as a service item with a service item number until you post this service invoice line or the service order.  
  
## See Also  
 [How to: Register Spare Parts](../how-to-register-spare-parts.md)   
 [How to: Replace Components](../how-to-replace-components.md)