---
    title: How to Correct VAT Transactions Reports
    description: You can correct and resend VAT transaction reports.

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
# Correct VAT Transactions Reports

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Reports**, and then choose the related link.  
2.  Create a new report. For more information, see [Create Electronic VAT Transactions Reports](how-to-create-electronic-vat-transactions-reports.md).  
3.  In the new report, change the **VAT Report Type** field to **Corrective** or **Cancellation**. In the **Original Report No.** field, select the report that you want to correct from the list of available reports. The **Start Date** and **End Date** fields are copied from the original report.  

    > [!NOTE]  
    >  You can only select VAT reports that are marked as Submitted, as it is required that the original report has a **Tax Auth. Receipt No.**  
    >   
    >  If it is a corrective report, on the **Home** tab, in the **Process** group, choose **Suggest Lines** to get the relevant VAT entries for the period. A cancellation report does not contain any lines.  
    >   
    >  The suggested lines are based on the VAT entries within the specified period and the current threshold setup. It is not correlated with the information from the original report.  

4.  Review the transaction details. To exclude a line from being reported to the tax authority, on the line, clear the **Incl. in Report** check box.  

    Choose the **Export** action. The **Export VAT Transactions** batch job opens.  

    > [!NOTE]  
    >  When you choose **Export** for a report with the status Open, it will be automatically validated and the status will be changed to Released. At this point, you can reopen the report to make changes.  

5.  Submit the file to the authority. Use the guidelines provided by the authority. For more information, see the [Italian Revenue Agency](https://go.microsoft.com/fwlink/?LinkID=206524).  

    After you receive a response from the tax authorities, you must update the VAT report.  

6.  On the **General** FastTab, in the **Tax Auth. Receipt No.** field, specify the receipt number that you received from the tax authorities.  
7.  Choose the **Mark as Submitted** action to finalize the report. The **Status** field is updated to Submitted.  

## See Also  
 [Export VAT Transactions Reports](how-to-export-vat-transactions-reports.md)
