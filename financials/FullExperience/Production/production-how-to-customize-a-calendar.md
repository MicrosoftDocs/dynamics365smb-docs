---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Customize a Calendar
The main task in customizing a base calendar for your company, or one of its business partners, is to enter any changes to working and nonworking day status.  
  
 For example, while a base calendar would typically list all Saturdays as nonworking days, the customized calendar for a particular location may list all Saturdays during the months of November and December, and leading up to the holiday season, as working days.  
  
 The following procedure uses the case of the location as an example. Note that at this point, you have already assigned a base calendar to the location.  
  
### To customize a calendar  
  
1.  In the **Search** box, enter **Locations**, and then choose the related link.  
  
2.  Open the location that you want to update. On the **Warehouse** FastTab, select the **Customized Calendar** field to open the **Customized Calendar Entries** window. Note that a calendar must be selected in the **Base Calendar Code** field.  
  
     The **Customized Calendar Entries** window opens. At this point, the date entries are the same as those in the base calendar. The **Nonworking** field is selected for nonworking days.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Maintain Customized Calendar Changes**.   
    The **Customized Calendar Changes** window opens.  
  
4.  Add lines for customized calendar entries. When you enter a line,  the **Nonworking** field is selected. You can clear the check mark if you want to change the status to a working day.  
  
5.  You can use the **Recurring System** field to set a particular date or day as a recurring nonworking day. You can select either the **Annual Recurring** or **Weekly Recurring** option. If you select Annual Recurring, you must also enter the relevant date in the **Date** field. If you select Weekly Recurring, you must also select the relevant day of the week in the **Day** field.   
    If you leave the field empty, you must fill in the **Date** field. The **Day** field is filled in automatically. This could be useful if you want to mark an individual date as a nonworking or working day. Choose the **OK** button.  
  
6.  On the **Customized Calendar Entries** window, you will observe that the date entries are updated with the changes that you made. Choose the **Close** button.  
  
7.  On the **Location** card, you will observe that the **Customized Calendar** field contains the word **Yes**, indicating that a customized calendar has been set up.  
  
> [!IMPORTANT]  
>  -   If you do not fill in the **Location Code** field on an order line, your company’s calendar is used.  
> -   If you do not fill in the **Shipping Agent Code** field on the order line, your company’s calendar is used.  
  
> [!NOTE]  
>  If you make changes to a base calendar for which customized calendar changes exist, all existing customized calendars are updated automatically.  
  
## See Also  
 [How to: Set Up Base Calendars](../how-to-set-up-base-calendars.md)   
 [How to: Assign Base Calendars](../how-to-assign-base-calendars.md)