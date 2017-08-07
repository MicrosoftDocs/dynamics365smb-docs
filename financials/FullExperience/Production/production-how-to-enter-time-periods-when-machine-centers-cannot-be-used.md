---
    title: How to Enter Time Periods When Machine Centers Cannot Be Used | Microsoft Docs
    description: You can define time periods where machine centers cannot be used.
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
# How to: Enter Time Periods When Machine Centers Cannot Be Used
You can define time periods where machine centers cannot be used.  
  
 The machine centers are not assigned their own shop calendar. The shop calendar of the work center is used.  
  
 The calendar for the machine center is calculated from the entries of the assigned shop calendar and the calendar absence entries of the machine center.  
  
 The result of the calculation is entries in the calendar for the machine center.  
  
### To enter time periods when machine centers cannot be used  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Machine Centers**, and then choose the related link.  
  
2.  Open the relevant **Machine Center** card   from the list.  
  
3.  On the **Navigate** tab, in the **Planning** group, choose **Absence**.  
  
4.  Fill in the **Date**, **Starting Time**, and **Ending Time** fields for the planned absence.  
  
     These calendar absence entries are only valid for the selected machine center.  
  
5.  On the **Navigate** tab, in the **Absence** group, choose **Update** to calculate the calendar entries for the machine center. This must be done every time you enter calendar entries.  
  
## See Also  
 [Shop Calendars](../shop-calendars.md)   
 [How to: Update Calendar Entries for Machine Centers](../how-to-update-calendar-entries-for-machine-centers.md)   
 [How to: Recalculate Calendar Entries for Machine Centers](../how-to-recalculate-calendar-entries-for-machine-centers.md)   
 [How to: Enter Time Periods When Work Centers Cannot Be Used](../how-to-enter-time-periods-when-work-centers-cannot-be-used.md)