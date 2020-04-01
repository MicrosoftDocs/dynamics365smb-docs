---
    title: How to Calculate Order Promising Dates | Microsoft Docs
    description: The order promising function is a tool for calculating the earliest possible date that an item is available for shipment or delivery. It also creates requisition lines for those dates that you accept.
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
# Calculate Order Promising Dates
A company must be able to inform their customers of order delivery dates. The **Order Promising Lines** page enables you to do this from a sales order line.  

Based on an item’s known and expected availability dates, [!INCLUDE[d365fin](includes/d365fin_md.md)] instantly calculates shipment and delivery dates, which can then be promised to the customer.  

If you specify a requested delivery date on a sales order line, then that date is used as the starting point for the following calculations:  

- requested delivery date - shipping time = planned shipment date  
- planned shipment date - outbound whse. handling time = shipment date  

If the items are available to pick on the shipment date, then the sales process can continue. If the items are not available to be picked on the shipment date, then a stock-out warning is displayed.  

If you do not specify a requested delivery date on a sales order line, or if the requested delivery date cannot be met, then the earliest date on which that the items are available is calculated. That date is then entered in the **Shipment Date** field on the line, and the date on which you plan to ship the items as well as the date on which they will be delivered to the customer are calculated using the following calculations:  

- shipment date + outbound whse. handling time = planned shipment date  
- planned shipment date + shipping time = planned delivery date  

## About Order Promising
The Order Promising functionality enables you to promise an order to be shipped or delivered on a specific date. The date that an item is available to promise or capable to promise is calculated, and order lines are created for those dates that you accept. The functionality calculates the earliest possible date that an item is available for shipment or delivery. It also creates requisition lines, in case the items must first be purchases, for those dates that you accept.

[!INCLUDE[d365fin](includes/d365fin_md.md)] uses two fundamental concepts:  

- Available to Promise (ATP)  
- Capable to Promise (CTP)  

### Available to Promise  
Available to promise (ATP) calculates dates based on the reservation system. It performs an availability check of the unreserved quantities in inventory with regard to planned production, purchases, transfers, and sales returns. Based on this information, [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically calculates the delivery date of the customer’s order because the items are available, either in inventory or on planned receipts.  

### Capable to Promise  
Capable to promise (CTP) assumes a “what if” scenario, which only applies to item quantities that are not in inventory or on scheduled orders. Based on this scenario, [!INCLUDE[d365fin](includes/d365fin_md.md)] calculates the earliest date that the item can be available if it is to be produced, purchased, or transferred.

#### Example
If there is an order for 10 pieces, and 6 pieces are available in inventory or on scheduled orders, then the Capable-to-Promise calculation will be based on 4 pieces.

### Calculations  
When [!INCLUDE[d365fin](includes/d365fin_md.md)] calculates the customer’s delivery date, it performs two tasks:  

- Calculates the earliest delivery date when the customer has not requested a specific delivery date.  
- Verifies if the delivery date requested by the customer or promised to the customer is realistic.  

If the customer does not request a specific delivery date, the shipment date is set to equal the work date, and availability is then based on that date. If the item is in inventory, [!INCLUDE[d365fin](includes/d365fin_md.md)] calculates forward in time to determine when the order can be delivered. This is accomplished by the following formulas:  

- Shipment Date + Outbound Warehouse Handling Time = Planned Shipment Date  
- Planned Shipment Date + Shipping Time = Planned Delivery Date  

[!INCLUDE[d365fin](includes/d365fin_md.md)] then verifies if the calculated delivery date is realistic by calculating backward in time to determine when the item must be available to meet the promised date. This is accomplished by the following formulas:  

- Planned Delivery Date - Shipping Time = Planned Shipment Date  
- Planned Shipment Date - Outbound Warehouse Handling = Shipment Date  

The shipment date is used to make the availability check. If the item is available on this date, [!INCLUDE[d365fin](includes/d365fin_md.md)] confirms that therequested/promised delivery can be met by setting the planned delivery date to equal the requested/promised delivery date. If the item is unavailable, it returns a blank date and the order processor can then use the CTP functionality.  

Based on new dates and times, all related dates are calculated according to the formulas listed earlier in this section. The CTP calculation takes longer but it gives an accurate date when the customer can expect to have the item delivered. The dates that are calculated from CTP are presented in the **Planned Delivery Date** and **Earliest Shipment Date** fields on the **Order Promising Lines** page.  

The order processor finishes the CTP process by accepting the dates. This means that a planning line and a reservation entry are created for the item before the calculated dates to ensure that the order is fulfilled.  

In addition to the external order promising that you can perform on the **Order Promising Lines** page, you can also promise internal or external delivery dates for bill-of-material items. For more information, see [View the Availability of Items](inventory-how-availability-overview.md).

## To set up order promising  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Order Promising Setup**, and then choose the related link.  
2. Enter a number and time unit code in the **Offset(Time)** field. Select one of the following codes.  

    |Code|Description|  
    |----------|-----------------|  
    |**d**|Calendar day|  
    |**w**|Week|  
    |**m**|Month|  
    |**q**|Quarter|  
    |**y**|Year|  

    For example, "3w" indicates that the offset time is three weeks. To indicate the current period, prefix to any of these codes with the letter “c”. For example, if you want the offset time to be the current month, enter **cm**.  
3. Enter a number series in the **Order Promising Nos.** field by selecting a line from the list on the **No. Series** page.  
4. Enter an order promising template in the **Order Promising Template** field by selecting a line from the list on the **Req. Worksheet Template List** page.  
5. Enter a requisition worksheet in the **Order Promising Worksheet** field by selecting a line from the list on the **Req. Wksh. Names** page.

### To enter inbound warehouse handling time in the inventory setup page  
If you want to include warehouse handling time in the order promising calculation on the purchase line, you can set it up as a default for the inventory and for your location.    
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.  
2. On the **General** FastTab, in the **Inbound Whse. Handling Time** field, enter the number of days that you want to include in the order promising calculation.  

> [!NOTE]  
>  If you have filled in the **Inbound Whse. Handling Time** field on the **Location Card** for your location this field is used as the default inbound warehouse handling time.  

### To enter inbound warehouse handling time on location cards  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Location**, and then choose the related link.  
2.  Open the relevant location card.  
3.  On the **Warehouse** FastTab, in the **Inbound Whse. Handling Time** field, enter the number of days that you want to be included in the order promising calculation.  

> [!NOTE]  
>  If you leave the **Inbound Whse. Handling Time** field blank, then the calculation uses the value in the **Inventory Setup**  page.

### To enter outbound warehouse handling time in the inventory setup page  
If you want to set up an outbound warehouse handling time to be included in the order promising calculation on the sales line, you can set this up as a default for the inventory.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.  
2. On the **General** FastTab, in the **Outbound Whse. Handling Time** field, enter the number of days you want to include in the order promising calculation.  

> [!NOTE]  
>  If you have filled in the **Outbound Whse. Handling Time** field on the Location card for your location, this field is used as the default outbound warehouse handling time.  

### To enter outbound warehouse handling time on location cards  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
2.  Open the relevant location card.  
3.  On the **Warehouse** FastTab, in the **Outbound Whse. Handling Time** field, enter the number of days that you want to include in the order promising calculation.  

> [!NOTE]  
>  If you leave the **Outbound Whse. Handling Time** field blank, then the calculation uses the value in the **Inventory Setup**  page.

## To make an item critical  
Before an item can be included in the order promising calculation, it must be marked as critical. This setup ensures that non-critical items do not cause irrelevant order promising calculations.   
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2.  Open the relevant item card.  
3.  On the **Planning** FastTab, select the **Critical** field.  

## To calculate an order promising date  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Order**, and then choose the related link.  
2.  Open the relevant sales order and select the sales order lines that you want application to calculate.  
3.  Choose the **Order Promising** action, and then choose the **Order Promising Lines** action.  
4.  Select a line, and then select one of the following options:  

    - Select **Available-to-Promise** if you want to calculate the earliest date that the item will be available with respect to inventory, scheduled receipts, and gross requirements.  
    - Select **Capable-to-Promise** if you know that the item is presently out of stock and you want to calculate the earliest date that the item can be available by issuing new replenishment requisitions.  
5.  Choose the **Accept** button to accept the earliest shipment date available.  

## See Also  
[Sales](sales-manage-sales.md)  
[Date Calculation for Purchases](purchasing-date-calculation-for-purchases.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
