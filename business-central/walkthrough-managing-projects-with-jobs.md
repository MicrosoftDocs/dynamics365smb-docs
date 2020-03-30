---
    title: Walkthrough - Managing Projects with Jobs | Microsoft Docs
    description: This walkthrough introduces you to the project management features in jobs. Jobs are a way for you to schedule the usage of your company's resources and to keep track of the various costs associated with the resources on a specific project. Jobs involves the consumption of employee hours, machine hours, inventory items, and other types of usage that you may want to track as a job progresses.
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
# Walkthrough: Managing Projects with Jobs

**Note**: This walkthrough must be performed on a demonstration company with the **Full Evaluation - Complete Sample Data** option, which is available in the Sandbox environment. For more information, see [Creating a Sandbox Environment](across-how-create-sandbox-environment.md).

This walkthrough introduces you to the project management features in jobs. Jobs are a way for you to schedule the usage of your company's resources and to keep track of the various costs associated with the resources on a specific project. Jobs involves the consumption of employee hours, machine hours, inventory items, and other types of usage that you may want to track as a job progresses.  

 This walkthrough covers the setup of a new job in addition to some common tasks such as handling fixed pricing, making payment by installments, posting invoices from jobs, and copying jobs.  

## About This Walkthrough  
 This walkthrough demonstrates the following tasks:  

### Setting Up a Job  
 With the budget structure set up for jobs, creating a job is straightforward. This walkthrough covers the following procedures:  

-   Setting up job task lines and planning lines.  
-   Creating job-specific prices for items, resources, and general ledger accounts.  
-   Invoicing from a job.  

### Handling Fixed Prices  
 In jobs, you can handle fixed prices and the prices for services or goods that are agreed upon in advance with customers. In this walkthrough, you can do the following:  

-   See how contract and invoice values are determined.  
-   Allow for extra work in the schedule that has not been invoiced.  

### Copying a Job  
 This part of the walkthrough focuses on how to copy part or all of a job in order to reduce manual data entry and improve accuracy. It includes the following:  

-   Copying part of a job to a new job.  
-   Copying job-specific prices.  
-   Copying planning lines.  

### Making Payment by Installment  
 When a large, expensive project lasts for a long period, the customer often makes an agreement with the company to pay by installments. This scenario shows how you set up payment by installments and covers:  

-   Creating payment by installments for a job.  
-   Invoicing payments to customers.  
-   Accounting for usage in a job set up for payment by installments.  

## Roles  
 This walkthrough includes tasks for the following roles:  

-   Project Manager  
-   Project Team Member  

## Prerequisites  
 Before you can perform the tasks in the walkthrough, you must do the following:  

-   Install the CRONUS International Ltd. demonstration database.
-   Create sample data by using the steps in the following section.  

## Story  
This walkthrough focuses on CRONUS International Ltd., a design and consultancy firm that designs and fits new infrastructures, such as conference halls and offices, with furniture, accessories, and storage units. Most of its work is project oriented. Prakash is a project manager at CRONUS. He uses jobs to give him an overview of each ongoing job that CRONUS has started, as well as the jobs that are completed. He is usually the one who sets up deals with customers and enters the core of the job, which is task and planning lines in addition to prices, into [!INCLUDE[d365fin](includes/d365fin_md.md)]. He finds that creating, maintaining, and reviewing information is straightforward. Prakash also likes the way [!INCLUDE[d365fin](includes/d365fin_md.md)] enables copying jobs and payment by installments.

 Tricia, a project team member who reports to Prakash, is responsible for monitoring the job day-to-day. She enters her own work in addition to the work performed by technicians on every task. She records the items that they have used and the costs that they have incurred.  

## Preparing Sample Data  
 To prepare for this walkthrough, you must add Tricia as a new resource.  

### To prepare the sample data  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resources**, and then choose the related link.  
2.  Choose the **New** action to create a new resource card.  
3.  On the **General** FastTab, enter the following information:  

    - **No.**: **Tricia**  
    - **Name**: **Tricia**  
    - **Type**: **Person**  

4.  Choose the **Base Unit of Measure** field, and choose the **New** action to open the **Resource Unit of Measure** page. In the **Code** field, select **Hour**.  
5.  On the **Invoicing** FastTab, enter the following information:  

    -   **Direct Unit Cost**: **5**  
    -   **Indirect Cost %**: **4**  
    -   **Unit Cost**: **10**  
    -   **Gen. Prod. Posting Group**: **Services**  
    -   **VAT Prod. Posting Group**: **VAT 25**  

6. Close the page.

In the next procedure, you create a job journal batch for Tricia in order to post her usage.  

### To create a Job Journal batch  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.  
2.  On the **Job Journal** page, choose the **Batch Name** field. The **Job Journal Batches** page opens.  
3.  Choose the **New** action to create a new line with the following information:  

    -   **Name**: **Tricia**  
    -   **Description**: **Tricia**  
    -   **No. Series**: **JJNL-GEN**  

4.  Choose the **OK**  button to save the changes.

## Setting Up a Job  
 In this scenario, CRONUS has won a contract with a customer, Progressive Home Furnishings, to design a conference and dining hall. The customer is based in the United States and the project will require special software. The project manager reaches an agreement with the customer and creates a job that covers the agreement.  

### To set up a job  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2.  Choose the **New** action to create a new card.  
3.  On the **General** FastTab, enter the following information:  

    -   **Description**: **Advising on conference hall setup**  
    -   **Bill-to-Customer No.**: **01445544**  

4.  On the **Posting** FastTab, enter the following information:  

    -   **Status**: **Planning**  
    -   **Job Posting Group**: **Setting Up**  
    -   **WIP Method**: **Cost Value**  

5.  On the **Duration** FastTab, type today's date into the **Starting Date** and **Ending Date** fields. These dates will help apply currency conversions when the job is invoiced.  
6.  On the **Foreign Trade** FastTab, set the currency code to **USD**. If you select USD in the **Invoice Currency Code** field, then the job will be invoiced in U.S. dollars and planned in the local currency of CRONUS only.  

 You can customize the pricing for customers on a per job basis, depending on the agreements you have set up. In the next procedure, the project manager specifies a cost for Tricia’s time, sets the price for the required software, and adds in the travel costs that the customer has agreed to pay.  

### To customize pricing  

1.  From the job card, choose the **Resource** action.  
2.  On the **Job Resource Prices** page, enter the following information:  

    -   **Code**: **Tricia**  
    -   **Unit Price**: **20**  

3.  Close the page.  
4.  Choose the **Item** action.  
5.  On the **Job Item Prices** page, enter the following information and customized price:  

    1.  **Item No.**: **80201 (Graphic Program)**  
    2.  **Unit Price**: **200**  

6.  Close the page.  
7.  Choose the **G/L Account** action.  
8.  On the **Job G/L Account Prices** page, enter the following information and the cost of travel, for which the customer has agreed to pay cost plus 25 percent:  

    1.  **G/L Account**: **8430 (Travel)**  
    2.  **Unit Cost Factor**: **1.25**  

9. Close the page.  

 The final steps in setting up a job are adding the job tasks and the planning lines that are part of each task. The planning lines determine what is invoiced to the customer.  

### To add job tasks  

1.  On the **Job** card for the new job, choose the **Job Task Lines** action.  
2.  The following table describes the information that you should enter in the fields.  

    |Job Task No.|Description|Job Task Type|  
    |------------------|---------------------------------------|-------------------|  
    |1000|Consulting on hall setup|Begin-Total|  
    |1010|Consultation meeting with customer|Posting|  
    |1020|Development|Posting|  
    |1090|Consulting Total|End-Total|  

3.  To show that some tasks are subcategories of other tasks, choose the **Indent Job Tasks** action.  

 A planning line can be one of the following types:  

-   **Schedule**: Added to the schedule, but not invoiced.  
-   **Contract**: Invoiced, but not added to the schedule.  
-   **Both Budget and Billable**: Invoiced and added to the schedule.  

 In this walkthrough, the project manager uses **Both Budget and Billable**. He creates three planning lines for task 1010, and two planning lines for task 1020.  

### To create planning lines  

1.  Select line 1010, and then choose the **Job Planning Lines** action. Enter the following information:  

     **Line 1**  

    -   **Line Type**: **Both Budget and Billable**  
    -   **Planning Date**: **(today’s date)**  
    -   **Type**: **Resource**  
    -   **No.**: **Tricia**  
    -   **Quantity**: **40**  

     **Line 2**  

    -   **Line Type**: **Both Budget and Billable**  
    -   **Planning Date**: **(today’s date)**  
    -   **Type**: **Resource**  
    -   **No.**: **Timothy**  
    -   **Quantity**: **40**  

     **Line 3**  

    -   **Line Type**: **Both Budget and Billable**  
    -   **Planning Date**: **(today’s date)**  
    -   **Type**: **G/L Account**  
    -   **No.**: **8430 (Travel)**  
    -   **Quantity**: **2**  
    -   **Unit Cost**: **400**  

2.  Close the page. The totals are updated on the **Job Task Lines** page.  
3.  Select line 1020, and then choose the **Job Planning Lines** action. Enter the following information:  

     **Line 1**  

    -   **Line Type**: **Both Budget and Billable**  
    -   **Planning Date**: **(today’s date)**  
    -   **Type**: **Resource**  
    -   **No.**: **Tricia**  
    -   **Quantity**: **80**  

     **Line 2**  

    -   **Line Type**: **Both Budget and Billable**  
    -   **Planning Date**: **(today’s date)**  
    -   **Type**: **Item**  
    -   **No.**: **80201 (Graphic program)**  
    -   **Quantity**: **1**  

4.  Close the page. Totals are updated on the **Job Task Lines** page.  

## Calculating Remaining Usage  
 Tricia, the team project member, has been working on the job for a while and wants to register her hours and usage on the job. She has not worked more hours than was agreed upon with the customer in advance. She uses the **Calculate Remaining Usage** batch job to calculate remaining usage for the job in a job journal. For each task, the batch job calculates the difference between scheduled usage of items, resources, and general ledger expenses and the actual usage posted in job ledger entries. The remaining usage is then displayed in the job journal from where she can post it.  

### To calculate remaining usage  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.  
2.  On the **Job Journal** page, in the **Batch Name** field, open the **Job Journals Batches** list. Select the **Tricia** job journal batch.  
3.  Choose the **Calc. Remaining Usage** action.  
4.  On the **Job Calc. Remaining Usage** page, on the **Job Task** FastTab, choose the **Job No.** field, and select the relevant job number, typically job J00010.  
5.  On the **Options** FastTab, type **J00001** in the **Document No.** field. This makes future tracking of the posting easier.  
6.  Enter today’s date as the posting date.  
7.  Choose the **OK** button. This will generate job journal lines derived from the planning lines that Prakash created for the job.  
8.  Choose the **OK** button on the confirmation page. The generated lines are added to the job journal.  
9. Make sure that all the document numbers are J00001, and then choose the **Post** action. Choose **Yes** to confirm the posting.  

The lines are now posted.  

## Creating and Posting a Job Sales Invoice  
 Next, Tricia can create a new invoice for the whole job or for part of a job. She can also attach the invoice to another invoice for the same customer for the same job. In this case, she invoices for the whole job, because the project is now completed.  

### To create a job sales invoice  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2.  Select the job that you created earlier, and then choose the **Create Job Sales Invoice** action.  
3.  On the **Job Task** FastTab, clear any filter on **Job Task No.** in order to invoice the job. In the **Job No.** field, select the relevant job.  
4.  On the **Options** FastTab, fill in the posting date and define whether you want to create one invoice per task or just a single invoice for all tasks.  
5.  Choose the **OK** button to create the invoice and choose the **OK** button on the confirmation page.  

 After Tricia creates the invoice, she can access it from the **Sales Order Processor** Role Center, for example. 

### To post a new sales invoice  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then choose the related link.  
2.  Open the invoice for Customer No. 01445544. You can see the information that was entered from the planning lines.  
3.  Choose the **Post** action. Choose **Yes** to confirm the posting.  

### To view the posted invoice  

1.  Open the job, and then choose the **Job Planning Lines** action.  
2.  Select any of the planning lines that have been invoiced, and then choose the **Sales Invoice/Credit Memo** action.
3. On the **Job Invoices** page, choose the **Open Sales Invoice/Credit Memo** action.  

 Tricia has a question about the prices, costs, and profits that are relevant to this particular job, so she accesses that information on the **Statistics** page.  

### To open the Statistics page  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2.  Choose the **Statistics** action. You can review detailed information about the job prices, costs, and profits in both local and foreign currencies.  
3.  Choose the **Close** button to close the **Job Statistics** page.  

## Handling Fixed Prices  
 CRONUS has been contracted to set up conference rooms. As the project manager, Prakash wants a good overview of the tasks required for the job with the associated budgeted and incurred costs for each task. In addition, he wants to know the total contracted price for the job and the amount that has been invoiced to this point. He has reached an agreement with the customer regarding fixed pricing for the job.  

### To manage fixed pricing in jobs  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2.  Select the **Guildford** job number, and then choose the **Jobs Task Lines** action.  
3.  Select line 1120, and in the **Schedule (Total Cost)** field, right-click the amount and choose **DrillDown**.  

     By reviewing the Job Planning lines, Prakash determines that he will also need Tricia for 30 hours for this stage of the project. He agrees on a fixed price with the customer.  

4.  On the **Job Task Lines** page, select line 1120, and then choose the **Job Planning Lines** action.  
5.  Choose the **New** to create a new line with the following information:  

    -   **Line Type**: **Both Budget and Billable**  
    -   **Type**: **Resource**  
    -   **No.**: **Tricia**  
    -   **Quantity**: **30**  

7.  Close the page.  
8.  In the **Schedule (Total Cost)** field, right-click the field, and choose **Drilldown** again on the **Job Task Lines** page. View the changes to the schedule. You see that 30 hours have been added to the schedule.  
9. Close the pages.  

After Tricia has been added to the schedule for this task line, she works 25 hours on the job. She enters these hours into the job journal.  

### To enter hours in the Job Journal  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.  
2.  On a new line, enter the following information:  

    -   **Line Type**: **(blank)**  
    -   **Posting Date**: **(today's date)**  
    -   **Document No.**: **J00002**  
    -   **Job No.**: **Guildford**  
    -   **Job Task No.**: **1120**  
    -   **Type**: **Resource**  
    -   **No.**: **Tricia**  
    -   **Quantity**: **25**  

3.  Choose the **Post** action.  

     A few days later, Tricia works for another 10 hours on the job. She has now worked 35 hours in all. Because the agreement is for 30 hours with the customer, only five of these hours will be charged to the customer. Tricia will manually add the additional five hours she worked to the schedule.  

4.  On the **Job Journal** page, choose the **Calc. Remaining Usage** action.  
5.  On the **Job Calc. Remaining Usage** page, on the **Options** FastTab, enter the following information:  

    -   **Document No.**: **J00003**  
    -   **Posting Date**: **(today's date)**  

6.  On the **Job Task** FastTab, enter the following information:  

    -   **Job No.**: **Guildford**  
    -   **Job Task No.**: **1120**  

7. Choose the **OK** button to run the calculation.

    There are five hours of work remaining for Tricia. The **Line Type** field is blank, which indicates that only the usage remains to be posted because the work has already been scheduled.  

8.  In the **Job Journal**, create a new line with the following information. Make sure that both job numbers are sequential with those that you have already used:  

    -   **Line Type**: **Schedule**  
    -   **Job No.**: **Guildford**  
    -   **Job Task No.**: **1120**  
    -   **Type**: **Resource**  
    -   **No.**: **Tricia**  
    -   **Quantity**: **5**  

     By using the **Schedule** line type, there are updates to the scheduled costs and prices, but no updates to the contract costs and prices that are invoiced to the customer.  

9.  Choose the **Post** action. Choose the **OK** button to close the page.  
10. Open the **Jobs** list.  
11. Select the GUILDFORD job, and then choose the **Job Task Lines** action.  
12. Select line 1120 and in the **Schedule (Total Cost)** field, right-click the amount. Choose **DrillDown** to view the information.  

     Changes are automatically entered on the line for Job Task No. 1120. In the total cost of scheduled work, five additional hours of work by Tricia has been added to the schedule.  

13. Choose the **Close** button to close the page.  
14. Right-click the amount in the **Contract (Total Cost)** field and choose **DrillDown** to view the information.  

In the total price for the contract, only the original contracted 30 hours are included, because this is what was agreed upon with the customer.  

## Copying Jobs  
 Prakash has reached an agreement with a customer, Selagorian Ltd, to set up 10 conference rooms. The agreement resembles an earlier job. Therefore, it will save time to copy that earlier job.  

 On the **Copy Job** page, you can select the job and task lines that you want to copy. You can also select to copy the source job ledger entries, which creates planning lines based on actual usage, or you can copy the source job planning lines, which copies the original planning lines to the new job. You can then choose what planning line or ledger entry line type that you want to include, selecting only what is relevant to this new job. Finally, you can select the job that you want to copy to and define whether prices and quantities should be copied as well.  

### To copy a job  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2.  Choose the **New** action to create a new job. Enter the following information:  

    -   **Description**: **Setting up 10 Conference Rooms**  
    -   **Bill-To Customer No.**: **20000**  

3.  Choose the **Copy Job Tasks from** action.  
4.  On the **Copy Job Tasks** page, enter the following:  

    -   **Job No.**: **Guildford**  
    -   **Job Task No. From**: **1000**  
    -   **Source**: **Job Planning Lines**  
    -   **Incl. Planning Line Type**: **Schedule + Contract**  
    -   **To Job No.**: **GuildfordSetting up 10 Conference Rooms**  
    -   Select the **Copy Dimensions** and **Copy Quantity** fields.  

5.  Choose the **OK** button to copy the job, and then choose the **OK** button to close the confirmation page.  

By comparing prices, job task lines, and job planning lines for the two jobs, you can see that the information was successfully copied.  

## Making Payments by Installments  
 CRONUS has just landed a large project that will take a year to be completed. Because it requires the dedication of many resources, the project manager sets up the contract so that the customer pays part of the price up front, part when the project is halfway completed, and the final payment upon completion.  

### To set up a new account  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2.  On the **Chart of Accounts** page, choose the **New** action to create a new card.  
3.  On the **New G/L Account** card, enter the following information:  

    -   **No.**: **6630**  
    -   **Name**: **Job Payment**  

4.  On the **Posting** FastTab, in the **Gen. Prod. Posting Group** field, select **MISC**. Close the page.  
5.  On the **Chart of Accounts** page, select **No. 6630 Job Payment**, and then choose the **Indent Chart of Accounts** action. Choose **Yes** to confirm.  

 The following procedures show how to create a new job, set pricing, and then set up payment by installment. In the job task lines, you can create specific lines dedicated to the payment by installments. All work completed on the job that is added to the schedule will be entered on the usage lines. For each payment task line on the planning lines, the line type is Contract, which means that the customer will be invoiced. Enter a new line for the down payment. On the usage task line, you can enter the information for the items and resources that have been used in this project, which will increase the schedule, such as employee hours and items used on the job.  

### To make a payment by installment  

1.  Create a new job.  
2.  On the new **Job** card, fill in the following information:  

    -   **Description**: **Redecoration of Reception Area**  
    -   **Bill-to-Customer No.**: **30000**  
    -   **Job Posting Group**: **Setting up**  
    -   **WIP Method**: **Cost Value**  

3.  On the job card, choose the **Resource** action. Enter the following information:  

    -   **Code**: **Tricia**  
    -   **Unit Price**: **10**  

     Close the page.  

4.  On the **Job** card, choose the **Job Task Lines** action.  

     The following table describes the lines that you will create.  

    |Line|Job Task No.|Description|Job Task Type|  
    |----------|------------------|---------------------------------------|-------------------|  
    |1|1000|Payment-Down Payment|Posting|  
    |2|2000|Usage|Posting|  
    |3|3000|Payment - Midway|Posting|  
    |4|4000|Payment - Completion|Posting|  

5.  On the **Job Task Lines** page, select task 1000, and then choose the **Job Planning Lines** action.  
6.  Create a planning line with the following information:  

    -   **Line Type**: **Contract**  
    -   **Planning Date**:  **(today's date)**  
    -   **Type**: **G/L Account**  
    -   **No.**: **6630**  
    -   **Quantity**: **1**  
    -   **Unit Price**: **5000**  

     Close the page.  

7.  On the **Job Task Lines** page, select **task 2000**, and open its **Job Planning Lines**.  

     The following table describes the planning lines that you will create.  

    |Line|Line Type|Planning Date|Type|No.|Quantity|  
    |----------|---------------|-------------------|----------|---------|--------------|  
    |1|Schedule|(today’s date)|Resource|Tricia|120|  
    |2|Schedule|(today’s date)|Item|70104|10|  

     Close the page. On the **Job Task Lines** page, you can see the schedule amounts have been updated.  

8.  On the **Job Task Lines** page, select **task 3000**.  
9. Create a planning line with the following information:  

    -   **Line Type**: **Contract**  
    -   **Planning Date**: **a future date**  
    -   **Type**: **G/L Account**  
    -   **No.**: **6630**  
    -   **Quantity**: **1**  
    -   **Unit Price**: **5000**  

     Close the page.  

10. Create a similar planning line entry for job task 4000.  

 Now that the task and planning lines have been entered, Prakash creates an invoice for the first payment. He does this from the job task lines to make sure that the invoice only contains the lines for the first payment. You can open the sales order from the planning lines or the task lines.  

### To create an invoice  

1.  On the **Job Task Lines** page, select line 1000, and then choose the **Create Sales Invoice** action.  
2.  On the **Create Sales Invoice** page, set today’s date as the posting date, specify **Per Task**, and choose the **OK** button to create an invoice with the default information. Choose the **OK** button to close the confirmation page.  
3.  Choose the **Sales Invoice/Credit Memo** action. On the sales invoice, you can see that only the down payment is included in the invoice. You can now send this to the customer as agreed.  

## Next Steps  
 This walkthrough has taken you through some of the basic steps of working with jobs in [!INCLUDE[d365fin](includes/d365fin_md.md)]. You have learned about how to create a new job, how to copy a job, and how to handle payments. Also, you have seen a demonstration of how to track hours and create invoices.  

## See Also  
 [Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)   
 [Setting Up Project Management](projects-setup-projects.md)   
 [Use Resources](projects-how-use-resources.md)   
 [Monitor Progress and Performance](projects-how-monitor-progress-performance.md)   
 [Invoice Jobs](projects-how-invoice-jobs.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
