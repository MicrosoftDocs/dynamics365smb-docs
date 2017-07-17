---
title: Submit VAT Reports to Tax Authorities| Microsoft Docs
description: Learn how to prepare reports that lists VAT from sales during a period, or from sales and purchases, and submit the report to a tax authority.
author: bholtorf

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, tax, report, EC sales list, statement
ms.date: 07/17/2017
ms.author: bholtorf

---

# How To: Report VAT to Tax Authorities
This topic provides information about how to report value-added tax (VAT) amounts for sales and purchases to tax authorities in your region. You can use the following reports in [!INCLUDE[d365fin](includes/d365fin_md.md)] to submit the reports to your tax authority's web service:

* The **EC Sales List** report lists the value added tax (VAT) amounts that you have collected for sales within the European Union (EU).
* The **VAT Return** report includes VAT for sales and purchases. <!-- is this within and outside the EU? -->

## About the EC Sales List report
Companies that run VAT-registered businesses and sell or move goods to other VAT-registered businesses in the European Union (EU) must record and report about data on their sales activities to the government.  

All companies in EU member states that sell more than a certain value to customers in EU member states must submit an electronic version of their European Community (EC) sales list report in XML format to their country's tax authorities. In the UK, this is through Her Majesty's Revenue and Customs (HMRC) website. The EC Sales List report works only for countries in the EU. For example, it does not include VAT on sales to countries like the United States or China.

The report includes one line for each type of transaction with the customer, and displays the total amount for each type of transactions. There are three types of transactions that the report can include:  

* B2B Goods  
* B2B Services  
* B2B Triangulated Goods  

B2B goods and services specify whether you sold a good or a service, and are controlled by the **EU Service** setting in the VAT posting setup. B2B Triangulated Goods indicate whether you engaged in trade with a 3rd party, and are controlled by the **EU 3-Party Trade** setting on sales documents, such as sales orders, invoices, credit memos, and so on.  

After the tax authority reviews your report, they will send an email to the contact person for your company. In [!INCLUDE[d365fin](includes/d365fin_md.md)], the contact person is specified on the **Company Information** page. Before you submit the report, make sure that a contact person is chosen.

<!--> [!NOTE]  
>   The EC Sales List report can contain up to 1000 lines. If you have more lines, you must submit another report. -->

## About the VAT Return report
Use this report to submit VAT for sales and purchase documents, such as purchase and sales orders, invoices, and credit memos. The information in the report is in the same format as on the declaration form from the customs and tax authorities.
VAT is calculated on the basis of the VAT Posting Setup table and the VAT Posting Groups that you have set up.

Financials validates that the VAT report is set up correctly. If the validation fails, the errors are shown under **Error Messages** so that you can address them. For example, an error displays if you release a report without adding lines.

For the VAT report, you can specify the entries to include:

* Submit open transactions only, or open and closed.
* Submit only entries from the specified periods, or also include entries from preview periods.

## To connect to your tax authority's web service
[!INCLUDE[d365fin](includes/d365fin_md.md)] provides service connections to tax authority websites. For example, if you are in the UK, you must enable the **GovTalk** service connetion.  

To report VAT to a tax authority electronically, you need to connect [!INCLUDE[d365fin](includes/d365fin_md.md)] to the tax authority's web service. This requires that you set up an account with your tax authority. When you have an account, you can enable a service connection that we provide in [!INCLUDE[d365fin](includes/d365fin_md.md)].

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Connections**, and then choose appropriate link. <!-- remember to get the updated text for this-->  
2. Fill in the required fields.  

## To set up the VAT reports
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Report Setup**, and then choose the related link.  
2. If you want to let users change and resubmit this report, choose the **Modify Submitted Reports** check box.  
3. Choose the number series to use for each report.  

## To prepare and submit a VAT report
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **EC Sales List** or **VAT Return**, and then choose the related link.  
2. Choose **New**, and then fill in the required fields.  
3. To generate the content of the report, choose the **Suggest Lines** action.  

    > [!NOTE]  
>   You can review the transactions included in the report lines before you submit the report. To do that, choose the line, and then choose the **Show VAT Entries** action.  
4. To prepare the report for submission, choose the **Release** action.  
>  [!NOTE]  
>  [!INCLUDE[d365fin](includes/d365fin_md.md)] validates whether the report is set up correctly. If the validation fails, the errors display under **Messages** so that you can make the appropriate changes. If the message is about a missing setting in Financials, you can click the message to open the page that contains the information to correct.   
5. To submit the report, choose the **Submit** action.  

After you submit the report, [!INCLUDE[d365fin](includes/d365fin_md.md)] monitors the service and keeps a record of your communications. The **Status** field indicates where the report is in the process. For example, when the authorities process your report, the status of the report changes to **Succeeded**. If the tax authority found mistakes in the report you submitted, the status of the report will be **Failed**. You can view the errors under **Messages**, correct them, and then submit the report again. To view a list of all your EC Sales List reports, go to the **EC Sales List Reports** page.  

## Viewing communications with your tax authority
In some countries, you exchange messages with the tax authority when you submit reports. You can view the first and the last message you sent or received by choosing the **Download Submission Message** and **Download Response Message** actions.  

## Submitting VAT reports manually
If you use another method to submit the report, for example by exporting the XML and uploading it to a tax authority website, afterward you can choose **Mark as Submitted** to close the reporting period. When you mark the report as released, it becomes non-editable. If you must change the report after you mark it as released, you must reopen it.

## Configuring your own VAT reports
You can use the EC Sales List report out-of-the-box, however, you can also create your own reports. This requires that you create a few codeunits. If you need help with that, contact a Microsoft Partner.  

The following table describes the codeunits that you must create for your report.

| Codeunit | What it must do |
|----|-----|
|Suggest Lines| Fetch information from the VAT Entries table, and display it in lines on the VAT report.|
|Content | Control the format of the report. For example, whether it is XML or JSON. The format to use depends on the requirements of your tax authority's web service. |
|Submission | Control how, and when, you submit the report based on the requirements of your tax authority. |
|Response Handler | Handle the return from the tax authority. For example, it might send an email message to your company's contact person. |
|Cancel | Send a cancellation of a VAT report that was submitted earlier to your tax authority. |

> [!NOTE]  
>   When you create codeunits for the report, pay attention to the value in the **VAT Report Version** field. This field must reflect the version of the report that is, or was, required by the tax authority. For example, you might enter **2017** in the field to indicate that the report conforms to the requirements that were in place that year. To find the current version, contact your tax authority.  

<!--  -->

## See also
[Set up VAT](finance-setup-vat.md)  
[Set Up Sales](sales-setup-sales.md)  
[How to: Invoice Sales](sales-setup-sales.md)  
