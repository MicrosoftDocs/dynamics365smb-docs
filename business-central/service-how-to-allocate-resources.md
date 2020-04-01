---
    title: How to Allocate Resources | Microsoft Docs
    description: You can change the annual amount of the service contract or contract quote to correct the amount that will be invoiced annually.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---

# Allocate Resources
The key element to service management is the people who supply service. You can set up [!INCLUDE[d365fin](includes/d365fin_md.md)] to assign the appropriate people to the appropriate jobs. Assignments can be based on service zones where the people are located or where the service occurs. In addition, you can group resources together when responding to service requests. For more information, see [Set Up Resource Allocation](service-how-setup-resource-allocation.md).

You can allocate resources, for example, technicians, by using the **Dispatch Board**, or from a service order. You can use resource availability to allocate resources to perform the service tasks in the orders or quotes.

You can allocate the same resource, for example, a technician, or resource group to all the service items in a service order. Allocation entries are created for the other service items in the order with the same resource number and allocation date as the line you allocated. The allocated hours are the hours you allocated divided by the number of service items in the order. The **Status** field is automatically set to **Active** for all the entries that were created.

## To see an overview of service orders and service quotes  
You may often need to see the list of service orders or service quotes that meet certain requirements to be able to perform specific actions with them one by one. For example,you may need to allocate resources to service orders that belong to a specific customer.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dispatch Board**, and then choose the related link.  
2. In the **Document Filter** field, choose the type of the documents you want to see.
3. To get a list of documents that contain service tasks a certain resource or resource group is allocated to, fill in the **Resource Filter** and **Resource Group Filter** fields and press Enter.  
4. To get a list of documents with a certain response date or response dates within a certain date period, fill in the **Response Date Filter** field and press **Enter**.  
5. To get a list of documents with a specified allocation state or document status, fill in the **Allocation Filter/Status Filter** field and press **Enter**.  
6. To get a list of documents that belong to a certain contract, customer, or zone, fill in the **Contract Filter/Customer Filter/Zone Filter** field and press **Enter**.  
7. Choose a line that corresponds to a service order or service quote, and then choose the **Show Document** action.  

    The **Service Order** or **Service Quote** page opens, and you can work with the document. To return to the **Dispatch Board** page, choose **OK**.

## To allocate a resource using resource or resource group availability    
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dispatch Board**, and choose the related link.  
2. Choose the service order, and then choose the **Resource Allocations** action.  
3. Choose the entry with the service task to which you want to allocate a resource.  
4. Choose either the **Resource Availability** or **Res. Group Availability** action.  
5. On the **Res. Availability (Service)** page, choose **Show Matrix**.  
6. Choose a resource to allocate. You can base your selection on whether the resource is skilled for the task, whether it is located in the customer zone, and/or whether it is preferred by the customer.  
7. Specify a date on which the resource has enough available hours for the task, and which is close to the response date of the service order.  
8. In the **Qty. to Allocate** field, enter the number of hours you want to allocate the resource to the service task for.  
9. Choose the **Allocate** action to allocate the selected resource on the selected date.  

     The **Status** field is automatically set to **Active**.  

 Repeat these steps for each date that you want to allocate the resource to the service task.  

> [!NOTE]  
>  For a service item in a service order, there can only be **Active** allocation entries with one resource or resource group at a time.  

## To allocate a resource using a service order  
After you have created and filled in a service order or service quote, you can allocate resources, for example, technicians, to perform service tasks registered as service item lines in the document.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.  
2. Choose the service order, and then choose **Edit**.  
3. Choose the service item line corresponding to the service task you want to allocate a resource to.  
4. Choose **Resource Allocations**.
5. On the **Resource Allocations** page, choose a nonactive allocation entry with the service task you want to allocate the resource to. If the allocation entry does not exist, you can create a new one by choosing **New**.  
7. Specify the service task by filling in the **Service Item No.** field on the same line.  
8. In the **Resource No.** field, choose the resource. If the resource is a member of a resource group, the number of the resource group is entered automatically into the **Resource Group No.** field.  
9. Fill in the **Allocation Date** and **Allocated Hours** fields. The **Status** field is set to **Active**. This means that the resource is allocated to the service task.  
10. Optionally, to assign the resource to all items, choose **Allocate to All Service Items**.

> [!NOTE]  
>  For a service item in a service order, there can only be active allocation entries with one resource or resource group at a time.

## To reallocate resources on a service order  
You can reallocate resources directly from a service order or service quote when you are working with it. The original entry will still exist, but its status is updated as follows:  

* If service was started while the allocation was **Active**, that is, if the repair status of the service item in the entry was changed to **In Process**, the allocation status changes from **Reallocation Needed** to **Finished**.  
* If service was not started while the allocation was **Active**, allocation status changes from **Reallocation Needed** to **Canceled**.  
* If you are reallocating a service order that you have converted from a quote, the status of the allocation entries registered for the quote always changes to **Finished** when you reallocate the service items in the service order.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.  
2. Open the relevant service order.  
3. Select the service item line corresponding to the service task you want to allocate a resource to, and then choose the **Resource Allocations** action.  
4. On the **Resource Allocations** page, select an allocation entry with the service task you want to reallocate the resource to. In the **Resource No.** field, select the relevant resource. This overwrites the resource number already in the field.  
5. Press the Enter key. A dialog box opens, asking whether you want to reallocate this entry. Fill in the **Reason Code** field if appropriate and choose the **Yes** button to confirm the reallocation.  
6. Fill in the **Allocation Date** and **Allocated Hours** fields. The entry now contains the new resource and its status is **Active**.

## To reallocate a resource using the dispatch board  
If the resource allocated to a service task cannot accomplish the work, it means that this service task needs reallocation. Usually you reallocate resources to a service task by using the **Dispatch Board**.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dispatch Board**, and then choose the related link.  
2. In the **Allocation Filter** field, select **Reallocation Needed**. The **Dispatch Board** page now shows the list of service orders that include service tasks that need reallocation.  
3. Select the relevant service order, and then choose the **Resource Allocations** action. The **Resource Allocations** page opens.  
4. Select the allocation entry with the service task you want to reallocate a resource to.  
5. In the **Resource No.** field, select the relevant resource. It overwrites the resource number already in the field.  
6. Press Enter. The **Reallocation Entry Reasons** dialog box opens, asking whether you want to reallocate this entry. Fill in the **Reason Code** field if appropriate and choose the **Yes** button to confirm the reallocation.  
7.  Fill in the **Allocation Date** and **Allocated Hours** fields. The entry now contains the new resource and its status is **Active**.  

    > [!NOTE]  
    >  The old entry still exists but the status is updated in the following ways:  
    >   
    >  * If service was started while the allocation was **Active**, that is, if the repair status of the service item in the entry was changed to **In Process**, the allocation status changes from **Reallocation Needed** to **Finished**.  
    > * If service was not started while the allocation was **Active**, the allocation status changes from **Reallocation Needed** to **Canceled**.  
    > * If you are reallocating a service order that you have converted from a quote, the status of the allocation entries registered for the quote always changes to **Finished** when you reallocate the service items in the service order.  

## To register resource hours  
When working on service items in service orders, you need to register the resource hours used for the service. The following procedure shows how to register the resource hours on the **Service Item Worksheet** page.  

You can use the same procedure to register the hours on the **Service Lines** page, which you can open from the Service Order page. Open the relevant service card, and then choose the **Service Lines** action.  

If the same resource works on all the service items in the service order, you can register the total resource hours for one service item only and then split the resource line to assign the resource hours to the other service items.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Tasks**, and then choose the related link.
2. Select the line that includes the relevant service item, and then choose the **Item Worksheet** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To assign a resource to all service items in an order
If the same resource, for example a technician, works on all the service items in the service order, you can register the total resource hours for one service item only and then split the resource line to divide the resource hours onto the resource lines for the other service items.  

The following procedure shows how to split resource lines on the **Service Invoice Lines** page.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.  
2. Open the relevant service order.  
3. On the **Lines** FastTab, choose the **Service Lines** action. The **Service Lines** page opens.  
4. Select the resource line you want to split. The contents of the **Quantity** field is divided between all the service items in the order.  
5. Choose the **Split Resource Line** action. Choose **Yes** to confirm.  

    Resource lines for the other service items in the order are created with the same resource number as the line you split. The quantity is the quantity for the line you split divided by the number of service items in the order.  

## To cancel an allocation  
You can cancel resource allocations for service tasks without reallocating the tasks.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dispatch Board**, and then choose the related link.  
2. Choose the service order, and then choose the **Resource Allocations** action.  
3. Choose the allocation entry with the service task that you want to cancel allocation for.  
4. Choose the **Cancel Allocation** action.  
5. In the **Reason Code** field, select the appropriate reason code.  
6. Choose **Yes** to confirm the cancellation.  

    > [!NOTE]  
    > In the **Status** field, the **Reallocation Needed** option is automatically selected. If the repair status of the service item in the entry is **Initial**, the repair status is changed to **Referred**, that is, no service has been started. If the repair status is **In Process**, it is changed to **Partly Serviced**, that is, some service has been completed.

## See Also
[Set Up Resource Allocation](service-how-setup-resource-allocation.md)  
[Allocation Status and Repair Status](service-allocation-status-and-repair-status.md)  
