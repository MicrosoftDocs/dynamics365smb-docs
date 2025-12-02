---
title: How to create service orders
description: Learn the different tasks involved in creating service orders in Business Central such as creating a new service order or orders based on a service contract.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: service order, create service order, service management, service management setup, service item, service contract, service quote
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create service orders

You can use the **Service Order** page to create documents where you enter information about a service, such as repairs and maintenance, on service items by customer request.  

When creating a service order, you only have to fill in a few fields. Some fields are optional and many are automatically filled in when you fill in related fields.  

## Create a service order

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Orders**, and then choose the related link.  
2. Create a new service order.  
3. In the **No.** field, enter a number for the service order.  

    Alternatively, if you have set up number series for service orders on the **Service Management Setup** page, you can select <kbd>Enter</kbd> to select the next available service order number.  

4. In the **Customer No.** field, select the relevant customer from the list. The customer-relevant fields are filled in with information from the **Customer** table.  

5. Depending on the settings on the **Mandatory Fields** FastTab on the **Service Management Setup** page, you may need to fill in the **Service Order Type** field and the **Salesperson Code** field.  
6. Optionally, fill in the rest of the fields.  
7. Register the service item lines.  

## Create a service order from a contract

You can automatically create service orders for the maintenance of service items based on service contracts.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Create Contract Service Orders**, and then choose the related link.  
2. On the **Service Contract Header** FastTab, set the filters you want to apply.  
3. On the **Options** FastTab, fill in the **Starting Date** and **Ending Date** fields with the starting date and ending date for the period that you want to create contract service orders for. The batch job creates service orders that include service items in service contracts with next planned service dates within this period.  

    > [!NOTE]  
    > There's a limit to the number of days you can use as the date range each time you use this batch job. You set this limit in the **Contract Serv. Ord. Max. Days** field on the **Service Management Setup** page.  

4. In the **Action** field, choose **Create Service Order**.  
    > [!NOTE]  
    > You can't create order with multiple service item, if you set **One Service Item Line/Order** field on the **Service Management Setup** page.

## Convert a service quote to a service order

When a customer has accepted a service quote, you convert it to a service order. The quote is deleted and a new service order is set up with the same description as the service quote. The response date and time are recalculated for the service order and the status is set to **Pending**. The repair statuses of the service items in the order are changed to **Initial**.  

[!INCLUDE[prod_short](includes/prod_short.md)] searches for allocation entries for all the service items in the service quote that have the status **Active**. If it finds such allocation entries, their allocation status is updated to **Reallocation Needed**. When you reallocate the service items in the service order, the status of the allocation entries registered for the quote are updated to **Finished**.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Contract Quotes**, and then choose the related link.  
2. Choose the service quote to convert to a service order.  
3. Choose the **Make Order** action.  

## Check item availability for one or more orders

You can check and see if an item you need to fulfill an order is in stock, and if it isn't, when the item is in stock. In addition, if an item is available to reserve, you can reserve it to make sure it's available for your use. You can check availability for a particular order, or for all orders.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Dispatch Board**, and then choose the related link.  
2. Do one of the following:  

    * For a particular order, choose the order, and then choose the **Demand Overview** action.  
    * For all orders, choose **Show Document**. The **Service Order** page opens.  

3. On the **Demand Overview** page, expand the item grouping, and view information about the availability of the item. For example, you can see how many items are in inventory. You can also see if and when an item is available if it is on back order, that is, Source Type = Purchase, or whether it has been reserved.

## Reserve an item for a service order

If you need to be sure that an item is available for a service order, you can reserve the item.

1. In the **Search** box, enter **Service Orders**, and then choose the related link.  
2. Choose the service order, and then choose **Edit**.  
3. Choose **Actions**, choose **Order**, and then choose **Service Lines**.  
4. On the **Service Lines** page, choose the item to reserve, and then choose the **Reserve** action.  
5. On the **Reservation** page, choose **Reserve from Current Line**.

## Insert lines based on standard service codes

If you have set up standard service codes and assigned them to service item groups, you can insert the standard lines linked to the standard service codes on service documents. Learn more in [Set Up Standard Service Codes](service-how-setup-service-coding.md).

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Orders**, and then choose the related link.  
2. Create a new service order.  
3. Fill in the fields as necessary..  
4. Fill in the service item lines with the required information.  
5. Choose the line with the service item that you want to create service lines for, and then choose **Get Std. Service Codes**. The **Standard Serv. Item Gr. Codes** page opens with the standard codes for the service item group specified on the line.  
6. Choose the appropriate code, and choose the **OK** button to enter standard service lines.  

> [!NOTE]  
> If the **Service Item Group Code** field on the service item line of the document is blank, this means that the service item doesn't belong to any service item group. In this case, the **Standard Serv. Item Gr. Codes** page contains a list of all standard service codes. You should select from the list to insert standard service lines in the document. You may also select from the list of standard service codes assigned to a specific service item group. To view the list, select the relevant code in the **Service Item Group Code** field on the **Standard Serv. Item Gr. Codes** page.  

## Register internal or public comments

You can add comments that are printed on service orders and service quotes to provide additional information. You can add up to 80 characters, including spaces. If you need to enter additional text, choose another line. To register a comment, choose a line, and then choose the **Comments** action.  

## Delete invoiced service orders

Orders are deleted automatically after having been fully invoiced. When an invoice is posted, a corresponding entry is created on the **Posted Service Invoices** page. The posted document can be viewed on the **Posted Service Invoice** page.  

Service orders aren't deleted automatically, however, if the total quantity on the order has been posted not from the service order itself, but from the **Service Invoice** page. Then you may need to delete invoiced orders that weren't deleted. You can do this by running the **Delete Invoiced Service Orders** batch job.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Delete Invoiced Service Orders**, and then choose the related link. The **Delete Invoiced Service Orders** batch job request page opens.  
2. To select the orders to be deleted, you can set filters in the **No.**, **Customer No.**, and **Bill-to Customer No.** fields.  
3. Choose **OK**.  

## Related information

[Service Posting](service-service-posting.md)  
[Post a Service Order](service-how-to-post-service-orders.md)  
[Set Up Service Management](service-setup-service.md)  
[Work on Service Tasks](service-how-to-work-on-service-tasks.md)  
[Allocate Resources](service-how-to-allocate-resources.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
