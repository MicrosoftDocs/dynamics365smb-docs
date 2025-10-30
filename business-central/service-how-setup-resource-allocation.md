---
title: Set up resource allocation | Microsoft Docs
description: Learn how the system can help ensure that you assign someone who has the skills required to provide a service.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: resource, skill, service, zones
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up resource allocation

To ensure that a service task is performed well, it's important to find a resource who is qualified to do the work. You can set up [!INCLUDE[prod_short](includes/prod_short.md)] so that it's easy to allocate someone who has the right skills for the job. In [!INCLUDE[prod_short](includes/prod_short.md)], we call this _resource allocation_. You can allocate resources based on their skill, availability, or whether they are in the same service zone as the customer. 

To use resource allocation, you must set up:  
  
* The skills required to repair and maintain service items. You assign these to service items and resources.  
* Geographic regions, called zones, that you define for your market. For example, East, West, Central, and so on. You assign these to customers and resources.  
* Whether to display resource skills and zones, and whether to display a warning if someone chooses unqualified resource, or a resource that isn't in the customer zone.  

## Set up skills

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Skills**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## Assign skills to service items and resources

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Items** or **Resources**, and then choose the related link.  
2. Open the card for the service item or resource, and then choose one of the following:  
  
    * For service items, choose **Resource Skills**.  
    * For resources, choose **Skills**.  

## Set up zones

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Zones**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## Assign zones to customers and resources

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customers** or **Resources**, and then choose the related link.  
2. Open the card for the service item or resource, and then choose one of the following:  
  
    * For customers, choose a zone in the **Service Zone Code** field.  
    * For resources, choose the **Service Zones** action.  

## Specify what to show when a resource is chosen

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Management Setup**, and then choose the related link. 
2. In the **Resource Skills Option** field, choose one of the options described in the following table.  
  
    |**Option**|**Description**|  
    |------------|-------------|  
    |Code Shown | Displays the code only.|  
    |Warning Displayed | Shows the information and displays a warning if you choose a resource that isn't qualified.|  
    |Not Used | Doesn't show this information.|  

## Update resource capacity

You may need to change the capacity of resources.  
  
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Resource Capacity**, and then choose the related link.  
2. Choose the resource, and then choose the **Set Capacity** action.  
3. Make the changes, and then choose **Update Capacity**.  

## Update skills for items, service items, or service item groups

If you want to change the skill codes assigned to items, for example from **PC** to **PCS**, you can do so either for an item, service item, or for all items in a service item group.  
  
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items** or **Service Item**, or **Service Item Group**, and then choose the related link.  
2. Choose the entity to update, and then choose the **Resource Skills** action.  
3. On the line with the code to be changed, in the **Skill Code** field, choose the relevant skill code.  
4. If the item has associated service items, a dialog box opens with the following two options:  
  
    * Change the skill codes to the selected value: Select this option if you want to replace the old skill code with the new one on all the related service items.  
    * Delete the skill codes or update their relation: Select this option if you want to change the skill code on this item only. The skill code on the related service items will be reassigned, that is, the **Assigned From** field will be updated.  
  
## Related information

[Allocate Resources](service-how-to-allocate-resources.md)  
[Set Up Work Hours and Service Hours](service-how-setup-work-service-hours.md)  
[Set Up Fault Reporting](service-how-setup-fault-reporting.md)  
[Set Up Codes for Standard Services](service-how-setup-service-coding.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
