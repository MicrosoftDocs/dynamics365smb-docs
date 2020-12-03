---
title: How to Adjust and Reconcile Inventory Cost with General Ledger with Job Queue | Microsoft Docs
description: To optimize the experience, automatic cost adjustment and posting to GL are turned on by default. However, as data accumulates over time, that might impact performance. To reduce the load on the application, it is often helpful to use job queue entries to move tasks to run in the background.
author: AndreiPanko

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.date: 12/12/2020
ms.author: andreipa

---
# How to Adjust and Reconcile Inventory Cost with General Ledger with Job Queue
To optimize the experience, automatic cost adjustment and posting to GL are turned on by default. However, as data accumulates over time, that might impact performance. To reduce the load on the application, it is often helpful to use job queue entries to move tasks to run in the background.

## Move the task of adjusting item costs to the background with help of assisted setup

Creating the job queue entries can be tricky, even for an experienced consultant, so we have an assisted setup guide to make the process easier for adjusting item costs. 

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.  
2. On the **Invnetory Setup** page, turn off the **Automatic Cost Posting** toggle, or specify **Never** in the **Automatic Cost Adjustment** field. The notification will display at the top of the page.
3. Choose **Schedule Job Queue Entry** in the notification.
4. Select which task you want to schedule.
> [!NOTE]
> If job queue entry for specific task already exists, system will not allow you to create new job queue entry. 
5. Select the **View job queue entries when finished** check box to review and adjust settings. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## To create a job queue entry for adjusting and reconciling inventory cost manually

Alternatively, you can create job queue entries manually.

The following procedure shows how to set the **Adjust Cost - Item Entries** batch job to automatically run daily. 

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Queue Entries**, and then choose the related link.  
2. Choose the **New** action.  
3. In the **Object Type to Run** field, select **Report**.  
4. In the **Object ID to Run** field, select 795, **Adjust Cost - Item Entries**.
5. In the **Next Run Date Formula** field, enter 1D.
6. In the **Starting Time** field, enter 2 AM.
7. Choose the **Set Status to Ready** action.

Inventory cost will be updated every night.

The steps are similar for **Post Inventory Cost to G/L** batch job. In the **Object Type to Run** field, select **Codeunit** and in the **Object ID to Run** field, select 2846, **Post Inventory Cost to G/L**.

> [!NOTE]
> To avoid locking do not schedule **Adjust Cost - Item Entries**, **Post Inventory Cost to G/L**, sales and purchase posting jobs at the same time and ensure they use same Job Queue Category.



## See Also

[Adjust Item Costs](inventory-how-adjust-item-costs.md)  
[Reconcile Inventory Costs with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md) 
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
