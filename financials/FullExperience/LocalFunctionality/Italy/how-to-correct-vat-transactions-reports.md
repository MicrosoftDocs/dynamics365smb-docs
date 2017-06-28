---
title: "How to: Correct VAT Transactions Reports"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 8be50aa7-614d-42d3-b6fc-05111be9ed24
caps.latest.revision: 5
ms.author: "edupont"
translation.priority.ht: 
  - "it-it"
---
# How to: Correct VAT Transactions Reports
### To send a corrected VAT transaction report  
  
1.  In the **Search** box, enter **VAT Reports**, and then choose the related link.  
  
2.  Create a new report. For more information, see [How to: Create Electronic VAT Transactions Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-create-electronic-vat-transactions-reports.md).  
  
3.  In the new report, change the **\($ T\_740\_3 VAT Report Type $\)** field to **Corrective** or **Cancellation**. In the **\($ T\_740\_9 Original Report No. $\)** field, select the report that you want to correct from the list of available reports. The**\($ T\_740\_4 Start Date $\)** and **\($ T\_740\_5 End Date $\)** fields are copied from the original report.  
  
    > [!NOTE]  
    >  You can only select VAT reports that are marked as Submitted, as it is required that the original report has a **\($ T\_740\_12100 Tax Auth. Receipt No. $\)**  
    >   
    >  If it is a corrective report, on the **Home** tab, in the **Process** group, choose **Suggest Lines** to get the relevant VAT entries for the period. A cancellation report does not contain any lines.  
    >   
    >  The suggested lines are based on the VAT entries within the specified period and the current threshold setup. It is not correlated with the information from the original report.  
  
4.  Review the transaction details. To exclude a line from being reported to the tax authority, on the line, clear the **\($ T\_741\_12111 Incl. in Report $\)** check box.  
  
     On the **Home** tab, in the **Process** group, choose **Export**. The **\($ B\_12193 Export VAT Transactions $\)** batch job opens.  
  
    > [!NOTE]  
    >  When you choose **Export** for a report with the status Open, it will be automatically validated and the status will be changed to Released. At this point, you can reopen the report to make changes.  
  
5.  Submit the file to the authority. Use the guidelines provided by the authority. For more information, see the [Italian Revenue Agency](http://go.microsoft.com/fwlink/?LinkID=206524).  
  
     After you receive a response from the tax authorities, you must update the VAT report.  
  
6.  On the **General** FastTab, in the **\($ T\_740\_12100 Tax Auth. Receipt No. $\)** field, specify the receipt number that you received from the tax authorities.  
  
7.  On the **Home** tab, in the **Process** group, choose **Mark as Submitted** to finalize the report. The **\($ T\_740\_6 Status $\)** field is updated to Submitted.  
  
## See Also  
 [How to: Export VAT Transactions Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-export-vat-transactions-reports.md)   
 [\($ T\_740\_3 VAT Report Type $\)](assetId:///7fc4bd03-3960-4fcf-ad6c-cc6936cf0fc5)