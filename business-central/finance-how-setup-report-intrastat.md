---
title: Set up Intrastat reporting
description: This article explains how to set up Intrastat reporting features to report trade with companies in other EU countries.
author: altotovi 
ms.author: altotovi
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 04/05/2023
ms.custom: bap-template
ms.search.keywords: electronic document, Intrastat, trade, EU, European Union
ms.search.form: 308, 309, 310, 311, 325, 326, 327, 328, 405, 406, 4810, 4811, 8451, 12202, 31077
---
# Set up Intrastat reporting

All companies in the European Union (EU) must report their trade with other EU countries/regions. Companies must report the movement of goods to the statistics authorities in their country/region every month, and the report must be delivered to the tax authorities. Intrastat is the system used to collect trade statistics of goods within these countries/regions. Use the Intrastat report to complete periodic Intrastat reporting, collecting, recording, and reporting the trade of goods according to local legislation.

Intrastat reporting is based on basic EU regulations that apply to all countries. However, there are differences within the individual countries. Each country has its rules of what and how to report.

> [!NOTE]
> Intrastat information doesn't apply to the movement of services between countries. Instead, the information only applies to goods such as items and fixed assets. If your government requires you to register the movement of services between countries, use the **Service Declaration** feature.
>
> This feature is available starting November 2022 as an app that you can download from [AppSource](https://go.microsoft.com/fwlink/?linkid=2081646). To use this feature, install it on the **Extension Management** page.

> [!IMPORTANT]
> This article covers the new Intrastat experience available from [!INCLUDE[prod_short](includes/prod_short.md)] version 21. Consult your administrator to learn which version your company is using and whether you should enable the new functionality.
>
> Read the previous version's Intrastat setup and usage article, [Set Up and Report Intrastat](finance-how-setup-report-intrastat-v20.md).

## Enable the new Intrastat experience

In the 2022 release wave 2, [!INCLUDE[prod_short](includes/prod_short.md)] includes a redesigned Intrastat experience with extended features. If the new Intrastat functionality isn't enabled in your environment, an administrator can enable it on the **Feature Management** page.

> [!IMPORTANT]
> You can't use the old and new experiences in parallel. Before you activate the extension in a production environment, we recommend that you test it in a sandbox environment using a copy of your production data. After you activate a new user experience in your production environment, you can't revert to the old Intrastat functionality.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Feature Management**, and then select the related link.
2. On the **Feature Management** page, select the line, **Feature Update: Replace the existing Intrastat functionality with the new Intrastat extension**. To learn more about feature management, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).
3. In the **Enable for** column, select **All Users**.
4. Read the explanation of how the system will be upgraded and select **Yes** to agree.
5. Select **Next**. You will get the basic setup for Intrastat. To read more about the Intrastat setup, see the [Intrastat configuration](#intrastat-configuration) section later in this article.
6. After set up is complete, select **Finish** to start using the new Intrastat experience.

    > [!NOTE]
    > Depending on your company location, enabling the feature described above will be enough. For countries with specific features for Intrastat reporting, enable the country-specific Intrastat app in addition to the core extension.

## Intrastat configuration

Before you can use Intrastat reports, there are several configurations that must be set up.

### Intrastat reporting setup

Use the **Intrastat Reporting Setup** page to enable and set the default behavior for Intrastat reporting. You can specify whether you need to report Intrastat from shipments (dispatches), receipts (arrivals), or both, depending on thresholds set by your local regulations. You can also set default transaction types for the regular and return documents used for transaction reporting.

Complete the following steps to set up Intrastat reporting.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report Setup**, and then select the related link.
2. On the **General** FastTab, select or enter field information as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] The following table describes some of the key fields.

   | Field | Description |
   | --- | --- |
   | **Report Receipts** | Specifies that you must include arrivals of received goods in Intrastat reports. |
   | **Report Shipments** | Specifies that you must include shipments of dispatched items in Intrastat reports. |
   | **Shipments Based On**  | Specifies based on which country code Intrastat report lines are taken.  |
   | **VAT No. Based On** | Specifies which customer or vendor code the value-added tax (VAT) number taken for the Intrastat report is based on.  |
   | **Company VAT No. on File** | Specifies how the company's VAT registration number exports to the Intrastat file.  |
   | **Vendor VAT No. on File** | Specifies how a vendor's VAT registration number is exported to the Intrastat file.  |
   | **Customer VAT No. on File** | Specifies how a customer's VAT registration number is exported to the Intrastat file.  |
   | **Get Partner VAT** | Specifies which type of Intrastat report line the partner's VAT registration number is updated from. Depending on your local requirements, you can choose only for receipt, only for shipment, or for both types of lines. |
3. On the **Default Transactions** FastTab, select or enter field information as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] The following table describes some of the key fields.

   | Field | Description |
   | --- | --- |
   | **Default Trans. Type** | Specifies the default transaction type for regular sales shipments, service shipments, and purchase receipts. |
   | **Default Trans. Type – Returns** | Specifies the default transaction type for sales returns, service returns, and purchase returns. |
   | **Default Private Person VAT No.** | Specifies the default private person VAT number if the private person must have a dedicated VAT number on the Intrastat report. |
   | **Default 3-Party Trade VAT No.** | Specifies the default 3-party trade VAT number if you don't have its VAT number. |
   | **Default VAT for Unknown State** | Specifies the default VAT number for an unknown state. |
   | **Default Country/Region Code** | Specifies the default receiving country code. |
4. On the **Reporting** FastTab, select or enter the field information as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] The following table describes some of the key fields.

   | Field | Description |
   | --- | --- |
   | **Data Exch. Def. Code** | Specifies the data exchange definition code to generate the Intrastat file. This field is only available if the **Split Receipts/Shipments Files** field is set to **No**. |
   | **Split Receipts/Shipments Files** | Specifies if receipts and shipments should be reported in two separate files. |
   | **Zip File(-s)** | Specifies if the report files should be added to the .zip file. |
   | **Data Exch. Def. Code – Receipt** | Specifies the data exchange definition code to generate the Intrastat file for received goods. This field is available only if the **Split Receipts/Shipments Files** field is set to **Yes**. |
   | **Data Exch. Def. Code – Shipment** | Specifies the data exchange definition code to generate the Intrastat file for shipped goods. This field is available only if the **Split Receipts/Shipments Files** field is set to **Yes**. |
5. On the **Numbering** FastTab, enter a value in the **Intrastat Nos** field.

### Set up a reporting file

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Data Exchange Definitions**, and then select the related link.
2. Select **New**, and on the **General** FastTab, enter information about the data exchange definition, the data file type, column separator, related codeunits, XMLport, and other fields as needed.
3. On the **Line Definitions** FastTab, enter a value in the **Line Type** field to describe the formatting of lines in the data file and where you need to define the number of columns for this line.
4. On the **Column Definitions** FastTab, fill in the line for each planned column. You can define column names, data types such as text, date, or decimal, the length of the fixed-width line that holds the column if the file is of type *Fixed text*, and other parameters.
5. On the **Line Definitions** FastTab, select **Field Mapping**.
6. On the **Field Mapping** page, create a new entry. 
7. On the **General** FastTab, select the **Table ID** (for **Intrastat Report Line**, choose 4812), and enter the following field information.
   1. In the **Key Index** field, Specify the key index to sort the source records before exporting.
   2. In the **Mapping Codeunit** field, select a value.
8. On the **Field Mapping** FastTab, add the columns you previously configured in the **Column Definitions** FastTab, and then add the following field information.
   1. Specify the **Field ID** for each of the columns.
   2. Specify the **Transformation Rule** for each column as needed. The value specifies the rule that transforms imported text to a supported value before it can be mapped to a specified field in [!INCLUDE[prod_short](includes/prod_short.md)]. When you choose a value in this field, the exact value is entered in the **Transformation Rule** field in the **Data Exch. Field Mapping Buf.** table and vice versa.
9. If you need to group entries based on some columns, on the **Field Grouping** FastTab, select the fields you want to use for grouping.

> [!NOTE]
> [!INCLUDE[prod_long](includes/prod_long.md)] comes with the preconfigured data exchange definition for Intrastat for all localized countries. To learn more about creating a new data exchange definition, see [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).

### Set mandatory fields with the Intrastat report checklist

In some countries, the authorities require that Intrastat reports include, for example, the shipment method for purchases or other values when sales are over a certain threshold.

To set mandatory fields or values on the **Intrastat Report** page, complete the following steps.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report Setup**, and then select the related link.
2. Select **Intrastat Report Checklist**.
3. Using the following instructions, add the necessary lines for checking.
   1. Set the **Field No.** field to a field that must be checked for a non-empty value.
   2. Enter a value in the **Filter Expression** field if needed, based on the following rules.
      1. When you open the **Filter Page**, select the filter you need to use for checking.
      2. Select a value related to the filter you used.
      3. If you have more filters you need to fill for this specific field, repeat the previous two steps to add another filter.
      4. When you finish entering the filters for the chosen field, select **OK**.
   3. Select the **Reversed Filter Expression** check box to specify that the check for fields is run only on those lines that don't match the filter expression. If the line isn't filtered, this field is ignored.

> [!NOTE]
> When you open the **Filter Page** from the **Filter Expression** line, you can use all standard filter expressions related to the specific field you want to filter.
>
> Be careful when you set up validation rules as they can differ between countries.

## Use custom codeunits in Intrastat reporting

If you want to change how Intrastat works and the default configuration isn't enough, you can customize the system by extending the standard features. If you need to further change the Intrastat behavior, you can develop your own codeunits. When you create codeunits, you need to make additional changes to use them. To configure the system to use your own objects, complete the following steps.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Reports Configuration**, and then chooseselect the related link.
2. On the **VAT Reports Configuration** page, add a new line.
3. In the **VAT Report Type** field, select **Intrastat Report**.
4. In the **VAT Report Version** field, specify the version of the report.
5. Add your codeunits for the following options:
   a. In the **Suggest Lines Codeunit ID** field, specify the new codeunit for suggesting lines in the Intrastat report lines.
   b. In the **Content Codeunit ID** field, specify the new codeunit for exporting data as a file using a Data Exchange Definition.
   c. In the **Validate Codeunit ID** field, specify the new codeunits for validating results inside Intrastat report lines.

> [!IMPORTANT]
> This line must be empty if you use the standard codeunits. You should only create a line and configure it if you have developed custom codeunits.

## Other Intrastat configurations

Customer and vendor cards include the **Intrastat Partner Type** field which has the same option values as the **Partner Type** field: 

    - "" (blank)
    - *Company*
    - *Person*
    
The **Intrastat Partner Type** field replaced the **Partner Type** field in Intrastat reporting. The **Partner Type** field is used in the Single Euro Payments Area (SEPA) to define the SEPA Direct Debit Scheme (Core or B2B). The **Intrastat Partner Type** field is used for Intrastat reporting only. This means you can specify different values for the two fields if necessary.

If the **Intrastat Partner Type** field is left blank, the value from the **Partner Type** field is used for Intrastat reporting.

In addition to **Intrastat Report Setup**, **Data Exchange Definitions**, and **Intrastat Report Checklist**, the following settings must also be configured.

| Page | Description |
| ---- | ----------- |
| **Countries/Regions** | On the **Countries/Regions** page, add the **EU Country/Region Code** and **Intrastat Code** to specify a code for the country/region you are trading with. This information will be used in Intrastat reporting. |
| **Tariff Numbers** | In many countries, the customs and tax authorities establish 8-digit codes for various items. So that item entries to contain the necessary information when the program imports them to the Intrastat journal line, enter the item code on the **Tariff Numbers** page. Find the codes for the items that your company deals with and enter them on the **Tariff Numbers** page. |
| **Transport Methods** | There are seven one-digit codes for Intrastat transport methods. **1** for sea, **2** for rail, **3** for road, **4** for air, **5** for the post, **7** for fixed installations, and **9** for own propulsion. For example, transporting a car by driving it. [!INCLUDE[prod_short](includes/prod_short.md)] doesn't require these specific codes. However, we recommend that the descriptions provide a similar meaning. |
| **Transaction Types** | Countries and regions have different codes for types of Intrastat transactions, such as ordinary purchase and sale, exchange of returned goods, and exchange of non-returned goods. Set up all the codes that apply to your country/region. These codes are then used on the **Foreign Trade** FastTab on sales and purchase documents and when you process returns. |
| **Transaction Specifications** | Set up codes to supplement the transaction type descriptions. |
  
  > [!NOTE]
  > Starting in January 2022, Intrastat requires different transaction nature codes for dispatches to private individuals or non-VAT registered businesses and VAT registered businesses. To comply with this requirement, we recommend that you review or add new transaction nature codes on the **Transaction Types** page according to the requirements in your country. You should also check and update the **Intrastat Partner Type** field to *Person* for a private individual or non-VAT registered business customers on the relevant **Customer** page. If you are unsure about the correct Intrastat partner type or transaction type to use, we recommend that you ask an expert in your country or region.

|   Field   |   Description   |
| --------- | --------------- |
| **Net Weight** | Weight is one of the basic configurations related to Intrastat reporting as the total weight is mandatory for reporting. To be ready for this requirement, enter a value in the **Net Weight** field on the item or fixed asset card. |
| **Country of Origin Code** | Use the two-letter ISO Alpha Codes on the item or fixed asset card for the country where the good was obtained or produced. If the good was produced in more than one country, the country of origin is the last country where it was significantly processed. |
| **VAT identification number of the partner operator in the Member State of import** | This is the VAT-ID number of the partner operator in the Member State of import. The VAT-ID is also used in the exchange of intra-EU-export data among the Member States and allows the Member States to allocate the received data to the importing company in their own country. Reporting units must report on the VAT-ID of the company that declared the intra-Union acquisition of goods in the Member State of import. |

Optionally, you can also set up:

* **Commodity codes**: Customs and tax authorities have established numerical codes that classify items and services. You can specify these codes on items.
* **Areas**: Supplementary information about countries and regions.
* **Entry/exit points**: Specify the locations where you ship or receive items to or from other countries. An airport is an example of an entry or exit point. You enter entry or exit points on sales and purchase documents on the **Foreign Trade** FastTab. This information is copied from the item entries when you create the Intrastat journal.
* **Supplementary unit of measure**: The quantity of goods for Intrastat reporting can be either net weight (in kilograms) or a supplementary unit. If supplementary units are required, you must configure them for items and fixed assets.

#### Set up transport methods

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transport Methods**, and then select the related link.
2. Fill in the field information as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

#### Set up transaction nature codes

1. select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transaction Types**, and tje select the related link.
2. Fill in the field information as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### Other related configurations

Before you use the Intrastat reporting feature, you must define fields on the item, fixed asset, customer, and vendor cards.

#### Item cards

Complete the following steps to set up all necessary information related to Intrastat on item cards.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then select the related link.
2. Select the item you want to configure.
3. On the **Costs & Posting** FastTab, in the **Tariff No.**, **Supplementary Unit of Measure**, and **Country/Region of Origin Code**, enter a value.

    > [!NOTE]
    > To use a unit of measure to supplement the base unit of measure, configure the supplementary unit of measure on the **Item Units of Measure** page.

4. On the **Inventory** FastTab, in the **Net Weight** field, enter a value in decimal format.

> [!NOTE]
> When you add the Tariff number to a unit of measure that's defined for the item, [!INCLUDE [prod_short](includes/prod_short.md)] automatically fills in the **Supplementary Unit of Measure** field based on the Tariff number configuration. You can change the **Supplementary Unit of Measure** field value as needed.

#### Set up fixed assets for Intrastat

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then select the related link.
2. Select the fixed asset you want to configure.
3. On the **Intrastat** FastTab, in the **Tariff No.**, **Net Weight**, and **Supplementary Unit of Measure** fields, enter a value.

> [!NOTE]
> You can use different units of measure as your supplementary unit of measure. But whatever **Unit of Measure Code** you choose, its **Quantity** in Intrastat reports will always be 1.

#### Set up vendors for Intrastat

Before you can include a vendor in Intrastat reporting, enter their information on the **Vendor Card** page. For example, specify a **Country/Region Code** and a **VAT Registration No.**.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then select the related link.
2. Select the vendor you want to configure.
3. On the **Intrastat** FastTab, in the **Default Trans. Type**, **Default Trans. Type - Returns**, and **Default Transport Method** fields, set a default value for each field.
4. On the **Payments** FastTab, in the **Intrastat Partner Type** field, specify whether the vendor is a person or a company.

#### Set up customers for Intrastat

Before you can include a customer in Intrastat reporting, enter their information on the **Customer Card** page. For example, you must specify a **Country/Region Code** and a **VAT Registration No.**.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then select the related link.
2. Select the customer you want to configure.
3. On the **Intrastat** FastTab, in the **Default Trans. Type**, **Default Trans. Type - Returns**, and **Default Transport Method** fields, set the default value for each field.
4. On the **Payments** FastTab, in the **Intrastat Partner Type** field, specify whether the vendor is a person or a company.

#### Exclude items and fixed assets from Intrastat reporting

If there is a reason for a specific item or fixed asset to be excluded from Intrastat reporting, change the option on their card.

##### Exclude an item from Intrastat reporting

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then select the related link.
2. Select the item you want to configure and on the **Cost & Posting** FastTab, select the **Exclude from Intrastat Report** check box.

##### Exclude a fixed asset from Intrastat reporting

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then select the related link.
2. Select the fixed asset you want to configure.
3. On the **Intrastat** FastTab, select the **Exclude from Intrastat Report** check box.

#### Set up tariff numbers

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Tariff Numbers**, and then select the related link.  
2. On the **Tariff Numbers** page, enter information in the fields described in the following table.

    |Field|Description|  
    |------------------------------------|---------------------------------------|
    | **No.**| Specifies the tariff number. |
    | **Description**|Specifies a description of related tariff number. |
    | **Supplementary Units**|Specifies whether the customs and tax authorities require information about the quantity and unit of measure for this item. |
    | **Conversion Factor**|Specifies the conversion factor for the tariff number. |
    |**Unit of Measure**|Specifies the unit of measure for the tariff number. |

> [!NOTE]
> If you add a supplementary unit of measure, [!INCLUDE [prod_short](includes/prod_short.md)] asks if you want to update related items. If you choose to update related items, the **Unit of Measure** on the **Item Units of Measure** page is updated for all items with the same tariff number.
> 
> When you add the **Tariff Number** with a defined **Unit of Measure** to the item, [!INCLUDE [prod_short](includes/prod_short.md)] automatically adds a new unit of measure to the **Item Units of Measure** for the item. The **Qty. per Unit of Measure** is based on the **Quantity Rounding Precision** field.

## Enter country-specific Intrastat settings

Intrastat requirements are similar in all member states of the EU, though there are important exceptions. In theory, the rules should be uniformly applied in all member states. However, there are differences in implementations because some member states provide guidelines on how to apply the principles in specific situations. For example, commercial samples and return of goods. These guidelines can produce different results for various situations. Therefore, the information that countries must enter can differ and the file format to use for reporting can also differ.

### Austria

Intrastat reporting in Austria requires two different files for receipts and shipments. To verify that your setup is correct, follow these steps.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report Setup**, and then select the related link.  
2. On the **Reporting** FastTab, check whether **Split Receipts/Shipments Files** is selected. Related to that, you will find two separate **Data Exch. Def, Codes** configured. 
3. Verify that the **Zip File(-s)** field is selected to ensure that report files will be added to the zip file.

The process of working with Intrastat reports is the same as the global feature.

<!-- ### Belgium-->

### Czech Republic

The new Intrastat report experience for the Czech Republic will be available in 2023 release wave 1. In the meantime, continue to use the **Intrastat Journal** feature.

### Finland

In Finland, there are a few additional steps to set up Intrastat. Intrastat reporting in Finland requires two different files for receipts and shipments. You will also find that there are two separate **Data Exch. Def, Codes** configured.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report Setup**, and then select the related link.  
2. On the **Intrastat Report Setup** page, on the **File Setup** FastTab, enter the field information as described in the following table.

    |                 Field              |            Description                |  
    |------------------------------------|---------------------------------------|
    | **Custom Code**| Specifies a custom code for the Intrastat file setup information. |
    | **Company Serial No.**| Specifies a company serial number for the Intrastat file setup information. |

3. On the **Reporting** FastTab, check whether **Split Receipts/Shipments Files** is selected.

The process of working with Intrastat Reports is the same as the global feature.

<!-- ### Germany-->

### Italy

A new Intrastat report experience for Italy will be available starting February 2023. In a meantime, continue to use the **Intrastat Journal** feature.

<!-- ### France-->

### Sweden

Intrastat reporting in Sweden requires two different files for receipts and shipments. To verify that your setup is correct, follow these steps.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report Setup**, and then select the related link.  
2. On the **Reporting** FastTab, verify that **Split Receipts/Shipments Files** is selected. Related to that, you will find two separate **Data Exch. Def, Codes** configured.

The process of working with Intrastat reports is the same as in global feature.

<!-- ### United Kingdom-->

## See related training at [Microsoft Learn](/learn/modules/process-intrastat-dynamics-365-business-central/index).

## See also

[Intrastat Reporting in Business Central](finance-how-report-intrastat.md)  
[Financial Management](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
