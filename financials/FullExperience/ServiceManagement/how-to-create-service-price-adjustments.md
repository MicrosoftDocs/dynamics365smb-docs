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
# How to: Create Service Price Adjustments
You can assign service price groups to service items in the **Service Order** window. The service pricing breakdown is inserted for the items. You can then automatically create service price adjustments for costs, spare parts, and resource hours for these service items.  
  
 For more information, see [How to: Set Up Service Price Groups](../FullExperience/how-to-set-up-service-price-adjustment-groups.md).  
  
### To create a service price adjustment  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  After you have created service price adjustment groups and service price groups, open the relevant service order.  
  
3.  On the **Lines** FastTab, on the service item line that you want to create a service price adjustment for, in the **Service Price Group Code** field, select the relevant service price group code.  
  
    > [!NOTE]  
    >  The service price adjustment function does not apply to service items that belong to service contracts. You can only adjust the service prices of items that are part of a service order. You cannot adjust the price of a service item if it has a warranty. You cannot adjust the price of a service item on a service order if the service lines linked to it have been posted as **Invoice**, either fully or in part. When you run the service price adjustment function, all discounts in the order are replaced by the values of the service price adjustment.  
  
4.  Choose **Actions**![Action Menu icon](../FullExperience/media/actionmenuicon.png "actionMenuIcon"), choose **Order**, and then choose **Service Lines**. The **Service Lines** window opens. Enter the information regarding the service price adjustment of the service items on the order.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Adjust Service Price**. Choose the **Yes** button to confirm that you want to adjust service prices. The **Service Line Price Adjmt.** window opens.  
  
     This window gives you an overview of what the results of the price adjustment will be. You can approve of these results, or you can make further changes to the amounts in the window manually, if you want to obtain different end results.  
  
6.  Choose the **OK** button to confirm the service price adjustments.  
  
7.  Choose **Actions**![Action Menu icon](../FullExperience/media/actionmenuicon.png "actionMenuIcon"), choose **Order**, and then choose **Service Lines** to view the adjustments made automatically.  
  
## See Also  
 [How to: Change Service Pricing for Service Items](../FullExperience/how-to-change-service-pricing-for-service-items.md)   
 [Service Price Management](../FullExperience/service-price-management.md)   
 [How to: Set Up Service Price Groups](../FullExperience/how-to-set-up-service-price-groups.md)