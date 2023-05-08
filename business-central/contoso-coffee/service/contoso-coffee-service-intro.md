# Introduction to Contoso Coffee Service Management

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for Business Central add demo data that you can use to learn how to use the Service Management capabilities in Business Central.

This app provides several elements that are used for the main walkthroughs:
 - Resources with assigned Skills and Zones
 - Items configured to create Service Items
 - Loaner Items

> [!IMPORTANT]
> Before you run any of the scenarios for Contoso Coffee, post any item journal lines with opening balances. For more requirements, see the [Set up Contoso Coffee data](#set-up-contoso-coffee-service-management-data) section.
>
> 
## Set up Contoso Coffee Service Management data

To use the Contoso Coffee Service Management demo data, you must install two apps in the relevant company in [!INCLUDE [prod_short](../../includes/prod_short.md)]:  

- **Contoso Coffee Demo Dataset**  

    This app delivers demo data for the base application.  
- **Contoso Coffee Demo Dataset (country ID)**  

    This app adds country-specific content on top of the base application.

Add the apps to an empty company in a paid subscription or as part of a trial. For example, create a new company with no sample data from the **Create New Company** assisted setup guide that you can open from the **Companies** list. Then add the apps from the [marketplace](../../ui-extensions-install-uninstall.md#install) if they are not already listed in the **Extension Management** page.  

Once the relevant apps are installed, go to the [Contoso Coffee Whse Demo Data](https://businesscentral.dynamics.com/?page=4761) page in [!INCLUDE [prod_short](../../includes/prod_short.md)], and change the default settings to suit your needs. The following tables describes the settings:  

|Field  |Description  |
|---------|---------|
|**Starting Year** |Specifies the first year that you you want to use for the Contoso Coffee demonstration data. Depending on the company setup, the year is either a calendar year or a fiscal year.|
|**Customer No.**  |The customer to use for the scenarios in sales operations.|
|**Vendor No.**  |The vendor to use for all scenarios in purchasing operations.|
|**Item 1 No.**  |The item to use for the contract scenarios.|
|**Item 2 No.**  |The item to use for the breakfix scenarios.|
|**Resource Local 1 No.**  |The resource to use for the contract scenarios.|
|**Resource Remote 1 No.**  |The resource to use for the breakfix scenarios.|
|**Customer Posting Group**|Specifies a business code for domestic customers. The business codes are used when transactions are posted. |
|**Customer General Business Posting Group**|Specifies a business code for domestic customers. The business codes are used when transactions are posted. |
|**Services - General Product Posting Group**    |Specifies a code for resources that must be used for posting sales.|
|**Domestic - General Business Posting Group**|Specifies a business code for domestic customers and vendors. The business codes are used when transactions are posted. |
|**Resale - Inventory Posting Group**    |Specifies a code for items that must be used for posting resale.|
|**Retail - General Product Posting Group**    |Specifies a code for items that must be used for posting retail.|
|**VAT Product Posting Group**    |Specifies a VAT product code for items for posting VAT if VAT is enabled..|
|**Price Factor**     |Specifies a factor to convert a price from USD/EUR to the local currency. *1* means that the price is the same amount in any currency. A higher number will be used to get the price in the local currency. |
|**Rounding Precision**  |Defines how calculated consumption quantities are rounded when entered on consumption journal lines. Quantities less than 0.5 will be rounded down. Quantities equal to or greater than 0.5 will be rounded up.|

Once you're ready, choose the **Create Demo Data** action. It takes a few minutes to add the data to the underlying database, but then you're ready to run the various scenarios.  

> [!IMPORTANT]
> If you are running the Scenarios, you may want to verify that your user has a Premium license and the Company Experience is set to Premium.