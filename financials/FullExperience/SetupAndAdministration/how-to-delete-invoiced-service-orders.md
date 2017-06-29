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
# How to: Delete Invoiced Service Orders
Orders are usually deleted automatically after having been fully invoiced. When an invoice is posted, a corresponding entry is created in the **Posted Service Invoices** window. The posted document can be viewed in the **Posted Service Invoice** window.  
  
 Service orders are not deleted automatically, however, if the total quantity on the order has been posted not from the service order itself, but from the **Service Invoice** window. Then you may need to delete invoiced orders that were not deleted. You can do this by running the **Delete Invoiced Service Orders** batch job.  
  
### To delete invoiced service orders  
  
1.  In the **Search** box, enter **Delete Invoiced Service Orders**, and then choose the related link. The **Delete Invoiced Service Orders** batch job request window opens.  
  
2.  To select the orders to be deleted, you can set filters in the **No.**, **Customer No.**, and **Bill\-to Customer No.** fields.  
  
3.  Choose the **OK** button.  
  
## See Also  
 [How to: View Additional Information About Posted Service Documents](../Service/how-to-view-additional-information-about-posted-service-documents.md)