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
Setup features for Service Management help you specify defaults, numbering series, and the fields that you want to require a customer service representative to fill in on service documents. The information stored in the underlying tables determines how to manage certain aspects of the service management activities. In addition, you can establish coding for standard services, symptoms, and fault codes, and the service items and service item types that your company's customer service needs require.  
  
When you define a service, you can associate it with the skills required to perform the service. To help your service representatives be efficient, you can also set up real time troubleshooting guidelines and assign typical startup costs, such as travel costs or other fees.  
  
The following table describes a sequence of tasks, with links to the topics that describe them.   
  
|**To**|**See**|  
|------------|-------------|  
|Define and map the skills that a service requires to people and other resources.|[How to: Set Up Skill Codes](../how-to-set-up-skill-codes.md)|  
|Set up guidelines to support the **Troubleshooting** window.|[How to: Set Up Troubleshooting Guidelines](../how-to-set-up-troubleshooting-guidelines.md)|  
|Associate specific costs with service items. Examples of costs include travel costs and support costs.|[How to: Set Up Service Costs](../how-to-set-up-service-costs.md)| 

## How to: Specify General and Mandatory Settings for Service Management
The first thing to do to set up Service Management is to specify:  

* Some overall settings for various processes, such as warnings, next service calculations for service items, the starting fee to assess, the fault reporting level to use, and so on.  
* The types if information that a technician must enter on service documents. For example, you can require them to specify the type of order, the start and/or end dates for the work, and the type of work that was done.     
* Some default settings for response times and warranties. These include a default response time for starting service, warranty discount percentages for parts and labor, and how long warranties are valid for.  
* Settings for contracts, such as the maximum number of days that you can use for contract service orders, whether to use reason codes when a contract is canceled, standard texts for contract descriptions, and contract values.
* The number sequences to use for service-related documents and items.    

### To enter general and mandatory settings
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Setup**, and then choose the related link.    
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

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

### To specify the overall level of fault reporting to use
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Setup**, and then choose the related link.
2. In the **Fault Reporting Level** field, choose one of the options described in the following table.

    |**Fault Level**|**Description**|  
    |------------|-------------|  
    |None | No reporting codes are used.|  
    |Fault | Codes are listed in the **Fault Codes** table. These codes identify service item faults or actions to take on service items. You can cluster related codes into **Fault Area Code** groupings.|  
    |Fault + Symptom | You provide a combination of codes in the **Fault Codes** and **Symptom Codes** tables. Typical symptom codes include indicators that a customer might use to describe a problem, such as a noise or a quality.|  
    |Fault + Symptom + Area | You use fault, symptom, and fault area codes as an implementation of the International Repair Coding System (IRIS).|  
  
<!--To complete the setup of fault reporting, you can also specify what repairs or resolutions are associated with a fault or defect. You set that up on the **Fault/Resolution Code Relationships** page, where you set up combinations of codes for the service item group of the service item from which you accessed the witndow and the number of occurrences for each one.-->

### To register fault/resolution codes  
<!--this needs to go in a working with topic-->
After repairing a service item, you can register both the fault code and the resolution code for the item by selecting a combination from the existing fault/resolution codes relationships.
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Tasks**, and then choose the related link.  
2. Choose the line that includes the relevant service item, and then choose the **Item Worksheet** action.  
3. On the **Service Item Worksheet** page, choose **Fault/Resol. Codes Relationships**. The **Fault/Resolution Codes Relationships** window opens.  
  
    Filters are set on the relationships that are shown in the window by copying the service item group and the fault codes from the **Service Item Worksheet** window.  
  
4.  Fill out the line. Choose the combination of fault and resolution codes, and then choose the **OK** button to copy it to the service item. If an appropriate combination cannot be found, you can create a new combination in the window.  
  
 The selected fault and resolution codes now appear in the corresponding fields in the **Service Item Worksheet** window. You can also register the codes directly in this window. 

### To insert Fault and Resolution Code Relationships
<!--this needs to go in a working with topic-->
To be able to see the most common methods of repair for particular item faults when you are servicing the items, you need to build up information on fault/resolution codes relationships. Use the **Insert Fault/Resol. Codes Relationships** batch job to find all the combination of fault and resolution codes in posted service orders and record them on the **Fault/Resol. Codes Relationships** page. 
  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Insert Fault/Resol. Codes Relationships**, and then choose the related link.  
2. Enter dates to define the period you want to include in the batch job.  
3. To group the relationships by service item group, choose the **Relation Based on Service Item Group** check box.  
4. To retain the records that you have already inserted manually in the **Fault/Resol. Codes Relationships** page, choose the **Retain Manually Inserted Rec.** check box.  

## Setting Up Troubleshooting for Service Items
You can set up troubleshooting guidelines that help technicians solve problems when providing service. For example, guidelines might be a list of steps to perform a repair, or a series of questions to ask about the items. After you set up troubleshooting guidelines, you can assign them to service item groups, service items, and items. There is an inheritance hierarchy for guidelines. If you assign them to a service item group, the items included in the group will inherit the guidelines unless you specify them for the items. Similarly, service items will inherit guidelines from items.  

### To set up troubleshooting guidelines
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Troubleshooting**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

### To assign troubleshooting guidelines to items, service items, or service item groups
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, **Service Items**, or **Service Item Groups**, and then choose the related link.  
2. Choose the relevant entity, and then choose the **Troubleshooting** action.  

## How to: Set Up Skills and Zones for Resource Allocation
If you want to use allocation of resources to service items, then you can allocate resources to service the service items in question depending on their skill or depending on their availablilty in the same service zone as the customer. To enable resource allocation, you must set up:  
  
* The skills that are required to repair and maintain service items. You assign these to service items and resources.  
* The geographic regions, called zones, that you define for your market. For example, East, West, Central, and so on. You assign these to customers and resources.  
* Whether to display resource skills and zones, and whether to display a warning if someone chooses unqualified resource, or a resource that is not in the customer zone.  

### To set up skills
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Skills**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

### To assign skills to service items and resources
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Items** or **Resources**, and then choose the related link.  
2. Open the card for the service item or resource, and then choose one of the following:  
  
    * For service items, choose **Resource Skills**.  
    * For resources, choose **Skills**.  

### To specify what to show when a resource is chosen
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Setup**, and then choose the related link.  
2. In the **Resource Skills Option** field, choose one of the options described in the following table.  
  
    |**Option**|**Description**|  
    |------------|-------------|  
    |Code Shown | Displays the code only.|  
    |Warning Displayed | Shows the information and displays a warning if you choose a resource that is not qualified.|  
    |Not Used | Does not show this information.|  

### To set up zones
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Zones**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

### To assign zones to customers and resources 
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers** or **Resources**, and then choose the related link.  
2. Open the card for the service item or resource, and then choose one of the following:  
  
    * For customers, choose a zone in the **Service Zone Code** field.  
    * For resources, choose the **Service Zones** action.  

### To specify what to show when a resource is chosen 
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Setup**, and then choose the related link.  
2. In the **Falut Reporting Level** field, choose one of the options described in the following table.  
  
    |**Option**|**Description**|  
    |------------|-------------|  
    |Code Shown | Displays the code only.|  
    |Warning Displayed | Shows the information and displays a warning if you choose a resource that is not located in the customer zone.|  
    |Not Used | Does not show this information.|  
    
## How to: Set Up Service Costs
You can specify cost codes that specify set prices for specific services, such as travel costs to particular service zones.

### To set up service costs
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Costs**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]



## See Also  
[Service Management](service-service.md)