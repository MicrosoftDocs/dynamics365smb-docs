---
title: Set Up Resource Costs, Prices, and Capacity| Microsoft Docs
description: To use resources and facilitate project management, you specify costs and prices for individual resources or resource groups, and set the resource capacity.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, capacity, staff
ms.date: 06/06/2017
ms.author: sgroespe

---
# Set Up Resources
To correctly manage resource activities, you must set up your resources and the related costs and prices. The job-related prices, discounts, and cost factor rules are set up on the job card. You can specify the costs and prices for individual resources, resource groups, or all available resources of the company.

When resources are used or sold in a job, the prices and costs associated with them are retrieved from the information that you set up.

You specify the default amount per hour when the resource is created. For example, if you use a specific machine on a job for five hours, the job would be calculated based on the amount per hour.

## To set up a resource
Create a card for each resource that you want to use in projects.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resources**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## To set up a resource group
You can combine several resources in one resource group. All capacities and budgets of resource groups are accumulated from the individual resources. It is also possible to enter capacities for resource groups either independently of the accumulated values or in addition to them.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resource groups**, and then choose the related link.
2. Choose the **New** action.
3. Fill in the fields as necessary.

## To set capacity for a resource
To calculate how much time a resource can spend on jobs, their capacity must first be set up as available time per period on the work calendar. This setup is used when you fill in job planning lines that contain the resource. For more information, see [Create Jobs](projects-how-create-jobs.md).

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resources**, and then choose the related link.
2. Open the relevant resource card, and then choose the **Resource Capacity** action.
3. In the **Resource Capacity** window, in the **View By** field, specify the length of the period, such as **Day**, that is shown on columns on the **Resource Capacity Matrix** FastTab.
4. For each resource on a line, specify for each period on the columns the number of hours that the resource is available.
5. Alternatively, to detail the resource's weekly capacity within a starting and ending date, choose the **Set Capacity** action.
6. In the **Resource Capacity Settings** window, fill in the fields as necessary.
7. Choose the **Update Capacity** action. The **Resource Capacity** window is updated with the entered capacity.
8. Close the window.

## To set up alternate resource costs
In addition to the cost specified on the resource card, you can set up alternate costs for each resource. For example, if you pay an employee a higher hourly rate for overtime, you can set up a resource cost for the overtime rate. The alternate cost that you set up for the resource will override the cost on the resource card when you use the resource in the resource journal.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resources**, and then choose the related link.  
2. Select the resource for that you want to set up one or more alternate costs for, and then choose the **Costs** action.  
3. In the **Resource Costs** window, fill in the fields on a line as necessary.  
4. Repeat step 3 for each alternate resource cost that you want to set up.

**Note**. To set up resource costs that will apply to all resources and resource groups, open the **Resource Costs** window and fill in the fields.

## To set up alternate resource prices
In addition to price specified on the resource card, you can set up alternate prices for each resource. These alternate prices can be conditional. They can depend on whether the resource is used with a specific job or work type.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resources**, and then choose the related link.
2. Select the resource for that you want to set up one or more alternate prices for, and then choose the **Prices** action.
3. In the **Resource Prices** window, fill in the fields on a line as necessary.
4. Repeat step 3 for each alternate resource price that you want to set up.

## See Also
[Setting Up Project Management](projects-setup-projects.md)  
[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)         
[Sales](sales-manage-sales.md)      
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
