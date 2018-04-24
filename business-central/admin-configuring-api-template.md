---
title: "Configuring API Templates for Dynamics 365 Business Central"
description: "Describing the steps you must go through to configure the API templates for Dynamics 365 Business Central."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 04/24/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

# Configuring the API Templates
The API library for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] provides a simplified representation of the underlying entities. All the properties in the application are not exposed through the associated API. The **API Setup** page allows you to define templates that are used to populate empty properties on an entity when you create a POST action through the API. 

For example, if a configuration template is defined for the item entity, when a new item record is created through the items API, any properties for the new item that are not defined in the API call will be populated from the selected template. If, for example, no value is defined for the **Gen. Prod. Posting Group** through the API, but a value is defined in the selected template, then the posting group value defined in the template will be applied to the new item. 

## Set up the entity template
To use templates with the API library, you must first set up and define properties for the templates. You can set up these templates in the [Configuration Templates](admin-use-templates-to-prepare-customer-data-for-migration.md) page displayed below. 

![Configure template header](media/api-setup-create.png)  

## Assign the template to an API

To assign the template to an API, you must go through the following steps.

1. In [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], search for **API Setup** and select the related link.
2. Choose **New**, and then choose the **Order** value for the record.  
If there is more than one template selected for an API (Page ID), the templates are applied in the order defined in the **Order** column.   
When each template is applied, field values defined in the template are only applied to fields that have not already had a value defined, either explicitly in the API, or in a previously applied template in the order. 
3. Select a **Page ID** value.  
This is the page for the API to which the template will be applied. The **Page ID** lookup provides a list of all APIs available in the library.
4. Select a **Template Code**. The **Template Code** is the code for the template that was defined in the [Configuration Templates](admin-use-templates-to-prepare-customer-data-for-migration.md) page. The template values defined are applied to the API. 
5. Select the **Conditions** for which the template should be applied. The defined template is applied to a new record created through the API if, and only if, the conditions defined in the **Conditions** field are met by the values already defined for the new instance of the entity.

![Edit API template](media/api-setup-edit-list.png)

## See Also
[API Documentation](/dynamics-nav/fin-graph)  
[Developing Connect Apps for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]](/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps)  
[Enabling the APIs](/dynamics-nav/enabling-apis-for-dynamics-nav)  
[Endpoints for the APIs](/dynamics-nav/endpoints-apis-for-dynamics)  
[Setting Up a Company with RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)