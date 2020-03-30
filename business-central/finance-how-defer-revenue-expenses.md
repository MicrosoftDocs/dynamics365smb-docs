---
title: Defer Revenues and Expenses| Microsoft Docs
description: To recognize revenues and expenses in periods other than the period in which the transaction was posted, you can automatically defer or postpone them over a specified schedule.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: postpone
ms.date: 04/01/2020
ms.author: sgroespe

---
# Defer Revenues and Expenses
To recognize a revenue or an expense in a period other than the period in which the transaction was posted, you can use functionality to automatically defer revenues and expenses over a specified schedule.

To distribute revenues or expenses on the involved accounting periods, you set up a deferral template for the resource, item, or G/L account that the revenue or expense will be posted for. When you post the related sales or purchase document, the revenue or expense are deferred to the involved accounting periods, according to a deferral schedule that is governed by settings in the deferral template and the posting date.

## To set up a G/L account for deferral
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the fields as necessary to create a G/L account for deferred revenues. For more information, see [The General Ledger and the Chart of Accounts](finance-general-ledger.md).
4. Repeat steps 2 and 3 to create a new G/L account for deferred expenses.

For both types of deferral, select **Balance Sheet** in the **Type** field, and name the accounts appropriately, such as "Unearned Income" for deferred revenues and "Unpaid Expenses" for deferred expenses.

## To set up a deferral template
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Deferral Templates**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the fields as necessary.
4. In the **Calc. Method** field, specify how the **Amount** field for each period on the **Deferral Schedule** page is calculated. You can choose between the following options:

   * **Straight-Line**: The periodic deferral amounts are calculated according to the number of periods, distributed according to period length.
   * **Equal Per Period**: The periodic deferral amounts are calculated according to the number of periods, distributed evenly on periods.
   * **Days Per Period**: The periodic deferral amounts are calculated according to the number of days in the period.
   * **User-Defined**: The periodic deferral amounts are not calculated. You must manually fill the **Amount** field for each period in the Deferral Schedule page. For more information, see the “To change a deferral schedule from a sales invoice” section.
5. In the **Period Desc.** field, specify a description that will be shown on entries for the deferral posting. You can enter the following placeholder codes for typical values, which will be inserted automatically when the period description is displayed.

   * %1 = The day number of the period posting date
   * %2 = The week number of the period posting date
   * %3 = The month number of the period posting date
   * %4 = The month name of the period posting date
   * %5 = The accounting period name of the period posting date
   * %6 = The fiscal year of the period posting date

Example: The posting date is 02/06/2016. If you enter “Expenses deferred for %4 %6”, then the description displayed will be "Expenses deferred for February 2016".

## To assign a deferral template to an item
> [!NOTE]  
>   The steps in this procedure are the same as when you assign a deferral template to a G/L account or a resource.
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item**, and then choose the related link.
2. Open the card for the item for which revenues or expenses must be deferred to the accounting periods when the item was sold or purchased.
3. In the **Default Deferral Template** field, select the relevant deferral template.

## To change a deferral schedule from a sales invoice
> [!NOTE]  
>   The steps in this procedure are the same as when you change a deferral schedule, for expenses, from a purchase invoice.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then choose the related link.
2. Create a sales invoice for an item that has a deferral template assigned. For more information, see [Invoice Sales](sales-how-invoice-sales.md).

    Notice that as soon as you enter the item (or resource or G/L account) on the invoice line, the **Deferral Code** field is filled with the code of the assigned deferral template.
3. Choose the **Deferral Schedule** action.
4. On the **Deferral Schedule** page, change settings on the header or values on the lines, for example to defer the amount to an additional accounting period.
5. Choose the **Calculate Schedule** action.
6. Choose the **OK** button. The deferral schedule is updated for the sales invoice. The related deferral template is unchanged.

## To preview how deferred revenues or expenses will be posted to the general ledger
> [!NOTE]  
>   The steps in this procedure are the same as when you preview how expense deferrals are posted.

1. On the **Sales Invoice** page, choose the **Preview Posting** action.
2. On the **Posting Preview** page, choose the **G/L Entry** action, and then choose the **Show Related Entries** action.

G/L entries to be posted to the specified deferral account, for example, Unearned Income, are denoted by the description that you entered in the **Period Desc.** field in the deferral template, for example, "Expenses deferred for February 2016".

## To review posted deferrals in the Sales Deferral Summary report
> [!NOTE]  
>   The steps in this procedure are the same as when you review the Purchasing Deferral Summary report.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Deferral Summary**, and then choose the related link.
2. On the **Sales Deferral Summary** page, in the **Balance as of** field, enter the date up to which you want to see deferred revenues.
3. Choose the **Preview** button.

## See Also
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working with General Journals](ui-work-general-journals.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
