---
title: Project Reports and Analytics
description: See which project reports and analytics are available in the standard version of Business Central so that you can keep track of your business.
author: AndreiPanko

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 06/01/2021
ms.author: andreipa

---
# Project Reports and Analytics in Business Central

Project reporting in [!INCLUDE [prod_short](includes/prod_short.md)] allows project and business professionals to get insights and statistics about current and past project activities.  

## Reports

The following table describes some of the key reports in jobs reporting.

|Report |Object ID|Description  |
|---------|---------|---------|
|**Job Analysis**|1008|Analyzes your job by using settings that you specify. For example, you can create a report that shows you the budgeted prices, usage prices, and billable prices, and then compares the three sets of prices.<br>Use a combination of the available **Amount** fields to create your own analysis. For each field, select one of the following prices, costs, or profit values: Schedule, Usage, Contract, and Invoiced. <br>Select whether the currency is specified in Local Currency or Foreign Currency. |
|**Job Planning Lines**|1006|This report shows the different job planning and job task lines – including the line type, quantities, unit of measure, total costs, etc.|
|**Job Actual to Budget**|1009|Compares scheduled and usage amounts for selected jobs. All lines of the selected job show quantity, total cost, and line amount. <br>This report is intended for completed jobs, although you can use it at any time during a job.<br>In the US, Canada, and Mexico, this report is not available. Instead, use the **Job Actual to Budget (Cost)** (10210) or **Job Actual to Budget (Price)** (10211) reports.|
|**Job Suggested Billing**|1011|Shows a list of all jobs, grouped by customer, how much the customer has already been invoiced, and how much remains to be invoiced, that is, the suggested billing. <br>In the US, Canada, and Mexico, this report is not available. Instead, use the **Job Cost Suggested Billing** (10219) report.|
|**Jobs per Customer**|1012|Shows a list of all jobs, grouped by customer. It allows you to compare the scheduled price, the percentage of completion, the invoiced price, and the percentage of invoiced amounts for each **Bill-to Customer**.|
|**Items per Job** or **Jobs per Item**|1013 or 1014|An overview about the used items in a job. Depending on the report that you want to use to get an overview about the planned items for a project, you can set an additional filter. The report shows the relevant items and an accumulated value about the costs.|
|**Job Transaction Detail**|1007|This report will give you an overview over the posted job tasks like resources and items. Includes a detailed information about the total costs and total prices plus an information concerning line discounts,and so on. The report shows data from the job ledger entries.|
|**Job WIP to G/L**|1010|Shows the value of work in process on the jobs that you select compared to the amount that has been posted in the general ledger.|




## Tasks

The following articles describe some of the key tasks for analyzing the state of your business:

* [Monitor Job Progress and Performance](projects-how-monitor-progress-performance.md)  


## See also

[Setting Up Project Management](projects-setup-projects.md)  
[Project management](projects-manage-projects.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
