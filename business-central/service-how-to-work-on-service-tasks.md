---
    title: How to Work on Service Tasks | Microsoft Docs
    description: After you have created a service order or service quote, registered service item lines, and allocated resources to the service items in the order or quote, you can start repairing and maintaining the service items.
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
# Work on Service Tasks
After you have created a service order or service quote, registered service item lines, and allocated resources to the service items in the order or quote, you can start repairing and maintaining the service items.  

[!INCLUDE[d365fin](includes/d365fin_md.md)] features a **Service Tasks** page that gives an overview of all the service items that need attention. Think of it as your service dashboard where you can see what orders are pending, look for and register spare parts, and keep your inventory up-to-date.  

To track changes and get a graphical view of your service business, use [!INCLUDE[d365fin](includes/d365fin_md.md)] statistics tools for quick, automatically generated charting and analysis.  

## To work on a service task  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Tasks**, and then choose the related link.
2. If you want a list of service tasks a certain resource or resource group is allocated to, fill in the **Resource Filter** or **Resource Group Filter** field and press Enter.  
3. If you want a list of service tasks with a certain response date or response dates within a certain time period, fill in the **Response Date Filter** field and press Enter.  
4. If you want a list of service tasks with a certain allocation status or repair status, fill in the **Allocation Status Filter** or **Repair Status Code Filter** field and press Enter.  
5. Select the service task you want to work on. Choose the **Item Worksheet** action. The **Service Item Worksheet** page opens.  
6. Register standard texts, spare parts, resource hours, and costs as appropriate using the corresponding options in the **Type** field:  <Blank>, **Item**, **Resource**, and **Cost**.  
7. In the **Repair Status** field, select the appropriate status.  

   > [!NOTE]  
   >  Fill in the **Repair Status** field with the **Finished** or **Partly Serviced** status if the service item has been completely serviced or another resource will continue servicing. The **Finished** or **Reallocation Needed** status is specified automatically for the allocation entry corresponding to the service item.  

## To register service operations  
When performing a service on a service order, you can register the details specifying the items used, costs incurred, and the time spent. The data you specify is stored on the **Service Item Worksheet** page. You can update the data when necessary.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.  
2. Open the service order to register the service for, and choose the item line.  
3. Choose the **Service Item Worksheet** action  
4. On the lines, specify the items used, costs incurred, and the time spent on the service.  

   > [!NOTE]  
   >  You can also register service directly on the service lines linked to the service order.  

## To register spare parts  
When working on service items in service orders, you may need to use spare parts for the service. The following procedure shows how to register the spare parts you use on the **Service Item Worksheet** page.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Tasks**, and then choose the related link.
2. Choose the line that includes the relevant service item, and then choose the **Item Worksheet** action.  
3. Enter a new service line.  
4. In the **Type** field, choose **Item**.  
5. In the **No.** field, choose the relevant spare part.  
6. In the **Quantity** field, enter the quantity of items you want to use.  

 You can use a similar procedure to register the spare parts on the **Service Lines** page, which you can open from the **Service Order** page.  

## To register spare parts from a service order  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.  
2. Open the service order you want to register spare parts for.  
3. Choose the line that includes the relevant service item. Choose **Actions**, choose **Order**, and then choose **Service Lines**.  
4. enter a new service line.  

## To replace a service item or a service item component  
When you service a service item that is composed of components, you may need to replace a faulty component with a new one. Every time that you enter a spare part for a service item with components, you have the option of replacing a component or creating a new one. The new item is not registered as a component of the service item until you post this service line or the service order.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Tasks**, and then choose the related link.
2. Choose the line that includes the service item, and then choose the **Item Worksheet** action.  
3. Enter a new service line.  
4. In the **Type** field, choose **Item**.  
5. In the **No.** field, choose the component to replace.  
6. Press **Enter**. A dialog box opens with three options: **Replace Component**, **New Component**, and **Ignore**. The following table describes the options.  

    |Option | Description|  
    |----------------------------------|---------------------------------------|  
    |**Replace Component**|Changes the status of the component you are replacing to not active, and it will appear on the replaced component list for the service item.|  
    |**New Component**|Enters the new component in the component list of the service item.|  
    |**Ignore**|Does nothing to the component list of the service item.|  

7. Choose **Replace Component**.  
8. Choose the component to replace, and then choose **OK**.  

## To change the response time for a service item line  
When you register a service item line in a service order or quote, depending on whether the service item is on a service contract the response time in hours is automatically entered and the response date and time are calculated accordingly. You can change the response time in hours and the response date and time if you need to.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders** or **Service Quotes**, and then choose the related link.  
2. Choose the service order or quote to open the card.  
3. On the service item line you want to change the response time for, either in the **Response Time (Hours)** field or in the **Response Date** and **Response Time** fields, enter the new response hours or response date and time.  

## To register fault/resolution codes  
After repairing a service item, you can register both the fault code and the resolution code for the item by selecting a combination from the existing fault/resolution codes relationships. The fault and resolution codes will appear in the corresponding fields on the **Service Item Worksheet** page. You can also register the codes directly in this page.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Tasks**, and then choose the related link.
2. Choose the line that includes the relevant service item, and then choose the **Item Worksheet** action.  
3. On the **Service Item Worksheet** page, choose **Fault/Resol. Codes Relationships**. The **Fault/Resolution Codes Relationships** page opens.  

  >  [!NOTE]
  >  Filters are set on the relationships that are shown on the page by copying the service item group and the fault codes from the **Service Item Worksheet** page.  

4. Fill out the line. Choose the combination of fault and resolution codes, and then choose **OK** to copy it to the service item. If an appropriate combination cannot be found, you can create a new combination on the page.  

## See Also  
[Set Up Fault Reporting](service-how-setup-fault-reporting.md)
[Allocation Status and Repair Status](service-allocation-status-and-repair-status.md)  
[Service Posting](service-service-posting.md)  
