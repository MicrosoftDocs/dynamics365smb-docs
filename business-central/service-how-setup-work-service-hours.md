---
title: How to set up work hours and service hours
description: Learn how to set up the work and service hours used to calculate the response date and time for service orders and quotes.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: service hours, work hours, service management, service order, service contract, service item, service quote, service request
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ms.custom: bap-template
---

# Set up work hours and service hours

Typically, a service management system tracks resource hours and service order status in order to forecast workloads and service needs. [!INCLUDE[prod_short](includes/prod_short.md)] has built-in tools that you can customize to record this kind of information.  
  
After you set the default service hours of your company, you can calculate response times for service orders or send warnings or alerts when service calls come in. The alert feature is implemented together with the job scheduler.
  
As you work on a service order, update its status so that you can monitor progress. The service order status reflects the repair status of all the service items in the service order. Learn more in [Understanding Service Order and Repair Status](service-order-repair-status.md).

## Set up default service hours

You use the **Default Service Hours** page to set up the usual service working hours in your company. These service hours are used to calculate the response date and time for service orders and quotes and to send response time warnings. The default service hours are used for service contracts unless you specify special service hours for a contract.  
  
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Default Service Hours**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
  
> [!IMPORTANT]  
> If you leave the lines on the **Default Service Hours** page empty, the default value is 24 hours, valid only for calendar working days.  
  
## Set up work hour templates

You can use the **Work Hour Template** page to set up templates that contain the working hours for different types of resources in your company. For example, you can create templates for full time technicians and part time technicians. You use work hour templates when you set capacity for resources. Learn more in [Set capacity for a resource](projects-how-setup-resources.md#to-set-capacity-for-a-resource) for information about setting capacity for a resource.
  
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Work Hour Templates**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
  
> [!Note]
> After you enter work hours for each day, the value in the **Total per Week** field is calculated automatically.  

## Set up contract specific service hours

You can use the **Service Hours** page to set up specific service hours for the customer that owns the service contract. Service hours are used to calculate the response date and time for service orders and quotes that belong to the service contract.  
  
If you don't set up specific service hours for the service contract, the default service hours for service contracts are used.  
  
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Contracts**, and then choose the related link.  
2. Open the service contract you want to set up specific service hours for, and choose **Service Hours**.  
3. To set up service hours based on default service hours, choose the **Copy Default Service Hours** action.  
4. Edit the fields in the service hours entries. Insert or delete entries to set up the service hours for the contract. The fields **Day**, **Starting Time** and **Ending Time** are required for each line.  
5. If you want the service hours to be valid from a specific date, fill in the **Starting Date** field.  
6. If you want the service hours to be valid on holidays, select the check box in the **Valid on Holidays** field.  

## Related information

[Understand Allocation Status and Repair Status](service-allocation-status-and-repair-status.md)  
[Set Up Service Management](service-setup-service.md)  
[Understand Service Order and Repair Status](service-order-repair-status.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
