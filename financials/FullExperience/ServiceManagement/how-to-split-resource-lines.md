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
# How to: Split Resource Lines
If the same resource, for example, a technician, works on all the service items in the service order, you can register the total resource hours for one service item only and then split the resource line to divide the resource hours onto the resource lines for the other service items.  
  
 The following procedure shows how to split resource lines in the **Service Invoice Lines** window.  
  
### To split a resource line  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  Open the relevant service order.  
  
3.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../FullExperience/media/actionmenuicon.png "actionMenuIcon"), choose **Order**, and then choose **Service Lines**. The **Service Lines** window opens.  
  
4.  Select the resource line you want to split. The contents of the **Quantity** field is divided between all the service items in the order.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Split Resource Line**. Choose **Yes** to confirm.  
  
     Resource lines for the other service items in the order are created with the same resource number as the line you split. The quantity is the quantity for the line you split divided by the number of service items in the order.  
  
## See Also  
 [How to: Register Resource Hours](../FullExperience/how-to-register-resource-hours.md)