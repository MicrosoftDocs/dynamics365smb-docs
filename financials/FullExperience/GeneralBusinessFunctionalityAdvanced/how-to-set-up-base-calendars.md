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
# How to: Set Up Base Calendars
The main task in setting up a new base calendar is to specify and define the nonworking days that you want to apply.  
  
### To set up a base calendar  
  
1.  In the **Search** box, enter **Base Calendar**, and then choose the related link.  
  
2.  Create a new Base Calendar Card. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Fill in the **Code** field.  
  
4.  At this point, the calendar lists all date entries as working days. To register nonworking days, on the **Actions** tab, in the **Functions** group, choose **Maintain Base Calendar Changes**. The **Base Calendar Changes** window opens.  
  
5.  You can use the **Recurring System** field to mark a particular date or day as a recurring nonworking day. You can select either the **Annual Recurring** or **Weekly Recurring** option.  
  
     If you select **Annual Recurring**, you must also enter the relevant date in the **Date** field.  
  
     If you select **Weekly Recurring**, you must also select the relevant day of the week in the **Day** field. If you leave the field empty, you must fill in the **Date** field. The **Day** field is filled in automatically.  
  
6.  When you make an entry, the **Nonworking** field is selected. You can choose to clear the check mark to make it a working day.  
  
7.  When you return to the base calendar card, you will observe that the nonworking day entries that you made have been updated. These entries now appear in red and the **Nonworking** field is selected.  
  
> [!NOTE]  
>  When setting up a new base calendar, you can select and copy lines from an existing calendar. You do this in the relevant **Base Calendar Changes** window.  
  
> [!IMPORTANT]  
>  Any base calendar defined for the vendor or the location affects how the dates are calculated and rounded to working days. For more information, see the Lead Time Calculation field on purchase lines.  
  
## See Also  
 [How to: Assign Base Calendars](../../Production/how-to-assign-base-calendars.md)   
 [How to: Customize a Calendar](../../Production/how-to-customize-a-calendar.md)   
 [How to: Create Work Center Calendars](../../OperationsPlanning/how-to-create-work-center-calendars.md)