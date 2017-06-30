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
# How to: Create Remittance Suggestions
You can create a remittance suggestion so that payment proposals are sent to vendors who are set up to receive remittance payments. One payment transaction per posting date for each vendor is transferred to the bank.  
  
> [!NOTE]  
>  To avoid creating payment suggestions for vendors who are remitted when the usual vendor suggestion process is used, add a filter for **Remittance** in the **Suggest Vendor Payments** window and set the filter to **No**.  
  
### To create a remittance suggestion  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Remittance Suggestion**.  
  
3.  In the **Suggest Remittance Payments** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_15000001\_F\_1\_1 Last Payment Date $\)**|Specify the last payment date.|  
    |**\($ R\_15000001\_F\_1\_2 Find Payment Discounts $\)**|Select if you want to search for entries where a payment discount is available.|  
    |**\($ R\_15000001\_F\_1\_3 Use Vendor Priority $\)**|Select if the vendor priority should be used to search entries.|  
    |**\($ R\_15000001\_F\_1\_4 Available Amount \(LCY\) $\)**|Specify the payments for total amounts that are less than or equal to the given amount.|  
    |**\($ R\_15000001\_F\_1\_5 Posting Date $\)**|Specify a posting date.|  
    |**\($ R\_15000001\_F\_1\_1080001 Replace Posting Date with Due Date $\)**|Select to insert the due date of the entry as the posting date for the payments.|  
    |**\($ R\_15000001\_F\_1\_1080006 Test Document Type $\)**|Specify which of the following document types should be tested for payment:<br /><br /> -   **All** - All document types are tested.<br />-   **Invoice\/Credit memo** - Only invoice or credit memo entries are tested.|  
    |**\($ R\_15000001\_F\_1\_1080002 Invoice\/Debit Vendor Ledger Entries only $\)**|Select to pay only invoice or debit entries.|  
  
4.  Choose the **OK** button.  
  
## See Also  
 [Electronic Payments to Vendors in Norway](../electronic-payments-to-vendors-in-norway.md)   
 [How to: Set Up Remittance Agreements](../how-to-set-up-remittance-agreements.md)   
 [How to: Create Remittance Accounts](../how-to-create-remittance-accounts.md)   
 [How to: Set Up Vendors for Remittance](../how-to-set-up-vendors-for-remittance.md)   
 [Recipient Reference Codes](../recipient-reference-codes.md)   
 [How to: Create Manual Remittance Payments](../how-to-create-manual-remittance-payments.md)   
 [How to: Set Up Payment Line Information](../how-to-set-up-payment-line-information.md)   
 [How to: Test Remittance Payments](../how-to-test-remittance-payments.md)   
 [How to: Export Remittance Payments](../how-to-export-remittance-payments.md)   
 [Types of Payment Returns Files](../types-of-payment-returns-files.md)   
 [How to: Import Payment Return Data](../how-to-import-payment-return-data.md)   
 [How to: Delete Remittance Payment Orders](../how-to-delete-remittance-payment-orders.md)   
 [Remittance Errors](../remittance-errors.md)   
 [How to: View Remittance Error Codes](../how-to-view-remittance-error-codes.md)   
 [How to: Cancel Payments](../how-to-cancel-payments.md)