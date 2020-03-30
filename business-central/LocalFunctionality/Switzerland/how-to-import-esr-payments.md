---
    title: How to Import ESR Payments
    description: After you receive payment from a customer, you receive a file that contains information about paid invoices. You can receive this file from your bank electronically, or by mail.

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
# Import ESR Payments
After you receive payment from a customer, you receive a file that contains information about paid invoices. You can receive this file from your bank electronically, or by mail.  

You can import the Einzahlungsschein mit Referenznummer (ESR) invoice data from the file, print the data by using the sales invoice ESR report or the sales ESR coupon report, and verify before posting. For more information, see [Print ESR Invoices](how-to-print-esr-invoices.md).  

## To import ESR payments  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Cash Receipt Journals**, and then choose the related link.  
2.  In the **Batch Name** field, select the required journal batch.  

    > [!NOTE]  
    >  The journal must be empty before you import the ESR file. You cannot import more than one ESR file into the same cash receipt journal.  

3.  Choose the **Read ESR File** action.  

    > [!NOTE]  
    >  If you have defined more than one ESR bank, a warning message displays instructing you to choose the relevant bank. For more information, see the ESR Setup table.  

4.  Choose the **Yes** button, and then choose the **OK** button.  

The payments information is imported to the journal lines. The payments are automatically applied to the respective invoices according to unique ESR reference numbers.  

## See Also  
 [Swiss Electronic Payments Using ESR](swiss-electronic-payments-using-esr.md)   
 [Print ESR Invoices](how-to-print-esr-invoices.md)
