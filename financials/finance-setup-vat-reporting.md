---
title: 'How to: Set Up, Prepare, and Submit VAT Reports| Microsoft Docs'
description: 'Describes how to set up the European Community Sales List and VAT Statement reports, and how to provide them to tax authorities.'
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/05/2017
ms.author: bholtorf

---

# Set Up VAT reports a nd submit them to a tax authority
On the Business Manager and Accountant Role Centers you'll find two reports that you can use to electronically submit VAT for sales and purchases to a tax authority:  

* European Community (EC) Sales List - Report VAT for sales to other EU countries/regions to customs and tax authorities. In the report, the information is in the same format as on the declaration form from the customs and tax authorities.
VAT is calculated on the basis of the VAT Posting Setup table and the VAT Posting Groups that you have set up. VAT information is based on sales documents, like sales orders, sales invoices, sales credit memos, and so on.
* VAT Report - Report VAT based on information in sales _and_ purchase documents, such as sales and purchase orders, sales and purchase invoices, and so on.

You can use these reports right away, but you can also configure your own VAT reports to meet the requirements of your tax authority. This makes it easy to generate the VAT information for the reports, review the contents, and then submit it electronically to the tax authority directly from Financials.

After you submit a report electronically to a tax authority service, Financials monitors the service, and keeps a record of your communications in the **Entries Log**. When Financials discovers that the authorities have processed your report, the status of the report changes to Succeeded. If the tax authority found mistakes in the report you submitted, the status of the report will be **Failed**. You can view the errors in the **Error Messges** fact box, correct them, and then submit the report again. 

**Note**: If use another method to submit the report to your tax authority, for example by exporting the XML and uploading it to a tax authority website, afterward you can choose **Mark as Submitted** to close the reporting period.

<!-- Does the log capture this as well?

c=to get to the report, enter VAT Reports List, where you can create a vat report
choose a number

you can submit open, or open and closed, or both, and only entries from the specified periods or also include entries from preview periods. 

Set up the number series

Going to make it available on the accountant and business manager role centers. On the bmrc, it\s under the finance activity. On the Accountant role center, it'll be on the navigation pand on te left.

Error messages display on the Error messages Fact Box 

For the EC Sales list.
Users receive an email when the authorities have processed the report. 

they're now talking about removing the View Errors field, and just showing errors in the fact Box

the report cannot contain more than 1000 lines. If this happens, you will need to submit more than one report. 


  -->

## To set up VAT reports
1. In the **Search for Pages or Reports** field, enter **VAT Report List**, and then choose the related link.  
2. Choose the **Modify Submitted Reports** field to let users modify VAT reports that have been submitted to the tax authorities.  

    **Note**: If you leave the field blank, users must create a corrective VAT report instead.
3. Specify the number series that will be used for standard VAT reports.  

    **Note**: You can use the same number series for all VAT reports, or separate number series for each type of VAT report. For example, if your company uses separate number series for standard and corrective VAT reports, this number series is the default number series. Users can select a different number series in the No. field when they create corrective reports.
  
## To prepare a VAT report
1. In the **Search for Pages or Reports** field, enter **VAT Report**, and then choose the related link.
2. Fill in the required fields. 
3. To generate the report, choose the **Suggest Lines** action.
  
    **Tip** After you add lines, you can drill down in the Amount field to see the VAT ledger entries that the line contains.  
4. Choose the **Release** action.

Financials validates that the VAT report is set up correctly. If the validation fails, the errors are shown in the **Error Log** window so that you can make the appropriate changes. For example, an error displays if you try to release a standard VAT report but you have not yet added any lines to the report.

When you mark a VAT report as released, it becomes non-editable. If you must change the report after marking it as released, you must first reopen it.

## To submit a VAT report
1. In the **Search for Pages or Reports** field, enter **VAT Reports**, and then choose the related link.
2. Choose the report, and then choose the **Submit** action.

## To correct a VAT report
You can correct a VAT report, and resubmit it. When you regenerate the report by choosing Suggest Lines, the options in the 

