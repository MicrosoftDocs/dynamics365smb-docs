---
title: Synchronize customers and companies
description: Import customers and companies from or export to Shopify. 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.date: 07/14/2025
ms.topic: how-to
ms.service: dynamics-365-business-central
ms.search.form: 30105, 30106, 30107, 30108, 30109, 
ms.custom: bap-template
---

# Synchronize customers and companies

When you import an order from Shopify, getting the information about the customer is essential for further processing the document in [!INCLUDE[prod_short](../includes/prod_short.md)]. There are two main options for doing so, and several combinations:

* Use a special customer for all orders.
* Import the customer information from Shopify. This option is also available when you export customers to Shopify from [!INCLUDE[prod_short](../includes/prod_short.md)].

Shopify allows you to run your business to business (B2B) and direct to customer (DTC) business from one place with the power and ease of Shopify's all-in-one platform. Shopify Connector also works with different flavors of e-commerce.

While Shopify has two entities—customer and company—[!INCLUDE[prod_short](../includes/prod_short.md)] has only the customer entity, which affects how synchronization works.

When you run DTC, the buyer is created in Shopify as a customer. The customer is then imported to [!INCLUDE[prod_short](../includes/prod_short.md)] as a Shopify customer, and linked or converted to a customer.

If you run B2B, the buyer is created in Shopify as a customer linked to a company. The customer is imported to [!INCLUDE[prod_short](../includes/prod_short.md)] as a Shopify customer, and the company is imported to [!INCLUDE[prod_short](../includes/prod_short.md)] as a Shopify company and linked or converted to a customer.

To export a customer from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify, the steps are different depending on what you want to do:

* Export a customer as a Shopify customer for DTC.
* Export a customer as a company and customer pair for the B2B flow.

## Important settings when importing DTC customers from Shopify

Whether you import customers from Shopify in bulk or when you import orders, use the following settings to manage the process:

|Field|Description|
|------|-----------|
|**Customer Import from Shopify**|Select **All Customers** if you plan to import customers from Shopify in bulk; either manually using the **Sync Customers** action or via the job queue for recurring updates. Regardless of the selection, the customer information will always be imported together with the order. However, the use of this information depends on the **Customer Setup by Country/Region** page and settings in the **Customer Mapping Type** field.|
|**Customer Mapping Type**|Define how you want the connector to perform the mapping.</br></br>- **By Email/Phone** if you want the connector to use email account and telephone information to map the imported Shopify customer to a customer in Business Central.</br></br>- **By Bill-to Info** if you want the connector to use the address of the invoice recipient to map the imported Shopify customer to an existing customer in Business Central.</br></br>- **Always Take the Default Customer** if you want the system to use a customer from the **Default Customer No.** field. |
|**Shopify Can Update Customers**| Select this field if you want the connector to update the customers it finds when either of the **By Email/Phone** or **By Bill-to Info** options are selected in the **Customer Mapping Type** field. When you use the **Sync Customers** action, this setting also updates the customers you imported with Shopify orders.|
|**Auto Create Unknown Customers**| Select this field if you want the connector to create missing customers when the **By Email/Phone** or **By Bill-to Info** options are selected in the **Customer Mapping Type** field. A new customer is created using imported data and the **Customer Template Code** defined on the **Shopify Shop Card** or **Shopify Customer Template** pages. Notice that the Shopify customer must have at least one address. Orders created via Shopify POS sales channel are often missing address details. If this option isn't enabled, you must create a customer manually and link it to the Shopify customer.|
|**Customer/Company Template Code**|Use this field together with **Auto Create Unknown Customers**.</br></br>Choose the default template to use for automatically created customers. Make sure the selected template contains the mandatory fields such as **Gen. Business Posting Group**, **Customer Posting Group**, and value-added tax (VAT) or tax-related fields.</br></br>You can define templates per country/region on the **Customer Setup by Country/Region** page, which helps calculate taxes correctly.</br></br>Learn more at [Set Up Taxes](setup-taxes.md).|

Learn more at [How the connector chooses which customer to use](synchronize-orders.md#how-the-connector-chooses-which-customer-to-use)  

### Customer setup per country/region

Some settings can be defined at the country/regional level or a state/province level. The settings can be configured in [Shipping and Delivery](https://www.shopify.com/admin/settings/shipping) in Shopify.

You can do the following for each customer using the **Customer Setup by Country/Region** page:

1. Specify the **Default Customer No.**, which takes priority over the selection in the **Customer Import from Shopify** and **Customer Mapping Type** fields. It's used in the imported sales order.
2. Define the **Customer Template Code**, which is used to create missing customers if **Auto Create Unknown Customers** is enabled. If the **Customer Template Code** is empty, then the function uses the **Customer Template Code** defined on the **Shopify Shop Card**. The system first tries to find a template for the **Country/Region Code** for the default address. If it doesn't find a template, it uses the first address.
3. In some cases, the **Customer Template Code** defined for a country/region isn't enough to ensure correct tax calculations (for example, for countries/regions with sales tax). In this case, including **Tax Area** could be a useful addition.
4. The **Tax Area** field also contains a **Country Code** and **County Name** pair. This pair is useful when the connector needs to convert a code to a name, or vice versa.

> [!NOTE]  
> The country codes are ISO 3166-1 alpha-2 country codes. Learn more at [Country Code](https://help.shopify.com/en/api/custom-storefronts/storefront-api/reference/enum/countrycode).

### Populate customer information in Business Central

A customer in Shopify has a first name, family name, email, and/or phone number. A customer might also have multiple addresses that might contain a company and address in addition to their first name, family name, and/or phone number. The following table describes how data from the customer and address is imported into [!INCLUDE[prod_short](../includes/prod_short.md)]. Note that while the customer might have multiple addresses, only one is marked as default and is used to populate fields in [!INCLUDE[prod_short](../includes/prod_short.md)].

|[!INCLUDE[prod_short](../includes/prod_short.md)]|Field when imported from Shopify|
|------|-----------------|
|Name| Based on the selection in the **Name Source** field, this field can contain first and last name, or company from the default address. |
|Name 2|Based on the selection in the **Name 2 Source** field, this field can contain first and last name, or company from the default address. </br>Field is populated only if **Name** already has a value. Otherwise, the extracted value is assigned to the **Name** field. |
|Contact |Based on the selection in the **Contact Source** field, this field can contain first and last name, or company from the default address. </br>Field is populated only if **Name** already has value. Otherwise, the extracted value is assigned to the **Name** field. |
|Country / Region Code| Country from the default address. Mapping is done by ISO code.|
|County | State/Province from the default address. Based on selection in the **State Source** field, it can be a code or description.|
|Post Code| Zip code from the default address.|
|City| City from the default address.|
|Phone| Phone number from the default address. If a phone number isn't defined for the default address, then it's the phone number from the customer.|
|Email|Email address from the customer.|

The **Tax Area Code**, **Tax Liable**, **VAT Bus. Posting Group** are from the [Customer setup per country/region](#customer-setup-per-countryregion).

## Important settings when exporting DTC customers to Shopify

You can export existing customers to Shopify in bulk. In each case, a customer and one default address are created. You can manage the process using the following settings:

|Field|Description|
|------|-----------|
|**Can update Shopify Customers**| Enable this option if you want to generate updates later from Business Central for customers that already exist in Shopify.|

The following are requirements for exporting a customer:

* The customer must have a valid email address.
* When a country/region is selected on the customer card, make sure to fill in the **ISO Code** field. For local customers with a blank country/region, Shopify Connector uses the country/region specified on the **Company Information** page. That is especially important when you export customers with addresses that include provinces/states.
* If the customer has a phone number, the number must be unique because Shopify won't accept a second customer with the same phone number. The phone number must be in the E.164 format. Different formats are supported if they represent a number that can be dialed from anywhere in the world. The following formats are valid:

  * xxxxxxxxxx
  * +xxxxxxxxxxx
  * (xxx)xxx-xxxx
  * +x xxx-xxx-xxxx

After you create the customers in Shopify, you can send them direct invitations to encourage them to activate their accounts.

### Populate customer information in Shopify

A customer in Shopify has a first name, family name, email, and/or phone number. You can enter first and family names from the customer card in [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priority|Field in the customer card|Description|
|------|------|-----------|
|1|**Contact Name**|Highest priority, if the **Contact Name** field is filled and the **Contact Source** field in the **Shopify Shop Card** contains either the *First Name and Last Name* or *Last Name and First Name* option to define how to split the values.|
|2|**Name 2**|If the **Name 2** field is filled in and the **Name 2 Source** field in the **Shopify Shop Card** contains either the *First Name and Last Name* or *Last Name and First Name* option to define how to split the values.|
|3|**Name**|Lowest priority, if the **Name** field is filled and the **Name Source** field in the **Shopify Shop Card** contains either the *First Name and Last Name* or *Last Name and First Name* options to define how to split the values.|

A customer in Shopify also has a default address. The address might contain a company and address in addition to their first name, family name, and/or phone number. You can populate the **Company** field based on data from the customer card in [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priority|Field in the customer card|Description|
|------|------|-----------|
|1|**Name**|Highest priority, if the **Name Source** field in the **Shopify Shop Card** contains *Company Name*.|
|2|**Name 2**|Lowest priority, if the **Name 2 Source** field in the **Shopify Shop Card** contains *Company Name*.|

For addresses where the county/province is used, select **Code** or **Name** in the **County Source** field on the **Shopify Shop Card** page. The code or name specifies the type of data stored in [!INCLUDE[prod_short](../includes/prod_short.md)] in the **County** field. Remember to initialize customer setup per country/region so that the county code/name mapping is ready.

## Export DTC customers to Shopify

### Initial sync of customers from Business Central to Shopify

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Customers**, and choose the related link.
2. Choose the **Add Customer** action.
3. In the **Shop Code** field, enter the code. If you open the **Shopify Customers** window from the **Shop Card** page, the shop code is populated automatically.
4. Define filters on customers as required. For example, you can filter by Country/Region code.
5. Choose **OK**.

The resulting customers are automatically created in Shopify with addresses.

> [!NOTE]  
> The initial sync of customers from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify doesn't consider the **Can Update Shopify Customers** settings.

### Sync customers

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify shop**, and then choose the related link.
2. Select the specific shop for which you want to synchronize customers.
3. Choose the **Sync Customers** action.

Alternatively, use the **Start Customer Sync** action on the **Shopify Customers** window or search for the **Sync Customers** batch job.

You can schedule the task to be performed in an automated manner. Learn more at [Schedule recurring tasks](background.md#to-schedule-recurring-tasks).

## B2B Companies

If you use B2B in Shopify, you can create companies in addition to customers. You can link one or more individual customers to a company.

### Important settings when importing B2B companies from Shopify

The Shopify Connector imports all company locations, including billing address, payment terms and tax IDs, which it can use for automatic entity mapping. The information is available on the **Shopify Locations** page, which you open the page from the **Shopify Companies** and **Shopify Company Card** pages. The first imported location is used to create the customer and add address information and other fields on the **Customer Card** page. This location is marked as the **Default**.

When you import a Shopify company, you get the associated payment terms for each company location. If the Shopify Connector is configured to update the customer, it uses the payment term from the default location. It's important that the corresponding record exists on the **Shopify Payment Terms Mapping** page.

Whether you import companies from Shopify in bulk or when you import orders, use the settings in the following table to manage the process.

|Field|Description|
|------|-----------|
|**Company Import from Shopify**|Select **All Companies** if you plan to import companies from Shopify in bulk, either manually using the **Sync Companies** action or via the job queue for recurring updates. Regardless of the selection, the customer information is always imported together with the order. However, the use of this information depends on the **Customer Setup by Country/Region** page and settings in the **Company Mapping Type** field.|
|**Company Mapping Type**|Define how you want the connector to do the mapping.</br></br>- **By Email/Phone** if you want the connector to map the imported Shopify companies to an existing customer in [!INCLUDE [prod_short](../includes/prod_short.md)] using the main contact's email and phone number.</br></br>- Select **Always Take the Default Company** if you want to use the company in the **Default Company No.** field. </br></br>- Select **By Tax ID** if you want the connector to use tax details to map the imported Shopify companies to an existing customer in [!INCLUDE [prod_short](../includes/prod_short.md)]. Use the **Company Tax ID Mapping** field to specify where to store tax details. |
|**Company Tax ID Mapping**| Specifies whether to store company tax details in the **Registration Number** or the **VAT Registration No.** field.|
|**Shopify Can Update Company**| Select this field if you want the connector to update the customers it finds when the **By Email/Phone** option is selected in the **Company Mapping Type** field.|
|**Auto Create Unknown Companies**| Select this field if you want the connector to create new customers when the **By Email/Phone** or **By Tax ID** option is selected in the **Company Mapping Type** field. A new customer is created using the imported data and the **Customer/Company Template Code** defined on the **Shopify Shop Card** or **Shopify Customer Template** pages.|
|**Customer/Company Template Code**|Use this field together with **Auto Create Unknown Company**.</br></br>- Choose the default template to use for automatically created customers. Make sure the mandatory fields are filled in on the template, such as the **Gen. Business Posting Group**, **Customer Posting Group**, **Value-added tax (VAT)** or other tax-related fields.</br></br>- You can define templates per country/region on the **Customer Setup by Country/Region** page, which is useful for proper tax calculation.</br></br>Learn more at [Set up Taxes](setup-taxes.md).|

> [!NOTE]  
> The company must have a main contact. Otherwise, the connector skips the company.
>
> The oldest location is used as source of information when creating or updating the customer in [!INCLUDE [prod_short](../includes/prod_short.md)].
> 
> Only the main contact is imported.

### Important settings when exporting B2B companies to Shopify

You can export existing customers to Shopify in bulk as a company. In each case, a company and one default location are created and one main contact. It's also possible to create a catalog.

When you export a customer as a Shopify company, the **Company ID** field is filled in with the value in the **No.** field from the **Customer Card** page, which helps traceability. Also, the connector fills in the **Company/Attention** field on the new company location with the company name. The name is used on imported orders.

|Field|Description|
|------|-----------|
|**Can update Shopify Companies**| Enable this option if you want to generate updates later from Business Central for companies that already exist in Shopify.|
|**Default Contact Permissions**| Specify which permissions must be assigned to the main contact; you can choose between **None**, **Ordering only**, and **Location admin**.|
|**Auto Create Catalog**| Enable this option if you want to create a catalog that includes all products. A catalog is created for each exported company. When you export a customer as a Shopify company, if you configured the Shopify Connector to create a catalog, the **Customer No.** field is filled in for the catalog. This value ensures that the connector uses the specific customer to calculate prices, which eliminates the need to fill in the **Customer Price Group**, **Customer Discount Group**, and **Allow Line Discount** fields. You just need to turn on the **Sync Prices** toggle and select **Sync Prices** to start synchronizing catalog prices so that your customers get consistent pricing in Shopify and [!INCLUDE [prod_short](../includes/prod_short.md)]. For more information, see [Sync prices for B2B Catalog](synchronize-items.md#sync-prices-for-b2b-catalog)|
|**Company Tax ID Mapping**| Specifies if company tax details are stored in the **Registration Number** or the **VAT Registration No.** field.|

The Company Location feature in Shopify allows merchants to define default payment terms. When you export customer information as a Shopify company, payment term details transfer to Shopify and are stored in the default company location if:
* The **Payment Term** field in the **Customer Card** contains a value.
* A corresponding record is located in the **Shopify Payment Terms Mapping** page.

Shopify Connector lets you export customers from [!INCLUDE [prod_short](../includes/prod_short.md)] as additional B2B company locations in Shopify. When you use the **Sell-to Customer** and **Bill-to Customer** fields on the company location level, you get more flexibility and convenience for managing customer information across both applications. 
Learn more at [How the connector chooses which customer to use](synchronize-orders.md#how-the-connector-chooses-which-customer-to-use).

### Export a B2B company to Shopify

#### Initial sync of B2B companies from Business Central to Shopify

1. Go to the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Company**, and choose the related link.
2. Choose the **Add Company** action.
3. In the **Shop Code** field, enter the code. If you open the **Shopify Company** window from the **Shop Card** page, the shop code is populated automatically.
4. Define filters on the customer as required. For example, you can filter by Country/Region code.
5. Choose **OK**.

The resulting company and customers are automatically created in Shopify.

> [!NOTE]  
> The initial sync of companies from [!INCLUDE[prod_short](../includes/prod_short.md)] to Shopify doesn't consider **Can Update Shopify Company** settings.

When you select the **Add customer as Shopify Location** action, you can add customers as company locations. The customer you select must not already be exported.

### Sync a B2B company

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify shop**, and then choose the related link.
2. Select the specific shop for which you want to synchronize customers.
3. Choose the **Sync Company** action.

Alternatively, use the **Start Company Sync** action on the **Shopify Company** page or search for the **Sync Company** batch job.

You can schedule the task to run in an automated way. Learn more at [Schedule recurring tasks](background.md#to-schedule-recurring-tasks).

## Import and export customer information using Shopify metafields

Shopify's platform includes data models for basic commerce concepts. However, commerce is diverse and often requires more complex or specific data models. The custom data platform lets you extend Shopify's data models and create your own by using metafields. Metafields are a flexible way to add and store additional information about a Shopify resource, such as customer, or company. The additional information stored in metafields can be almost anything related to a resource. Some examples are preferences, credit limits, loyalty programs, social media links, or segment information.

You can import and export data stored in metafields into [!INCLUDE [prod_short](../includes/prod_short.md)]. Also, there's an extensibility model that allows developers to map standard or custom fields, or other related entries in [!INCLUDE [prod_short](../includes/prod_short.md)] to metafields in Shopify.

You can edit metafields on the **Shopify Metafields** page, which you open from the **Shopify Customers**, **Shopify Customer Card**, **Shopify Companies**, or **Shopify Company Card** pages.

> [!NOTE]
> You can edit the **Shopify Metafields** page in the following cases:
>
> * For a Shopify customer, if the **Customer Import from Shopify** field is set to **None** or **With Order Import**, and the **Can Update Shopify Customers** toggle is turned on.
> * For a Shopify company, if the **Company  Import from Shopify** field is set to **None** or **With Order Import**, and the **Can Update Shopify Companies** toggle is turned on.
>
> When you add a new record, the connector immediately sends a request to Shopify and stores the entry only when it gets a response with the Shopify ID for the metafield. You can't edit types that have AssistEdit functionality defined directly on the line.

If standard metafields are defined, you can use the **Get Metafield Definitions** action to get the list from Shopify. All supported metafields are imported. You only need to update the values.

#### Supported metafield content types

> [!NOTE]
> Metafields definitions with *List of values* aren't supported.

**Date and time:**

* Date
* Date and time

**Measurements:**

* Dimension
* Volume
* Weight

**Number:**

* Decimal
* Integer

**Text:**

* Single line text
* Multi-line text

> [!NOTE]
> Rich text isn't supported.

**References:**

* Product
* Variant
* Collection
* File
* Metaobject
* Page
* Company
* Customer

**Other:**

* True or false
* Color
* URL
* Money

> [!NOTE]
> Link and Rating aren't supported.

**Advanced:**

* Mixed reference
* JSON

## Related information

[Shopify Connector overview](shopify-connector-overview.md)  
[FAQ for the Shopify connector](shopify-faq.md)  
[Troubleshoot the Shopify Connector](troubleshoot.md)  
[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)  
