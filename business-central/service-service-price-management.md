---
    title: Service Price Management | Microsoft Docs
    description: This topic describes how to apply the best price to service orders, set up personalized service price agreements for customers, improve service employees' efficiency, and accelerate the invoicing process.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Service Price Management
The service price management functionality lets you apply the best price to service orders, set up personalized service price agreements for customers, improve service employees' efficiency, and accelerate the invoicing process.  
  
Service price management lets you set up different service price groups so you can consider the service item or service item group, in addition to the type of fault that the service task involves. You can set up these groups for a limited period of time, or for a specific customer or currency. You can use price calculation structures as templates to assign a specific price to a specific service task.  
  
For example, this makes it possible to assign specific items included in the service price, in addition to the type of work included. This also makes it possible to use different VAT and discount amounts for different service price groups. To make sure that the correct prices are applied, you can assign fixed, minimum, or maximum prices, depending on the agreements that you have with your customers.  
  
Before adjusting the price of a service item on a service order, you are provided with an overview of what the results of the price adjustment will be. You can approve of these results, or you can make additional changes, if you want to have a different result. The whole adjustment is performed line by line, which means that there are no additional lines created.  
  
Finally, service price group statistics and standard reports let you keep track of the profitability of each service price group.  
  
## Service Price Adjustment Groups  
You use service price adjustment groups to set up the different types of price adjustments. For example, you can set up a service price adjustment group that adjusts prices for spare parts, one that adjust prices for labor, one that adjusts prices for costs, and so on. You can also specify whether the service price adjustment should be applied to just one specific item or resource, or to all items or resources.  
  
Each service price adjustment group holds the information about the adjustments that you want to make on the service lines.  
  
The service price adjustment function does not apply to service items that belong to service contracts. You can only adjust the service prices of items that are part of a service order. You cannot adjust the price of a service item if it has a warranty. You cannot adjust the price of a service item on a service order if the service line linked to it has been posted as invoice, either fully or in part.  
  
When you run the service price adjustment function, all of the discounts in the order will be replaced by the values of the service price adjustment.  
  
## Service Price Groups  
You can set up service price groups to create groups of service items that receive the same special service pricing. When you have set up service price groups, you can then assign them to service items on service item lines. You can also assign service price groups to service item groups.  
  
Before you can assign a service price group to a service item, you have to determine to which fault area, currency, or service price adjustment group the service price group applies. You have to determine to which amount the service price should be adjusted, and whether this amount should include VAT and discounts. You also have to determine whether this adjustment concerns a fixed amount, or should only be applied under certain conditions.  
  
When you assign a service price group to a service item, all the special service pricing that you set up in this group will then apply for this service item.  
  
## Service Pricing  
You set up the actual types of service pricing (price adjustment type and price) for a combination of service price groups and customer price groups. For each type of service pricing, you select a service price adjustment group. You also specify the service price adjustment type, fixed, maximum, or minimum, and the actual price.  
  
For example, you can set up types of service pricing for a radio service price group. For customers without a price group, you can decide to have service pricing with maximum price on labor, which is the labor price adjustment group. For customers with a particular price group, you can decide to have service pricing with a fixed price on labor, the same labor price adjustment group.  
  
## Service Price Adjustment  
Service price adjustment lets you adjust the price of an item, resource, general ledger account, or cost on a service order.  
  
After you have entered an item on the service item line, you then enter all information about the costs of this item on the service lines. When you run the Adjust Service Price function, you can preview the price adjustments. You can make modifications if you have to. When you acknowledge the modifications, the adjustments are calculated, and are then transferred to the service lines. You then post the service order.  
  
Depending on the type of service price adjustment, the total amount of the adjustments is calculated.  
  
The following table describes the calculations.  
  
|Option | Description |  
|----------------------------------|---------------------------------------|  
|**Fixed Price**|This means that you charge a fixed price for the service item, resource, general ledger account, or cost, regardless of the real costs or regular charges. Selecting this option means that the service price adjustment will reach the exact amount specified in the service price group.|  
|**Maximum**|This means that you put an upper limit on the charge to your customer, regardless of the real costs or regular charges. Selecting this option means that the service price adjustment will only be performed if the total price exceeds the amount specified in the service price group.|  
|**Minimum**|This means that you put a lower limit on the charge to your customer, regardless of the real costs or regular charges. Selecting this option means that the service price adjustment will only be performed if the total amount is less than the amount specified on the service price group.|  
  
## See Also  
[Set Up Pricing and Additional Costs for Services](service-how-setup-service-costs-pricing.md)  
[Setting Up Service Management](service-setup-service.md)  
