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
# How to: Create Customers within Service Orders
When you create service orders for customers that are not registered in ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]-->, you can create the customers within the **Service Order** or **Service Quote** windows.  
  
 You need to set up customer templates before you can create customers within service orders. For more information, see [How to: Set Up Customer Templates](../how-to-set-up-customer-templates.md).  
  
### To create a customer within a service order  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  Create a new service order.  
  
3.  In the **No.** field, enter a number for the service order.  
  
     Alternatively, if you have set up number series for service orders in the **Service Mgt. Setup** window, you can press the Enter key to select the next available service order number.  
  
4.  Fill in the **Name** , **Address**, and **Post Code\/City** fields for the new customer.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Create Customer**. The **Customer Templates List** window opens. Browse to the relevant template, and then choose the **OK** button.  
  
 A number is automatically assigned to the new customer and a customer card is created with the relevant fields in the service order filled in by copying information from the service customer template.  
  
## See Also  
 [How to: Create Service Orders](../how-to-create-service-orders.md)