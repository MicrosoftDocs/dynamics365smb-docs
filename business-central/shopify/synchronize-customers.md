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

When an order is imported from Shopify, the information about customer is essential for further processing the document in [!INCLUDE[prod_short](../includes/prod_short.md)]. There are two main options and their combinations:

* Use special customer for all orders.
* Import actual customer information from Shopify. This option is also available when you export customer to Shopify from [!INCLUDE[prod_short](../includes/prod_short.md)] first.

## How system chooses which customer to use

Import order from Shopify system tries to select customer in the following order:

1. If **Default Customer No.** is defined in the **Shopify Customer Template** for corresponding country, then **Default Customer No.** is used, regardless of settings in **Customer Import From Shopify** and **Customer Mapping Type**.
2. If **Customer Import From Shopify** and **Default Customer No.** is defined, then the **Default Customer No.** is used.

Next steps depend on **Customer Mapping Type**.

* **Always take the default customer**, then use customer defined in the **Default Customer No.** field in **Shopify Shop Card** window.
* **By EMail/Phone**, system tries to find existing customer by ID first, then by email, and then by phone. If customer isn't found - system creates a new customer.
* **By Bill-to Info**, system tries to find existing customer by ID first and then by bill-to address information. If not found - system creates a new customer.

> [!NOTE]
> System uses information from bill-to address and creates Bill-To customer in [!INCLUDE[prod_short](../includes/prod_short.md)]. Sell-to customer is equal to Bill-to customer.

## Important setting when importing customers from Shopify

Either you import customers from Shopify in bulk or together with import of orders, following settings let you manage the process:

|Field|Description|
|------|-----------|
|**Customer Import from Shopify**|Select **All Customers** if you plan to import customers from Shopify in bulk; either manually using **Sync Customers** action or via job queue for recurring updates. Regardless of selection, customer information will always be imported together with order. However, the use of this information depends on **Shopify Customer Templates** and settings in the **Customer Mapping Type** field.|
|**Customer Mapping Type**|Define how you want system to perform mapping.<br>- **By Email/Phone** if you want system to map imported Shopify customer to existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)] using email and phone.</br>- **By BillTo Info** if you want system to map imported Shopify customer to existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)] using address information of party that receives invoice.</br>Select **Always Take the Default customer** if you want system to use customer from the **Default Customer No.** field. |
|**Shopify Can Update Customers**| Select if you want system to update customers founded, when  **By Email/Phone** or **By Bill-To Info** options are selected in the **Customer Mapping Type** field.| 
|**Auto Create Unknown Customers**| Select if you want system to create missing customers, when  **By Email/Phone** or **By BillTo Info** options are selected in the **Customer Mapping Type** field. New customer will be created using imported data and **Customer Template Code** defined on **Shopify Shop Card** or **Shopify Customer Template** pages. Notice that Shopify customer must have at least one address. If this option isn't enabled, you'll need to create Customer manually and link it to the Shopify customer. You can always trigger creation of customer manually from the **Shopify Order** page.|
|**Customer Template Code**|Used together with **Auto Create Unknown Customers**.<br> Choose default template to be used for automatically created customers. You can define templates per country/region in the **Shopify Customer Templates** window, which is useful for proper tax calculation. For more information, see [Tax remarks](synchronize-orders.md#tax-remarks).|

### Customer template per country

Some settings can be defined at country/regional level, or at state/province level. The settings can be configured in [Shipping and Delivery](https://www.shopify.com/admin/settings/shipping) at Shopify.

**Shopify Customer Template** lets you do following for each country:

1. Specify **Default Customer No.**, which takes priority over selection in the **Customer Import from Shopify** and **Customer Mapping Type** fields. It's used in the imported sales order.
2. Define **Customer Template Code**, which is used to create missing customers, if **Auto Create Unknown Customers** is enabled. If **Customer Template Code** is empty, then system uses **Customer Template Code** defined on the **Shopify Shop Card**.
3. In some cases, **Customer Template Code** per country isn't enough to ensure right calculation of taxes. For example, for countries with sales tax.

> [!NOTE]
> The country codes are ISO 3166-1 alpha-2 country codes. For more information: <https://help.shopify.com/en/api/custom-storefronts/storefront-api/reference/enum/countrycode>

## Export customers to Shopify

Existing customers can be exported to Shopify in bulk. As a result, a customer and one default address is created. You can manage the process with the help of following settings:

|Field|Description|
|------|-----------|
|**Export customers to Shopify**|Select if you plan to export all customers with a valid e-mail address from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify in bulk; either manually, using **Sync Customers** action or via job queue for recurring updates.|
|**Can update Shopify Customers**|Used together with **Export customer to Shopify**. Enable it, if you want to propagate updates later from [!INCLUDE[prod_short](../includes/prod_short.md)] for customers that already exist in Shopify.|

> [!NOTE]
> Once you have created customers in Shopify, you might like to send direct invitations to customers. It will encourage them to activate their account.

### Populate customer information in Shopify

Customer in Shopify has first name, last name, email, and/or phone number.
You can populate first name and last name based on the data from customer card in [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priority|Field in Customer card|Description|
|------|------|-----------|
|1|**Contact Name**|Highest priority. If the **Contact Name** field is filled in and the **Contact Source** field in the **Shopify Shop Card** contains *First Name and Last Name* or *Last Name and First Name* options, defining how to split the values.|
|2|**Name 2**|If the **Name 2** field is filled in and the **Name 2 Source** field in the **Shopify Shop Card** contains *First Name and Last Name* or *Last Name and First Name* options, defining how to split the values.|
|3|**Name**|Lowest priority. If the **Name** field is filled in and the **Name Source** field in the **Shopify Shop Card** contains *First Name and Last Name* or *Last Name and First Name* options, defining how to split the values.|

Customer in Shopify also has default address, which in addition to first name, last name, email and/or phone may contain company and address.

You can populate Company field based on data from Customer Card in [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priority|Field in Customer card|Description|
|------|------|-----------|
|1|**Name**|Highest priority. If the **Name Source** field in the **Shopify Shop Card** contains *Company Name*.|
|2|**Name 2**|Lowest priority. If the **Name 2 Source** field in the **Shopify Shop Card** contains *Company Name*.|

For addresses where country/province is used, select *Code* or *Name* in the **Country Source** field in the **Shopify Shop Card** to specify what type of data is stored in [!INCLUDE[prod_short](../includes/prod_short.md)] in the **Country** field.

## Sync customers

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the Shop for which you want to synchronize customers to open **Shopify Shop Card** page.
3. Choose the **Sync Customers** action.

Alternatively, you can use the **Start Customer Sync** action on the **Shopify Customers** window or search for **Sync Customers** batch job.
