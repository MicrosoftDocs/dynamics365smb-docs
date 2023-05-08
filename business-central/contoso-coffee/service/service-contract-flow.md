# Walkthrough of Service Contracts for Service Items

This walkthrough demonstrates several core processes:
 - Creation of Service Items through Sales
 - Creating and Invoicing for a Service Contract
 - Creating a Service Order for a Service Contract
 - Assign a Resource based on Skill and Zone
 - Complete the time entry for the Service Order
 - Post and Invoice the Contract Service Order

## Creation of Service Items and and Invoicing a Service Contract

### Scenario  
Susan, the order processor, posts a sales order selling an Item configured to generate a Service Item.  Charles, the service manager, then creates a Service Contract for to invoice for regular maintenance visits.

### Steps
1. Post the **Sales Order** to create the Service Item for the Customer.  

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
    2. Select the order for customer 10000. The External Orders No. is *SVC-1*. Use the personalization tools if the **External Order No.** field isn't visible. For more information, see [Personalize Your Workspace](../../ui-personalization-user.md).
	3. Choose the **Post** action to ship the item to the customer.

2. Create the **Service Contract** for the new Service Item
    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contracts**, and then choose the related link.
    2. Choose the **New** action.  
    3. Select Customer **10000** in the Sell-To Customer No. field.
    4. On the Invoice FastTab, in the Serv. Contract Acc. Gr. Code field, enter **BASIC**.
    5. On the Service FastTab, in the Service Zone Code field, enter **LOCAL**; in the Service Period, enter **1M**; in the Service Order Type, enter **MAINT**.
    6. In the Lines, enter the following information:

    |Service Item No.|Line Value|  
    |----------------|----------|  
    |SV000001|6000|

    7. Choose the **Sign Contract** action and confirm the signing.
    8. Choose **Yes** to confirm creation of a Service Invoice. You'll receive a confirmation message with the Service Invoice number.

3. Post the Service Invoice
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Invoices**, and then choose the related link.
   2. Locate the Service Invoice and choose the **Post** action.

### Results
 - A Service Item will be created for Customer 10000
 - A Signed Service Contract will be created, with Ledger Entries
 - A Posted Service Invoice will be created

## Creating a Service Order for a Service Contract and Assign Resources

### Scenario  
Charles, the service manager, will create the Service Orders for regular maintenance orders under Service Contract, then review the Dispatch Board to assign them.

### Steps
1. Run the Service Orders that will fulfill the obligations of active Service Contracts.
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Create Contract Service Orders**, and then choose the related link.
   2. Enter the beginning and ending dates of the month in the Starting Date and Ending Date fields in the Options FastTab
   3. Choose **OK** to confirm creation of Service Orders. You'll receive a confirmation message with number of created Service Invoices.

2. Review the Orders awaiting assignment via the Dispatch Board
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Dispatch Board**, and then choose the related link.
   2. The Dispatch Board will show all open Service Orders, along with the **No. of Allocations** to show if the Service Orders have been assigned to a Resource.
   3. Choosing the **Show Documents** action to open a Service Order.  You will see that the Service Item Lines FactBox will show which Resources are skilled at working with this item.

3. Assign a Resource to the Service Order
   1. From the Service Order, choose the Line action **Resource Allocations**
   2. Enter the following information for the Resource Allocation

    |Service Item No.|Resource No.|Allocation Date|Allocated Hours|
    |----------------|------------|---------------|---------------|  
    |SV000001|LOCAL1|t|1|

    3. The Allocation will be changed to a Status to Active.
    4. Refreshing the Dispatch Board will show the **No of Allocations** changed from 0 to 1 for the Service Order.

### Results
 - Service Orders will be created for the Service Contracts
 - The Service Orders will be allocated to a resource to complete the work

## Complete the time entry for the Service Order and Post the Service Invoice

### Scenario  
The service technician, LOCAL1, will register their time directly against the Service Order, then Post the Order.

> [!NOTE]
> Time Entry for Service Orders can be entered via Time Sheets. For more information, see [link to Timesheet if this note makes sense].

### Steps
1. Locate the Service Order and enter the time into the Service Item Worksheet
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**, and then choose the related link.
   2. Locate the Service Order to enter time for.
   3. Choose the Line action **Service Item Worksheet**.
   4. Enter the following information

    |Type|No.|Quantity|
    |----|---|--------|  
    |Resource|LOCAL1|2|

2. On the Service Order, Post the Invoice
   1. Choose the **Post** action to complete the Service Order, select the **Receive** action, and then choose the **OK** button.

### Results
 - A Posted Service Invoice will be created
 - Service Ledger Entries will be created associated with the Service Item, Service Contract, and Resource


