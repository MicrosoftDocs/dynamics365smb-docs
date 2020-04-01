---
    title: How to Set Up Work Hours and Service Hours | Microsoft Docs
    description: You can specify the usual service working hours in your company. These service hours are used to calculate the response date and time for service orders and quotes, and to send response time warnings.
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
# Set Up Work Hours and Service Hours
Typically, a service management system tracks resource hours and service order status in order to forecast workloads and service needs. [!INCLUDE[d365fin](includes/d365fin_md.md)] has built-in tools that you can customize to record this kind of information.  
  
After you set the default service hours of your company, you can calculate response times for service orders or send warnings or alerts when service calls come in. The alert feature is implemented together with the job scheduler.   
  
As you work on a service order, you will want to update it's status so that you can monitor progress. The service order status reflects the repair status of all the service items in the service order. For more information, see [Understanding Service Order and Repair Status](service-order-repair-status.md). 

## To set up default service hours  
You use the **Default Service Hours** page to set up the usual service working hours in your company. These service hours are used to calculate the response date and time for service orders and quotes and to send response time warnings. The default service hours are used for service contracts unless you specify special service hours for a contract.  
  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Default Service Hours**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
  
> [!IMPORTANT]  
>  If you leave the lines on the **Default Service Hours** page empty, the default value is 24 hours, valid only for calendar working days.  
  
## To set up work-hour templates
You can use the **Work-Hour Template** page to set up templates that contain the typical working hours in your company. For example, you can create templates for full time technicians and part time technicians. You can use work-hour templates when you add capacity to resources.  
  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Work Hour Templates**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
  
> [!Note]
> After you enter work hours for each day, the value in the **Total per Week** field is calculated automatically.  

## To set up contract specific service hours  
You can use the **Service Hours** page to set up specific service hours for the customer that owns the service contract. Service hours are used to calculate the response date and time for service orders and quotes that belong to the service contract.  
  
If you do not set up specific service hours for the service contract, the default service hours for service contracts are used.  
  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Contracts**, and then choose the related link.  
2. Open the service contract you want to set up specific service hours for, and choose **Service Hours**.  
4. To set up service hours based on default service hours, choose the **Copy Default Service Hours** action.  
5. Edit the fields in the service hours entries. Insert or delete entries to set up the service hours for the contract. Note that the fields **Day**, **Starting Time** and **Ending Time** are required for each line.  
6. If you want the service hours to be valid from a specific date, fill in the **Starting Date** field.  
7. If you want the service hours to be valid on holidays, select the check box in the **Valid on Holidays** field.  

## See Also  
[Understanding Allocation Status and Repair Status](service-allocation-status-and-repair-status.md)  
[Setting Up Service Management](service-setup-service.md)  
[Understanding Service Order and Repair Status](service-order-repair-status.md)  
