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
Typically, a service management system tracks resource hours and service order status in order to forecast workloads and service needs. [!INCLUDE[d365fin](includes/d365fin_md.md)] has built-in tools that you can customize to record this kind of information.  
  
After you set the default service hours of your company, you can calculate response times for service orders or send warnings or alerts when service calls come in. The alert feature is implemented together with the job scheduler.  
  
|Track order and repair status in order to forecast service priorities.|[Service Order Status and Repair Status](../service-order-status-and-repair-status.md)| 

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
  
## How to: Set Up Work-Hour Templates
You can use the **Work-Hour Template** window to set up templates that contain the typical working hours in your company. For example, you can create templates for full time technicians and part time technicians. You can use work-hour templates when you add capacity to resources.  
  
### To set up a work-hour template  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Work Hour Templates**, and then choose the related link.  
2. Create a new work-hour template. On the **Home** tab, in the **New** group, choose **New**.  
3. Fill in the **Code** and **Description** fields.  
4. In the **Monday**, **Tuesday**, **Wednesday**, **Thursday**, **Friday**, **Saturday**, and **Sunday** fields, enter the number of work-hours for each day of the week. The **Total per Week** field is calculated automatically.  

## How to: Set Up Contract Specific Service Hours
You can use the **Service Hours** window to set up specific service hours for the customer that owns the service contract. Service hours are used to calculate the response date and time for service orders and quotes that belong to the service contract.  
  
If you do not set up specific service hours for the service contract, the default service hours for service contracts are used.  
  
### To set up contract specific service hours  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Contracts**, and then choose the related link.  
2. Open the service contract you want to set up specific service hours for, and choose **Service Hours**.  
4. To set up service hours based on default service hours, choose the **Copy Default Service Hours** action.  
5. Edit the fields in the service hours entries. Insert or delete entries to set up the service hours for the contract. Note that the fields **Day**, **Starting Time** and **Ending Time** are required for each line.  
6. If you want the service hours to be valid from a specific date, fill in the **Starting Date** field.  
7. If you want the service hours to be valid on holidays, select the check box in the **Valid on Holidays** field.  

## See Also  
[Setting Up Service Management](service-setup-service.md)