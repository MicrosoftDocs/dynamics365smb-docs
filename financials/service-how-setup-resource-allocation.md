---
    title: Set Up Resource Allocation | Microsoft Docs
    description: Learn how the system can help ensure that you assign someone who has the skills required to provide a service.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: resource, skill, service
    ms.date: 08/22/2017
    ms.author: sgroespe

---

# How to: Set Up Resource Allocation
If you want to use allocation of resources to service items, then you can allocate resources to service the service items in question depending on their skill or depending on their availablilty in the same service zone as the customer. To enable resource allocation, you must set up:  
  
* The skills that are required to repair and maintain service items. You assign these to service items and resources.  
* The geographic regions, called zones, that you define for your market. For example, East, West, Central, and so on. You assign these to customers and resources.  
* Whether to display resource skills and zones, and whether to display a warning if someone chooses unqualified resource, or a resource that is not in the customer zone.  

## To set up skills
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Skills**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## To assign skills to service items and resources
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Items** or **Resources**, and then choose the related link.  
2. Open the card for the service item or resource, and then choose one of the following:  
  
    * For service items, choose **Resource Skills**.  
    * For resources, choose **Skills**.  

## To specify what to show when a resource is chosen
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Setup**, and then choose the related link. 2. In the **Resource Skills Option** field, choose one of the options described in the following table.  
  
    |**Option**|**Description**|  
    |------------|-------------|  
    |Code Shown | Displays the code only.|  
    |Warning Displayed | Shows the information and displays a warning if you choose a resource that is not qualified.|  
    |Not Used | Does not show this information.|  

## To set up zones
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Zones**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## To assign zones to customers and resources 
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers** or **Resources**, and then choose the related link.  
2. Open the card for the service item or resource, and then choose one of the following:  
  
    * For customers, choose a zone in the **Service Zone Code** field.  
    * For resources, choose the **Service Zones** action.  

## To specify what to show when a resource is chosen 
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Setup**, and then choose the related link. 2. In the **Falut Reporting Level** field, choose one of the options described in the following table.  
  
    |**Option**|**Description**|  
    |------------|-------------|  
    |Code Shown | Displays the code only.|  
    |Warning Displayed | Shows the information and displays a warning if you choose a resource that is not located in the customer zone.|  
    |Not Used | Does not show this information.|  

## See Also
[How to: Set Up Fault Reporting](service-how-setup-fault-reporting.md)  
[How to: Set Up Resource Allocation](service-how-setup-resource-allocation.md)  
[How to: Set Up Codes for Standard Services](service-how-setup-service-coding.md)  
[How to: Set Up Additional Costs for Services](service-how-setup-service-costs.md)  
[How to: Set Up Troubleshooting](service-how-setup-troubleshooting.md)  
