---
    title: How to Set Up Work Hours and Service Hours | Microsoft Docs
    description: You can specify the usual service working hours in your company. These service hours are used to calculate the response date and time for service orders and quotes, and to send response time warnings.
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
# How to: Set Up Work Hours and Service Hours


## How to: Set Up Default Service Hours
You use the **Default Service Hours** window to set up the usual service working hours in your company. These service hours are used to calculate the response date and time for service orders and quotes and to send response time warnings. The default service hours are used for service contracts unless you specify special service hours for a contract.  
  
### To set up default service hours  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Default Service Hours**, and then choose the related link.  
2. Create a new default service hour entry.  
3. On the lines, in the **Starting Date** field, enter the date the service hours are valid from. If you leave this field empty, the service hours are always valid.  
4. In the **Day** field, select the day of the week you are defining service hours entry for. This field must be filled in.  
5. In the **Starting Time** and **Ending Time** fields, insert the starting and ending time of service hours for the service hours entry. These fields must be filled in.  
6. In the **Valid on Holidays** field, select the check box if you want the service hours entry to be valid on holidays.  
   
> [!IMPORTANT]  
>  If you leave the lines in the **Default Service Hours** window empty, the default value is 24 hours, valid only for calendar working days.  
  
# How to: Set Up Work-Hour Templates
You can use the **Work-Hour Template** window to set up templates that contain the typical working hours in your company. For example, you can create templates for full time technicians and part time technicians. You can use work-hour templates when you add capacity to resources.  
  
### To set up a work-hour template  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Work Hour Templates**, and then choose the related link.  
2. Create a new work-hour template. On the **Home** tab, in the **New** group, choose **New**.  
3. Fill in the **Code** and **Description** fields.  
4. In the **Monday**, **Tuesday**, **Wednesday**, **Thursday**, **Friday**, **Saturday**, and **Sunday** fields, enter the number of work-hours for each day of the week. The **Total per Week** field is calculated automatically.  

## See Also  
 [How to: Set Up Contract Specific Service Hours](../how-to-set-up-contract-specific-service-hours.md)