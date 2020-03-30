---
    title: How to Set Up Shop Calendars | Microsoft Docs
    description: A work center calendar specifies the working days and hours, shifts, holidays, and absences that determine the work center’s gross available capacity, measured in time, according to its defined efficiency and capacity values. Creating and enabling a work center calendar involves several preparatory tasks.
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
# Set Up Shop Calendars
A work center or machine calendar specifies the working days and hours, shifts, holidays, and absences that determine the center’s gross available capacity, measured in time, according to its defined efficiency and capacity values.

As a foundation for calculating a specific work or machine center calendar, you must first set up one or more general shop calendars. A shop calendar defines a standard work week according to start and end times of each working day and the work shift relation. In addition, the shop calendar defines the fixed holidays during a year.  

The following describes how to set up work center calendars. The steps are similar when setting up machine center calendars.  

## To create work shifts  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Work Shifts**, and then choose the related link.  
2.  On a blank line, enter a number in the **Code** field to identify the work shift, for example, **1**.  
3.  Describe the work shift in the **Description** field, for example, **1st shift**.  
4.  Optionally, fill in lines for a second or third work shift.  

Even if your work centers do not work in different work shifts, enter at least one work shift code.  

## To set up a shop calendar  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shop Calendars**, and then choose the related link.  
2.  On a blank line, enter a number in the **Code** field to identify the shop calendar.  
3.  Describe the shop calendar in the **Description** field.  
4.  Choose the **Working Days** action.
5.  On the **Shop Calendar Working Days** page, define a complete work week, with the start and end times for each day.  

    In the **Work Shift Code** field, select one of the shifts that you previously defined. Add a line for every working day and every shift. For example:  

    Monday  07:00 15:00 1   
    Tuesday 07:00 15:00 1  

    If you need a shop calendar with two work shifts, you must fill it in in this manner:  

    Monday 07:00 15:00 1   
    Monday 15:00 23:00 2  
    Tuesday 07:00 15:00 1  
    Tuesday 15:00 23:00 2  

    Any week days that you do not define in the shop calendar, such as Saturday and Sunday, are considered non-working days and will have zero available capacity in a work center calendar.  

    When all the working days of a week are defined, you can close the **Shop Calendar Working Days** page and proceed to enter holidays.  

6.  On the **Shop Calendars** page, select the shop calendar, and then choose the **Holidays** action.
7. On the **Shop Calendar Holidays** page, define the holidays of the year by entering the start date and time, the end time, and description of each holiday on individual lines. For example:  

    04/07/14 0:00:00 23:59:00 Summer Holiday  
    05/07/14 0:00:00 23:59:00 Summer Holiday  
    06/07/14 0:00:00 23:59:00 Summer Holiday  

The defined holidays will have zero available capacity in a work center calendar.  

The shop calendar can now be assigned to a work center to calculate the work shop calendar that will govern all operation scheduling at that work center.  

## To calculate a work center calendar  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Work Centers**, and then choose the related link.
2. Open the work center that you want to update.  
3. In the **Shop Calendar Code** field, select which shop calendar to use as the foundation for a work center calendar.  
4. Choose the **Calendar** action.  
5. On the **Work Center Calendar** page, choose the **Show Matrix** action.  

    The left side of the matrix page lists the work centers that are set up. The right side shows a calendar displaying the available capacity values for each working day in the defined unit of measure, for example, **480** minutes. Each line represents the calendar of one work center.  

    > [!NOTE]  
    >  You can also select to view the capacity values for each week or month by changing the selection in the **View By** field on the **Work Center Calendar** page.  

    To reflect the new shop calendar as a line on the selected work center, it must first be calculated.  

6.  Choose the **Calculate** action.  
7.  On the **Work Center** FastTab, you can set a filter to only calculate for one work center. If you do not set a filter, all existing work center calendars will be calculated.  
8.  Define the starting and ending dates of the calendar period that should be calculated, for example, one year from 01/01/14 to 31/12/14.
9. Choose the **OK** button to calculate capacity.  

Calendar entries are now created or updated displaying the available capacity for each period according to the following three sets of master data:  

- The working days and shift defined in the assigned shop calendar.  
- The value in the **Capacity** field on the work center card.  
- The value in the **Efficiency** field on the work center card.  

The calculated work center calendar will now define when and how much capacity is available at this work center. This controls the detailed scheduling of operations performed at the work center.  

## To record work center absence  
1.  On the **Work Center Calendar** page, choose the **Show Matrix** action.
2. On the **Work Center Calendar Matrix** page, select the work center and calendar day when the absence time should be recorded, and then choose the **Absence** action.  
3.  On the **Absence** page, define the starting time, ending time, and description of that day’s absence. For example:  

    25/01/01 08:00 10:00 Maintenance  

4.  Choose the **Update** action, and then close the **Absence** page.  

The capacity of the selected day has now decreased by the recorded absence time.  

## See Also  
[Set Up Base Calendars](across-how-to-assign-base-calendars.md)  
[Set Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
