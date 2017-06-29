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
# How to: Close an LSV Collection
You must close Lastschrift Verfahren \(LSV\+\) collections to write LSV files that can be sent to the bank for payment collection. When you close a collection, the collection is complete, and the postings in the LSV journal are combined.  
  
 When the collection is complete, the current collection number is assigned in the LSV journal, based on the last collection. This LSV number is transferred to the customer entries for all outstanding invoices. The collection file can be reconstructed at any time using the LSV number. The **On Hold** field is also populated with **LSV** in the customer entries to avoid the duplication of open entries. For more information, see the **LSV Journal** table and the **Cust. Ledger Entry** table. You can also reopen a closed collection.  
  
### To close an LSV collection  
  
1.  In the **Search** box, enter **LSV Journal List**, and then choose the related link.  
  
2.  Select the required journal line, on the **Actions** tab, in the **Functions** group, select **Modify Posting Date**. This will modify the value in the **Credit Date** field by using the value suggested during the LSV collection.  
  
3.  In the **New Date** field, enter the new date.  
  
4.  On the **Actions** tab, in the **Functions** group, select **Close Collection**.  
  
    > [!NOTE]  
    >  The fields on the **Options** FastTab for the **LSV Close Collection** batch job cannot be modified, and correspond to the selected journal line.  
  
5.  Choose the **OK** button.  
  
     In the **LSV Journal List** window, the value in the **LSV Status** field is changed from **Edit** to **Released**. The journal lines can no longer be modified.  
  
### To reopen an LSV collection  
  
1.  In the **Search** box, enter **LSV Journal List**, and then choose the related link.  
  
2.  Select the required journal line for which you want to reopen the collection, on the **Actions** tab, in the **Functions** group, select **Reopen Collection**.  
  
    > [!NOTE]  
    >  You can only reopen the collection if you have not yet submitted the LSV\+ file to the bank.  
  
3.  Choose the **Yes** button to confirm the reopening of the collection.  
  
## See Also  
 [Swiss Electronic Payments Using LSV\+](../swiss-electronic-payments-using-lsv-.md)   
 [How to: Process an LSV Collection](../how-to-process-an-lsv-collection.md)   
 [How to: Post LSV\+ Payments](../how-to-post-lsv-payments.md)   
 [How to: Export Payments Using LSV](../how-to-export-payments-using-lsv.md)   
 LSV Journal   
 LSV Journal Line   
 Cust. Ledger Entry