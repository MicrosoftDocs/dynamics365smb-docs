---
title: Run Batch Jobs and XMLports
description: You run batch jobs to process data and update information, for example, to do periodic accounting activities, or to do calculations.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: task, process
ms.search.form: 672, 676, 682
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Run Batch Jobs and XMLports

A batch job is a routine that processes data in batches, for example the **Adjust Exchange Rates** batch job. There are batch jobs that perform periodic accounting activities, such as closing the income statement at the end of a fiscal year. Many batch jobs do calculation work, such as calculation of finance charges, exchange rate adjustment, and calculation of unit prices.

A batch job is like a report, except the batch job uses the result of its work to update information directly, instead of printing the results.

You can schedule when a batch job runs. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## To run a batch job
1. To open the request page for the relevant batch job, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter the name of the batch job, and then choose the related link.
2. If there is an **Options** FastTab for the batch job, fill in the fields to determine what the batch job will do.
3. The page may contain one or more FastTab with filters, which you can use to limit the data included in the batch job. You can enter criteria in the suggested filters or add more filters.
4. Choose the **OK** button to start the batch job.

## Related information
[Sorting, Searching, and Filtering Lists](ui-enter-criteria-filters.md)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
