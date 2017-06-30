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
# How to: Create Work Center Calendars
A work center calendar specifies the working days and hours, shifts, holidays, and absences that determine the work center’s gross available capacity, measured in time, according to its defined efficiency and capacity values. Creating and enabling a work center calendar involves several preparatory tasks.  
  
 As a foundation for calculating a specific work center calendar, you must first set up one or more general shop calendars. A shop calendar defines a standard work week according to start and end times of each working day and the work shift relation. In addition, the shop calendar defines the fixed holidays during a year.  
  
 **Prerequisite**  
  
 Gather all data about work times on your shop floor.  
  
### To create work shifts  
  
1.  In the **Search** box, enter **Work Shifts**, and then choose the related link.  
  
2.  On a blank line, enter a number in the **Code** field to identify the work shift, for example, **1**.  
  
3.  Describe the work shift in the **Description** field, for example, **1st shift**.  
  
4.  Optionally, fill in lines for a second or third work shift.  
  
 Even if your work centers do not work in different work shifts, enter at least one work shift code.  
  
### To set up a shop calendar  
  
1.  In the **Search** box, enter **Shop Calendars**, and then choose the related link.  
  
2.  On a blank line, enter a number in the **Code** field to identify the shop calendar.  
  
3.  Describe the shop calendar in the **Description** field.  
  
     The initial naming of the new shop calendar is complete. Now, you can proceed to define its contents.  
  
4.  Select the shop calendar. On the **Navigate** tab, in the  **Shop Cal.** group, choose **Working Days**. The **Shop Calendar Working Days** window opens with the name of the shop calendar.  
  
5.  Define a complete work week, with the start and end times for each day.  
  
     In the **Work Shift Code** field, select one of the shifts that you previously defined. Add a line for every working day and every shift. For example:  
  
     Monday  07:00 15:00 1   
    Tuesday 07:00 15:00 1  
  
     If you need a shop calendar with two work shifts, you must fill it in in this manner:  
  
     Monday 07:00 15:00 1   
    Monday 15:00 23:00 2  
    Tuesday 07:00 15:00 1  
    Tuesday 15:00 23:00 2  
  
     Any week days that you do not define in the shop calendar, such as Saturday and Sunday, are considered non-working days and will have zero available capacity in a work center calendar.  
  
     When all the working days of a week are defined, you can close the **Shop Calendar Working Days** window and proceed to enter holidays.  
  
6.  In the **Shop Calendars** window, select the shop calendar. On the **Navigate** tab, in the **Shop Cal.** group, choose **Holidays**. The **Shop Calendar Holidays** window opens.  
  
7.  Define the holidays of the year by entering the start date and time, the end time, and description of each holiday on individual lines. For example:  
  
     04\/07\/14 0:00:00 23:59:00 Summer Holiday  
    05\/07\/14 0:00:00 23:59:00 Summer Holiday  
    06\/07\/14 0:00:00 23:59:00 Summer Holiday  
  
 The defined holidays will have zero available capacity in a work center calendar.  
  
 The shop calendar can now be assigned to a work center to calculate the work shop calendar that will govern all operation scheduling at that work center.  
  
### To calculate a work center calendar  
  
1.  In the **Search** box, enter **Work Centers**, and then choose the related link. Open the work center that you want to update.  
  
2.  On the **Scheduling** FastTab, in the **Shop Calendar Code** field, select which shop calendar to use as the foundation for a work center calendar.  
  
3.  On the **Navigate** tab, in the **Planning** group, choose **Calendar**.  
  
4.  In the **Work Center Calendar** window, on the **Actions** tab, in the **General** group, choose **Show Matrix**.  
  
     The left side of the matrix window lists the work centers that are set up. The right side shows a calendar displaying the available capacity values for each working day in the defined unit of measure, for example, **480** minutes. Each line represents the calendar of one work center.  
  
    > [!NOTE]  
    >  You can also select to view the capacity values for each week or month by changing the selection in the **View By** field on the **Matrix Options** FastTab in the **Work Center Calendar** window.  
  
     To reflect the new shop calendar as a line on the selected work center, it must first be calculated.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Calculate**.  
  
6.  On the **Work Center** FastTab, you can set a filter to only calculate for one work center. If you do not set a filter, all existing work center calendars will be calculated.  
  
7.  Define the starting and ending dates of the calendar period that should be calculated, for example, one year from 01\/01\/14 to 31\/12\/14. Choose the **OK** button to calculate capacity.  
  
 Calendar entries are now created or updated displaying the available capacity for each period according to the following three sets of master data:  
  
-   The working days and shift defined in the assigned shop calendar.  
  
-   The value in the **Capacity** field on the work center card.  
  
-   The value in the **Efficiency** field on the work center card.  
  
 The calculated work center calendar will now define when and how much capacity is available at this work center. This controls the detailed scheduling of operations performed at the work center.  
  
### To record work center absence  
  
1.  In the **Work Center Calendar** window, on the **Actions** tab, in the **General** group, choose **Show Matrix**. The **Work Center Calendar Matrix** window opens.  
  
2.  Select the work center and calendar day when the absence time should be recorded. On the **Navigate** tab, in the **Planning** group, choose **Absence**.  
  
3.  In the **Absence** window, define the starting time, ending time, and description of that day’s absence. For example:  
  
     25\/01\/01 08:00 10:00 Maintenance  
  
4.  On the **Navigate** tab, in the **Absence** group, choose **Update**, and then close the **Absence** window.  
  
 The capacity of the selected day has now decreased by the recorded absence time.  
  
## See Also  
 [Shop Calendars](../shop-calendars.md)