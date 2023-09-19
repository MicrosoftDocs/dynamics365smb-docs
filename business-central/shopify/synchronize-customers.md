---
title: Synchronize customers
description: Import customers from or export to Shopify 
ms.date: 06/06/2023
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: 30105, 30106, 30107, 30108, 30109, 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
---

# Synchronize Customers

When you import an order from Shopify, getting the information about the customer is essential for further processing the document in [!INCLUDE[prod_short](../includes/prod_short.md)]. There are two main options for doing so, and several combinations:

* Use a special customer for all orders.
* Import the actual customer information from Shopify. This option is also available when you export customers to Shopify from [!INCLUDE[prod_short](../includes/prod_short.md)] first.

## Important settings when importing customers from Shopify

Whether you import customers from Shopify in bulk or when you import orders, use the following settings to manage the process:

|Field|Description|
|------|-----------|
|**Customer Import from Shopify**|Select **All Customers** if you plan to import customers from Shopify in bulk; either manually using the **Sync Customers** action or via the job queue for recurring updates. Regardless of the selection, the customer information will always be imported together with the order. However, the use of this information depends on the **Shopify Customer Templates** and settings in the **Customer Mapping Type** field.|
|**Customer Mapping Type**|Define how you want the connector to perform the mapping.<br>- **By Email/Phone** if you want the connector to map the imported Shopify customer to an existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)] using email and phone.</br>- **By Bill-to Info** if you want the connector to use the address of the invoice recipient to map the imported Shopify customer to an existing customer in [!INCLUDE[prod_short](../includes/prod_short.md)].</br>- Select **Always Take the Default Customer** if you want the system to use a customer from the **Default Customer No.** field. |
|**Shopify Can Update Customers**| Select this field if you want the connector to update the customers it finds when either of the **By Email/Phone** or **By Bill-to Info** options are selected in the **Customer Mapping Type** field.|
|**Auto Create Unknown Customers**| Select this field if you want the connector to create missing customers when the **By Email/Phone** or **By Bill-to Info** options are selected in the **Customer Mapping Type** field. A new customer will be created using imported data and the **Customer Template Code** defined on the **Shopify Shop Card** or **Shopify Customer Template** pages. Notice that the Shopify customer must have at least one address. Orders created via Shopify POS sales channel are often missing address details. If this option isn't enabled, you'll need to create a customer manually and link it to the Shopify customer.|
|**Customer Template Code**|This field is used together with **Auto Create Unknown Customers**.<br>- Choose the default template to be used for automatically created customers. Make sure that the selected template contains the mandatory fields, such as the **Gen. Business Posting Group**, **Customer Posting Group**, and value-added tax (VAT)- or tax-related fields.<br>- You can define templates per country/region on the **Shopify Customer Templates** page, which is useful for proper tax calculation. <br>- Learn more at [Set up Taxes](setup-taxes.md).|

### Customer template per country/region

Some settings can be defined at the country/regional level or a state/province level. The settings can be configured in [Shipping and Delivery](https://www.shopify.com/admin/settings/shipping) in Shopify.

You can do the following for each customer using the **Shopify Customer Template**:

1. Specify the **Default Customer No.**, which takes priority over the selection in the **Customer Import from Shopify** and **Customer Mapping Type** fields. It's used in the imported sales order.
2. Define the **Customer Template Code**, which is used to create missing customers if **Auto Create Unknown Customers** is enabled. If the **Customer Template Code** is empty, then the function uses the **Customer Template Code** defined on the **Shopify Shop Card**. The system first tries to find a template for the **Contry/Region Code** for the default address. If it doesn't find a template, it uses the first address.
3. In some cases, the **Customer Template Code** defined for a country/region isn't enough to ensure correct tax calculations (for example, for countries/regions with sales tax). In this case, including **Tax Area** could be a useful addition.
4. The **Tax Area** field also contains a **Country Code** and **County Name** pair. This pair is useful when the connector needs to convert a code to a name, or vice versa.

> [!NOTE]  
> The country codes are ISO 3166-1 alpha-2 country codes. Learn more at [Country Code](https://help.shopify.com/en/api/custom-storefronts/storefront-api/reference/enum/countrycode).

## Export customers to Shopify

You can export existing customers to Shopify in bulk. In each case, a customer and one default address are created. You can manage the process using the following settings:

|Field|Description|
|------|-----------|
|**Export customers to Shopify**|Select this option if you plan to export all customers from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify in bulk. You can do it either manually, using the **Sync Customers** action, or automatically, using a job queue for recurring updates.<br> When exporting customers with addresses that include provinces/states, make sure that **ISO Code** is filled in for countries/regions.|
|**Can update Shopify Customers**|This option works together with the **Export customer to Shopify** setting. Enable this option if you want to generate updates later from [!INCLUDE[prod_short](../includes/prod_short.md)] for customers that already exist in Shopify.|

The following are requirements for exporting a customer:

* The customer must have a valid email address.
* A country/region is selected on the customer card, for local customers, with blank country/region the country/region specified in the **Company Information** page must have an ISO Code defined.
* If the customer has a phone number, the number must be unique because Shopify won't accept a second customer with the same phone number.
* If the customer has a phone number, it must be in the E.164 format. Different formats are supported if they represent a number that can be dialed from anywhere in the world. The following formats are valid:

  * xxxxxxxxxx
  * +xxxxxxxxxxx
  * (xxx)xxx-xxxx
  * +x xxx-xxx-xxxx

After you've created the customers in Shopify, you can send them direct invitations to encourage them to activate their accounts.

### Populate customer information in Shopify

A customer in Shopify has a first name, family name, email, and/or phone number. You can enter first and family names from the customer card in [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priority|Field in the customer card|Description|
|------|------|-----------|
|1|**Contact Name**|Highest priority, if the **Contact Name** field is filled and the **Contact Source** field in the **Shopify Shop Card** contains either the *First Name and Last Name* or *Last Name and First Name* option to define how to split the values.|
|2|**Name 2**|If the **Name 2** field is filled in and the **Name 2 Source** field in the **Shopify Shop Card** contains either the *First Name and Last Name* or *Last Name and First Name* option to define how to split the values.|
|3|**Name**|Lowest priority, if the **Name** field is filled and the **Name Source** field in the **Shopify Shop Card** contains either the *First Name and Last Name* or *Last Name and First Name* options to define how to split the values.|

A customer in Shopify also has a default address. The address might contain a company and address in addition to their first name, family name, email, and/or phone number. You can populate the **Company** field based on data from the customer card in [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priority|Field in the customer card|Description|
|------|------|-----------|
|1|**Name**|Highest priority, if the **Name Source** field in the **Shopify Shop Card** contains *Company Name*.|
|2|**Name 2**|Lowest priority, if the **Name 2 Source** field in the **Shopify Shop Card** contains *Company Name*.|

For addresses where the county/province is used, select **Code** or **Name** in the **County Source** field on the **Shopify Shop Card** page. The code or name specifies the type of data stored in [!INCLUDE[prod_short](../includes/prod_short.md)] in the **County** field. Remember to initialize customer templates per country/region so that the county code/name mapping is ready. 


## Sync customers

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify shop**, and then choose the related link.
2. Select the specific shop for which you want to synchronize customers.
3. Choose the **Sync Customers** action.

Alternatively, use the **Start Customer Sync** action on the **Shopify Customers** window or search for the **Sync Customers** batch job.

You can schedule the task to be performed in an automated manner. Learn more at [Schedule recurring tasks](background.md#to-schedule-recurring-tasks).

## See also

[Get Started with the Connector for Shopify](get-started.md)  
