---
title: 
description: 
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
manager: 
---

# Synchronize customers

When importing order from Shopify, the information about customer is essential for further processing of document in [!INCLUDEprod_short]. Hence you have two main  options and their combinations:
* Use special customer for all orders.
* Import customers from Shopify.
Regardless of your settings, when importe

## How system chooses which customer to use
When import order from Shopify system tries to select customer to use and it does it in following order:
1. If **Fixed Customer No.** is defined in the **Customer Template** for corresponding country, then **Fixed Customer No.** will be used, regardless of settings in **Customer Import From Shopify** and **Customer Mapping Type**.
2. If **Customer Import From Shopify** and **Default Customer No.** is defined, then **Default Customer No.** is used.
3. Next steps depends on **Customer Mapping Type**. 
- **Always take the default customer**, then use customer defined in the **Default Customer No.** field in **Shopify Shop Card** window.
- **By EMail/Phone**, first system tries to find existing customer by Id, then by email, then by phone. 
- **By Bill-to Info**, first system tries to find existing customer by Id, then by bill-to addresse information.

## Important setting when importing customers from Shopify
Either you import customers from Shopify in bulk or together with import of orders, following settings let you manage the process:
|Field|Description|
|------|-----------|
|**Customer Import from Shopify**|Select **All Customers** if you plan import customers from Shopify in bulk either manually using **Sync Customers** action or via job queue for reccuring updates. Regardless of selection customer information will be always imported together with order, but wether this infomation will be used depends on **Customer Templates** and setting in the **Customer Mapping Type** field.|
|**Customer Mapping Type**|Define who you want system to perform mapping.<br>- **By Email/Phone** if you want to system to map imported Shopify customer to existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)] using email and phone.</br>- **By BillTo Info** if you want to system to map imported Shopify customer to existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)] using address information of party that receives invoice.</br>Select **Always Take the Default customer** if you want system to use customer from the **Default Customer** field. |
|**Shopify Can Update Customers**| Select if you want system to update customers founded, when  **By Email/Phone** or **By BillTo Info** options are selected in the **Customer Mapping Type** field.| 
|**Auto Create Unknown Customers**| Select if you want system to create missing customers, when  **By Email/Phone** or **By BillTo Info** options are selected in the **Customer Mapping Type** field. New customer will be created using imported data and **Customer Template Code** defined on **Shopify Shop Card** or **Shopify Customer Template** pages. If this option is disabled you will need to create Item manually and use **Map Product** action from **Shopify Products** page. You can always create customer manually from the **Shopify Order** page.|
|**Customer Template Code**|Used together with **Auto create unknown customers**.<br> Choose default template to be used for automatically created customers. You can define templates per country/region in the **Customer Templates** window, which might be particularly useful for proper tax calculation of taxes.|







# WIP


- **Export customer to Shopify  
 **With this option, you can export all customers with a valid e-mail address from Microsoft Dynamics 365 Business Central to Shopify.

- **Can update Shopify Customers  
 **Define if Microsoft Dynamics 365 for Business Central can only create customers or also update customers.

- **Name Source**  
    Define how you want to sync the name of the customer

    -   Company name

    -   First name and last name

    -   Last name and first name

    -   Not

- **Name 2 Source**  
    Define how you want to sync name 2 of the customer

    -   Company name

    -   First name and last name

    -   Last name and first name

    -   Not

- **Contact Source**  
    Define how you want to sync the contact of the customer

    -   First name and last name

    -   Last name and first name

    -   Not

- **County Source**  
    Define how you want to sync the county

    -   Code

    -   Name


# Customer template per country

Some settings can be defined per county/region level, or even state/province configured in [Shipping and Delivery](https://www.shopify.com/admin/settings/shipping) in Shopify. 

**Customer Template** allows you for each country:
1. Specify **Fixed Customer No.**, which takes priority over election in the  in the **Customer Import from Shopify** and **Customer Mapping Type** fields and used in the imported sales order.
2. Define **Customer Template Code**, which will be used to create missing customers, if **Auto Create Unknown Customers** is enabled. If **Customer Template Code** is empty, then system will use **Customer Template Code** defined on the **Shopify Shop Card**. 
3. In some cases **Customer Template Code** per country isn't enough to ensure right calcualtion of taxes. This is particularty true for countries with sales tax per provice/county. 





![Graphical user interface  application Description automatically generated](media/image61.png)

The country codes are ISO 3166-1 alpha-2 country codes. For more information: <https://help.shopify.com/en/api/custom-storefronts/storefront-api/reference/enum/countrycode>

When you use multiple VAT/tax percentages, NAV should be leading. Furthermore, the item should already exist in NAV. A new item is created based on the defined item template and uses the VAT/tax percentage defined in this template, not the one set in the Shopify Shop.

When a customer has a country code for which you have not defined a template, the customer has not been created. The sell-to customer in the Shopify orders stays empty. In the Shopify customer templates, the country code was added so you can define a template for this.

Remark: If you have not defined a country-specific customer template, but a general customer template in the Shopify Shop setup, the general template will be used to create the customer in Dynamics 365 Business Central.

![](media/image62.png)

![](media/image63.png)

# Synchronize customers

Remark: The customer created is the bill-to customer.

## Manually sync customers

There are two ways to go to the customer sync.

-   Via 'Customers'

![](media/image64.png)

![](media/image65.png)

-   Via the Shopify Shop Card

![](media/image66.png)

![](media/image67.png)

##  Verify customer creation

Verify that the new customer is created in Dynamics 365 Business Central.
Go to 'Customers' and verify the customer is added to the list and a customer number is linked.

![](media/image64.png)

![](media/image68.png)

![](media/image69.png)
