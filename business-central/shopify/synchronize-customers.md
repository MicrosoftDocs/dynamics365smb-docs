---
title: Synchronize customers
description: Import customers from or export to Shopify 
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
manager: 
---

# Synchronize customers
When importing order from Shopify, the information about customer is essential for further processing of document in [!INCLUDE[prod_short](../includes/prod_short.md)]. Hence you have two main  options and their combinations:
* Use special customer for all orders.
* Import customers from Shopify.

## How system chooses which customer to use
When import order from Shopify system tries to select customer to use and it does it in following order:
1. If **Fixed Customer No.** is defined in the **Customer Template** for corresponding country, then **Fixed Customer No.** will be used, regardless of settings in **Customer Import From Shopify** and **Customer Mapping Type**.
2. If **Customer Import From Shopify** and **Default Customer No.** is defined, then **Default Customer No.** is used.
3. Next steps depend on **Customer Mapping Type**. 
- **Always take the default customer**, then use customer defined in the **Default Customer No.** field in **Shopify Shop Card** window.
- **By EMail/Phone**, first system tries to find existing customer by Id, then by email, then by phone. If not found - system creates new customer.
- **By Bill-to Info**, first system tries to find existing customer by Id, then by bill-to address information. If not found - system creates new customer.

> [!NOTE]
> System uses information from bill-to address and creates Bill-To Customer in [!INCLUDE[prod_short](../includes/prod_short.md)]. Sell-to Customer is equal to Bill-to Customer.

## Important setting when importing customers from Shopify
Either you import customers from Shopify in bulk or together with import of orders, following settings let you manage the process:

|Field|Description|
|------|-----------|
|**Customer Import from Shopify**|Select **All Customers** if you plan import customers from Shopify in bulk either manually using **Sync Customers** action or via job queue for recurring updates. Regardless of selection customer information will be always imported together with order, however will this information be used depends on **Customer Templates** and setting in the **Customer Mapping Type** field.|
|**Customer Mapping Type**|Define how you want system to perform mapping.<br>- **By Email/Phone** if you want to system to map imported Shopify customer to existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)] using email and phone.</br>- **By BillTo Info** if you want to system to map imported Shopify customer to existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)] using address information of party that receives invoice.</br>Select **Always Take the Default customer** if you want system to use customer from the **Default Customer** field. |
|**Shopify Can Update Customers**| Select if you want system to update customers founded, when  **By Email/Phone** or **By BillTo Info** options are selected in the **Customer Mapping Type** field.| 
|**Auto Create Unknown Customers**| Select if you want system to create missing customers, when  **By Email/Phone** or **By BillTo Info** options are selected in the **Customer Mapping Type** field. New customer will be created using imported data and **Customer Template Code** defined on **Shopify Shop Card** or **Shopify Customer Template** pages. Notice that Shopify customer must have at least one address.</br>If this option is disabled you will need to create Customer manually and link it to the Shopify customer. You can always trigger creation of customer manually from the **Shopify Order** page.|
|**Customer Template Code**|Used together with **Auto create unknown customers**.<br> Choose default template to be used for automatically created customers. You can define templates per country/region in the **Customer Templates** window, which is useful for proper tax calculation of taxes. For more information, see [Tax remarks](synchronize-orders.md#tax-remarks).|

### Customer template per country

Some settings can be defined per county/region level, or even state/province configured in [Shipping and Delivery](https://www.shopify.com/admin/settings/shipping) in Shopify. 

**Customer Template** allows you for each country:
1. Specify **Fixed Customer No.**, which takes priority over selection in the **Customer Import from Shopify** and **Customer Mapping Type** fields and used in the imported sales order.
2. Define **Customer Template Code**, which will be used to create missing customers, if **Auto Create Unknown Customers** is enabled. If **Customer Template Code** is empty, then system will use **Customer Template Code** defined on the **Shopify Shop Card**. 
3. In some cases **Customer Template Code** per country isn't enough to ensure right calculation of taxes, for example for countries with sales tax per provice/county. 

> [!NOTE]
> The country codes are ISO 3166-1 alpha-2 country codes. For more information: <https://help.shopify.com/en/api/custom-storefronts/storefront-api/reference/enum/countrycode>


## Exporting customers to Shopify
You can export existing customers to Shopify in bulk. As result customer and one default address will be created. Following settings let you manage the process:

|Field|Description|
|------|-----------|
|**Export customer to Shopify**|Select if you plan to export all customers with a valid e-mail address or phone from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify in bulk either manually using **Sync Customers** action or via job queue for recurring updates.|
|**Can update Shopify Customers**|Used together with **Export customer to Shopify**. Enable if want propagate later updates from [!INCLUDE[prod_short](../includes/prod_short.md)] for customers that already exist in Shopify.|

> [!NOTE]
> Once you created customers in Shopify, you may want to send customers direct invitations to encourage them to activate an account.

### Populate Customer information in Shopify
Customer in Shopify has First Name, Last Name, Email, and or Phone number.
You can populate First Name and Last Name based on data from Customer Card in [!INCLUDE[prod_short](../includes/prod_short.md)]. 

|Priority|Field in Customer Card|Description|
|------|------|-----------|
|1|**Contact Name**|Highest priority. If the **Contact Name** field is filled in and the **Contact Source** field in the **Shopify Shop Card** contains *First Name and Last Name* or *Last Name and First Name* options, defining how to split the values.|
|2|**Name 2**|If the **Name 2** field is filled in and the **Name 2 Source** field in the **Shopify Shop Card** contains *First Name and Last Name* or *Last Name and First Name* options, defining how to split the values.|
|3|**Name**|Lowest priority. If the **Name** field is filled in and the **Name Source** field in the **Shopify Shop Card** contains *First Name and Last Name* or *Last Name and First Name* options, defining how to split the values.|

Customer is Shopify also has default address, which in addition to First Name, Last Name, email and/or phone may contain Company and address.

You can populate Company field based on data from Customer Card in [!INCLUDE[prod_short](../includes/prod_short.md)]. 

|Priority|Field in Customer Card|Description|
|------|------|-----------|
|1|**Name**|Highest priority. If the **Name Source** field in the **Shopify Shop Card** contains *Company Name*.|
|2|**Name 2**|Lowest priority. If the **Name 2 Source** field in the **Shopify Shop Card** contains *Company Name*.|

For addresses where county/province is used, select *Code* or *Name* in the **County Source** field in the **Shopify Shop Card** to specify what type of data is stored in [!INCLUDE[prod_short](../includes/prod_short.md)] in the **County** field.


## Synchronize customers

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to synchronize items to open **Shopify Shop Card** page.
3. Choose the **Sync Customers** action. 

Alternatively you can use the **Start Customer Sync** action on the **Shopify Customers** window or search for **Sync Customers** batch job.
