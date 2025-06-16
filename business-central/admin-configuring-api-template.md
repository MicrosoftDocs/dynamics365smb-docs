---
title: Configure API Templates
description: Describing the steps you must go through to configure API templates for Dynamics 365 Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: API templates, configuring templates
ms.search.form: 5469
ms.date: 06/07/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Configure API Templates

The API library for [!INCLUDE[prod_short_md](includes/prod_short.md)] provides a simplified representation of the underlying entities. All the properties in the application are not exposed through the associated API. The **API Setup** page allows you to define templates that are used to populate empty properties on an entity when you create a POST action through the API. 

For example, if a configuration template is defined for the item entity, when a new item record is created through the items API, any properties for the new item that are not defined in the API call will be populated from the selected template. If, for example, no value is defined for the **Gen. Prod. Posting Group** field through the API, but a value is defined in the selected template, then the posting group value defined in the template will be applied to the new item. 

## Setting up the Entity Template

To use templates with the API library, you must first set up and define properties for the templates. You can set up these templates on the **Configuration Templates** page. For more information, see [Migrate On-Premises Data to Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) (in English only) in the administration content.  

## Assign the template to an API

To assign a template to an API, you must go through the following steps.

> [!NOTE]  
> API templates can only be set up with the following API pages: contacts, countriesRegions, currencies, customers, employees, itemCategories, paymentMethods, paymentTerms, shipmentMethods, unitsOfMeasure, and vendors.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **API Setup**, and choose the related link.
2. Choose **New**, and then choose the **Order** value for the record.  

    If there is more than one template selected for an API (Page ID), the templates are applied in the order defined in the **Order** column.  

    When each template is applied, field values defined in the template are only applied to fields that have not already had a value defined, either explicitly in the API, or in a previously applied template in the order.  
3. Select a **Page ID** value.  

    This is the page for the API to which the template will be applied. The **Page ID** lookup provides a list of all APIs available in the library.
4. Select a value in the **Template Code** field.  

    The template code is the code for the template that was defined on the **Configuration Templates** page. The template values defined are applied to the API.  
5. In the **Conditions** field, specify which template should be applied.  

    The defined template is applied to a new record created through the API if, and only if, the conditions defined in the **Conditions** field are met by the values already defined for the new instance of the entity.

## Related information

[API Documentation](/dynamics-nav/fin-graph)  
[Develop Connect Apps for [!INCLUDE[prod_short_md](includes/prod_short.md)]](/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps)  
[Enabling the APIs](/dynamics-nav/enabling-apis-for-dynamics-nav)  
[Endpoints for the APIs](/dynamics-nav/endpoints-apis-for-dynamics)  
[Administration](admin-setup-and-administration.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
