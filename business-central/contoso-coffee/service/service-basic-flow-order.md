# Walkthrough of Service Orders for Service Items

This walkthrough demonstrates several core processes:
  - Selling an Item to a Customer, which creates a Service Item
  - Create a Breakfix Service Order for the Service Item
  - Assign a Resource
  - Install a Loaner Item for this breakfix
  - Complete the time entry for the Service Order
  - Post and Invoice the Service Order



## Creation of Service Items and and Invoicing a Service Order

### Scenario  
Susan, the order processor, posts a sales order selling an Item configured to generate a Service Item.  Charles, the service manager, then creates a Service Order for a resource to fix a broken item.

### Steps
1. Post the **Sales Order** to create the Service Item for the Customer.  

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
    2. Select the order for customer 10000. The External Orders No. is *SVC-2*. Use the personalization tools if the **External Order No.** field isn't visible. For more information, see [Personalize Your Workspace](../../ui-personalization-user.md).
	3. Choose the **Post** action to ship the item to the customer.

### Results
 - A Service Item will be created for Customer 10000

## Creating a Service Order and Assign Resources

### Scenario  
Charles, the service manager, will create a Service Order for a Break/Fix scenario and assign the Resource Directly.

### Steps
1. Create the Service Order manually for the Service Item
   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Orders**
   2. Choose the **New** action.
   3. Enter **10000** into the Customer No. field
   4. Select **BREAKFIX** for the Service Order Type field.
   5. In the Lines, select **SV000001** as the Service Item No.
   6. Choose the Line action **Resource Allocations**
   7. Enter the following information for the Resource Allocation

    |Service Item No.|Resource No.|Allocation Date|Allocated Hours|
    |----------------|------------|---------------|---------------|  
    |SV000001|LOCAL2|t|4|

    3. The Allocation will be changed to a Status to Active.

### Results
 - A Service Order will be created for the Service Item
 - The Service Order will be allocated to a resource to complete the work

## Recording Lending Out and Receipt of a Loaner

### Scenario  
The technician needs to give the Customer a Loaner, and then will return the unit afterwards, recieving the Loaner back.

### Steps
1. Lend the Loaner to the Customer
   1. Open the Service Order
   2. In the Lines, select **LOANER1** as the Loaner No.
   3. Confirm the issuance of the Loaner by selecting **Yes** to lend the Loaner out. 

2. Receive the Loaner back from the Customer
   1. Open the Service Order
   2. In the Lines, select the **Receive Loaner** action.
   3. Confirm the return of the Loaner by selecting **Yes** to return the Loaner.

### Results
 - The Service Order's Service Document Log will show the Loaner activities
 - The Loaner will have a Ledger Entry to reflect the lending.

## Complete the time entry for the Service Order and Post the Service Invoice

### Scenario  
The service technician, LOCAL2, will register their time directly against the Service Order, then Post the Order.

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
    |Resource|LOCAL2|2|

2. On the Service Order, Post the Invoice
   1. Choose the **Post** action to complete the Service Order, select the **Receive** action, and then choose the **OK** button.

### Results
 - A Posted Service Invoice will be created
 - Service Ledger Entries will be created associated with the Service Item, Service Contract, and Resource


