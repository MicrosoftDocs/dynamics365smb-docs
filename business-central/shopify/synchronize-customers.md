---
title: Synchronize customers
description: Import customers from or export to Shopify 
ms.date: 05/27/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
ms.reviewer: solsen
---

# Synchronize Customers

When an order is imported from Shopify, the information about the customer is essential for further processing the document in [!INCLUDE[prod_short](../includes/prod_short.md)]. There are two main options and their combinations:

* Use a special customer for all orders.
* Import the actual customer information from Shopify. This option is also available when you export customers to Shopify from [!INCLUDE[prod_short](../includes/prod_short.md)] first.

## How the connector chooses which customer to use

The *Import order from Shopify* function tries to select the customer in the following order:

1. If the **Default Customer No.** field is defined in the **Shopify Customer Template** for the corresponding country, then the **Default Customer No.** is used, regardless of the settings in the **Customer Import From Shopify** and **Customer Mapping Type** fields. For more information, see [Customer Template per Country](synchronize-customers.md#customer-template-per-country).
2. If the **Customer Import From Shopify** is set to *None* and the **Default Customer No.** is defined in the **Shopify Shop Card**, then the **Default Customer No.** is used.

The next steps depend on the **Customer Mapping Type**.

* **Always take the default customer**, then the connector uses the customer defined in the **Default Customer No.** field in the **Shopify Shop Card** page.
* **By EMail/Phone**, the connector tries to find the existing customer by ID first, then by email, and then by phone. If the customer isn't found - the connector creates a new customer.
* **By Bill-to Info**, the connector tries to find the existing customer by ID first and then by the bill-to address information. If not found - the connector creates a new customer.

> [!NOTE]  
> The connector uses information from the bill-to address and creates the bill-to customer in [!INCLUDE[prod_short](../includes/prod_short.md)]. Sell-to customer is equal to bill-to customer.

## Important settings when importing customers from Shopify

Either you import customers from Shopify in bulk or together with the import of orders, the following settings let you manage the process:

|Field|Description|
|------|-----------|
|**Customer Import from Shopify**|Select **All Customers** if you plan to import customers from Shopify in bulk; either manually using the **Sync Customers** action or via the job queue for recurring updates. Regardless of the selection, the customer information will always be imported together with the order. However, the use of this information depends on the **Shopify Customer Templates** and settings in the **Customer Mapping Type** field.|
|**Customer Mapping Type**|Define how you want the connector to perform the mapping.<br>- **By Email/Phone** if you want the connector to map the imported Shopify customer to an existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)] using email and phone.</br>- **By Bill-to Info** if you want the connector to map the imported Shopify customer to an existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)] using the address information of the party that receives the invoice.</br>Select **Always Take the Default Customer** if you want the system to use a customer from the **Default Customer No.** field. |
|**Shopify Can Update Customers**| Select if you want the connector to update customers that are found, when **By Email/Phone** or **By Bill-to Info** options are selected in the **Customer Mapping Type** field.|
|**Auto Create Unknown Customers**| Select if you want the connector to create missing customers, when the **By Email/Phone** or **By Bill-to Info** options are selected in the **Customer Mapping Type** field. A new customer will be created using imported data and the **Customer Template Code** defined on the **Shopify Shop Card** or **Shopify Customer Template** pages. Notice that the Shopify customer must have at least one address. If this option isn't enabled, you'll need to create a Customer manually and link it to the Shopify customer. You can always initiate creation of a customer manually from the **Shopify Order** page.|
|**Customer Template Code**|Used together with **Auto Create Unknown Customers**.<br> Choose the default template to be used for automatically created customers. Make sure that the selected template contains the mandatory fields, such as the **Gen. Business Posting Group**, **Customer Posting Group**, VAT or Tax related fields.<br> You can define templates per country/region in the **Shopify Customer Templates** page, which is useful for proper tax calculation. For more information, see [Tax Remarks](synchronize-orders.md#tax-remarks).|

### Customer template per country

Some settings can be defined at the country/regional level, or at a state/province level. The settings can be configured in [Shipping and Delivery](https://www.shopify.com/admin/settings/shipping) at Shopify.

The **Shopify Customer Template** lets you do following for each country:

1. Specify the **Default Customer No.**, which takes priority over the selection in the **Customer Import from Shopify** and **Customer Mapping Type** fields. It's used in the imported sales order.
2. Define the **Customer Template Code**, which is used to create missing customers if **Auto Create Unknown Customers** is enabled. If the **Customer Template Code** is empty, then the function uses the **Customer Template Code** defined on the **Shopify Shop Card**.
3. In some cases, **Customer Template Code** defined for country isn't enough to ensure right calculation of taxes. For example, for countries with sales tax. In this case, the **Tax Areas** could be a useful addition.

> [!NOTE]  
> The country codes are ISO 3166-1 alpha-2 country codes. For more information, see [Country Code](https://help.shopify.com/en/api/custom-storefronts/storefront-api/reference/enum/countrycode).

## Export customers to Shopify

Existing customers can be exported to Shopify in bulk. As a result, a customer and one default address are created. You can manage the process with the help of following settings:

|Field|Description|
|------|-----------|
|**Export customers to Shopify**|Select if you plan to export all customers with a valid e-mail address from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify in bulk; either manually, using the **Sync Customers** action, or via a job queue for recurring updates.|
|**Can update Shopify Customers**|Used together with the **Export customer to Shopify** setting. Enable it if you want to generate updates later from [!INCLUDE[prod_short](../includes/prod_short.md)] for customers that already exist in Shopify.|

> [!NOTE]  
> Once you have created the customers in Shopify, you might like to send direct invitations to customers. It will encourage them to activate their account.

### Populate customer information in Shopify

A customer in Shopify has a first name, last name, email, and/or phone number. You can populate the first name and last name from the customer card in [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priority|Field in Customer card|Description|
|------|------|-----------|
|1|**Contact Name**|Highest priority, if the **Contact Name** field is filled and the **Contact Source** field in the **Shopify Shop Card** contains *First Name and Last Name* or *Last Name and First Name* options, defining how to split the values.|
|2|**Name 2**|If the **Name 2** field is filled and the **Name 2 Source** field in the **Shopify Shop Card** contains *First Name and Last Name* or *Last Name and First Name* options, defining how to split the values.|
|3|**Name**|Lowest priority, if the **Name** field is filled and the **Name Source** field in the **Shopify Shop Card** contains *First Name and Last Name* or *Last Name and First Name* options, defining how to split the values.|

A customer in Shopify also has a default address, which in addition to the first name, last name, email and/or phone may contain company and address. You can populate the **Company** field based on data from Customer Card in [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priority|Field in Customer card|Description|
|------|------|-----------|
|1|**Name**|Highest priority, if the **Name Source** field in the **Shopify Shop Card** contains *Company Name*.|
|2|**Name 2**|Lowest priority, if the **Name 2 Source** field in the **Shopify Shop Card** contains *Company Name*.|

For addresses where the country/province is used, select *Code* or *Name* in the **Country Source** field in the **Shopify Shop Card** to specify what type of data is stored in [!INCLUDE[prod_short](../includes/prod_short.md)] in the **Country** field.

## Sync customers

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to synchronize customers to open the **Shopify Shop Card** page.
3. Choose the **Sync Customers** action.

Alternatively, you can use the **Start Customer Sync** action on the **Shopify Customers** window or search for the **Sync Customers** batch job.

You can schedule the task to be performed in an automated manner. For more information, see [Schedule recurring tasks](background.md#to-schedule-recurring-tasks).

## See also

[Get Started with the Connector for Shopify](get-started.md)  