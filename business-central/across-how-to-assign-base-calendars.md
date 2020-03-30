---
    title: How to Set Up Base Calendars | Microsoft Docs
    description: You can assign a base calendar to your company and its business partners, such as customers, vendors, or locations. Delivery and receipt dates on future sales order, purchase order, transfer order, and production order lines are calculated according to the calendar’s specified working days.
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
# Set Up Base Calendars
You can assign a base calendar to your company and its business partners, such as customers, vendors, or locations. Delivery and receipt dates on future sales order, purchase order, transfer order, and production order lines are calculated according to the calendar’s specified working days. The main task in setting up a new base calendar is to specify and define the non-working days that you want to apply.  

## To set up a base calendar  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Base Calendar**, and then choose the related link.  
2.  Choose the **New** action.  
3.  Fill in the **Code** field.  
4. Choose the **Maintain Base Calendar Changes** action.
5. On the **Base Calendar Changes** page, use the **Recurring System** field to mark a particular date or day as a recurring nonworking day. You can select either the **Annual Recurring** or **Weekly Recurring** option.  

    If you select **Annual Recurring**, you must also enter the relevant date in the **Date** field.  

    If you select **Weekly Recurring**, you must also select the relevant day of the week in the **Day** field. If you leave the field empty, you must fill in the **Date** field. The **Day** field is filled in automatically.  

When you make an entry, the **Nonworking** field is selected. You can choose to clear the check mark to make it a working day.  
 When you return to the base calendar card, you will observe that the nonworking day entries that you made have been updated. These entries now appear in red and the **Nonworking** field is selected.  

> [!NOTE]  
>  When setting up a new base calendar, you can select and copy lines from an existing calendar. You do this in the relevant **Base Calendar Changes** page.  

> [!IMPORTANT]  
>  Any base calendar defined for the vendor or the location affects how the dates are calculated and rounded to working days.
Specifies a date formula for the time that it takes to replenish the item. It is used to calculate the **Planned Receipt Date** field, if calculating forward, and **Order Date** field, if calculating backwards. See [Lead Time Calculation](across-how-to-assign-base-calendars.md#lead-time-calculation).

## Lead Time Calculation
Any base calendar defined for the vendor or the location affects how the dates are calculated and rounded to working days. Accordingly, the two date fields on purchase order lines are calculated as follows under different conditions.

|Calculation Direction|Vendor Calendar Defined|Vendor Calendar Not Defined|
|---------------------|-----------------------|---------------------------|
|Forward|planned receipt date = order date + vendor lead time (per the vendor calendar and rounded to the next working day in first the vendor calendar and then the location calendar)|planned receipt date = order date + vendor lead time (per the location calendar)|
|Backward|order date = planned receipt date - vendor lead time (per the vendor calendar and rounded to the previous working day in first the vendor calendar and then the location calendar)|order date = planned receipt date - vendor lead time (per the location calendar)|

> [!NOTE]
> In addition to the lead time calculation that affects the planned receipt date and order date, as shown in the above table, warehouse handling time and safety lead time may be added to the formulas to make up the value in the **Expected Receipt Date** field, as follows: Planned Receipt Date + Safety Lead Time + Inbound Warehouse Handling Time = Expected Receipt Date.

> [!Important]
> If your location uses a significantly different calendar than your vendors do, then it is important that you set up specific calendars for those vendors, to calculate optimal vendor lead times. For information about how to set up vendor calendars, see [To assign a base calendar](across-how-to-assign-base-calendars.md#to-assign-a-base-calendar).

The contents of the **Lead Time Calculation** field is copied from either the item card or the SKU card, if the lead time is defined for the item, or on the **Item Vendor Catalog** page, if the lead time is defined for the vendor.

## To customize a calendar
The main task in customizing a base calendar for your company, or one of its business partners, is to enter any changes to working and nonworking day status.

For example, while a base calendar would typically list all Saturdays as non-working days, the customized calendar for a particular location may list all Saturdays during the months of November and December, and leading up to the holiday season, as working days.

The following procedure uses the case of the location as an example. Note that at this point, you have already assigned a base calendar to the location.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the location that you want to update, and then select the **Customized Calendar** field. Note that a calendar must be selected in the **Base Calendar Code** field.
3. On the **Customized Calendar Entries** page opens, choose the **Maintain Customized Calendar Changes** action.
4. In the **Customized Calendar Changes**, add lines for customized calendar entries.

    When you enter a line, the **Nonworking** check box is selected. You can clear the check box if you want to change the status to a working day.

    You can use the **Recurring System** field to set a particular date or day as a recurring nonworking day. You can select either the **Annual Recurring** or **Weekly Recurring** option.

    If you select **Annual Recurring**, you must also enter the relevant date in the **Date** field. If you select **Weekly Recurring**, you must also select the relevant day of the week in the **Day** field. If you leave the field empty, you must fill in the **Date** field. The **Day** field is then filled in automatically. This could be useful if you want to mark an individual date as a nonworking or working day.

5. Choose the **OK** button.

On the **Customized Calendar Entries** page, you will observe that the date entries are updated with the changes that you made.

On the Location card, you will observe that the **Customized Calendar** field contains **Yes**, indicating that a customized calendar has been set up.

> [!Important]
> If you do not fill in the **Location Code** field on an order line, your company’s calendar is used.


If you do not fill in the **Shipping Agent Code** field on the order line, your company’s calendar is used.

> [!NOTE]  
> If you make changes to a base calendar for which customized calendar changes exist, all existing customized calendars are updated automatically.

## To assign a base calendar  
The following procedure schedules delivery dates on sales order lines for a customer as an example.

Base calendars are assigned to your own company, customers, vendors, locations, and shipping agents as follows:  

-   On the **Company Information** and **Customer** cards, the base calendar is assigned on the **Shipping** FastTab.  
-   On the **Vendor** card, the base calendar is assigned on the **Receiving** FastTab.  
-   On the **Location** card, the base calendar is assigned on the **Warehouse** FastTab.  
-   On the **Shipping Agents** page, the base calendar is assigned on the **Shipping Agent Services** page.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
2.  Open the **Customer** card for whom you will assign a base calendar.  
3.  On the **Shipping** FastTab, in the **Base Calendar Code** field, select the base calendar that you want to assign.  

> [!IMPORTANT]  
>  -   If you do not assign a base calendar to a company, all dates are calculated as working days.  
> -   If you enter a blank location on an order line, all dates are calculated as working days.  
> -   Any base calendar defined for the vendor or the location affects how the dates are calculated and rounded to working days.

> [!NOTE]  
>  Before you can make customized calendar entries, you must first assign a base calendar to the company.  

## See Also
[Purchasing](purchasing-manage-purchasing.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
