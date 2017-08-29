---
    title: Create Invoices for Services | Microsoft Docs
    description: Learn how to create invoices, so you can get paid for your service.
    services: project-madeira
    documentationcenter: ''
    author: bholtorf

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/22/2017
    ms.author: bholtorf

---
# How to: Invoice Customers for Services
You can invoice service contracts periodically. The invoice period for each contract defines how often you invoice it.  
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Create Contract Invoices**, and then choose the related link.  
2. Set the filters you want to apply.  
3. In the **Posting Date** field, enter the date to use as the posting date on the service invoices.  
4. In the **Invoice to Date** field, enter the date up to which you want to invoice contracts. The batch job will include the contracts with the next invoice dates, up to this date.  
5. In the **Action** field, choose **Create Invoices**.  
6. Choose **OK** to create the service invoices.  
  
## To invoice a service contract from the Service Contract page  
You can also invoice a service contract directly from the **Service Contract** page, if the next invoice date on the contract is earlier than the working date.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Contracts**, and then choose the related link.  
2. Select and open the service contract that you want to invoice, and then choose the **Create Service Invoice** action.  
  
> [!NOTE]  
>  You cannot create service invoices for the service contract when the **Change Status** field value is set to **Open**.  

## To invoice posted shipment lines  
You might need to create a service invoice for the service that has already been shipped, either from one or several service orders, but not yet invoiced or consumed. You can fill in the invoice lines automatically with the selected posted shipment lines for a specific customer.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Invoices**, and then choose the related link.  
2. On the **Home** tab, in the **New** group, choose **New**. Create a new service invoice.  
3. Fill in the fields on the **General** FastTab.  
4. Create invoice lines for services shipped but not invoiced. Alternatively, you can run the **Get Shipment Lines** function.  
  
    1. Choose **Actions**, choose **Functions**, and then choose **Get Shipment Lines**.  
    2. On the **Get Service Shipment Lines** page, choose the shipment lines to invoice, and then choose **OK**. The posted shipment lines are inserted into the invoice.  
  
5. Post the service invoice.  
  
 The posted service invoice and the corresponding ledger entries are created. Previously posted shipment documents are updated with the invoiced quantities and the relevant quantities on the service lines of the source orders.  