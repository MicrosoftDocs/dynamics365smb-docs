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
# How to: Process an LSV Collection
You can use **LSV Journals** to create and process payments from Lastschrift Verfahren \(LSV\+\) customers. You can register these payments in the cash receipt journal, create an LSV file, and then print the collection order. For more information, see the Cash Receipt Journal window and [How to: Export Payments Using LSV](how-to-export-payments-using-lsv.md).  
  
 When you run the **LSV Suggest Collection** batch job, each suggested collection is registered on an LSV journal line, and the open invoices are transferred to the LSV journals. For more information, see the LSV Journal table.  
  
 You can view, edit, or delete the suggested payment lines. If you correct the suggested amount, then the difference is marked as a discount. You can run the batch job multiple times for different customer groups. The suggestion lines can be placed in the same journal.  
  
### To create an LSV collection  
  
1.  In the **Search** box, enter **LSV Journal List**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **LSV Journal List** window, fill in the required fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**LSV Bank Code**|Select the LSV bank code for the bank that will perform the collection.|  
    |**LSV Journal Description**|Enter a description for the entry.|  
  
4.  Select the required LSV journal entry, and on the **Actions** tab, in the **Functions** group, choose **LSV Suggest Collection** to create the payments to be collected automatically by LSV\+.  
  
5.  In the **LSV Suggest Collection** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**No.**|Enter the LSV journal number.|  
    |**From due date**|Specify the starting due date of open entries to be suggested for collection.|  
    |**To due date**|Specify the ending due date of open entries to be suggested for collection.|  
    |**Collection date**|Specify the date on which the collection closes. The LSV\+ order must be submitted at least three banking days before the collection date.|  
  
6.  Choose the **OK** button.  
  
 All related lines are transferred to the LSV journal. After processing the LSV collection, you can view, check, or edit the suggested payments in the **LSV Journal** window. For more information, see the LSV Journal Line table.  
  
### To manage suggested payments  
  
1.  In the **LSV Journal List** window, select the required journal entry.  
  
2.  On the **Home** tab, in the **Process** group, select **LSV Journal Line**.  
  
     You can view and modify the suggested payments in this window. You can enter the required payments manually. For new journal lines, the **LSV Status** field is set to **Open** to indicate that the invoice is unpaid.  
  
3.  Choose the **OK** button.  
  
## See Also  
 [Swiss Electronic Payments Using LSV\+](swiss-electronic-payments-using-lsv-.md)   
 [How to: Close an LSV Collection](how-to-close-an-lsv-collection.md)   
 [How to: Post LSV\+ Payments](how-to-post-lsv-payments.md)   
 [How to: Export Payments Using LSV](how-to-export-payments-using-lsv.md)   
 Cash Receipt Journal   
 LSV Journal   
 LSV Journal Line