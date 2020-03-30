---
    title: How to Create Service Orders | Microsoft Docs
    description: You can use the **Service Order** page to create documents where you enter information about a service, such as repairs and maintenance, on service items by customer request.
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
# Create Service Orders
You can use the **Service Order** page to create documents where you enter information about a service, such as repairs and maintenance, on service items by customer request.  

When creating a service order, you only have to fill in a few fields. Some fields are optional and many are automatically filled in when you fill in related fields.  

## To create a service order    
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.  
2. Create a new service order.  
3. In the **No.** field, enter a number for the service order.  

     Alternatively, if you have set up number series for service orders on the **Service Management Setup** page, you can press Enter to select the next available service order number.  

4. In the **Customer No.** field, select the relevant customer from the list. The customer-relevant fields are filled in with information from the **Customer** table.  

5. Depending on the settings on the **Mandatory Fields** FastTab on the **Service Management Setup** page, you may need to fill in the **Service Order Type** field and the **Salesperson Code** field.  
6. Optionally, fill in the rest of the fields.  
7. Register the service item lines.  

## To create a service order from a contract  
You can automatically create service orders for the maintenance of service items based on service contracts.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Create Contract Service Orders**, and then choose the related link.  
2. On the **Service Contract Header** FastTab, set the filters you want to apply.  
3. On the **Options** FastTab, fill in the **Starting Date** and **Ending Date** fields with the starting date and ending date for the period that you want to create contract service orders for. The batch job creates service orders that include service items in service contracts with next planned service dates within this period.  

    > [!NOTE]  
    >  There is a limit to the number of days you can use as the date range each time you use this batch job. You set this limit in the **Contract Serv. Ord. Max. Days** field on the **Service Management Setup** page.  

4. In the **Action** field, choose **Create Service Order**.  
    > [!NOTE]  
    >  You will not be able to create order with multiple service item, if you set **One Service Item Line/Order** field on the **Service Management Setup** page. 

## To convert a service quote to a service order
When a customer has accepted a service quote, you convert it to a service order. The quote is deleted and a new service order is set up with the same description as the service quote. The response date and time are recalculated for the service order and the status is set to **Pending**. The repair status of the service items in the order are changed to **Initial**.  

[!INCLUDE[d365fin](includes/d365fin_md.md)] searches for allocation entries for all the service items in the service quote that have the status **Active**. If it finds such allocation entries, their allocation status is updated to **Reallocation Needed**. When you reallocate the service items in the service order, the status of the allocation entries registered for the quote are updated to **Finished**.   

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contract Quotes**, and then choose the related link.  
2. Choose the service quote to convert to a service order.  
3. Choose the **Make Order** action.  

## To check item availability for one or more orders  
You can check and see if an item you need to fulfill an order is in stock, and if it is not, when the item will be in stock. In addition, if an item is available to reserve, you can reserve it to make sure it is available for your use. You can check availability for a particular order, or for all orders.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dispatch Board**, and then choose the related link.  
2. Do one of the following:  

    * For a particular order, choose the order, and then choose the **Demand Overview** action.  
    * For all orders, choose **Show Document**. The **Service Order** page opens.  

3. On the **Demand Overview** page, expand the item grouping, and view information about the availability of the item. For example, you can see how many items are in inventory. You can also see if and when an item will be available if it is on back order, that is, Source Type = Purchase, or whether it has been reserved.

## To reserve an item for a service order
If you need to be sure that an item is available for a service order, you can reserve the item.

1. In the **Search** box, enter **Service Orders**, and then choose the related link.  
2. Choose the service order, and then choose **Edit**.  
3. Choose **Actions**, choose **Order**, and then choose **Service Lines**.  
4. On the **Service Lines** page, choose the item to reserve, and then choose the **Reserve** action.  
5. On the **Reservation** page, choose **Reserve from Current Line**.

## To insert lines based on standard service codes  
If you have set up standard service codes and assigned them to service item groups, you can insert the standard lines linked to the standard service codes on service documents. For more information, see [Set Up Standard Service Codes](service-how-setup-service-coding.md).   

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.  
2. Create a new service order.  
3. Fill in the fields as necessary..  
4. Fill in the service item lines with the required information.  
5. Choose the line with the service item that you want to create service lines for, and then choose **Get Std. Service Codes**. The **Standard Serv. Item Gr. Codes** page opens with the standard codes for the service item group specified on the line.  
6. Choose the appropriate code, and choose the **OK** button to enter standard service lines.  

> [!NOTE]  
>  If the **Service Item Group Code** field on the service item line of the document is blank, this means that the service item does not belong to any service item group. In this case, the **Standard Serv. Item Gr. Codes** page will contain a list of all standard service codes. You should select from the list to insert standard service lines in the document. You may also select from the list of standard service codes assigned to a specific service item group. To view the list, select the relevant code in the **Service Item Group Code** field on the **Standard Serv. Item Gr. Codes** page.  

## To register internal or public comments
You can add comments that will be printed on service orders and service quotes to provide additional information. You can add up to 80 characters, including spaces. If you need to enter additional text, choose another line. To register a comment, choose a line, and then choose the **Comments** action.  

## To delete invoiced service orders  
Orders are usually deleted automatically after having been fully invoiced. When an invoice is posted, a corresponding entry is created on the **Posted Service Invoices** page. The posted document can be viewed on the **Posted Service Invoice** page.  

Service orders are not deleted automatically, however, if the total quantity on the order has been posted not from the service order itself, but from the **Service Invoice** page. Then you may need to delete invoiced orders that were not deleted. You can do this by running the **Delete Invoiced Service Orders** batch job.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Invoiced Service Orders**, and then choose the related link. The **Delete Invoiced Service Orders** batch job request page opens.  
2. To select the orders to be deleted, you can set filters in the **No.**, **Customer No.**, and **Bill-to Customer No.** fields.  
3. Choose **OK**.  


## See Also  
[Service Posting](service-service-posting.md)  
[Post a Service Order](service-how-to-post-service-orders.md)  
[Setting Up Service Management](service-setup-service.md)  
[Work on Service Tasks](service-how-to-work-on-service-tasks.md)  
[Allocate Resources](service-how-to-allocate-resources.md)  
