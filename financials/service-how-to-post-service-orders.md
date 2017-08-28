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
# How to: Post Service Orders and Credit Memos
When you have created a service order, filled in all the necessary information and made any modifications, you can post the service order. The order must contain at least one service item line and one service line before you can post it. Should the order contain more than one service line, all the lines are posted at one time.  

If you have a large number of service orders, you can save time by using a batch job to post them.

> [!Tip]
> Before you post a service document, it's a good idea to use the **Test Report** action to to check for any errors or missing information. If there are errors, you must correct the problem. You can print a new test report to verify the fix, and then post the document.
  
## To post a service order    
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Orders**, and then choose the related link.  
2. Open the relevant service order.  
3. On the **Service Order** page, choose one of the following actions.  
  
    |**Action**|**Result**|  
    |------------------|----------------|  
    |**Test Report** | Checks all parts of the document and presents the result in a report. If the report indicates any errors or a lack of information, you must correct the problem. You can then print a new test report.|  
    |**Post** | Posts the order without printing a shipment or an invoice.|  
    |**Post and Print** | Posts the order and prints a shipment (if you ship the order without invoicing it) or an invoice (if you invoice the order).|  
    |**Post Batch** | Posts multiple service orders at one time once.|  
  
4. When you post the order, you must specify one of the following options for how you want to post the order.  
  
    |**Posting Option**|**Result**|  
    |------------------------|----------------|  
    |**Ship** | Posts shipment of the items.|  
    |**Invoice** | Invoices items that have already been shipped.|  
    |**Ship and Invoice** | Invoices and ships the items.|  
    |**Ship and Consume** | Posts shipment and consumption on the order. It updates the relevant quantities on the service lines of the order and on the previously posted service shipment document.|  
  
You can post consumption only if the line contains a quantity that has shipped but not invoiced or consumed.  
  
When posting the order, the corresponding ledger entries and posted documents are created. The relevant fields are updated in the service order document.  

## To batch post service orders
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Orders**, and then choose the related link.  
2. Choose the **Post Batch** action. 
  
     When you use the **Batch Post Service Orders** batch job, it does not matter which service order you work from.  
  
3.  You can set a filter to select specific service order numbers or an interval of order numbers for the batch job to process.  
4.  Choose **OK** to start the batch job.  

## To post a service credit memo  
When you have created a service credit memo and filled it in, you can post the credit memo. If there are errors or a lack of information on the credit memo while posting, the process will be interrupted by an error message.  
   
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Credit Memos**, and then choose the related link.  
2. Create a new service credit memo. On the **Home** tab, in the **New** group, choose **New**.  
3. Fill in the necessary fields.  
4. On the **Actions** tab, in the **Posting** group, choose **Post**. If you want to print the credit memo at the same time as you post, choose **Post and Print** instead.  
  
 To test credit memos before you post them,  choose **Test Report**. When you run the report, the posting dates specified in the document are verified, and so on.  
  
 To post several service credit memos at the same time. run the **Batch Post Service Cr. Memos** batch job. This can be an advantage if you have a large number of credit memos that must be posted.  
  
> [!NOTE]  
>  It is important to enter all the necessary information on the credit memos before they are batch posted. Otherwise, it is possible that they will not be posted. When the batch job has finished posting, a message is displayed that shows how many of the service credit memos have been posted.  

## To post consumption from a service order  
The following procedure describes how to post the items, resource hours, and or costs used for a specific service operation for which you will not charge your customer. It is not possible to post consumption before posting shipment and you cannot post consumption for lines where all quantity shipped has already been invoiced. Note that you can post consumed items, hours, or costs only for a posted shipment that has no posted invoices or consumption.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Orders**, and then choose the related link.  
2. Open the service order to post consumption for.  
3. Choose the service item. Choose **Actions**, choose **Order**, and then choose **Service Lines**.  
4. Find the required entries, and specify the quantities for which you will post consumption in the **Qty. to Consume** field. The quantity cannot be larger than the quantity already shipped and the quantity remaining but not invoiced after partial invoicing of this shipment.  
  
    > [!NOTE]  
    >  To register consumption with respect to a job, fill in the **Job No.**, **Job Task No.**, and the **Job Line Type** fields on the service line.  
  
5. Choose the lines to post, and then choose the **Post** action. On the page that opens, select **Ship and Consume**.  
  
The service is posted as consumed either partially or fully, depending on the value in the **Qty. to Consume** field, and the relevant ledger entries are created. In addition,previously posted service shipment documents are updated chronologically with the consumed quantities. The relevant quantities will be updated on the service lines of the order.  

## To undo posted consumption  
You can cancel the consumption on the service orders. For example, because it was posted by mistake.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Service Shipments**, and then choose the related link.  
2. Open the posted service shipment for which the erroneous consumption was posted.  
3. On the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Shipment**, and then choose **Service Shipment Lines**.  
4. In the **Posted Service Shipment Lines** window, select the lines containing the incorrect consumption. On the **Actions** tab, in the **Functions** group, choose **Undo Consumption**.  
  
 A balancing service shipment line is inserted with negative values in the quantity fields for the selected lines.  
  
> [!NOTE]  
>  You cannot undo service consumption if:  

>    * The service order has been closed.  
>    * It has been posted to the Jobs area, so there are job ledger entries linked to it.  
  
## To post service lines  
If you have to work on a service order for a considerable time without posting it, you may want to post some of the service lines linked to it as a way, for example, of keeping your inventory updated. You can post by specifying the relevant quantities on the lines to be posted. You may choose to post the lines one by one or by selecting several lines at a time.  
  
The following procedure describes shipment posting directly from a service order in locations without warehouse handling set up. If the location is set up to require warehouse handling, then shipment posting happens in a different warehouse document, depending on the location setup.
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Orders**, and then choose the related link.  
2. Open the relevant service order, and then choose the **Service Lines** action.  
4. On the lines you are going to post, fill in the **Qty. to Ship**, **Qty. to Invoice**, and **Qty. to Consume** fields, depending on how you will post the lines.  
5. Choose the **Post** action.
  
## See Also  
[Posting in Service Management](service-service-posting.md) 
[How to: Create a Service Order](service-how-to-create-service-orders.md)