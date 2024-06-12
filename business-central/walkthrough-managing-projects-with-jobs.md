---
title: Walkthrough - Managing Projects with Projects
description: This walkthrough introduces you to the project management features in projects which allow you to schedule the usage of your company's resources and more.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords:
ms.date: 06/24/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Walkthrough: Managing Projects

<!-- [!INCLUDE[complete_sample_data](includes/complete_sample_data.md)]   -->

This walkthrough introduces you to the project management features. Projects are a way for you to schedule the usage of your company's resources and to keep track of the various costs associated with the resources on a specific project. Projects involves the consumption of employee hours, machine hours, inventory items, and other types of usage that you may want to track as a project progresses.  

 This walkthrough covers the setup of a new project in addition to some common tasks such as handling fixed pricing, making payment by installments, posting invoices from projects, and copying projects.  

## About This Walkthrough

 This walkthrough demonstrates the following tasks:  

### Setting Up a Project

 With the budget structure set up for projects, creating a project is straightforward. This walkthrough covers the following procedures:  

- Setting up project task lines and planning lines.  
- Creating project-specific prices for items, resources, and general ledger accounts.  
- Invoicing from a project.  

### Handling Fixed Prices

 You can handle fixed prices and the prices for services or goods that are agreed upon in advance with customers. In this walkthrough, you can do the following:  

- See how contract and invoice values are determined.  
- Allow for extra work in the schedule that has not been invoiced.  

### Copying a Project

 This part of the walkthrough focuses on how to copy part or all of a project in order to reduce manual data entry and improve accuracy. It includes the following:  

- Copying part of a project to a new project.  
- Copying project-specific prices.  
- Copying planning lines.  

### Making Payment by Installment

 When a large, expensive project lasts for a long period, the customer often makes an agreement with the company to pay by installments. This scenario shows how you set up payment by installments and covers:  

- Creating payment by installments for a project.  
- Invoicing payments to customers.  
- Accounting for usage in a project set up for payment by installments.  

## Roles

 This walkthrough includes tasks for the following roles:  

- Project Manager  
- Project Team Member  

## Prerequisites

 Before you can perform the tasks in the walkthrough, you must do the following:  

- Install the CRONUS demonstration database.
- Create sample data by using the steps in the following section.  

## Story

This walkthrough focuses on CRONUS, a design and consultancy firm that designs and fits new infrastructures, such as conference halls and offices, with furniture, accessories, and storage units. Most of its work is project oriented. Prakash, a project manager at CRONUS uses project to get an overview of each ongoing task that CRONUS has started, as well as the tasks that are completed. Prakash is usually the one who sets up deals with customers and enters the core of the project, which is task and planning lines in addition to prices, into [!INCLUDE[prod_short](includes/prod_short.md)]. Prakash finds that creating, maintaining, and reviewing information is straightforward. Prakash also likes the way [!INCLUDE[prod_short](includes/prod_short.md)] enables copying projects and payment by installments.

 Tricia, a project team member who reports to Prakash, is responsible for monitoring the project day-to-day. Tricia enters her own work in addition to the work performed by technicians on every task, records the items that they have used, and the costs that they have incurred.  

## Preparing Sample Data

 To prepare for this walkthrough, you must add Tricia as a new resource.  

### To prepare the sample data  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resources**, and then choose the related link.  
2. Choose the **New** action to create a new resource card.  
3. On the **General** FastTab, enter the following information:  

    - **No.**: **Tricia**  
    - **Name**: **Tricia**  
    - **Type**: **Person**  

4. Choose the **Base Unit of Measure** field, and choose the **New** action to open the **Resource Unit of Measure** page. In the **Code** field, select **Hour**.  
5. On the **Invoicing** FastTab, enter the following information:  

    - **Direct Unit Cost**: **5**  
    - **Indirect Cost %**: **4**  
    - **Unit Cost**: **10**  
    - **Gen. Prod. Posting Group**: **Services**  
    - **VAT Prod. Posting Group**: **VAT 25**  

6. Close the page.

In the next procedure, you create a project journal batch for Tricia in order to post their usage.  

### To create a project journal batch  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Project Journals**, and then choose the related link.  
2. On the **Project Journal** page, choose the **Batch Name** field. The **Project Journal Batches** page opens.  
3. Choose the **New** action to create a new line with the following information:  

    - **Name**: **Tricia**  
    - **Description**: **Tricia**  
    - **No. Series**: **JJNL-GEN**  

4. Choose the **OK** button to save the changes.

## Setting Up a Project

 In this scenario, CRONUS has won a contract with a customer, Progressive Home Furnishings, to design a conference and dining hall. The customer is based in the United States and the project will require special software. The project manager reaches an agreement with the customer and creates a project that covers the agreement.  

### To set up a project  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Projects**, and then choose the related link.  
2. Choose the **New** action to create a new card.  
3. On the **General** FastTab, enter the following information:  

    - **Description**: **Advising on conference hall setup**  
    - **Bill-to-Customer No.**: **01445544**  

4. On the **Posting** FastTab, enter the following information:  

    - **Status**: **Planning**  
    - **Project Posting Group**: **Setting Up**  
    - **WIP Method**: **Cost Value**  

5. On the **Duration** FastTab, type today's date into the **Starting Date** and **Ending Date** fields. These dates will help apply currency conversions when the project is invoiced.  
6. On the **Foreign Trade** FastTab, set the currency code to **USD**. If you select USD in the **Invoice Currency Code** field, then the project will be invoiced in U.S. dollars and planned in the local currency of CRONUS only.  

 You can customize the pricing for customers on a per project basis, depending on the agreements you have set up. In the next procedure, the project manager specifies a cost for Tricia's time, sets the price for the required software, and adds in the travel costs that the customer has agreed to pay.  

### To customize pricing  

1. From the **Project Card**, choose the **Resource** action.  
2. On the **Project Resource Prices** page, enter the following information:  

    - **Code**: **Tricia**  
    - **Unit Price**: **20**  

3. Close the page.  
4. Choose the **Item** action.  
5. On the **Project Item Prices** page, enter the following information and customized price:  

    1. **Item No.**: **80201 (Graphic Program)**  
    2. **Unit Price**: **200**  

6. Close the page.  
7. Choose the **G/L Account** action.  
8. On the **Project G/L Account Prices** page, enter the following information and the cost of travel, for which the customer has agreed to pay cost plus 25 percent:  

    1. **G/L Account**: **8430 (Travel)**  
    2. **Unit Cost Factor**: **1.25**  

9. Close the page.  

 The final steps in setting up a project are adding the project tasks and the planning lines that are part of each task. The planning lines determine what is invoiced to the customer.  

### To add project tasks  

1.  On the **Project** card for the new project, choose the **Project Task Lines** action.  
2.  The following table describes the information that you should enter in the fields.  

    |Project Task No.|Description|Project Task Type|  
    |------------------|---------------------------------------|-------------------|  
    |1000|Consulting on hall setup|Begin-Total|  
    |1010|Consultation meeting with customer|Posting|  
    |1020|Development|Posting|  
    |1090|Consulting Total|End-Total|  

3.  To show that some tasks are subcategories of other tasks, choose the **Indent Project Tasks** action.  

 A planning line can be one of the following types:  

- **Budget**: Added to the schedule, but not invoiced.  
- **Billable**: Invoiced, but not added to the schedule.  
- **Both Budget and Billable**: Invoiced and added to the schedule.  

 In this walkthrough, the project manager uses **Both Budget and Billable**. They create three planning lines for task 1010, and two planning lines for task 1020.  

### To create planning lines  

1. Select line 1010, and then choose the **Project Planning Lines** action.  

2. Create planning lines with the following information:  

    | Line | Line Type | Planning Date  | Type        | No.   | Quantity | Unit Price |
    |------|-----------|----------------|-------------|-------|----------|------------|
    | 1    | Both Budget and Billable | (today's date) | Resource | Tricia | 40        |     |
    | 2    | Both Budget and Billable | (today's date) | Resource | Timothy | 40        |     |
    | 3    | Both Budget and Billable | (today's date) | G/L Account | 8430 (Travel) | 2 | 400    |

     Close the page. The totals are updated on the **Project Task Lines** page.  
3. Select line 1020, and then choose the **Project Planning Lines** action. Enter the following information:  

    | Line | Line Type | Planning Date  | Type        | No.   | Quantity | Unit Price |
    |------|-----------|----------------|-------------|-------|----------|------------|
    | 1    | Both Budget and Billable | (today's date) | Resource | Tricia | 80        |     |
    | 2    | Both Budget and Billable | (today's date) | Item | 80201 (Graphic program) | 1 |     |

4. Close the page. Totals are updated on the **Project Task Lines** page.  

## Calculating Remaining Usage

 Tricia, the team project member, has been working on the project for a while and wants to register their hours and usage. Tricia hasn't worked more hours than was agreed upon with the customer in advance. Tricia uses the **Calculate Remaining Usage** batch job to calculate remaining usage in a project journal. For each task, the batch job calculates the difference between scheduled usage of items, resources, and general ledger expenses and the actual usage posted in project ledger entries. The remaining usage is then displayed in the project journal from where she can post it.  

### To calculate remaining usage  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Project Journals**, and then choose the related link.  
2. On the **Project Journal** page, in the **Batch Name** field, open the **Project Journals Batches** list. Select the **Tricia** project journal batch.  
3. Choose the **Calc. Remaining Usage** action.  
4. On the **Project Calc. Remaining Usage** page, on the **Project Task** FastTab, choose the **Project No.** field, and select the relevant job number, typically job J00010.  
5. On the **Options** FastTab, type **J00001** in the **Document No.** field. This makes future tracking of the posting easier.  
6. Enter today's date as the posting date.  
7. Choose the **OK** button. This will generate project journal lines based on the planning lines that Prakash created.  
8. Choose the **OK** button on the confirmation page. The generated lines are added to the project journal.  
9. Make sure that all the document numbers are J00001, and then choose the **Post** action. Choose **Yes** to confirm the posting.  

The lines are now posted.  

## Creating and Posting a Project Sales Invoice

 Next, Tricia can create a new invoice for the whole project or for part of a project. Tricia can also attach the invoice to another invoice for the same customer for the same project. In this case, Tricia invoices for the whole project because the project is now completed.  

### To create a Project Sales Invoice  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Projects**, and then choose the related link.  
2.  Select the project that you created earlier, and then choose the **Create project Sales Invoice** action.  
3.  On the **Project Task** FastTab, clear any filter on **Project Task No.** in order to invoice the job. In the **Project No.** field, select the relevant job.  
4.  On the **Options** FastTab, fill in the posting date and define whether you want to create one invoice per task or just a single invoice for all tasks.  
5.  Choose the **OK** button to create the invoice and choose the **OK** button on the confirmation page.  

 After creating the invoice, Tricia can access it from the **Sales Order Processor** Role Center, for example. 

### To post a new sales invoice  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then choose the related link.  
2.  Open the invoice for Customer No. 01445544. You can see the information that was entered from the planning lines.  
3.  Choose the **Post** action. Choose **Yes** to confirm the posting.  

### To view the posted invoice  

1.  Open the project, and then choose the **Project Planning Lines** action.  
2.  Select any of the planning lines that have been invoiced, and then choose the **Sales Invoice/Credit Memo** action.
3. On the **Project Invoices** page, choose the **Open Sales Invoice/Credit Memo** action.  

 Tricia has a question about the prices, costs, and profits that are relevant to this particular project, so Tricia accesses that information on the **Statistics** page.  

### To open the Statistics page  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Projects**, and then choose the related link.  
2.  Choose the **Statistics** action. You can review detailed information about the project prices, costs, and profits in both local and foreign currencies.  
3.  Choose the **Close** button to close the **Project Statistics** page.  

## Handling Fixed Prices

 CRONUS has been contracted to set up conference rooms. As the project manager, Prakash wants a good overview of the tasks required for the project with the associated budgeted and incurred costs for each task. In addition, Prakash wants to know the total contracted price for the project and the amount that has been invoiced to this point. They have reached an agreement with the customer regarding fixed pricing for the project.  

### To manage fixed pricing in projects  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Projects**, and then choose the related link.  
2. Select the **Guildford** project number, and then choose the **Project Task Lines** action.  
3. Select line 1120, and in the **Budget (Total Cost)** field, right-click the amount and choose **DrillDown**.  

     By reviewing the Project Planning Lines, it is determined that Prakash will also need Tricia for 30 hours for this stage of the project. Prakash agrees on a fixed price with the customer.  

4. On the **Project Task Lines** page, select line 1120, and then choose the **Project Planning Lines** action. Create a planning line with the following information:  

    | Line | Line Type | Type        | No.   | Quantity |
    |------|-----------|-------------|-------|----------|
    | 1    | Both Budget and Billable  | Resource | Tricia | 30 |

     Close the page.  
5. In the **Budget (Total Cost)** field, right-click the field, and choose **Drilldown** again on the **Project Task Lines** page. View the changes to the schedule. You see that 30 hours have been added to the schedule.  
6. Close the pages.  

After being added to the schedule for this task line, Tricia works 25 hours on the project, and enters these hours into the project journal.  

### To enter hours in a project journal  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Project Journals**, and then choose the related link.  
2. On a new line, enter the following information:  

    - **Line Type**: **(blank)**  
    - **Posting Date**: **(today's date)**  
    - **Document No.**: **J00002**  
    - **Project No.**: **Guildford**  
    - **Project Task No.**: **1120**  
    - **Type**: **Resource**  
    - **No.**: **Tricia**  
    - **Quantity**: **25**  

3. Choose the **Post** action.  

     A few days later, Tricia works for another 10 hours on the job, and has now worked 35 hours in all. Because the agreement is for 30 hours with the customer, only five of these hours will be charged to the customer. Tricia will manually add the additional five hours worked to the schedule.  

4. On the **Project Journal** page, choose the **Calc. Remaining Usage** action.  
5. On the **Project Calc. Remaining Usage** page, on the **Options** FastTab, enter the following information:  

    - **Document No.**: **J00003**  
    - **Posting Date**: **(today's date)**  

6. On the **Project Task** FastTab, enter the following information:  

    - **Project No.**: **Guildford**  
    - **Project Task No.**: **1120**  

7. Choose the **OK** button to run the calculation.

    There are five hours of work remaining for Tricia. The **Line Type** field is blank, which indicates that only the usage remains to be posted because the work has already been scheduled.  

8. In the **Project Journal**, create a new line with the following information. Make sure that both project numbers are sequential with those that you have already used:  

    - **Line Type**: **Budget**  
    - **Project No.**: **Guildford**  
    - **Project Task No.**: **1120**  
    - **Type**: **Resource**  
    - **No.**: **Tricia**  
    - **Quantity**: **5**  

     By using the **Budget** line type, there are updates to the scheduled costs and prices, but no updates to the contract costs and prices that are invoiced to the customer.  

9. Choose the **Post** action. Choose the **OK** button to close the page.  
10. Open the **Projects** list.  
11. Select the GUILDFORD job, and then, in the **Project Task Lines** section, select line 1120 and in the **Budget (Total Cost)** field, right-click the amount. Choose **DrillDown** to view the information.  

     Changes are automatically entered on the line for Project Task No. 1120. In the total cost of scheduled work, five additional hours of work by Tricia has been added to the schedule.  

12. Choose the **Close** button to close the page.  
13. Right-click the amount in the **Contract (Total Cost)** field and choose **DrillDown** to view the information.  

In the total price for the contract, only the original contracted 30 hours are included, because this is what was agreed upon with the customer.  

## Copying projects

Prakash has reached an agreement with a customer, Selagorian Ltd, to set up 10 conference rooms. The agreement resembles an earlier project. Therefore, it will save time to copy that earlier project.  

On the **Copy Project** page, you can select the project and task lines that you want to copy. You can also select to copy the source project ledger entries, which creates planning lines based on actual usage, or you can copy the source project planning lines, which copies the original planning lines to the new project. You can then choose what planning line or ledger entry line type that you want to include, selecting only what is relevant to this new project. Finally, you can select the project that you want to copy to and define whether prices and quantities should be copied as well.  

### To copy a project  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Projects**, and then choose the related link.  
2. Choose the **New** action to create a new project. Enter the following information:  

    - **Description**: **Setting up 10 Conference Rooms**  
    - **Bill-To Customer No.**: **20000**  

3. Choose the **Copy Project Tasks from** action.  
4. On the **Copy Project Tasks** page, enter the following:  

    - **Project No.**: **Guildford**  
    - **Project Task No. From**: **1000**  
    - **Source**: **Project Planning Lines**  
    - **Incl. Planning Line Type**: **Budget + Billable**  
    - **To Project No.**: **GuildfordSetting up 10 Conference Rooms**  
    - Select the **Copy Dimensions** and **Copy Quantity** fields.  

5. Choose the **OK** button to copy the project, and then choose the **OK** button to close the confirmation page.  

By comparing prices, project task lines, and project planning lines for the two projects, you can see that the information was successfully copied.  

## Making Payments by Installments

CRONUS has just landed a large project that will take a year to be completed. Because it requires the dedication of many resources, the project manager sets up the contract so that the customer pays part of the price up front, part when the project is halfway completed, and the final payment upon completion.  

### To set up a new account  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2. On the **Chart of Accounts** page, choose the **New** action to create a new card.  
3. On the **New G/L Account** card, enter the following information:  

    - **No.**: **40255**  
    - **Name**: **Project Payment**  

4. On the **Posting** FastTab, in the **Gen. Prod. Posting Group** field, select **Services**. Close the page.  
5. On the **Chart of Accounts** page, select **No. 40255 Job Payment**, and then choose the **Indent Chart of Accounts** action. Choose **Yes** to confirm.  

The following procedures show how to create a new project, set pricing, and then set up payment by installment. In the project task lines, you can create specific lines dedicated to the payment by installments. All work completed on the project that is added to the schedule will be entered on the usage lines. For each payment task line on the planning lines, the line type is **Billable**, which means that the customer will be invoiced. Enter a new line for the down payment. On the usage task line, you can enter the information for the items and resources that have been used in this project, which will increase the schedule, such as employee hours and items used on the project.  

### To make a payment by installment  

1. Create a new project.  
2. On the new **Project** card, fill in the following information:  

    - **Description**: **Redecoration of Reception Area**  
    - **Bill-to-Customer No.**: **30000**  
    - **Project Posting Group**: **Setting up**  
    - **WIP Method**: **Cost Value**  

3. On the Project Card, choose the **Prices** action, and then choose the **Resource** action. Enter the following information:  

    - **Code**: **Tricia**  
    - **Unit Price**: **10**  

     Close the page.  

4. On the **Project** card, in the **Tasks** section, add project task lines as described in the following table:  

    | Line | Project Task No. | Description          | Project Task Type |
    |------|--------------|----------------------|---------------|
    | 1    | 1000         | Payment-Down Payment | Posting       |
    | 2    | 2000         | Usage                | Posting       |
    | 3    | 3000         | Payment - Midway     | Posting       |
    | 4    | 4000         | Payment - Completion | Posting       |

5. Choose task 1000, and then choose the **Project Planning Lines** action.  

6. Create a planning line with the following information:  

    | Line | Line Type | Planning Date  | Type        | No.   | Quantity | Unit Price |
    |------|-----------|----------------|-------------|-------|----------|------------|
    | 1    | Billable  | (today's date) | G/L Account | 40255 | 1        | 5000       |

     Close the page.  

7. Choose task 2000, and then choose the **Project Planning Lines** action.  

8. Create a planning line with the following information:

    | Line | Line Type | Planning Date  | Type     | No.    | Quantity |
    |------|-----------|----------------|----------|--------|----------|
    | 1    | Budget    | (today's date) | Resource | Tricia | 120      |
    | 2    | Budget    | (today's date) | Item     | 70104  | 10       |

     Close the page. On the **Project Task Lines** page, you can see the schedule amounts have been updated.  

9. Choose task 32000, and then choose the **Project Planning Lines** action.  

10. Create a planning line with the following information:

    | Line | Line Type | Planning Date   | Type        | No.   | Quantity | Unit Price |
    |------|-----------|-----------------|-------------|-------|----------|------------|
    | 1    | Billable  | (a future date) | G/L Account | 40255 | 1        | 5000       |

     Close the page.  

11. Create a similar planning line entry for project task 4000.  

 Now that the task and planning lines have been entered, Prakash creates an invoice for the first payment. Prakash does this from the project task lines to make sure that the invoice only contains the lines for the first payment. You can open the sales order from the planning lines or the task lines.  

### To create an invoice  

1.  On the **Project Task Lines** page, select line 1000, and then choose the **Create Sales Invoice** action.  
2.  On the **Create Sales Invoice** page, set today's date as the posting date, specify **Per Task**, and choose the **OK** button to create an invoice with the default information. Choose the **OK** button to close the confirmation page.  
3.  Choose the **Sales Invoice/Credit Memo** action. On the sales invoice, you can see that only the down payment is included in the invoice. You can now send this to the customer as agreed.  

## Next Steps

 This walkthrough has taken you through some of the basic steps of working with projects in [!INCLUDE[prod_short](includes/prod_short.md)]. You have learned about how to create a new project, how to copy a project, and how to handle payments. Also, you have seen a demonstration of how to track hours and create invoices.  

## See also

 [Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)  
 [Setting Up Project Management](projects-setup-projects.md)  
 [Use Resources](projects-how-use-resources.md)  
 [Monitor Progress and Performance](projects-how-monitor-progress-performance.md)  
 [Invoice Projects](projects-how-invoice-jobs.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
