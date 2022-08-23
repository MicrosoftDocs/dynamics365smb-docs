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

When an order is imported from Shopify, getting the information about the customer is essential for further processing the document in [!INCLUDE[prod_short](../includes/prod_short.md)]. These are the two main options for doing so, and their combinations:

* Use a special customer for all orders.
* Import the actual customer information from Shopify. This option is also available when you export customers to Shopify from [!INCLUDE[prod_short](../includes/prod_short.md)] first.

## How the connector chooses which customer to use

The *Import order from Shopify* function tries to select customers in the following order:

1. If the **Default Customer No.** field is defined in the **Shopify Customer Template** for the corresponding country, then the **Default Customer No.** is used, regardless of the settings in the **Customer Import From Shopify** and **Customer Mapping Type** fields. Learn more at [Customer Template per Country](synchronize-customers.md#customer-template-per-country).
2. If the **Customer Import From Shopify** is set to *None* and the **Default Customer No.** is defined on the **Shopify Shop Card** page, then the **Default Customer No.** is used.

The next steps depend on the **Customer Mapping Type**.

* If it's **Always take the default customer**, then the connector uses the customer defined in the **Default Customer No.** field on the **Shopify Shop Card** page.
* If it's **By EMail/Phone**, the connector tries to find the existing customer by ID first, then by email, and then by phone number. If the customer isn't found, the connector creates a new customer.
* If it's **By Bill-to Info**, the connector tries to find the existing customer by ID first and then by the bill-to address information. If the customer isn't found, the connector creates a new customer.

> [!NOTE]  
> The connector uses information from the bill-to address and creates the bill-to customer in [!INCLUDE[prod_short](../includes/prod_short.md)]. The sell-to customer is the same as the bill-to customer.

## Important settings when importing customers from Shopify

Whether you import customers from Shopify in bulk or at the same time as you import orders, the following settings let you manage the process:

|Field|Description|
|------|-----------|
|**Customer Import from Shopify**|Select **All Customers** if you plan to import customers from Shopify in bulk; either manually using the **Sync Customers** action or via the job queue for recurring updates. Regardless of the selection, the customer information will always be imported together with the order. However, the use of this information depends on the **Shopify Customer Templates** and settings in the **Customer Mapping Type** field.|
|**Customer Mapping Type**|Define how you want the connector to perform the mapping.<br>- **By Email/Phone** if you want the connector to map the imported Shopify customer to an existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)] using email and phone.</br>- **By Bill-to Info** if you want the connector to use the address of the invoice recipient to map the imported Shopify customer to an existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)].</br>- Select **Always Take the Default Customer** if you want the system to use a customer from the **Default Customer No.** field. |
|**Shopify Can Update Customers**| Select this field if you want the connector to update the customers it finds when either of the **By Email/Phone** or **By Bill-to Info** options are selected in the **Customer Mapping Type** field.|
|**Auto Create Unknown Customers**| Select this field if you want the connector to create missing customers when the **By Email/Phone** or **By Bill-to Info** options are selected in the **Customer Mapping Type** field. A new customer will be created using imported data and the **Customer Template Code** defined on the **Shopify Shop Card** or **Shopify Customer Template** pages. Notice that the Shopify customer must have at least one address. If this option isn't enabled, you'll need to create a customer manually and link it to the Shopify customer. You can always initiate creation of a customer manually from the **Shopify Order** page.|
|**Customer Template Code**|This field is used together with **Auto Create Unknown Customers**.<br>- Choose the default template to be used for automatically created customers. Make sure that the selected template contains the mandatory fields, such as the **Gen. Business Posting Group**, **Customer Posting Group**, and value-added tax (VAT)- or tax-related fields.<br>- You can define templates per country/region on the **Shopify Customer Templates** page, which is useful for proper tax calculation. <br>- Learn more at [Set up taxes](setup-taxes.md).|

### Customer template per country

Some settings can be defined at the country/regional level or at a state/province level. The settings can be configured in [Shipping and Delivery](https://www.shopify.com/admin/settings/shipping) at Shopify.

You can do the following for each customer using the **Shopify Customer Template**:

1. Specify the **Default Customer No.**, which takes priority over the selection in the **Customer Import from Shopify** and **Customer Mapping Type** fields. It's used in the imported sales order.
2. Define the **Customer Template Code**, which is used to create missing customers if **Auto Create Unknown Customers** is enabled. If the **Customer Template Code** is empty, then the function uses the **Customer Template Code** defined on the **Shopify Shop Card**.
3. Define whether prices include VAT/tax for imported orders.
4. In some cases, the **Customer Template Code** defined for a country isn't enough to ensure the correct calculation of taxes (for example, for countries with sales tax). In this case, including **Tax Areas** could be a useful addition.

> [!NOTE]  
> The country codes are ISO 3166-1 alpha-2 country codes. Learn more at [Country Code](https://help.shopify.com/en/api/custom-storefronts/storefront-api/reference/enum/countrycode).

## Export customers to Shopify

Existing customers can be exported to Shopify in bulk. In each case, a customer and one default address are created. You can manage the process using the following settings:

|Field|Description|
|------|-----------|
|**Export customers to Shopify**|Select this if you plan to export all customers with a valid email address from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify in bulk. You can do it either manually, using the **Sync Customers** action, or automatically, using a job queue for recurring updates.<br> When exporting customers with addresses that include provinces/states, make sure that **ISO Code** is filled in for countries/regions.|
|**Can update Shopify Customers**|This is used together with the **Export customer to Shopify** setting. Enable it if you want to generate updates later from [!INCLUDE[prod_short](../includes/prod_short.md)] for customers that already exist in Shopify.|

> [!NOTE]  
> Once you've created the customers in Shopify, you can send them direct invitations encouraging them to activate their accounts.

### Populate customer information in Shopify

A customer in Shopify has a first name, last name, email, and/or phone number. You can populate the first and last names from the customer card in [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priority|Field in customer card|Description|
|------|------|-----------|
|1|**Contact Name**|Highest priority, if the **Contact Name** field is filled and the **Contact Source** field in the **Shopify Shop Card** contains either the *First Name and Last Name* or *Last Name and First Name* option to define how to split the values.|
|2|**Name 2**|If the **Name 2** field is filled and the **Name 2 Source** field in the **Shopify Shop Card** contains either the *First Name and Last Name* or *Last Name and First Name* option to define how to split the values.|
|3|**Name**|Lowest priority, if the **Name** field is filled and the **Name Source** field in the **Shopify Shop Card** contains either the *First Name and Last Name* or *Last Name and First Name* options to define how to split the values.|

A customer in Shopify also has a default address, which may contain a company and address in addition to their first name, last name, email, and/or phone. You can populate the **Company** field based on data from customer card in [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priority|Field in customer card|Description|
|------|------|-----------|
|1|**Name**|Highest priority, if the **Name Source** field in the **Shopify Shop Card** contains *Company Name*.|
|2|**Name 2**|Lowest priority, if the **Name 2 Source** field in the **Shopify Shop Card** contains *Company Name*.|

For addresses where the country/province is used, select *Code* or *Name* in the **Country Source** field in the **Shopify Shop Card**. This specifies the type of data stored in [!INCLUDE[prod_short](../includes/prod_short.md)] in the **Country** field.

## Sync customers

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify shop**, and then choose the related link.
2. Select the specific shop for which you want to synchronize customers.
3. Choose the **Sync Customers** action.

Alternatively, use the **Start Customer Sync** action on the **Shopify Customers** window or search for the **Sync Customers** batch job.

You can schedule the task to be performed in an automated manner. Learn more at [Schedule recurring tasks](background.md#to-schedule-recurring-tasks).

## See also

[Get Started with the Connector for Shopify](get-started.md)  
