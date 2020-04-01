---
    title: Walkthrough - Calculating Work in Process for a Job | Microsoft Docs
    description: With jobs, you can schedule the usage of your company's resources and keep track of the various costs associated with the usage of resources on a specific project. Jobs involve the consumption of employee hours, machine hours, inventory items, and other types of usage that have to be tracked as a job progresses.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Walkthrough: Calculating Work in Process for a Job

**Note**: This walkthrough must be performed on a demonstration company with the **Full Evaluation - Complete Sample Data** option, which is available in the Sandbox environment. For more information, see [Creating a Sandbox Environment](across-how-create-sandbox-environment.md).

With jobs, you can schedule the usage of your company's resources and keep track of the various costs associated with the usage of resources on a specific project. Jobs involve the consumption of employee hours, machine hours, inventory items, and other types of usage that have to be tracked as a job progresses. If a job runs over a long period, you may want to transfer these costs to a Work in Process (WIP) account on the balance sheet while the job is being completed. You can then recognize the costs and sales in your income statement accounts when it is appropriate.  

## About This Walkthrough  
 This walkthrough illustrates the following tasks:  

-   Calculating WIP.  
-   Selecting a WIP calculation method.  
-   Excluding part of a job from the WIP.  
-   Posting the WIP to the general ledger.  
-   Reversing a WIP posting.  

 Each step of the process calculates the value and moves the job transactions to the general ledger. The calculation and posting steps are separated to help you review your data and to make modifications before posting to the general ledger. Therefore, you should make sure that all information is correct after you run the calculation batch jobs and before you run the posting batch jobs.  

## Roles  
 This walkthrough uses the project team member (Tricia) as the persona.  

## Prerequisites  
 Before you can perform the tasks in the walkthrough, the [!INCLUDE[d365fin](includes/d365fin_md.md)] must be installed on your computer.  

## Story  
 This walkthrough focuses on CRONUS International Ltd., a design and consultancy firm that designs and fits new infrastructures, such as conference halls and offices, with furniture, accessories, and storage units. Most of the work at CRONUS is project-oriented and Tricia, a project team member, uses jobs to have an overview of each ongoing job that CRONUS has started and also the jobs that are completed. Some of the jobs can be very lengthy and can run over months. Tricia can use a WIP account to record the work in process and to track the costs throughout the job.  

## Calculating WIP  
 CRONUS has taken on a lengthy project that has now extended across reporting periods. Tricia, a project team member, calculates the work in process (WIP) to make sure that the financial statement of the company will be accurate.  

 During this procedure, Tricia will select a specific group of tasks that will be included in the WIP calculation. On the **Job Task Lines** page, she can specify these lines in the **WIP-Total** column.  

 The following table describes the three options.  

|Field|Description|  
|-------------------------------------|---------------------------------------|  
|**<blank>**|Leave blank if the job task is a part of a group of tasks.|  
|**Total**|Defines the range or group of tasks that are included in the WIP and recognition calculation. Within the group, any job task with **Job Task Type** set to **Posting** will be included in the WIP Total, unless its **WIP-Total** field is set to **Excluded**.|  
|**Excluded**|Applies only to a task with **Job Task Type** of **Posting**. The task is not included when WIP and recognition are calculated.|  

 In the following walkthrough, Tricia applies the Cost Value method, her company standard, to calculate WIP. She specifies what part of the job will be included in the WIP calculation by assigning WIP-Total values to various job task lines.  

### To calculate WIP  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2.  In the **Jobs** list, select the **Deerfield** job, and then choose the **Edit** action. This will open the job card in edit mode.  

     WIP can be calculated based on Cost Value, Sales Value, Cost of Sales, Percentage of Completion, or Completed Contract. In this example, CRONUS uses the Cost Value method.  

3.  On the **Posting** FastTab, choose the **WIP Method** field, and then select **Cost Value**.  
4.  Choose the **Job Task Lines** action and set the following values in the **WIP-Total** field.  

     The following table describes the values.  

    |Job Task No.|WIP-Total Field|  
    |------------------|----------------------|  
    |1130|Excluded|  
    |1190|Total|  
    |1210|Excluded|  
    |1310|Excluded|  

5.  Choose the **WIP** action, and then choose the **Calculate WIP** action.  
6.  On the **Job Calculate WIP** page, you can select a job that you want to calculate WIP. On the **Job** FastTab, select **Deerfield** in the **No.** field.  
7.  In the **Posting Date** field, enter a date that is later than the work date.
8.  In the **Document No.** field, enter **1**. This creates a document that you can refer to later for traceability.  
9. Choose the **OK** button to run the batch job. A message is displayed. Choose the **OK** button to continue. Close the **Job Task Lines** page.  

    > [!NOTE]  
    >  The message states that there are warnings associated with the WIP calculation. You will review the warnings in the next procedure.  

10. On the **Job** card, expand the **WIP and Recognition** FastTab to see the calculated values. You can also see the **WIP Posting Date** and the values that have been posted to the general ledger, if any.  

 Notice that the value for **Recog. Costs Amount** is 215.60 in the **To Post** column. This reflects the total costs of two of the items in the group of job tasks 1110 – 1130. The third item was set to **Excluded**, and therefore is not included in the WIP calculation.  

### To review WIP warnings  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job WIP Cockpit**, and then choose the related link.  
2.  Select the **Deerfield** job, and then choose the **Show Warnings** action.  
3.  On the **Job WIP Warnings** page, review the warning associated with the job.  

 After the accounting period ends, Tricia has to recalculate the WIP to include completed work to this point.  

### To recalculate WIP  

1.  On the **Job** card, choose the **WIP Entries** action to view the WIP calculation.  

     The **Job WIP Entries** page shows the WIP entries that were last calculated on a job, even if WIP has not yet been posted to the general ledger.  

2.  You can follow the steps in the procedure that explains how to calculate WIP to recalculate WIP. Every time WIP is calculated, an entry is created on the **Job WIP Entries** page.  
3.  Close the page.  

> [!NOTE]  
>  Work in Process and Recognition is only calculated. It is not posted to the general ledger. To do so, you must run **Post WIP to G/L** batch job after you have calculated the WIP and Recognition.

## Posting WIP to General Ledger  
 Now that Tricia has calculated WIP for this job, she can post it to the general ledger.  

### To post WIP to general ledger  

1.  From the **Jobs** list, select the **Deerfield** job.  
2.  Choose the **WIP** action, and then choose the **Post WIP to G/L** action.  
3.  On the **Job Post WIP to G/L** page, on the **Job** FastTab, select **Deerfield** in the **No.** field.  
4.  On the **Options** FastTab, in the **Reversal Document No.** field, enter **1**.  
5.  Choose the **OK** button to post WIP to the general ledger.  
6.  Choose the **OK** button to close the confirmation page.  

     After you have completed the posting, you can view the posting information on the **WIP G/L Entries** page.  

7.  In the **Jobs** list, select the **Deerfield** job, and then choose the **WIP G/L Entries** action.  

     On the **Job WIP G/L Entries** page, verify that the WIP has been posted to the general ledger.  

8.  Close the page.  
9. Open the **Job** card for the **Deerfield** job.  
10. On the **WIP and Recognition** FastTab, notice that in the **Posted** column, the **Recog. Costs G/L Amount** field is now filled in, which indicates that WIP was posted to the general ledger successfully.  
11. Choose the **OK** button to close the card.  

## Reversing a WIP Posting  
 Tricia determines that the job tasks that were excluded from the calculation of WIP should have been calculated in WIP. She can reverse the incorrect postings without having to post new WIP postings.  

### To reverse a WIP posting  

1.  From the **Jobs** list, select the **Deerfield** job.  
2.  Choose the **WIP** action, and then choose the **Post WIP to G/L** action.  
3.  On the **Job Post to WIP to G/L** page, on the **Job** FastTab, select **Deerfield** in the **No.** field.  
4.  On the **Options** FastTab, in the **Reversal Document No.** field, enter **1**.  
5.  In the **Reversal Posting Date** field, enter the original posting date. It should be the same date that you used to calculate WIP the first time.  
6.  Select the **Reverse Only** check box. This will reverse previously posted WIP, but does post new WIP to the general ledger.  
7.  Choose the **OK** button to run the batch job, and choose the **OK** button to close the confirmation page.  
8.  Open the **Job** card for **Deerfield**.  
9. On the **WIP and Recognition** FastTab, verify that there are no posted WIP entries.  
10. Close this page.  
11. In the **Jobs** list, select the **Deerfield** job, choose the **WIP** action, and then choose the **WIP G/L Entries** action. The WIP entries have the **Reversed** check box selected.  
12. Close this page.  
13. Open **Job Task Lines** for the job, include the parts of the job that should be in the WIP calculation, and then recalculate and post the new value to the general ledger.  

    > [!NOTE]  
    >  Suppose Tricia calculated and posted WIP for a job with incorrect dates. Following the method that was discussed earlier, she can reverse the incorrect postings, correct the dates, and repost to the general ledger.  

## Next Steps  
 This walkthrough has taken you through the steps of calculating WIP in [!INCLUDE[d365fin](includes/d365fin_md.md)]. In larger jobs, it may be useful to transfer the costs to a WIP account periodically while the job is being completed. This walkthrough has shown you how to exclude task lines from a calculation. It also shows you when you would have to recalculate. And finally, this walkthrough demonstrates how to post the WIP to the general ledger. An example of how to reverse a WIP posting to the general ledger is also included.  

## See Also  
 [Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)  
 [Walkthrough: Managing Projects with Jobs](walkthrough-managing-projects-with-jobs.md)   
 [Understanding WIP Methods](projects-understanding-wip.md)   
 [Monitor Progress and Performance](projects-how-monitor-progress-performance.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
