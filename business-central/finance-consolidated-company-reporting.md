---
title: Consolidate Data from Multiple Companies
description: This article explains how you can consolidate the general ledger entries of two or more separate companies (subsidiaries) into a consolidated company.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: consolidation, subsidiaries, consolidate
ms.search.form: 1826, 1827
ms.date: 09/29/2022
ms.author: bholtorf
---

# Consolidating Financial Data from Multiple Companies

Some organizations use [!INCLUDE [prod_short](includes/prod_short.md)] in multiple business units or legal entities. Others use [!INCLUDE [prod_short](includes/prod_short.md)] in subsidiaries that must report into parent organizations. In both cases, the accountants use built-in tools to help consolidate the financial data.  

You can consolidate the general ledger entries of two or more separate companies (subsidiaries) into a consolidated company. Each individual company involved in a consolidation is called a business unit. The combined company is called the consolidated company.  

You can import data into the consolidated company from other companies in the same [!INCLUDE [prod_short](includes/prod_short.md)] tenant from tenants or from files.  

If the financial statements of a business unit are in a different currency than the currency used in the consolidated company, you must set up exchange rates for consolidation.  

You can consolidate:  

* Across companies that have different charts of accounts.  
* Companies that use different fiscal years and different currencies.  
* Either the full amount or a percentage of a company's financial information
* Using different currency exchange rates in individual G/L accounts
* Companies in other accounting and business management programs

You set up the consolidated company in the same way that you set up other companies. The chart of accounts is independent of the chart of accounts in the business units. The chart of accounts in the business units can differ from one another. You set up a list of companies to consolidate, verify the accounting data before consolidating, import from files or databases, and generate consolidation reports. For more information, see [Set Up Company Consolidation](finance-consolidated-company-reporting-setup.md).  

> [!TIP]
> Consolidating financial data may especially be relevant in connection with intercompany processes. For more information, see [Managing Intercompany Transactions](intercompany-manage.md).

## Use the Consolidated Trial Balance report

The **Consolidated Trial Balance** report can give you an overview of the overall financial health of your business. The report combines general ledger entries from each of your companies in a new company that you created for the consolidated data. This company is typically referred to as the *consolidated company*. The consolidated company is just a container for the consolidated data, and doesn't have any live business data. The companies that you include in the consolidated company become **Business Units** in the report. For more information, see [Set Up Company Consolidation](finance-consolidated-company-reporting-setup.md). If you have four business units or fewer, you can also use the **Consolidated Trial Balance (4)** report.  

The report shows a line for each account, and follows the structure of the chart of accounts. An account isn't shown if all the amounts on the line are 0. The report shows the following information for each account:

* The account number and the name of the account.
* The totals for the consolidated company and for each business unit. Totals can display either as a net change or the balance to date.
* The eliminations made in the consolidated company. Eliminations always show for a period corresponding to the consolidated company's fiscal year.
* The total for the consolidated company after the eliminations show either as a net change or the balance to date.

## Consolidate data

Transferring the figures from the business units to the consolidated company is the actual *consolidation*. Before you consolidate, it's a good idea to check whether there are differences between the basic information in the business units and in the consolidated company. There are two reports that you can use to test the database and file.

### To test the data before you consolidate

Test your data before you transfer it to the consolidated company. [!INCLUDE[prod_short](includes/prod_short.md)] looks for differences in the information in the business units and the consolidated company. For example, whether account numbers or dimension codes are different. You must correct errors before you can run the report. You can test the database or, if you're importing data from an XML file, you can test the file.  

1. Open the consolidated company.  
2. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Business Units**, and then choose the related link.  
3. Test the file and database, as follows:  

    * To test a file, choose the **Test File** action, enter the name of the file to test, and then choose **Print**.  
    * To test the database, choose **Test Database**.  

### Run the consolidation

After you've tested the data, you can transfer it to the consolidated company.  

1. Sign in to the consolidated company.  
2. On the **Accountant Role Center**, choose the **Run Consolidation** action.  
3. Fill in the required fields.  
4. In the Filter section, set a filter for the relevant business unit or company name.  
5. Optionally, schedule the report to run at a convenient time.  

## Eliminate repeated transactions

After you consolidate the companies, you must find and eliminate any transactions that are recorded more than once across companies. Processing consolidation eliminations is a manual process.  

To eliminate repeated transactions:

1. Find transactions that might need to be adjusted, and enter general journal lines to eliminate them.
2. Run the **G/L Consolidation Eliminations** report to help you assess the effect of the general journal lines before posting.
3. Post the adjusting transactions.

The **G/L Consolidation Eliminations** report displays a tentative trial balance where you can simulate the consequences of eliminating entries. The report compares the entries in the consolidated company with the eliminations entered in the general journal.

Before a business unit can be included in the report, you must set up the unit on the **Business Units** page. The **Consolidate** field must be selected.

A line is created for each account, following the structure of the chart of accounts. An account isn't shown if all amounts on the line are 0. The following information is shown for each account:

* Account number.
* Account name.
* If you selected one or more business unit codes in the **Business Unit Code** field on the request page, a total shown for the consolidated company excludes the selected business units and eliminations. If you didn't fill in **Business Unit Code** field, the total for the consolidated company excludes eliminations.
* If you selected a business unit code in the **Business Unit Code** field on the request page, a total shows for the imported entries from the business unit. If you didn't fill in the **Business Unit Code** field, a total shows for the posted eliminations in the consolidated company.
* The total for the consolidated company with all the business units and all posted eliminations.
* The eliminations to make in the consolidated company. That is, the entries in the general journal that is selected on the request page.
* The posting text copied from the general journal.
* The consolidated company's total after the eliminations, if they're posted.

## Export and import consolidated data between databases

If data for a business unit is in another database, you must export the data to a file before you can include it in the consolidation. Each company must be exported separately. For this purpose, use the **Export Consolidation** batch job.  

> [!TIP]
> Use the same process to export consolidated data that must be submitted to Dynamics 365 Finance, such as if the current business unit is a subsidiary and the parent company uses Dynamics 365 Finance.

After you run the batch job, all entries in general ledger accounts are processed. For every combination of selected dimensions and date, the contents of the entries' **Amount** fields are totaled and exported. The next combination of the selected dimensions and date with the same account number is processed. Then the combinations in the next account number are processed, and so on.  

The exported entries contain the following fields: **Account No.**, **Posting Date**, and **Amount**. If dimensions information was also exported, dimension codes and dimension values are also included.  

1. For each exported line, if the total of the **Amount** fields is a debit, the account number that is set up in the business unit's **Consol. Debit Acc.** field is exported to the line. If the total is a credit, the corresponding number in the **Consol. Credit Acc.** field is exported to the line.  
2. The date used for each exported line is either the period's ending date or, if the transfer occurs each day, the exact date of the calculation.  
3. The dimension value exported for the entry will be the consolidated company dimension value that is specified in the **Consolidation Code** field for that dimension value. If a consolidated company dimension value hasn't been entered in the **Consolidated Code** field for the dimension value, the dimension value itself will be exported to the line.  
4. The XML files also contain the currency exchange rates in the consolidation period. These rates are included in a separate section at the beginning of the file.  

## See Also

[Set Up Company Consolidation](finance-consolidated-company-reporting-setup.md)  
[Managing Intercompany Transactions](intercompany-manage.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Exporting Your Business Data to Excel](about-export-data.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]