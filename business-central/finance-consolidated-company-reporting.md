---
title: Consolidate Data from Multiple Companies
description: This topic explains how you can consolidate the general ledger entries of two or more separate companies (subsidiaries) into a consolidated company.
author: edupont04


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: consolidation, subsidiaries, consolidate
ms.search.form: 1826, 1827
ms.date: 06/16/2021
ms.author: edupont

---

# Consolidating Financial Data from Multiple Companies

Some organizations use [!INCLUDE [prod_short](includes/prod_short.md)] in multiple business units or legal entities. Others use [!INCLUDE [prod_short](includes/prod_short.md)] in subsidiaries that must report into parent organizations. In both cases, the accountants use built-in tools to help consolidate the financial data.  

You can consolidate the general ledger entries of two or more separate companies (subsidiaries) into a consolidated company. Each individual company involved in a consolidation is called a business unit. The combined company is called the consolidated company.  

You can import data into the consolidated company from other companies in the same [!INCLUDE [prod_short](includes/prod_short.md)] tenant, from tenants, or from files.  

If the financial statements of a business unit are in a different currency than those of the consolidated company, you must set up exchange rates for consolidation.  

You can consolidate:  

* Across companies that have different charts of accounts.  
* Companies that use different fiscal years and different currencies.  
* Either the full amount or a percentage of a company's financial information
* Using different currency exchange rates in individual G/L accounts
* Companies in other accounting and business management programs

You set up the consolidated company in the same way that you set up other companies. The chart of accounts is independent of the chart of accounts in the other business units, and the chart of accounts in the individual business units may differ from one another. You set up a list of companies to consolidate, verify the accounting data before consolidating, import from files or databases, and generate consolidation reports. For more information, see [Set Up Company Consolidation](finance-consolidated-company-reporting-setup.md).  

> [!TIP]
> Consolidating financial data may especially be relevant in connection with intercompany processes. For more information, see [Managing Intercompany Transactions](intercompany-manage.md).

## Trial balance

If you have more than one company in [!INCLUDE[prod_short](includes/prod_short.md)], the **Consolidated Trial Balance** report can give you an overview of the financial health of your overall business.  

The report combines general ledger entries from each of your companies in a new company that you create to contain the consolidated data. This company is typically referred to as the "consolidated company". The consolidated company is just a container for the consolidated data, and does not have any live business data. The companies that you include in the consolidated company become **Business Units** in the report. For more information, see [Set Up Company Consolidation](finance-consolidated-company-reporting-setup.md).  

## Consolidate data

The process of transferring the figures from the business units to the consolidated company is the actual *consolidation*. Before you do this, it is a good idea to check whether there are differences between the basic information in the business units and in the consolidated company. There are two reports that you can use to test the database and file.

### To test the data before you consolidate

You can test your data before you transfer it to the consolidated company. [!INCLUDE[prod_short](includes/prod_short.md)] looks for differences in the information in the business units and the consolidated company. For example, whether account numbers or dimension codes are different. You must correct errors before you can run the report. You can test the database or, if you are importing data from an XML file, you can test the file.  

1. Open the consolidated company.  
2. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Business Units**, and then choose the related link.  
3. Do one of the following:  

    * To test a file, choose the **Test File** action, enter the name of the file to test, and then choose **Print**.  
    * To test the database, choose **Test Database**.  

### Run the consolidation

After you have tested the data, you can transfer it to the consolidated company.  

1. Sign in to the consolidated company.  
2. On the **Accountant Role Center**, choose the **Run Consolidation** action.  
3. Fill in the required fields.  
4. In the Filter section, set a filter for the relevant business unit or company name.  
5. Optionally, schedule the report to run at a convenient time.  

## Eliminate repeated transactions

After you have consolidated all the companies, you must find any transactions that are recorded more than once across companies and then post elimination entries to remove them.

Processing consolidation eliminations is a manual process.  

To eliminate repeated transactions:

1. Find transactions that potentially need to be adjusted and enter general journal lines to eliminate them.
2. Run the **G/L Consolidation Eliminations** report to help you assess the effect of the general journal lines before posting.
3. Post the adjusting transactions.

The **G/L Consolidation Eliminations** report displays a tentative trial balance where you can simulate the consequences of eliminating entries by comparing the entries in the consolidated company with the eliminations that have been entered in the general journal.

Before a business unit can be included in the report, it must be set up on the **Business Units** page and the **Consolidate** field must be selected.

Each account appears on a line by itself, following the structure of the chart of accounts. An account is not shown if all the amounts on the line are 0. The following information is shown for each account:

* Account number
* Account name.
* If you have selected one or more business unit codes in the **Business Unit Code** field on the request page, a total is shown for the consolidated company excluding the selected business units and eliminations. If you have not filled in the **Business Unit Code** field, a total is shown for the consolidated company excluding eliminations.
* If you have selected a business unit code in the **Business Unit Code** field on the request page, a total is shown for the imported entries from the business unit. If you have not filled in the **Business Unit Code** field, a total is shown for the posted eliminations in the consolidated company.
* The total for the consolidated company with all the business units and all posted eliminations.
* The eliminations to be made in the consolidated company, that is, the entries in the general journal that is selected on the request page.
* The posting text copied from the general journal.
* The consolidated company's total after the eliminations, if they are posted.

## Export and import consolidated data between databases

If data for a business unit is in another database, you must export the data to a file before you can include it in the consolidation. Each company must be exported separately. For this purpose, use the **Export Consolidation** batch job.  

> [!TIP]
> Use the same process to export consolidated data that must be submitted to Dynamics 365 Finance, such as if the current business unit is a subsidiary and the parent company uses Dynamics 365 Finance.

After you run the batch job, all entries in general ledger accounts are processed. For every combination of selected dimensions and date, the contents of the entries' **Amount** fields are totaled and exported. The next combination of selected dimensions and date with the same account number is processed, then the combinations in the next account number are processed, and so on.  

The exported entries contain the following fields: **Account No.**, **Posting Date**, and **Amount**. If dimensions information was also exported, dimension codes and dimension values are also included.  

1. For each exported line, if the total of the **Amount** fields is a debit, the account number that is set up in the business unit's **Consol. Debit Acc.** field is exported to the line. If the total is a credit, the corresponding number in the **Consol. Credit Acc.** field is exported to the line.  
2. The date used for each exported line is either the period's ending date or, if the transfer occurs each day, the exact date of the calculation.  
3. The dimension value exported for the entry will be the consolidated company dimension value that is set up in the **Consolidation Code** field for that dimension value. If no consolidated company dimension value has been entered in the **Consolidated Code** field for that dimension value, the dimension value itself will be exported to the line.  
4. The XML files also contain the currency exchange rates in the consolidation period. These rates are included in a separate section at the beginning of the file.  

## See Also

[Set Up Company Consolidation](finance-consolidated-company-reporting-setup.md)  
[Managing Intercompany Transactions](intercompany-manage.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Exporting Your Business Data to Excel](about-export-data.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]