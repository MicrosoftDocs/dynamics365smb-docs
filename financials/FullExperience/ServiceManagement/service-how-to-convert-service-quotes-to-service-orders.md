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
# How to: Convert Service Quotes to Service Orders
When a customer has accepted a service quote, you convert it to a service order.  
  
 You must have already created the service quote.  
  
### To convert a service quote to a service order  
  
1.  In the **Search** box, enter **Service Contract Quotes**, and then choose the related link.  
  
2.  Select the relevant service quote that you want to convert to a service order.  
  
3.  On the **Actions** tab, in the **General** group, choose **Make Order**.  
  
 The quote is converted to an order. It is deleted from the window and a new service order is set up with the same description as the service quote. The response date and time are recalculated for the service order and the status is set to **Pending**. The repair status of the service items in the order are changed to **Initial**.  
  
 ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> searches for allocation entries for all the service items in the service quote that have the status **Active**. If it finds such allocation entries, their allocation status is updated to **Reallocation Needed**. When you reallocate the service items in the service order, the status of the allocation entries registered for the quote are updated to **Finished**.  
  
## See Also  
 [How to: Create Service Quotes](../how-to-create-service-quotes.md)