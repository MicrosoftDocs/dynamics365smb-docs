---
    title: How to Create Service Quotes | Microsoft Docs
    description: You can use the **Service Quote** window to create documents where you enter information about a service, such as repairs and maintenance, on service items by customer request. You can use a service quote as a preliminary draft for a service order, and then convert the quote to a service order.
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
# How to: Create Service Quotes
You can use the **Service Quote** window to create documents where you enter information about a service, such as repairs and maintenance, on service items by customer request. You can use a service quote as a preliminary draft for a service order, and then convert the quote to a service order.  
  
## To create a service quote  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Quotes**, and then choose the related link.  
2. Create a new service quote.  
3. In the **No.** field, enter a number for the service quote. Alternatively, if you have set up a number series for service quotes in the **Service Mgt. Setup** window, you can press Enter to select the next available service quote number.  
4. In the **Customer No.**  field, select the relevant customer from the list.  

  > [!Note]  
  >  The customer fields are filled in automatically with information from the **Customer** card. If a **Customer** card does not exist for the customer, and you have set up a customer template, you can create the customer from the service quote. Fill in the relevant fields, and then choose the **Create Customer** action.  
  
5. Depending on the settings on the **Mandatory Fields** FastTab in the **Service Mgt. Setup** window, you may need to fill in the **Service Order Type** field and the **Salesperson Code** field.  
6. Fill in the service item lines.  
7. Register estimated costs on the service lines.  
  
## See Also  
 [How to: Register Service Item Lines](../how-to-register-service-item-lines.md)   
 [How to: Create Customers within Service Orders](../how-to-create-customers-within-service-orders.md)   
 [How to: Register Service Order Comments](../how-to-register-service-order-comments.md)   
 [How to: Allocate Resources by Using Resource Availability](../how-to-allocate-resources-by-using-resource-availability.md)   
 [How to: Convert Service Quotes to Service Orders](../how-to-convert-service-quotes-to-service-orders.md)   
 [How to: Create Service Orders](../how-to-create-service-orders.md)   
 Service Mgt. Setup