---
    title: How to Set Up Service Price Groups | Microsoft Docs
    description: You can use the **Service Price Groups** window to set up groups containing service items that you want to receive the same special service pricing. You assign service price groups to service items on service item lines. You can also assign service price groups to service item groups.
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
# How to: Set Up Service Price Groups
You can use the **Service Price Groups** window to set up groups containing service items that you want to receive the same special service pricing. You assign service price groups to service items on service item lines. You can also assign service price groups to service item groups.  
  
### To set up a service price group  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Price Groups**, and then choose the related link.  
  
2.  Create a new service price group. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Fill in the **Code** and **Description** fields.  
  
4.  On the **Actions** tab, in the **General** group, choose **Setup**. The **Service Price Group Setup** window opens.  
  
5.  Fill in the **Fault Area Code** field if you want to setup a service price group that includes service lines with a specific fault area code.  
  
6.  Fill in the **Cust. Price Group Code** field if you want to setup a service price group that includes service lines belonging to a specific customer.  
  
7.  Fill in the **Currency Code** field if you want to setup a service price group that includes service lines with a specific currency.  
  
8.  Fill in the **Starting Date** field if you want to setup a service price group that includes service lines that have a specific starting date.  
  
9. Fill in the **Serv. Price Adjmt. Gr. Code** field if you want to setup a service price group that includes service lines that belong to a specific service price adjustment group.  
  
10. Select the **Include Discounts** and **Include VAT** fields if you want to setup a service price group that includes service lines that include discounts or VAT.  
  
11. Fill in the **Amount** field if you want to setup a service price group that adjusts service prices to a specific amount.  
  
12. In combination with the **Amount** field, you can set up whether this adjustment concerns a fixed amount, or only applies when the total service price exceeds or is lower than the amount in the **Amount** field.  
  
 Repeat these steps for each of the service price groups you want to create.  
  
## See Also  
 [How to: Create Service Price Adjustments](../how-to-create-service-price-adjustments.md)   
 [How to: Set Up Service Price Adjustment Groups](../how-to-set-up-service-price-adjustment-groups.md)   
 [Service Price Management](../service-price-management.md)