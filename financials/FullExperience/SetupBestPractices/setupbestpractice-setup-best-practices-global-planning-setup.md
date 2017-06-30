---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# Setup Best Practices: Global Planning Setup
The **Planning** FastTab in the **Manufacturing Setup** window contains several fields that define global rules for supply planning.  
  
 The following table provides best practices on how to set up selected global planning parameter fields. For more information about a field, choose the link in the **Setup field** column.  
  
|Setup field|Best practice|Comment|  
|-----------------|-------------------|-------------|  
|Use Forecast on Locations|Select if you have forecasts for specific locations.||  
|Components at Location|If items are not defined as SKUs, select the location code of your main warehouse.|This also applies if you only use the requisition worksheet.|  
|Blank Overflow Level|Select **Allow Default Calculation** if the solution has just been upgraded from a version earlier than ADD INCLUDE<!--[!INCLUDE[nav_5](../../includes/nav_5_md.md)]--> SP1.|Use only if you want to allow all or some of your items to overflow the reorder point.|  
|Default Dampener Period|Set between 1D and 5D.<br /><br /> If new to planning in [!INCLUDE[d365fin](../../includes/d365fin_md.md)], then set a longer period.|When users are more familiar with the different reasons for action messages, then shorten the dampener period to allow more change suggestions.|  
|Default Dampener Quantity|Set between 5 and 20 percent of the item’s lot size.||  
  
## See Also  
 [Setup Best Practices: Supply Planning](../setup-best-practices-supply-planning.md)   
 Manufacturing Setup   
 [Design Details: Supply Planning](design-details-supply-planning.md)   
 [Set Up a Company With RapidStart Services for Microsoft Dynamics NAV](../set-up-a-company-with-rapidstart-services-for-microsoft-dynamics-nav.md)