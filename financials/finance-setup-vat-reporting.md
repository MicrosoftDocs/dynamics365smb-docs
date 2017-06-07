---
title: Manage VAT Reporting to the Tax Authorities| Microsoft Docs
description: Learn how to set up VAT correctly for sales and purchases, either manually or using the assisted setup guide.
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

# How To: Report VAT to the Tax Authorities
The European Community (EC) Sales List report lists of the value added tax (VAT) amounts that you have collected for sales, so you can submit the VAT amounts to a tax authority's web service.

**Note**: In the UK, all companies that sell more than a certain value every year to <!--customers, companies...? --> EU states must submit an electronic version of their European Community (EC) sales list report in XML format through Her Majesty's Revenue and Customs (HMRC) website.

To report VAT to a tax authority electronically, you need to connect [!INCLUDE[d365fin](includes/d365fin_md.md)] to the tax authority's web service. This requires that you set up an account with your tax authority. When you have an account, you can enable a service connection that we provide in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For example, in the UK you can use the **GovTalk** service connection.

<!-- Does the report generate one line for each customer, and show a consolidated total? Or does it create a line for each sale individually?-->

The report includes one line for each customer, and displays the total amount for each customer. To view each entry for the customer, choose the line number.

After you submit the report, [!INCLUDE[d365fin](includes/d365fin_md.md)] monitors the service and keeps a record of your communications. You can view the history by choosing the **Log Entries** action. The **Status** field indicates where the report is in the process. For example, when the authorities process your report, the status of the report changes to **Succeeded**. If the tax authority found mistakes in the report you submitted, the status of the report will be **Failed**. You can view the errors in the **Errors and Warningss** FactBox, correct them, and then submit the report again. To view a list of all your EC Sales List reports, go to the **VAT Report List** page.

<!-- Does the status update automatically?-->

**Note**: If you use another method to submit the report, for example by exporting the XML and uploading it to a tax authority website, afterward you can choose **Mark as Submitted** to close the reporting period. When you mark the report as released, it becomes non-editable. If you must change the report after you mark it as released, you must reopen it.

After the tax authority reviews your report, they will send an email to the contact person for your company. In [!INCLUDE[d365fin](includes/d365fin_md.md)], the contact person is specified on the **Company Information** page. Before you submit the report, make sure that a contact person is chosen.

**Note**: The EC Sales List report can contain up to 1000 lines. If you have more lines, you must submit another report.

## To Connect to your tax authority's web service
[!INCLUDE[d365fin](includes/d365fin_md.md)] provides service connections that connect to tax authority websites. For example, if you're in the UK, you must enable the **GovTalk** service connetion.  

1. In the **Search for Pages or Reports** field, enter **Service Connections**, and then choose appropriate link. <!-- remember to get the updated text for this-->
2. Fill in the required fields.  

## To set up the EC Sales List report
1. In the **Search for Pages or Reports** field, enter **VAT Report Setup**, and then choose the related link.  
2. If you want to let users change and resubmit this report, choose the **Modify Submitted Reports** check box.  

    **Note**: For example, choosing this option is useful when you need to adjust the report. If you do not choose this option, users must create a corrective report.  
3. Specify the number series to use for EC Sales List reports.  

## To prepare and submit the EC Sales List report
1. In the **Search for Pages or Reports** field, enter **VAT Report List**, and then choose the related link.
2. Choose **New**, and then fill in the required fields.
3. To generate the content of the report, choose the **Suggest Lines** action.
4. To prepare the report for submision, choose the **Release** action.
5. To submit the report, choose the **Submit** action

[!INCLUDE[d365fin](includes/d365fin_md.md)] validates whether the report is set up correctly. If the validation fails, the errors display in the **Error and Warnings** FactBox so that you can make the appropriate changes.

<!--## To correct a VAT report
You can correct a VAT report, and resubmit it. When you regenerate the report by choosing **Suggest Lines**, the options in the -->

## Configuring your own VAT reports
You can use the VAT report and EC Sales List reports out-of-the-box, however, you can also create your own reports. This requires a bit of coding, so you might need to contact a Microsoft Partner.

The following table describes the codeunits you'll need to create for your report.

| Codeunit | What it must do |
|----|-----|
|Suggest Lines| Fetch and information from the VAT Entries table, and display it in lines on the VAT report.|
|Content | Control the format of the report. For example, whether it's XML or JSON. The format to use depends on the requirements of your tax authority's web service. |
|Submission | Control how, and when, you submit the report based on the requirements of your tax authority. |
|Response Handler | Handle the return from the tax authority. For example, it might send an email message to your company's contact person. |
|Cancel | Send a cancellation of a VAT report that was submitted earlier to your tax authority. |
