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
# How to: Create Combined Invoices
Using this procedure, you can invoice the customer for services provided on different service orders. Invoice lines are created for items, resource hours, or costs that have already been shipped from different service orders but not yet invoiced.  
  
### To create a combined invoice  
  
1.  In the **Search** box, enter **Service Invoices**, and then choose the related link.  
  
2.  Create a new service invoice.  
  
3.  Specify the customer you want to invoice and fill in the document header.  
  
4.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Functions**, and then choose **Get Shipment Lines**. The **Get Service Shipment Lines** window displays all the shipped but not invoiced lines for the specified customer.  
  
5.  In the **Get Service Shipment Lines** window, select the lines for the service you want to invoice, and then choose the **OK** button to insert the service shipment lines into the invoice. The selected lines are copied to the service invoice.  
  
## See Also  
 [How to: Invoice Posted Shipment Lines](../how-to-invoice-posted-shipment-lines.md)   
 [How to: Get Service Shipment Lines](../how-to-get-service-shipment-lines.md)