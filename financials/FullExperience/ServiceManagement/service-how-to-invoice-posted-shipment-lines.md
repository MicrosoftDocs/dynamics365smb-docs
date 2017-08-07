---
    title: How to Invoice Posted Shipment Lines | Microsoft Docs
    description: You might need to create a service invoice for the service that has already been shipped, either from one or several service orders, but not yet invoiced or consumed. You can fill in the invoice lines automatically with the selected posted shipment lines for a specific customer.
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
# How to: Invoice Posted Shipment Lines
You might need to create a service invoice for the service that has already been shipped, either from one or several service orders, but not yet invoiced or consumed. You can fill in the invoice lines automatically with the selected posted shipment lines for a specific customer.  
  
### To invoice posted shipment lines  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Invoices**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**. Create a new service invoice.  
  
3.  Fill in the fields on the **General** FastTab.  
  
4.  Create invoice lines for services shipped but not invoiced. Alternatively, you can run the **Get Shipment Lines** function.  
  
    1.  Choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Functions**, and then choose **Get Shipment Lines**.  
  
    2.  In the **Get Service Shipment Lines** window, select the shipment lines that you want to invoice, and choose the **OK** button. The selected posted shipment lines are inserted into the invoice.  
  
5.  Post the service invoice.  
  
 The posted service invoice is created, as well as the corresponding ledger entries. Previously posted shipment documents are updated with the invoiced quantities and the relevant quantities on the service lines of the source orders.  
  
## See Also  
 [How to: Create Combined Invoices](../how-to-create-combined-invoices.md)   
 [How to: Create Service Invoices Manually](../how-to-create-service-invoices-manually.md)   
 [How to: Post Invoices from Service Orders](../how-to-post-invoices-from-service-orders.md)   
 [How to: Undo Service Shipments](../how-to-undo-service-shipments.md)