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
# How to: Set Up Service Price Adjustment Details
You can use the **Serv. Price Adjmt. Detail** window to set up the details for the service price adjustment groups. For example, you can specify which item belongs to the service price adjustment group, and whether this is an item, a resource, a resource group, or a service charge.  
  
### To set up service price adjustment details  
  
1.  In the **Search** box, enter **Service Price Adjustment Groups**, and then choose the related link.  
  
2.  Open a   service price adjustment group.  
  
3.  On the **Actions** tab, in the **General** group, choose **Details**.  
  
4.  On the **Home** tab, in the **New** group, choose **New** to enter a new item in the service price adjustment group.  
  
5.  In the **Type** field, enter the type of the entry that you want to adjust.  
  
6.  If you want the service price adjustment group to adjust only one specific entry, then enter the number of this entry in the **No.** field. When you leave this field blank, your adjustment group will adjust ALL entries of the type defined in the **Type** field.  
  
7.  If you want the service price adjustment group to adjust service prices related to only one specific service, you have to fill in the **Work Type** field. When you leave this field blank, it will just be ignored.  
  
8.  In the **Description** field, you can give a short description of the service price adjustment.  
  
9. If you want the service price adjustment group to adjust service prices related to only one specific general product posting group, you have to fill in the **Gen. Prod. Posting Group** field. When you leave this field blank, it will just be ignored.  
  
 Repeat these steps for each service price adjustment group that you want to create.  
  
## See Also  
 [How to: Set Up Service Price Adjustment Groups](../FullExperience/how-to-set-up-service-price-adjustment-groups.md)   
 [Service Price Management](../FullExperience/service-price-management.md)