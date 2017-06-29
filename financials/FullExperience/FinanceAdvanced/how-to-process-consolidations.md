---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Process Consolidations
This topic provides a high-level overview of how you can work through the consolidation process.  
  
## Setting Up the Consolidation Company  
 Before you can perform a consolidation, you must set up the consolidated company. The company must be set up like any other company with its own chart of accounts and dimensions.  
  
#### To set up the consolidation company  
  
1.  The chart of accounts for a company that will be consolidated must specify accounts for consolidation. For each posting general ledger account in each company, you must specify the general ledger account in the consolidated company to which the balance will be transferred on consolidation. This is a mapping that will allow companies with different chart of accounts to be consolidated together.  
  
     For more information about how to specify accounts for consolidations, see [How to: Enter Consolidation Information on General Ledger Accounts](../how-to-enter-consolidation-information-on-general-ledger-accounts.md).  
  
2.  To consolidate several companies' financial data in a consolidated company, you must enter information about the subsidiary as business units to be included and about how much their figures will be included.  
  
     For more information about how to enter information about the subsidiary, see [How to: Enter Basic Information for Consolidated Companies](../how-to-enter-basic-information-for-consolidated-companies.md).  
  
3.  You can specify exchange rates when consolidating the financial statements of business units if the financial statements are in a foreign currency. The three exchange rates that are used are **Average Rate \(Manual\)**, **Closing Rate**, and **Last Closing Rate**.  
  
     For more information about how to specify exchange rates, see [How to: Specify Exchange Rates for Consolidations](../how-to-specify-exchange-rates-for-consolidations.md).  
  
4.  You can consolidate dimension information and general ledger accounts. In the **Dimensions Value** window, fill out the **Consolidation Code** field. How the **Consolidation Code** field is filled in depends on whether dimension information is transferred to the consolidated company when you consolidate.  
  
    |Dimension information|Field definition|  
    |---------------------------|----------------------|  
    |If you do not want to consolidate dimension information.|Leave the **Consolidation Code** field blank.<br /><br /> **NOTE:** Make sure not to select any dimensions in the **Copy Dimensions** fields in any consolidation functions or reports described later in this topic.|  
    |If you want to consolidate dimension information.|Leave the **Consolidation Code** field blank.<br /><br /> **NOTE:** However, the consolidation will only work if the dimension values in the business unit are the same as the consolidated company.|  
    |When the dimension value code in the business unit is to be consolidated to a different dimension value code in the consolidated company.|Fill in the **Consolidated Code** field.<br /><br /> **NOTE:** The contents of the field should be the dimension value code that is contained in the consolidated company. For more information about how to consolidate dimension information, see [How to: Set Up Dimensions and Dimension Values](../how-to-set-up-dimensions-and-dimension-values.md).|  
  
## Exporting Data for Consolidations  
 If a business unit is located in another database, you must export the consolidation data to a file before it can be consolidated. Each company must be exported separately. For this purpose, use the **Export Consolidation** batch job.  
  
 After the batch job is run, all the entries in every general ledger account are processed. For every combination of selected dimensions and date, the contents of the entries' **Amount** fields are totaled and exported. The next combination of selected dimensions and date with the same account number is processed, then the combinations in the next account number are processed, and so on.  
  
 The exported entries contain the following fields: **Account No.**, **Posting Date**, and **Amount**. If dimensions information was also exported, dimension codes and dimension values will also be included.  
  
#### To export data for consolidation  
  
1.  For each exported line, if the total of the **Amount** fields is a debit, the account number that is set up in the business unit's **Consol. Debit Acc.** field is exported to the line. If the total is a credit, the corresponding number in the **Consol. Credit Acc.** field is exported to the line.  
  
2.  The date used for each exported line is either the period's ending date or, if the transfer occurs each day, the exact date of the calculation.  
  
3.  The dimension value exported for the entry will be the consolidated company dimension value that is set up in the **Consolidation Code** field for that dimension value. If no consolidated company dimension value has been entered in the **Consolidated Code** field for that dimension value, the dimension value itself will be exported to the line.  
  
4.  The XML files also contain the currency exchange rates in the consolidation period. These rates are included in a separate section at the beginning of the file.  
  
 For more information about how to export the consolidation data, see [How to: Export Business Unit Information](../how-to-export-business-unit-information.md).  
  
## Testing Data  
 Before you consolidate the data, it is a good idea to check whether there are differences between the basic information in the business units and in the consolidated company.  
  
#### To check differences between information found in the business units and the consolidated company  
  
1.  There are two reports that are designed to test a database and file.  
  
2.  For more information about how to test a database, see [How to: Test Databases Before Consolidating](../how-to-test-databases-before-consolidating.md).  
  
3.  For more information about how to test a file, see [How to: Test Files Before Consolidating](../how-to-test-files-before-consolidating.md).  
  
## Consolidating the Data  
 After you have tested the data, you can begin the consolidation by importing the data from the business units.  
  
#### To consolidate the data  
  
-   This process can be done by either consolidating from the same database or consolidating from files.  
  
     For more information, see [How to: Consolidate from Databases](../how-to-consolidate-from-files.md).  
  
## Processing Consolidation Eliminations  
 After you have consolidated all the companies, you must make elimination entries to remove transactions that are recorded across more than one company or remove entries involving intercompany transactions.  
  
#### To process consolidation eliminations  
  
1.  Manually calculate the eliminations.  
  
2.  Enter the amounts in a general journal.  
  
3.  Post the journal.  
  
 Before you post the eliminations, you can verify the effect on the trial balance of the consolidated company by using the ![Shortcut icon](../media/shortcutcoldicon.gif "shortcutColdIcon")**G\/L Consolidation Eliminations** report. The report displays a tentative trial balance. It shows the consequences of eliminating the entries by comparing the entries in the consolidated company with the eliminations that have been entered in the general journal. Calculating the eliminations is a time-consuming manual process that may be aided by setting up specific intercompany accounts, intercompany customers\/vendors, and intercompany posting groups.  
  
## See Also  
 Consolidated Trial Balance   
 Consolidated Trial Balance \(4\)%20$\).md)