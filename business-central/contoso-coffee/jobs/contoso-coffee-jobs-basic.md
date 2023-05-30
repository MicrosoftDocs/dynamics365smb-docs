# Walkthrough of Basic Jobs

This walkthrough demonstrates several core processes:
  - Adding job tasks to jobs
  - Recording time and material expenses to a job
  - Invoicing a job

## Adding a Job Task to a Job

### Scenario  
Simon, the project manager, wants to be record time spend educating the customer in espresso machine product use to a separate task in the job for installing a commercial machine on-site.

### Steps
1. Create the Job Task  

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
    2. Select the Job *J00010*.
	3. In the **Tasks** area, choose the **New Line** action.  Enter the following values:
 
    |Job Task No.|Description|Job Task Type|
    |------------|-----------|-------------|  
    |220|Customer Training|Posting|

2. Indent the Job Tasks
   1. In the Tasks area, locate the **Indent Job Tasks** action
   2. Confirm you wish to indent tasks by selecting **Yes**.

### Results
 - Now time and expenses can be recorded to the new job task

## Record Time and Material Expenses to a Job

### Scenario  
Edgin, the technician installing the machine, needs to record his time and the materials used during installation to the job for billing.  He has already added the travel and materials, and now needs to add the time for teaching staff how to use the machine.

### Steps
1. Create the additional Job Journal Lines

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.  
    2. Select the batch *CONTOSO*.  You will see several lines of Resource and Item types, reflecting the time (for the technician and the vehicle) and materials (the machine and supplies) used.
	3. Create a new line. Enter the following values:
 
    |Job No.|Job Task No.|Type|No.|Description|Quantity|
    |-------|------------|----|---|-----------|--------|  
    |J00010|220|Resource|EDGIN|Customer training|1|

2. Post the time and expense
   1. Choose the **Post** action
   2. Confirm you wish to post the lines by selecting **Yes**.

### Results
 - Job Ledger Entries and Resource Ledger Entries of type *Usage* will be created
 - Item Ledger Entries will be created to negatively adjust the inventory
 - On the Job Card, the Costs and Prices in the Tasks area will reflect the new balances waiting to be invoiced
 - On the Job Card, the Job Details FactBox will reflect the totals of the prices


## Creating a Sales Invoice for a Job

### Scenario  
Simon needs to create and post an invoice to be sent to the customer with the time and expenses from the job.

### Steps
1. Create the Sales Invoice

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
    2. In the list of Jobs, choose the **Create Job Sales Invoice** action.
    3. Set the **Job No.** filter to *J00010*.
    4. Choose **OK** to generate the Sales Invoice.  You will receive a confirmation of how many invoices are generated

2. Post the time and expense invoice
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then choose the related link.  
   2. Select the last invoice to open it for review.
   3. Choose the **Post** action.

### Results
 - Job Ledger Entries and Resource Ledger Entries of type *Sales* will be created
 - On the Job Card, the Costs and Prices in the Tasks area will reflect the new Invoiced balances
 - On the Job Card, the Job Details FactBox will reflect the totals of the prices in the Invoiced Price section


