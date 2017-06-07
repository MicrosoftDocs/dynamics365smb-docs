---
title: Manage VAT Reporting to Tax Authorities| Microsoft Docs
description: Learn how to prepare and submit a report that lists VAT from sales during a period to a tax authority.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, tax, report, EC sales list, statement
ms.date: 06/02/2017
ms.author: bholtorf

---

# How To: Report VAT to Tax Authorities
The European Community (EC) Sales List report lists of the value added tax (VAT) amounts that you have collected for sales within the EU, so you can submit the VAT amounts to a tax authority's web service.

**Note**: In the UK, all companies that sell more than a certain value every year to customers in EU member states must submit an electronic version of their European Community (EC) sales list report in XML format through Her Majesty's Revenue and Customs (HMRC) website.

This report only works for countries in the EU. For example, it does not include VAT on sales to countries like China or the United States.

To report VAT to a tax authority electronically, you need to connect [!INCLUDE[d365fin](includes/d365fin_md.md)] to the tax authority's web service. This requires that you set up an account with your tax authority. When you have an account, you can enable a service connection that we provide in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For example, in the UK you can use the **GovTalk** service connection.

The report includes one line for each type of transaction with the customer, and displays the total amount for each type of transactions. There are three types of transacitons that the report can include: 

* B2B Goods
* B2B Services
* B2B Triangulated Goods

B2B goods and services specify whether you sold a good or a service, and are controled by the EU Service setting in the VAT posting setup. B2B Triangulated Goods incidate whether you engaged in trade with a 3rd party, and are controled by the EU 3-Party Trade setting on the sales document (order, invoice, credit memo, and so on).

After you submit the report, [!INCLUDE[d365fin](includes/d365fin_md.md)] monitors the service and keeps a record of your communications. The **Status** field indicates where the report is in the process. For example, when the authorities process your report, the status of the report changes to **Succeeded**. If the tax authority found mistakes in the report you submitted, the status of the report will be **Failed**. You can view the errors under **Errors and Warningss**, correct them, and then submit the report again. To view a list of all your EC Sales List reports, go to the **EC Sales List Reports** page.

**Note**: If you use another method to submit the report, for example by exporting the XML and uploading it to a tax authority website, afterward you can choose **Mark as Submitted** to close the reporting period. When you mark the report as released, it becomes non-editable. If you must change the report after you mark it as released, you must reopen it.

After the tax authority reviews your report, they will send an email to the contact person for your company. In [!INCLUDE[d365fin](includes/d365fin_md.md)], the contact person is specified on the **Company Information** page. Before you submit the report, make sure that a contact person is chosen.

<!--**Note**: The EC Sales List report can contain up to 1000 lines. If you have more lines, you must submit another report. -->

## To Connect to your tax authority's web service
[!INCLUDE[d365fin](includes/d365fin_md.md)] provides service connections that connect to tax authority websites. For example, if you are in the UK, you must enable the **GovTalk** service connetion.  

1. In the **Search for Pages or Reports** field, enter **Service Connections**, and then choose appropriate link. <!-- remember to get the updated text for this-->
2. Fill in the required fields.  

## To set up the EC Sales List report
1. In the **Search for Pages or Reports** field, enter **VAT Report Setup**, and then choose the related link.  
2. If you want to let users change and resubmit this report, choose the **Modify Submitted Reports** check box.  
3. Specify the number series to use for EC Sales List reports.  

## To prepare and submit the EC Sales List report
1. In the **Search for Pages or Reports** field, enter **EC Sales List**, and then choose the related link.
2. Choose **New**, and then fill in the required fields.
3. To generate the content of the report, choose the **Suggest Lines** action.

    **Note**: If you want, you can review the transactions included in the line before you submit the report. To do that, choose the line, and then choose the **Show VAT Entries** action. 
4. To prepare the report for submision, choose the **Release** action.
5. To submit the report, choose the **Submit** action

[!INCLUDE[d365fin](includes/d365fin_md.md)] validates whether the report is set up correctly. If the validation fails, the errors display under **Error and Warnings** so that you can make the appropriate changes.

## Viewing communications with your tax authority
In some countries, you exchange messages with the tax authority when you submit reports. You can view the first and the last message you sent or received by choosing the **Download Submission Message** and **Download Response Message** actions.  

## Configuring your own VAT reports
You can use the VAT report and EC Sales List reports out-of-the-box, however, you can also create your own reports. This requires that you create a few codeunits. If you need help with that, contact a Microsoft Partner.  
    
The following table describes the codeunits that you must create for your report.

| Codeunit | What it must do |
|----|-----|
|Suggest Lines| Fetch information from the VAT Entries table, and display it in lines on the VAT report.|
|Content | Control the format of the report. For example, whether it is XML or JSON. The format to use depends on the requirements of your tax authority's web service. |
|Submission | Control how, and when, you submit the report based on the requirements of your tax authority. |
|Response Handler | Handle the return from the tax authority. For example, it might send an email message to your company's contact person. |
|Cancel | Send a cancellation of a VAT report that was submitted earlier to your tax authority. |

**Note**: When you create codeunits for the report, pay attention to the value in the **VAT Report Version** field. This field must reflect the version of the report that is, or was, required by the tax authority. For example, you might enter **2017** in the field to indicate that the report conforms to the requirements that were in place that year. To find the current version, contact your tax authority.  

## See also
[Set up VAT](finance-setup-vat.md)  
[Set Up Sales](sales-setup-sales.md)  
[How to: Invoice Sales](sales-setup-sales.md)  
