---
    title: How to Post Service Orders | Microsoft Docs
    description: When you have created a service order, filled in all the necessary information and made any modifications, you can post the service order. The order must contain at least one service item line and one service line before you can post it. Should the order contain more than one service line, all the lines are posted at one time.
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
# How to: Post Service Orders
When you have created a service order, filled in all the necessary information and made any modifications, you can post the service order. The order must contain at least one service item line and one service line before you can post it. Should the order contain more than one service line, all the lines are posted at one time.  
  
### To post a service order  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Orders**, and then choose the related link.  
  
2.  Open the relevant service order.  
  
3.  In the **Service Order** window, on the **Actions** tab, in the **Posting** group, select one of the following functions.  
  
    |**Function**|**Result**|  
    |------------------|----------------|  
    |**Test Report**|Checks all parts of the document and presents the result in a report. If the report indicates any errors or a lack of information, you must correct the problem. You can then print a new test report.|  
    |**Post**|Posts the order without printing a shipment or an invoice.|  
    |**Post and Print**|Posts the order and prints a shipment (if you ship the order without invoicing it) or an invoice (if you invoice the order).|  
    |**Post Batch**|Posts multiple service orders at one time once.|  
  
4.  When you post the order, a window opens in which you must specify one of the following options for how you want to post the order.  
  
    |**Posting Option**|**Result**|  
    |------------------------|----------------|  
    |**Ship**|Posts shipment of the items.|  
    |**Invoice**|Invoices items that have already been shipped.|  
    |**Ship and Invoice**|Invoices and ships the items.|  
    |**Ship and Consume**|Posts shipment and consumption on the order. It updates the relevant quantities on the service lines of the order and on the previously posted service shipment document.|  
  
 A window opens showing the status of the posting process.  
  
 It is possible to post consumption only if there is some shipped and not invoiced and not consumed quantity on the line.  
  
 When posting the order, the corresponding ledger entries and posted documents are created. The relevant fields are updated in the service order document.  
  
## See Also  
 [How to: Batch Post Service Orders](../how-to-batch-post-service-orders.md)   
 [How to: Post Service Lines](../how-to-post-service-lines.md)   
 [How to: Prepare Service Line Items for Warehouse Handling](../how-to-prepare-service-line-items-for-warehouse-handling.md)   
 [How to: Post Shipments from Service Orders](../how-to-post-shipments-from-service-orders.md)   
 [How to: Post Invoices from Service Orders](../how-to-post-invoices-from-service-orders.md)   
 [How to: Post Consumption from Service Orders](../how-to-post-consumption-from-service-orders.md)   
 [How to: Check Service Orders Before Posting Them](../how-to-check-service-orders-before-posting-them.md)   
 [How to: Invoice Service Contracts](../how-to-invoice-service-contracts.md)   
 [How to: Print Test Reports Before Posting Service Documents](../how-to-print-test-reports-before-posting-service-documents.md)