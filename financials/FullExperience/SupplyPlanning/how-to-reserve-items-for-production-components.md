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
# How to: Reserve Items for Production Components
You can reserve items for production orders. You have to distinguish between reserving for production order lines, meaning the parent item, and reserving for production order components.  
  
### To reserve items for production order components  
  
1.  In the **Search** box, enter **Firm Planned Prod. Order**, and then choose the related link.  
  
2.  Open the firm planned production order you want to reserve component items for.  
  
3.  Select the relevant production order line.  
  
4.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../FullExperience/media/actionmenuicon.png "actionMenuIcon"), choose **Line**, and then choose **Components**.  
  
5.  Select the relevant component line.  
  
6.  Choose **Actions**![Action Menu icon](../FullExperience/media/actionmenuicon.png "actionMenuIcon"), choose **Functions**, and then choose **Reserve**.  
  
7.  In the **Reservation** window, select a line, and then ADD INCLUDE<!--[!INCLUDE[bp_ribbonxml](../../includes/bp_ribbonxml_md.md)]--> on the **Actions** tab, in the **Functions** group, choose **Reserve from Current Line**.  
  
 The quantity you entered in the firm planned production component line is now reserved.  
  
> [!NOTE]  
>  If item tracking lines exist for the sales order, the reservation system will take you through additional steps. For more information, see [How to: Reserve Item-Tracked Items](../FullExperience/how-to-reserve-item-tracked-items.md).  
  
## See Also  
 [How to: Reserve Items for Production Order Lines](../FullExperience/how-to-reserve-items-for-production-order-lines.md)   
 [How to: Amend or Cancel Item Reservations](../FullExperience/how-to-amend-or-cancel-item-reservations.md)   
 [How to: Track Item Reservations](../FullExperience/how-to-track-item-reservations.md)   
 [How to: View Item Availability](../FullExperience/how-to-view-item-availability.md)   
 [About Production Orders](../FullExperience/about-production-orders.md)