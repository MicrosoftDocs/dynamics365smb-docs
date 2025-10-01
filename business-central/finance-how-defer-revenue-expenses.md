---
title: Defer revenues and expenses
description: Learn how to automatically defer or postpone revenues and expenses.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: postpone
ms.search.form: 1700, 1701, 1702, 1703, 1704, 1705, 1706, 1707, Report_1700, Report_1701, Report_1702
ms.date: 04/30/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Defer revenues and expenses

To recognize revenues or expenses in a later period than the transaction posted in, you can set up a schedule to automatically defer them.

To distribute revenues or expenses to accounting periods, you set up a deferral template for the resource, item, or G/L account that the revenue or expense is for. When you post the sales or purchase document, the revenue or expense is deferred to the accounting periods you specify in the deferral template and the posting date.

> [!NOTE]
> Sales and purchase journals validate the source code. The validation requires that the source code for sales journals and purchase journals aren't identical when you're using deferrals. If the source code is set up to be identical, you can work around this limitation by creating a template and batch that use another source code.

## To set up a G/L account for deferral

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Chart of Accounts**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the fields as necessary to create a G/L account for deferred revenues. For more information, see [The General Ledger and the Chart of Accounts](finance-general-ledger.md).
4. Repeat steps 2 and 3 to create a new G/L account for deferred expenses.

For both types of deferral, select **Balance Sheet** in the **Type** field, and name the accounts appropriately, such as *Unearned Income* for deferred revenues and *Unpaid Expenses* for deferred expenses.

## To set up a deferral template

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Deferral Templates**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
4. In the **Calc. Method** field, specify how to calculate the value in the **Amount** field for each period on the **Deferral Schedule** page. You can choose between the following options:

   * **Straight-Line**: The periodic deferral amounts are calculated according to the number of periods, distributed according to period length.
   * **Equal per Period**: The periodic deferral amounts are calculated according to the number of periods, distributed evenly on periods.
   * **Days per Period**: The periodic deferral amounts are calculated according to the number of days in the period.
   * **User-Defined**: The periodic deferral amounts aren't calculated. You must manually fill the **Amount** field for each period in the Deferral Schedule page. To learn more, go go [To change a deferral schedule from a sales invoice](#to-change-a-deferral-schedule-from-a-sales-invoice).
5. In the **Period Desc.** field, specify a description that shows on entries for the deferral posting. You can enter the following placeholder codes for typical values. The values are added automatically when the period description displays.

   * %1 = The day number of the period posting date
   * %2 = The week number of the period posting date
   * %3 = The month number of the period posting date
   * %4 = The month name of the period posting date
   * %5 = The accounting period name of the period posting date
   * %6 = The fiscal year of the period posting date

Example: The posting date is 02/06/2025. If you enter “Expenses deferred for %4 %6”, the description display "Expenses deferred for February 2025".

## To assign a deferral template to an item

> [!NOTE]  
> The steps in this procedure are the same as when you assign a deferral template to a G/L account or a resource.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, and then choose the related link.
2. Open the card for the item for which revenues or expenses must be deferred to the accounting periods when the item was sold or purchased.
3. On the **Costs & Posting** FastTab, in the **Default Deferral Template** field, select the relevant deferral template.

## To change a deferral schedule from a sales invoice

> [!NOTE]  
> The steps in this procedure are the same as when you change a deferral schedule, for expenses, from a purchase invoice.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Invoices**, and then choose the related link.
2. Create a sales invoice for an item that has a deferral template assigned. For more information, see [Invoice Sales](sales-how-invoice-sales.md).

    Notice that as soon as you enter the item (or resource or G/L account) on the invoice line, the **Deferral Code** field is filled with the code of the assigned deferral template.
3. Choose the **Deferral Schedule** action.
4. On the **Deferral Schedule** page, change settings on the header or values on the lines, for example, to defer the amount to another accounting period.
5. Choose the **Calculate Schedule** action.
6. Choose the **OK** button. The deferral schedule is updated for the sales invoice. The related deferral template is unchanged.

## To preview how deferred revenues or expenses post to the general ledger

> [!NOTE]  
> The steps in this procedure are the same as when you preview how expense deferrals are posted.

1. On the **Sales Invoice** page, choose the **Preview Posting** action.
2. On the **Posting Preview** page, choose the **G/L Entry** action, and then choose the **Show Related Entries** action.

G/L entries to be posted to the specified deferral account, for example, Unearned Income, are denoted by the description that you entered in the **Period Desc.** field in the deferral template, for example, "Expenses deferred for February 2016".

## To review posted deferrals in the Sales Deferral Summary or the Purchasing Deferral Summary report

> [!NOTE]  
> The steps in this procedure are the same as when you review the Purchasing Deferral Summary report.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Deferral Summary**, and then choose the related link.
2. On the **Sales Deferral Summary** page, in the **Balance as of** field, enter the date up to which you want to see deferred revenues.
3. Choose the **Preview** button.

## To specify a period in which to allow deferral posting

You can specify a period in which people can post transactions by entering dates in the **Allow Posting From** and **Allow Posting To** fields as follows:

* For all users, on the **General Ledger Setup** page
* For specific users, on the **User Setup** page

If you do that, you must make an exception for deferrals to allow them to be posted outside the period. To define the period, follow these steps.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Ledger Setup** or **User Setup**, and then choose the related link.
2. In the **Allow Deferral Posting From** and **Allow Deferral Posting To** fields, enter a start and end date for the period.

### Video guidance

The following video shows how to define the period in which you allow people to post deferred revenue and expenses, and how to specify exceptions.

> [!VIDEO https://learn-video.azurefd.net/vod/player?id=5d98a594-6b1c-45a5-b93a-1fb670a051e5]

## Deferral reports

You can analyze your deferral data with the data analysis tool or with out-of-the-box supplied reports. 

To enable ad-hoc analysis on non-posted deferral lines, [!INCLUDE[prod_short](includes/prod_short.md)] [!INCLUDE[prod_short](includes/2025-releasewave2-short.md)] includes three new list pages:

* Sales deferral lines
* Purchasing deferral lines
* G/L deferral lines

When you turn on analysis mode for these list pages, you can analyze deferral lines that you haven't posted yet across all documents.

[!INCLUDE [tip_open_report_from_docs](includes/tip-open-report-from-docs.md)]

[!INCLUDE [finance_reports_deferrals](includes/finance-reports-deferrals-include.md)]

## Related information

[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
