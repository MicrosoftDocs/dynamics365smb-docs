---
    title: How to Post LSV+ Payments
    description: You can post payments after you have received Lastschrift Verfahren (LSV+) payment advice from the bank.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Post LSV+ Payments
You can post payments after you have received Lastschrift Verfahren (LSV+) payment advice from the bank.  

## To post LSV+ payments  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Cash Receipt Journals**, and then choose the related link.  
2.  Select the required journal, and then choose the **Edit Journal** action.  

    > [!NOTE]  
    >  You can select the journal batch for LSV where the balance account you want to address is defined. You cannot import more than one LSV journal line into the same cash receipt journal. For more information, see the Cash Receipt Journal page.  

3.  Choose the **Get From LSV Journal** action.  
4.  On the **LSV Journal List** page, select the LSV journal line that you want to import to the cash receipt journal.  

    > [!NOTE]  
    >  You can only import journal lines where the **LSV Status** field is set to **File Created**.  

5.  Choose the **OK** button.  

    The LSV journal line is imported into the cash receipt journal. The value in the **LSV Status** field on the **LSV Journal List** page changes from **File Created** to **Finished**.  

    You can check the imported payments, and compare them with your bank payment advice on the **Cash Receipt Journal** page. You can also delete the payment lines that could not be processed by the bank, and for which you must follow up with the customer manually.  

6.  Choose the **Post** action.  

## See Also  
 [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md)   
 [Process an LSV Collection](how-to-process-an-lsv-collection.md)   
 [Close an LSV Collection](how-to-close-an-lsv-collection.md)   
 [Export Payments Using LSV](how-to-export-payments-using-lsv.md) 
