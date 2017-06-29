---
title: "How to: Set Up System Calendars and Accounting Periods"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "calendars, accounting periods"
  - "accounting calendars"
  - "system calendars"
  - "accounting periods, setting up"
ms.assetid: 0647c68d-2b9b-456e-abc5-edd850b03b59
caps.latest.revision: 46
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-gb"
---
# How to: Set Up System Calendars and Accounting Periods
For many companies, the fiscal year does not coincide with the calendar year. Fiscal periods can be measured in other units of time, such as months or quarters. For more information, see [\($ N\_10505 Calendar Setup $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/-$-n_10505-calendar-setup-$-.md), [\($ N\_10506 System Calendar $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/-$-n_10506-system-calendar-$-.md), and [\($ T\_10560 Accounting Period GB $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/-$-t_10560-accounting-period-gb-$-.md).  
  
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
  
 The following procedure describes how to set up accounting periods, but the same steps also apply to setting up system calendars. The difference in these procedures is that the **Closed** check box is not available in the **\($ N\_10506 System Calendar $\)** window for system dates.  
  
### To set up accounting periods  
  
1.  In the **Search** box, enter **Calendar Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, in the **Default Source Calendar** field, select **Acc. Period**.  
  
    > [!NOTE]  
    >  For system calendars, you must select **System** in the **Default Source Calendar** field.  
  
3.  Clear the check boxes described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_10505\_51 Use System For Day Period $\)**|Specifies if the day period information is retrieved from the accounting period calendar, instead of from the system calendar.|  
    |**\($ T\_10505\_52 Use System For Week Period $\)**|Specifies if the week period information is retrieved from the accounting period calendar, instead of from the system calendar.|  
    |**\($ T\_10505\_53 Use System For Month Period $\)**|Specifies if the month period information is retrieved from the accounting period calendar, instead of from the system calendar.|  
    |**\($ T\_10505\_54 Use System For Quarter Period $\)**|Specifies if the quarter period information is retrieved from the accounting period calendar, instead of from the system calendar.|  
  
    > [!NOTE]  
    >  If the check boxes are selected, these time periods are retrieved from the system calendar.  
  
4.  On the **Formatting** FastTab, in the **Acc. Period Calendar** section, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ N\_10505\_1040013 Day Format $\)**|Specifies the custom format property for period type **Day** when displaying dates using the accounting period calendar.|  
    |**\($ N\_10505\_1040015 Week Format $\)**|Specifies the custom format property for period type **Week** when displaying dates using the accounting period calendar.|  
    |**\($ N\_10505\_1040017 Month Format $\)**|Specifies the custom format property for period type **Month** when displaying dates using the accounting period calendar.|  
    |**\($ N\_10505\_1040019 Quarter Format $\)**|Specifies the custom format property for period type **Quarter** when displaying dates using the accounting period calendar.|  
    |**\($ N\_10505\_1040021 Year Format $\)**|Specifies the custom format property for period type **Year** when displaying dates using the accounting period calendar.|  
  
    > [!NOTE]  
    >  For system calendars, enter information for the display format in the **System Calendar** section.  
  
5.  On the **Navigate** tab, in the **Acc. Period** group, choose the time period for the corresponding **\($ T\_10560 Accounting Period GB $\)** window.  
  
6.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_10560\_1 Period Type $\)**|Specifies the period type for the accounting period.|  
    |**\($ T\_10560\_2 Period Start $\)**|Specifies the starting date for the accounting period.|  
    |**\($ T\_10560\_3 Period End $\)**|Specifies the ending date for the accounting period.|  
    |**\($ T\_10560\_4 Period No. $\)**|Specifies the number for the accounting period.|  
    |**\($ T\_10560\_5 Period Name $\)**|Specifies the name for the accounting period.|  
    |**\($ T\_10560\_10500 Closed $\)**|Specifies if the accounting period belongs to a closed fiscal year.|  
  
    > [!NOTE]  
    >  You cannot modify the period information for the system calendar.  
  
7.  Choose the **OK** button to return to the **\($ N\_10505 Calendar Setup $\)** window.  
  
8.  Choose the **OK** button.  
  
## See Also  
 [United Kingdom Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/united-kingdom-local-functionality.md)   
 [\($ T\_50 Accounting Period $\)](assetId:///38568c84-3fc6-4c5c-9a3c-b84927755c6a)   
 [\($ B\_10506 Change Dates $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/-$-b_10506-change-dates-$-.md)