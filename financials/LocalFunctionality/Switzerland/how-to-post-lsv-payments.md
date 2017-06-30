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
# How to: Post LSV+ Payments
You can post payments after you have received Lastschrift Verfahren \(LSV\+\) payment advice from the bank.  
  
### To post LSV\+ payments  
  
1.  In the **Search** box, enter **Cash Receipt Journals**, and then choose the related link.  
  
2.  Select the required journal, and on the **Home** tab, in the **Process** group, choose **Edit Journal**.  
  
    > [!NOTE]  
    >  You can select the journal batch for LSV where the balance account you want to address is defined. You cannot import more than one LSV journal line into the same cash receipt journal. For more information, see the Cash Receipt Journal window.  
  
3.  On the **Home** tab, in the **Process** group, choose **Get From LSV Journal**.  
  
4.  In the **LSV Journal List** window, select the LSV journal line that you want to import to the cash receipt journal.  
  
    > [!NOTE]  
    >  You can only import journal lines where the **LSV Status** field is set to **File Created**.  
  
5.  Choose the **OK** button.  
  
     The LSV journal line is imported into the cash receipt journal. The value in the **LSV Status** field in the **LSV Journal List** window changes from **File Created** to **Finished**.  
  
     You can check the imported payments, and compare them with your bank payment advice in the **Cash Receipt Journal** window. You can also delete the payment lines that could not be processed by the bank, and for which you must follow up with the customer manually.  
  
6.  On the **Home** tab, in the **Posting** group, choose **Post**.  
  
## See Also  
 [Swiss Electronic Payments Using LSV\+](../swiss-electronic-payments-using-lsv-.md)   
 [How to: Process an LSV Collection](../how-to-process-an-lsv-collection.md)   
 [How to: Close an LSV Collection](../how-to-close-an-lsv-collection.md)   
 [How to: Export Payments Using LSV](../how-to-export-payments-using-lsv.md)   
 Cash Receipt Journal   
 LSV Journal   
 LSV Journal Line