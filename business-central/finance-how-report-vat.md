---
title: Submit VAT reports to tax authorities
description: Learn how to prepare reports that list VAT from sales during a period, or from sales and purchases, and submit the report to a tax authority.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT, tax, report, EC sales list, statement
ms.search.form: 315_Primary, 321, 322, 323, 474, 475, 739, 740, 741, 742, 743, 744, 745, 746, 747, 748, 9401
ms.date: 08/05/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Report VAT to tax authorities

This article describes the reports in [!INCLUDE[prod_short](includes/prod_short.md)] that you can use to submit information about value-added tax (VAT) amounts for sales and purchases to tax authorities in your region. Depending on the specific country/region, the reports might include specific information, or there might be additional reports that you must submit. Check the articles for your country/region in the [Local Functionality](about-localization.md) section.  

You can use the following built-in reports:

* The **EC Sales List** report  

    The European Community (EC) Sales List report lists the value added tax (VAT) amounts that you have collected for sales to VAT-registered customers in the European Union (EU) countries/regioins.  
* The **VAT Return** report  

    The VAT Return report includes VAT for sales and purchases to customers and from vendors in all countries/regions that use VAT.  

In both cases (as in other VAT-related reports), VAT is calculated based on the VAT posting setup and the VAT posting groups that you have set up. [!INCLUDE[prod_short](includes/prod_short.md)] shows VAT entries always based on their **VAT Date** as a primary reporting date.  

> [!NOTE]
> All VAT related reports now run using the **VAT Date** to filter relevant records. Even if you set up **VAT Date Usage** as **Do not use VAT Date functionallity** [!INCLUDE[prod_short](includes/prod_short.md)] will hide all instances of the **VAT Date** across the application. However, the **VAT Date** is still used in all reportings and is auto-populated with the **Posting Date**.

If you want to view a complete history of VAT entries, every posting that involves VAT creates an entry on the **VAT Entries** page. These entries are used to calculate your VAT settlement amount, such as your payment and refund, for a specific period. To view VAT entries, choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Entries**, and then choose the related link.

> [!NOTE]
> Each [!INCLUDE[prod_short](includes/prod_short.md)] environment is meant to handle regulatory reporting in one single country/region. For example, the Dutch version of [!INCLUDE[prod_short](includes/prod_short.md)] handles VAT reporting in The Netherlands but not in other countries/regions. Similarly, the United States version of [!INCLUDE[prod_short](includes/prod_short.md)] handles 1099 reporting in the United States and does not support claiming VAT reporting in other countries/regions, unless brought by an extension delivered by our partner ecosystem or a customer-specific code modification.

## <a name="ecsaleslist"></a>About the EC Sales List report

In the European Union (EU) and in the UK, all companies that sell goods and services to VAT-registered customers, including customers in other European Union (EU) countries/regions, must submit an electronic version of the European Community (EC) Sales List report to their customs and tax authorities. The **EC Sales List** report works only for countries/regions in the EU.

The report includes one line for each type of transaction with the customer, and displays the total amount for each type of transactions. There are three types of transactions that the report can include:  

* B2B Goods  
* B2B Services  
* B2B Triangulated Goods  

*B2B* goods and services specify whether you sold a good or a service, and are controlled by the **EU Service** setting in the VAT posting setup. *B2B Triangulated Goods* indicate whether you engaged in trade with a 3rd party, and are controlled by the **EU 3-Party Trade** setting on sales documents, such as sales orders, invoices, credit memos, and so on.  

After the tax authority reviews your report, they'll send an email to the contact person for your company. In [!INCLUDE[prod_short](includes/prod_short.md)], the contact person is specified on the **Company Information** page. Before you submit the report, make sure that a contact person is chosen.  

### Submit an EC sales list report

[!INCLUDE [finance-ecsaleslist](includes/finance-ecsaleslist.md)]

## <a name="vatreturn"></a>About the VAT Return report

Use this report to submit VAT for sales and purchase documents, such as purchase and sales orders, invoices, and credit memos. The information in the report is in the same format as on the declaration form from the customs and tax authorities.  

For the VAT return, you can specify the entries to include:

* Submit open transactions only, or open and closed. For example, this is useful when you prepare your final annual VAT return.
* Submit only entries from the specified periods, or also include entries from previous periods. This is useful for updating a VAT return that you have already submitted, for example, if a vendor sends you a late invoice.    

## To connect to your tax authority's web service
[!INCLUDE[prod_short](includes/prod_short.md)] provides service connections to tax authority websites. For example, if you are in the UK, you can enable the **GovTalk** service connection to submit the EC Sales List and VAT Return reports electronically. If you want to submit the report manually, for example by entering your data on the tax authority's website, this isn't required.   

To report VAT to a tax authority electronically, you need to connect [!INCLUDE[prod_short](includes/prod_short.md)] to the tax authority's web service. This requires that you set up an account with your tax authority. When you have an account, you can enable a service connection that we provide in [!INCLUDE[prod_short](includes/prod_short.md)].

1. Choose the ![Lightbulb that opens the Tell Me feature 2.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Connections**, and then choose appropriate link.
2. Fill in the required fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    > [!NOTE]  
    > It is a good idea to test your connection. To do this, choose the **Test Mode** check box, then prepare and submit your VAT report as described in the [To prepare and submit a VAT report](#to-prepare-and-submit-a-vat-report) section. While in Test Mode, the service tests whether the tax authority can receive your report, and the status of the report will indicate whether the test submission was successful. It is important to remember that this is not an actual submission. To submit the report for real, you must clear the **Test Mode** check box, and then repeat the submission process.

## To set up VAT reports in [!INCLUDE[prod_short](includes/prod_short.md)]

[!INCLUDE [vat-report-setup](includes/vat-report-setup.md)]

### To set up VAT return periods

Optionally, if your business isn't located in the UK, use the **VAT Returns Periods** page to set up scheduled VAT returns. If your business is located in the UK, see [Making Tax Digital in the United Kingdom](LocalFunctionality/UnitedKingdom/making-tax-digital-submit-vat-return.md).  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **VAT Return Periods**, and then choose the related link.  
2. On the **VAT Return Periods** page, fill in the fields to set up the first period. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)].  
3. Repeat step 2 for any additional periods that you want to add.  

Now, when the time has come to submit a VAT report for a VAT return period, choose the period in  the **VAT Return Periods** page, and then choose the **Create VAR Return** action. Then, in the **VAT Return** card, choose the **Suggest Lines** action as described in step 3 in the following procedure.  

## To prepare and submit a VAT report

1. Choose the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **EC Sales List** or **VAT Returns**, and then choose the related link.  
2. Choose **New**, and then fill in the required fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To generate the content of the report, choose the **Suggest Lines** action.  

    > [!NOTE]  
    >  For the EC Sales List report, you can review the transactions included in the report lines before you submit the report. To do that, choose the line, and then choose the **Show VAT Entries** action.  

4. To export XML file for export goods or services in German or in other EU-countries run the **Ecport** action. You will get created and the XML file using the following naming convention **VIES_<Period>_<CompanyVAT>.xml**. 
6. To validate and prepare the report for submission, choose the **Release** action.  

    > [!NOTE]  
    > [!INCLUDE[prod_short](includes/prod_short.md)] validates whether the report is set up correctly. If the validation fails, the errors display under **Errors and Warnings** so that you know what to fix. Typically, if the message is about a missing setting in [!INCLUDE[prod_short](includes/prod_short.md)], you can click the message to open the page that contains the information to correct.  

7. To submit the report, choose the **Submit** action.  

After you submit the report, [!INCLUDE[prod_short](includes/prod_short.md)] monitors the service and keeps a record of your communications. The **Status** field indicates where the report is in the process. For example, when the authorities process your report, the status of the report changes to **Succeeded**. If the tax authority found mistakes in the report you submitted, the status of the report will be **Failed**. You can view the errors under **Errors and Warnings**, correct them, and then submit the report again. To view a list of all your EC Sales List reports, go to the **EC Sales List Reports** page.  

### VAT return statuses

VAT returns can have different statuses, as described in the following table.

| Status | Description |
|------------|-------------------------|
| Open | When you create a new VAT return. You can run the **Suggest Lines** action. If you need to correct values, you can run the **Suggest Lines** action again. You can't submit a VAT return that has this status. |
| Released | Status will be changed when you use the **Release** action. [!INCLUDE[prod_short](includes/prod_short.md)] will show the **Errors and Warnings** FastTab. You can't make changes or use the **Suggest Lines** action. To make changes, you must reopen the VAT return. |
| Rejected | If your submission wasn't successful (for example, if authentication failed), the status will change to **Rejected**. You can't reopen a VAT Return that has this status. |
| Submitted | The VAT return is submitted using the **Submit** action, or it's marked as submitted by using the **Mark as Submitted** action. |
| Accepted | The VAT return has this status if the report is marked as accepted by using the **Mark as Accepted** action. If the **VAT Return** report is marked as **Accepted**, you can run the **Calculate and Post VAT Settlement** action. |

## Viewing communications with your tax authority

In some countries/regions, you exchange messages with the tax authority when you submit reports. You can view the first and the last message you sent or received by choosing the **Download Submission Message** and **Download Response Message** actions.  

## Submitting VAT reports manually
If you use another method to submit the report, for example by exporting the XML and uploading it to a tax authority website, afterward you can choose **Mark as Submitted** to close the reporting period. When you mark the report as released, it becomes non-editable. If you must change the report after you mark it as released, you must reopen it.

## VAT settlement
Periodically, you must remit the net VAT to the tax authorities. If you need to settle VAT frequently, you can run the **Calc. and Post VAT Settlement** batch job to close the open VAT entries and transfer purchase and sales VAT amounts to the VAT settlement account.

When you transfer VAT amounts to the settlement account, the purchase VAT account is credited, and the sales VAT account is debited with the amounts calculated for the specified period. The net amount is credited or debited, if the purchase VAT amount is larger, to the VAT settlement account. You can post the settlement immediately or print a test report first.  

> [!Note]
> When you use the **Calc. and Post VAT Settlement** batch job, if you do not specify a **VAT Bus. Posting Group** and a **VAT Prod. Posting group**, entries with all business posting groups and product posting group codes are included.

## Configuring your own VAT reports

You can use the **EC Sales List** report out-of-the-box. However, you can also create your own reports, if you have a development license so that you can create codeunits. If you need assistance, contact a Microsoft Partner.  

The following table describes the codeunits that you must create for your report.  

| Codeunit | What it must do |
|----|-----|
|Suggest Lines| Fetch information from the **VAT Entries** table, and display it in lines on the VAT report.|
|Content | Control the format of the report. For example, whether it's XML or JSON. The format to use depends on the requirements of your tax authority's web service. |
|Submission | Control how, and when, you submit the report based on the requirements of your tax authority. |
|Response Handler | Handle the return from the tax authority. For example, it might send an email message to your company's contact person. |
|Cancel | Send a cancellation of a VAT report that was submitted earlier to your tax authority. |  

> [!Note]
> When you create codeunits for the report, pay attention to the value in the **VAT Report Version** field. This field must reflect the version of the report that is, or was, required by the tax authority. For example, you might enter **2021** in the field to indicate that the report conforms to the requirements that were in place that year. To find the current version, contact your tax authority.  

## Related information

[Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md)    
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)    
[Set Up Sales](sales-setup-sales.md)    
[Invoice Sales](sales-how-invoice-sales.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]
