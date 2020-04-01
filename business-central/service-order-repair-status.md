---
    title: Set Up Statuses for Service Orders and Repairs | Microsoft Docs
    description: You must set up nine repair status options that identify the progress of repair and maintenance of service items in service orders.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Set Up Statuses for Service Orders and Repairs
You must set up repair status options that identify the progress of repair and maintenance of service items in service orders. You must set up at least nine repair status options that identify situations or actions taken when servicing service items.  

You can set the priority level for service order status options. There four priorities are High, Medium High, Medium Low, and Low.  

When you change the repair status of a service item in a service order, the service order status is updated. The repair status of each service item is linked to the service order status. If the service items are linked to two or more service order status options, the service order status with the highest priority is selected.  

## To set up a repair status  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Repair Status**, and then choose the related link.
2. Create a new repair status.  
3. Fill in the **Code** and **Description** fields.  
4. In the **Service Order Status** field, choose the order status to link the repair status to. The **Priority** field displays the priority of the service order status you have chosen.  
5. Choose a repair status. You can choose only one.  
6. To be able to post service orders, including service items, with this repair status, choose the **Posting Allowed** field.  
7. To be able to manually change the service order status option to **Pending** in service orders including service items with this repair status, choose the **Pending Status Allowed** check box.  
8. Choose the **In Process Status Allowed**, **Finished Status Allowed**, and **On Hold Status Allowed** check boxes in the same way.
  
## To set up service status priorities  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Order Status**, and then choose the related link.  
2. Select the service order status you want to set a priority for.  
3. In the **Priority** field, choose the priority you want for this service order status. Repeat this step for each status.  

## See Also  
[Service Order Status and Repair Status](service-service-order-status-and-repair-status.md)  
[Setting Up Service Management](service-setup-service.md)  
