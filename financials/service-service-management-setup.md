---
    title: Set Up Service Management Processes | Microsoft Docs
    description: Learn how to set up processes that help ensure that your customers are thoroughly satisfied with your customer service.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/22/2017
    ms.author: sgroespe

---
# Setting Up Service Management
Setup features in Service Management help you specify defaults, numbering series, and the required fields that you want a customer service representative to fill in. The information stored in the underlying tables determines how to manage certain aspects of the service management activities.  
  
In addition, you can establish coding for standard services, symptom, and fault codes, and set up service item types that your company's customer service needs require.  
  
When you define a service, you can associate it with the skills required to perform the service. To help your service representatives be efficient, you can also set up real time troubleshooting guidelines and assign typical startup costs, such as travel costs or other fees.  
  
The following table describes a sequence of tasks, with links to the topics that describe them.   
  
|**To**|**See**|  
|------------|-------------|  
|Standardize coding for the service lines that underlie all service items.|[Service Coding](../service-coding.md)|  
|Standardize coding for fault reporting and resolution status.|[Fault Reporting](../fault-reporting.md)|  
|Define and map the skills that a service requires to people and other resources.|[How to: Set Up Skill Codes](../how-to-set-up-skill-codes.md)|  
|Set up guidelines to support the **Troubleshooting** window.|[How to: Set Up Troubleshooting Guidelines](../how-to-set-up-troubleshooting-guidelines.md)|  
|Associate specific costs with service items. Examples of costs include travel costs and support costs.|[How to: Set Up Service Costs](../how-to-set-up-service-costs.md)| 



## How to: Set Up Standard Service Codes
When you perform typical service, you often have to create service documents that use service lines that contain similar information. To make it easy to create these lines, you can set up standard service codes that have a predefined set of service lines. When you choose the code on a service document, the lines are entered automatically. You can set up any number of standard service codes, and each code can have an unlimited number of service lines of different types, including item, resource, cost, or standrd text linked to it. You create service lines of each standard serice code on the **Standard Service Code** card. You then assign standard service codes to service item groups on the **Standard Serv. Item Gr. Codes** page. Later, when you create a service document, you can use the **Get Standard Service Codes** action to add service lines.

> [!Tip]
>  You can use the same concept to create lines on sales and purchase documents. For more information, see [How to: Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md).    
  
### To set up a standard service code    
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Standard Service Codes**, and then choose the related link.    
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Fill in the service lines linked to this service code.

### To assign a standard service code to a service item group
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service item Groups**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Fill in the service lines linked to this service code.

### See Also  
 [How to: Insert Service Lines by Using Standard Service Codes](../how-to-insert-service-lines-by-using-standard-service-codes.md)   
 [How to: Assign Standard Service Codes to Service Item Groups](../how-to-assign-standard-service-codes-to-service-item-groups.md)

## Setting up fault reporting
Fault reporting lets you establish standards for recording fault information for service items. For example, you can specify what the problem is, the symptoms you see, the reason for the problem, and how to resolve it.  

Fault codes describe the typical service item faults or the actions taken on service items. Depending on the level of fault reporting in your company, you might need to set up fault area codes and symptom codes before you set up fault codes. Fault areas descrive areas of service item faults. Fault reason codes describe the reason for service item faults and, if needed, whether to exclude warranty and contract discounts. For example, you might want to exclude warranty and contract discounts if the customer was somehow responsible for the fault in the service item. You assign fault reason codes to service orders.  

## See Also  
[Service Management](service-service.md)