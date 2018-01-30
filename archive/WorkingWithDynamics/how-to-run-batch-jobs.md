---
    title: How to Run Batch Jobs | Microsoft Docs
    description: A batch job is a routine that processes data in batches, for example the **Adjust Exchange Rates** batch job. There are batch jobs that perform periodic accounting activities, such as closing the income statement at the end of a fiscal year and reporting Intrastat information. Many batch jobs do calculation work, such as calculation of finance charges, exchange rate adjustment, and calculation of unit prices.
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
# Run Batch Jobs
A batch job is a routine that processes data in batches, for example the **Adjust Exchange Rates** batch job. There are batch jobs that perform periodic accounting activities, such as closing the income statement at the end of a fiscal year and reporting Intrastat information. Many batch jobs do calculation work, such as calculation of finance charges, exchange rate adjustment, and calculation of unit prices.  
  
 A batch job is like a report, except the batch job uses the result of its work to update information directly, instead of printing the results.  
  
### To run a batch job  
  
1.  Open the request window for the relevant batch job.  
  
2.  If there is an **Options** FastTab for the batch job, fill in the fields on the **Options** FastTab to determine what the batch job will do.  
  
     To see Help for the batch job, press F1 in the batch job request window. The Help will explain how to fill in any option fields in the window.  
  
3.  The window may contain one or more FastTab with filters, which you can use to limit the data included in the batch job. You can enter criteria in the suggested filters or add more filters.  
  
     There may be two types of filters available:  
  
    -   Under the **Show results** heading, you can enter regular table filters.  
  
    -   Under the **Limit totals to** heading, you can enter FlowFilters.  
  
         For more information, see [FlowFilters](../FullExperience/how-to-set-filters.md).  
  
4.  Choose the **OK** button to start the batch job. If you do not want to run the batch job now, choose the **Cancel** button to close the window.  
  
## See Also  
 [Set Filters](../FullExperience/how-to-set-filters.md)   
 [Enter Criteria in Filters](../FullExperience/enter-criteria-in-filters.md)