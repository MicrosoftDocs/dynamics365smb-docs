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
# How to: Set Up System Calendars and Accounting Periods
For many companies, the fiscal year does not coincide with the calendar year. Fiscal periods can be measured in other units of time, such as months or quarters. For more information, see Calendar Setup, System Calendar, and Accounting Period GB.  
  
 You can set up system calendars and accounting periods to allow you to do the following:  
  
-   Extend accounting periods to allow for different weeks, months, quarters, and years.  
  
-   Switch between accounting periods and calendar periods.  
  
-   Filter data that uses the following criteria:  
  
    -   Work date  
  
    -   Week  
  
    -   Month  
  
    -   Quarter  
  
    -   Year  
  
-   Calculate formulas for account schedules based on related calendars.  
  
-   Access an overview of accounting periods.  
  
-   Access and print a report for accounting periods that do not follow the system calendar.  
  
 The following procedure describes how to set up accounting periods, but the same steps also apply to setting up system calendars. The difference in these procedures is that the **Closed** check box is not available in the **System Calendar** window for system dates.  
  
### To set up accounting periods  
  
1.  In the **Search** box, enter **Calendar Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, in the **Default Source Calendar** field, select **Acc. Period**.  
  
    > [!NOTE]  
    >  For system calendars, you must select **System** in the **Default Source Calendar** field.  
  
3.  Clear the check boxes described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Use System For Day Period**|Specifies if the day period information is retrieved from the accounting period calendar, instead of from the system calendar.|  
    |**Use System For Week Period**|Specifies if the week period information is retrieved from the accounting period calendar, instead of from the system calendar.|  
    |**Use System For Month Period**|Specifies if the month period information is retrieved from the accounting period calendar, instead of from the system calendar.|  
    |**Use System For Quarter Period**|Specifies if the quarter period information is retrieved from the accounting period calendar, instead of from the system calendar.|  
  
    > [!NOTE]  
    >  If the check boxes are selected, these time periods are retrieved from the system calendar.  
  
4.  On the **Formatting** FastTab, in the **Acc. Period Calendar** section, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Day Format**|Specifies the custom format property for period type **Day** when displaying dates using the accounting period calendar.|  
    |**Week Format**|Specifies the custom format property for period type **Week** when displaying dates using the accounting period calendar.|  
    |**Month Format**|Specifies the custom format property for period type **Month** when displaying dates using the accounting period calendar.|  
    |**Quarter Format**|Specifies the custom format property for period type **Quarter** when displaying dates using the accounting period calendar.|  
    |**Year Format**|Specifies the custom format property for period type **Year** when displaying dates using the accounting period calendar.|  
  
    > [!NOTE]  
    >  For system calendars, enter information for the display format in the **System Calendar** section.  
  
5.  On the **Navigate** tab, in the **Acc. Period** group, choose the time period for the corresponding **Accounting Period GB** window.  
  
6.  Fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Period Type**|Specifies the period type for the accounting period.|  
    |**Period Start**|Specifies the starting date for the accounting period.|  
    |**Period End**|Specifies the ending date for the accounting period.|  
    |**Period No.**|Specifies the number for the accounting period.|  
    |**Period Name**|Specifies the name for the accounting period.|  
    |**Closed**|Specifies if the accounting period belongs to a closed fiscal year.|  
  
    > [!NOTE]  
    >  You cannot modify the period information for the system calendar.  
  
7.  Choose the **OK** button to return to the **Calendar Setup** window.  
  
8.  Choose the **OK** button.  
  
## See Also  
 [United Kingdom Local Functionality](united-kingdom-local-functionality.md)   
 Accounting Period   
 Change Dates