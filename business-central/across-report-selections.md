---
title: Report selection in Business Central
description: Learn about how to set up the reports that you use to print various types of documents in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: setup, reporting
ms.search.form: 306, 307, 347, 385, 524, 865, 5932, 7401, 7355, 99000917
ms.date: 08/26/2025
ms.service: dynamics-365-business-central

---
# Report selection for documents in Business Central

You can set up default reports to use to print sales, purchases, and service documents, such as orders, quotes, and invoices, and which layout is used. For example, if you have a specific layout for sales invoices, you can specify that report in the **Report Selections - Sales** page. You can then use the report when you send or print sales invoices.  

## Available report selections

The **Report Selections** pages specify the reports to print in different situations and the layout to use. [!INCLUDE [prod_short](includes/prod_short.md)] provides default configurations, but you can change them if needed. You can also add reports to the **Report Selection** pages if you want to print more than one report per document type, for example.

The following table describes where you can find information about the different pages.  

|Area or task  |Learn more|
|--------------|----------|
|Example of how report selection works (sales)|[Report selection for sales documents](#example-report-selection-for-sales-documents)|
|Default layout for emails with sales and purchase documents  |[Set Up Reusable Email Texts and Layouts for Sales and Purchase Documents](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts) |
|Define check layouts |[Select a Check Layout](finance-how-define-check-layouts.md) |
|Define reports for value-added tax (VAT) reporting (Germany)|[Set Up Reports for VAT and Intrastat](LocalFunctionality/Germany/how-to-set-up-reports-for-vat-and-intrastat.md) |

> [!TIP]
> Your [!INCLUDE [prod_short](includes/prod_short.md)] can include additional **Report Selection** pages, depending on your location and industry, for example. To check your setup, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Report Selection**, then choose the relevant link.

The default version of [!INCLUDE [prod_short](includes/prod_short.md)] includes the following **Report Selection** pages:

* **Report Selection - Sales**  
* **Report Selection - Project**  
* **Report Selection - Service**
* **Report Selection - Purchase**  
* **Report Selection - Cash Flow**  
* **Report Selection - Warehouse**  
* **Report Selection - Inventory**  
* **Report Selection - Bank Account**  
* **Report Selection - Production Order**  
* **Report Selection - Reminder/Finance Charge**  

## Example: Report selection for sales documents

The **Report Selection - Sales** page offers default reports to use in different scenarios for each related document type. Choose a document type in the **Usage** field, then add or review the report selection. You can set up more than one report and specify the sequence the reports must be sent or printed in.  

[!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

You can't send all document types as email attachments. For the document types you can, the **Report Selection** page contains extra fields.  

For example, on the **Report Selection - Sales** and **Report Selection - Purchase** pages, the following fields help you set up email:

|Field name |Description  |
|-----------|-------------|
|**Use for Email Body**| Insert summarized information, such as the invoice number, due date, or a link to a payment service in an email.|
|**Use for Email Attachment**| Attach the related document to the email.|
|**Email Body Layout Description**|Specify the email body layout to use. Typically, it's a custom report layout. |
|**Report Layout**|Specify the layout to use for the report. Typically, it's a custom report layout. |

## Report selection for finance reports

Similar to document reports, you can also configure the financial report definition for core finance reports such as Balance Sheet, Income Statement, and Retained Earnings. To learn more, go to [Report selection for finance reports](finance-financial-reporting-report-selection.md).

## Related information

[Set Up Reusable Email Texts and Layouts](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts)  
[Select a Check Layout](finance-how-define-check-layouts.md)  
[Set Up Reports for VAT and Intrastat (Germany)](LocalFunctionality/Germany/how-to-set-up-reports-for-vat-and-intrastat.md)  
[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
[Define Document Layouts for Customers and Vendors](ui-define-customer-vendor-document-layouts.md)  
[Set Up Printers](ui-specify-printer-selection-reports.md)  
[Report selection for finance reports](finance-financial-reporting-report-selection.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
