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
# How to: Set Up Service Price Adjustment Groups
You can use the **Serv. Price Adjmt. Group** window to set up price adjustment groups to adjust service pricing of service items. For example, you can set up price adjustment groups that adjust price of freight or spare parts.  
  
### To set up a service price adjustment group  
  
1.  In the **Search** box, enter **Service Price Adjustment Groups**, and then choose the related link.  
  
2.  Create a new service price adjustment group. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Fill in the **Code** and **Description** fields.  
  
4.  On the **Actions** tab, in the **General** group, choose **Details**. The **Serv. Price Adjmt. Detail** window opens.  
  
5.  In the **Type** field, enter the type of the entry that you want to adjust.  
  
6.  If you want the service price adjustment group to adjust only one specific entry, then enter the number of this entry in the **No.** field. When you leave this field blank, your adjustment group will adjust ALL entries of the type defined in the **Type** field.  
  
7.  If you want the service price adjustment group to adjust service prices related to only one specific service, you have to fill in the **Work Type** field. When you leave this field blank, it will just be ignored.  
  
8.  In the **Description** field, you can give a short description of the service price adjustment.  
  
9. If you want the service price adjustment group to adjust service prices related to only one specific general product posting group, you have to fill in the **Gen. Prod. Posting Group** field. When you leave this field blank, it will just be ignored.  
  
 Repeat these steps for each group of service lines that you want to adjust, by using a service price adjustment group.  
  
## See Also  
 [How to: Set Up Service Price Groups](../how-to-set-up-service-price-groups.md)   
 [How to: Set Up Service Price Adjustment Details](../how-to-set-up-service-price-adjustment-details.md)   
 [Service Price Management](../service-price-management.md)