---
    title: How to Post LSV+ payments
    description: You can post payments after you receive Lastschrift Verfahren (LSV+) payment advice from the bank.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.search.form: 3010830, 3010831, 3010832,3010834, 3010835
    ms.date: 11/27/2023
    ms.author: bholtorf
---
# Post LSV+ payments
You can post payments after you receive Lastschrift Verfahren (LSV+) payment advice from the bank.  

## To post LSV+ payments  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Receipt Journals**, and then choose the related link.  
2.  Select the required journal, and then choose the **Edit Journal** action.  

    > [!NOTE]  
    >  You can select the journal batch for LSV where the balance account you want to address is defined. You cannot import more than one LSV journal line into the same cash receipt journal. For more information, see the Cash Receipt Journal page.  

3.  Choose the **Get From LSV Journal** action.  
4.  On the **LSV Journal List** page, select the LSV journal line that you want to import to the cash receipt journal.  

    > [!NOTE]  
    >  You can only import journal lines where the **LSV Status** field is set to **File Created**.  

5.  Choose the **OK** button.  

    The LSV journal line is imported into the cash receipt journal. The value in the **LSV Status** field on the **LSV Journal List** page changes from **File Created** to **Finished**.  

    You can check the imported payments, and compare them with your bank payment advice on the **Cash Receipt Journal** page. You can also delete the payment lines that the bank doesn't process, and for which you must follow up with the customer manually.  

6.  Choose the **Post** action.  

## See also  
 [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md)   
 [Process an LSV Collection](how-to-process-an-lsv-collection.md)   
 [Close an LSV Collection](how-to-close-an-lsv-collection.md)   
 [Export Payments Using LSV](how-to-export-payments-using-lsv.md) 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]