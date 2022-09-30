---
title: Set Up Intrastat Reporting
description: Learn how to set up Intrastat reporting features to report trade with companies in other EU countries.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, Intrastat, trade, EU, European Union
ms.search.form: 308, 309, 310, 311, 325, 326, 327, 328, 405, 406, 4810, 4811, 8451, 12202, 31077
ms.date: 09/02/2022
ms.author: altotovi
---
# Set Up Intrastat Reporting

All companies in the European Union (EU) must report their trade with other EU countries/regions. Companies must report the movement of goods to the statistics authorities in their country/region every month, and the report must be delivered to the tax authorities. Intrastat is the system for collecting trade statistics of goods within these countries/regions. You use **Intrastat Report** to complete periodic Intrastat reporting (typically monthly), collecting, recording, and reporting trade of goods according to local legislation.

Intrastat reporting is based on basic EU regulations that apply to all countries; however, in practice, there are some differences within the individual countries. Each country has its rules of what exactly and how to report.

> [!NOTE]
> Intrastat information doesn't apply to the movement of services between countries, but only goods (items and fixed assets). If the local government requires registering the movement of services between countries, it can be done using the **Service Declaration** feature.
>
> This feature is expected to be available from November 2022 as an app at [AppSource](https://go.microsoft.com/fwlink/?linkid=2081646) so, if you want to use it, you will first need to install it on the **Extension Management** page.

> [!IMPORTANT]
> This article covers the new Intrastat experience available from [!INCLUDE[prod_short](includes/prod_short.md)] version 21. Consult your administrator to learn which version your company is using and to enable the new functionality.
>
> Read the previous version's Intrastat setup and usage article at [Set Up and Report Intrastat](finance-how-setup-report-intrastat-v20.md).

## Enable the new Intrastat experience

In the 2022 release wave 2, [!INCLUDE[prod_short](includes/prod_short.md)] includes a redesigned Intrastat experience with extended features. If the new Intrastat functionality is not enabled in your environment, it can be manually enabled by an administrator on the **Feature Management** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Feature Management** and then choose the related link.
2. On the **Feature Management** page, select the **Feature Update: Replace the existing Intrastat functionality with the new Intrastat extension** line. Learn more about feature management at [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management) in the administration content.
3. On the **Enable for** column, choose **All Users**.
4. Read the explanation of how the system will be upgraded and choose **Yes** if you agree.
5. Select **Next** and you will get a basic setup for Intrastat. Read more about the Intrastat setup at the [Intrastat configuration](#intrastat-configuration) section.
6. After finishing the setup, choose **Finish** to start using the new Intrastat experience.

> [!IMPORTANT]
> Keep in mind that you cannot use old and new experiences in parallel. Before activating the extension in a production environment, it is recommended that you first enable and test this feature in a sandbox environment with a copy of the production data before doing this in a production environment. Once you activate a new user experience in your production environment, you cannot revert back to the old Intrastat functionality.

> [!NOTE]
> Depending on your company location, enabling the feature described above will be enough. For countries with specific features for Intrastat reporting, you should enable the country-specific Intrastat app in addition to the core extension.

## Intrastat configuration

Before you can use Intrastat reports, there are several configurations that must be set up.

### Intrastat reporting setup

The **Intrastat Reporting Setup** page is used to enable Intrastat reporting and set defaults for it. You can specify whether you need to report Intrastat from shipments (dispatches), receipts (arrivals), or both, depending on thresholds set by your local regulations. You can also set default transaction types for regular and return documents, used for the nature of transaction reporting.

To set up Intrastat reporting:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report Setup** and then choose the related link.
2. Open the **General** FastTab and fill the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] The table below describes some of the key fields:

   | Field | Description |
   | --- | --- |
   | **Report Receipts** | Specifies that you must include arrivals of received goods in Intrastat reports. |
   | **Report Shipments** | Specifies that you must include shipments of dispatched items in Intrastat reports. |
   | **Shipments Based On**  | Specifies based on which country code Intrastat report lines are taken. You can choose one of the options: **Sell-to Country**, **Bill-to Country**, or **Ship-to Country**. |
   | **VAT No. Based On** | Specifies based on which customer/vendor code the value-added tax (VAT) number is taken for the Intrastat report. You can choose one of the options: **Sell-to VAT** or **Bill-to VAT**. |
   | **Company VAT No. on File** | Specifies how the company's VAT registration number exports to the Intrastat file. You can choose one of the options: VAT Reg. No., adding the EU Country Code as a prefix and removing the EU Country Code from VAT Reg. No. |
   | **Vendor VAT No. on File** | Specifies how a vendor's VAT registration number is exported to the Intrastat file. You can choose one of the options: VAT Reg. No., adding the EU Country Code as a prefix and removing the EU Country Code from VAT Reg. No. |
   | **Customer VAT No. on File** | Specifies how a customer's VAT registration number is exported to the Intrastat file. You can choose one of the options: VAT Reg. No., adding the EU Country Code as a prefix and removing the EU Country Code from VAT Reg. No. |
   | **Get Partner VAT** | Specifies which type of **Intrastat Report** line the Partner's VAT registration number is updated from. Depending on your local requirements, you can choose only for receipt, only for shipment, or for both types of lines. |
3. Open the **Default Transactions** FastTab and fill the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] The table below describes some of the key fields:

   | Field | Description |
   | --- | --- |
   | **Default Trans. Type** | Specifies the default transaction type for regular sales shipments, service shipments, and purchase receipts. |
   | **Default Trans. Type – Returns** | Specifies the default transaction type for sales returns, service returns, and purchase returns. |
   | **Default Private Person VAT No.** | Specifies the default private person VAT number in case the private person must have a dedicated VAT number on the Intrastat report. |
   | **Default 3-Party Trade VAT No.** | Specifies the default 3-party trade VAT number in case you don't have its VAT number. |
   | **Default VAT for Unknown State** | Specifies the default VAT number for an unknown state. |
   | **Default Country/Region Code** | Specifies the default receiving country code. |
4. Open the **Reporting** FastTab and fill the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] The table below describes some of the key fields:

   | Field | Description |
   | --- | --- |
   | **Data Exch. Def. Code** | Specifies the data exchange definition code to generate the Intrastat file. It works only if the **Split Receipts/Shipments Files** field is set as **No**. |
   | **Split Receipts/Shipments Files** | Specifies if receipts and shipments shall be reported in two separate files. |
   | **Zip File(-s)** | Specifies if the report file(-s) shall be added to the .zip file. |
   | **Data Exch. Def. Code – Receipt** | Specifies the data exchange definition code to generate the Intrastat file for received goods. It works only if the **Split Receipts/Shipments Files** field is set as **Yes**. |
   | **Data Exch. Def. Code – Shipment** | Specifies the data exchange definition code to generate the Intrastat file for shipped goods. It works only if the **Split Receipts/Shipments Files** field is set as **Yes**. |
5. Open the **Numbering** FastTab to set up **Intrastat Nos**.

### Set up a reporting file

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Data Exchange Definitions** and then choose the related link.
2. Choose the **New** action.
3. On the **General** FastTab, describe the data exchange definition, the data file type, column separator, related codeunits, XMLport, and other fields by filling in the fields.
4. On the **Line Definitions** FastTab, describe the formatting of lines in the data file by filling the fields based on the **Line Type** field and where you need to define the number of columns for this line.
5. On the **Column Definitions** FastTab, fill in the line for each planned column. You can define column names, data types (*Text*, *Date*, or *Decimal*), length of the fixed-width line that holds the column if the file is of type Fixed Text, and some other parameters.
6. Choose the **Field Mapping** action on the **Line Definitions** FastTab to open the **Field Mapping** page.
7. Create the new entry, and on the **General** FastTab choose the proper **Table ID** (for **Intrastat Report Line**, choose 4812), then fill in more fields:
   1. Specify the key index to sort the source records before exporting in the **Key Index** field.
   2. Select the proper **Mapping Codeunit**.
8. On the **Field Mapping** FastTab, add columns you previously configured in the **Column Definitions** FastTab, then add the following:
   1. Specify the **Field ID** for each of the columns.
   2. Specify the **Transformation Rule** for each column you need it. It specifies the rule that transforms imported text to a supported value before it can be mapped to a specified field in [!INCLUDE[prod_short](includes/prod_short.md)]. When you choose a value in this field, the exact value is entered in the **Transformation Rule** field in the **Data Exch. Field Mapping Buf.** table and vice versa.
9. If you need to group entries based on some columns, on the **Field Grouping** FastTab, choose the fields you want to use for grouping.

> [!NOTE]
> [!INCLUDE[prod_long](includes/prod_long.md)] comes with the preconfigured data exchange definition for Intrastat for all localized countries. Learn more about creating a new data exchange definition at the [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md) article.

### Set mandatory fields with the Intrastat report checklist

In some countries, the authorities require that Intrastat reports include, for example, the shipment method for purchases or other values when sales are over a certain threshold.

To set mandatory fields and/or values on the **Intrastat Report** page:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Intrastat Report Setup**, then choose the related link.
2. Choose the **Intrastat Report Checklist** action.
3. Add the necessary lines for checking using the following instructions:
   1. Set the **Field No.** field to a field that must be checked for a non-empty value.
   2. Fill the **Filter Expression** field if needed, based on the following rules:
      1. When you open the **Filter Page**, choose the **Filter** you need to use for checking.
      2. On the next step, choose a value related to the **Filter** you used.
      3. If you have more filters you need to fill for this specific field, you can add another filter by following the same steps.
      4. When you finish entering the filters for the chosen field, choose **OK**.
   3. Select the **Reversed Filter Expression** field to specify that the check for fields is run only on those lines that do not match the filter expression. If the line is not filtered, this field is ignored.

> [!NOTE]
> When you open the **Filter Page** from the **Filter Expression** line, you can use all standard filter expressions related to the specific field you want to filter.
>
> Be careful with setting up validation rules, as they can differ from country to country.

## Use custom codeunits in Intrastat reporting

If you want to change how Intrastat works and the default configuration is not enough, you can customize the system by extending the standard features. If you need to further change the Intrastat behavior, you can develop your own codeunits. When you create codeunits, however, you need to make additional changes to use them. To configure the system to use your own objects:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Reports Configuration**, then choose the related link.
2. On the **VAT Reports Configuration** page, add a new line.
3. On the **VAT Report Type** field, choose the **Intrastat Report** option.
4. On the **VAT Report Version** field, specify the version of the report.
5. After that, you can add your codeunits for the following options:
   a. On the **Suggest Lines Codeunit ID** field, specify the new codeunit for suggesting lines in the Intrastat report lines.
   b. On the **Content Codeunit ID** field, specify the new codeunit for exporting data as a file using a Data Exchange Definition.
   c. On the **Validate Codeunit ID** field, specify the new codeunits for validating results inside Intrastat report lines.

> [!IMPORTANT]
>
> This line must be empty if you use the standard codeunits. You should only create a line and configure it if you have developed custom codeunits.

## Other Intrastat configurations

> [!IMPORTANT]
> Customer and vendor cards include a field, **Intrastat Partner Type**, that has the same option values as the **Partner Type** field: "" (blank), *Company*, and *Person*. The **Intrastat Partner Type** field has replaced the **Partner Type** field in Intrastat reporting. The **Partner Type** field is used in the Single Euro Payments Area (SEPA) to define the SEPA Direct Debit Scheme (Core or B2B). The **Intrastat Partner Type** field is used for Intrastat reporting only. This way, you can specify different values for the two fields if necessary.
>
> If the **Intrastat Partner Type** field is left blank, the value from the **Partner Type** field is used for Intrastat reporting.

Except for **Intrastat Report Setup**, **Data Exchange Definitions**, and **Intrastat Report Checklist**, you also need to configure other settings:

| Page | Description |
| ---- | ----------- |
| **Countries/Regions** | Before starting using Intrastat reports, you must also set up the **Countries/Regions** page. On this page, you must add the **EU Country/Region Code** and **Intrastat Code** to specify a code for the country/region you are trading with, as it will be used in Intrastat reporting. |
| **Tariff Numbers** | In many countries, the customs and tax authorities establish 8-digit codes for various items. In order for item entries to contain the necessary information when the program imports them to the Intrastat journal line, you must enter the item code on the **Tariff Numbers** page. Find the codes for the items that your company deals with and enter them on the **Tariff Numbers** page. |
| **Transport Methods** | There are seven one-digit codes for Intrastat transport methods. **1** for sea, **2** for rail, **3** for road, **4** for air, **5** for the post, **7** for fixed installations, and **9** for own propulsion (for example, transporting a car by driving it). [!INCLUDE[prod_short](includes/prod_short.md)] does not require these specific codes; however, we recommend that the descriptions provide a similar meaning. |
| **Transaction Types** | Countries and regions have different codes for types of Intrastat transactions, such as ordinary purchase and sale, exchange of returned goods, and exchange of non-returned goods. Set up all the codes that apply to your country/region. These codes are then used on the **Foreign Trade** FastTab on sales and purchase documents and when you process returns. |
| **Transaction Specifications** | Set up codes to supplement the transaction type descriptions. |
  > [!NOTE]
  > Starting in January 2022, Intrastat requires different transaction nature codes for dispatches to private individuals or non-VAT registered businesses and VAT registered businesses. To comply with this requirement, we recommend that you review and/or add new transaction nature codes on the **Transaction Types** page according to the requirements in your country. You should also check and update the **Intrastat Partner Type** field to *Person* for a private individual or non-VAT registered business customers on the relevant **Customer** page. If you are unsure about the correct Intrastat partner type or transaction type to use, we recommend that you ask an expert in your country or region.

| **Field** | **Description** |
| --------- | --------------- |
| **Net Weight** | Weight is one of the basic configurations related to Intrastat reporting as the **Total Weight** is mandatory for reporting. To be ready for this requirement, you must also fill in the **Net Weight** field on the item or fixed asset card. |
| **Country of Origin Code** | Use the two-letter ISO Alpha Codes on the item or fixed asset card for the country where the good was obtained or produced. If the good was produced in more than one country, the country of origin is the last country where it was significantly processed. |
| **VAT identification number of the partner operator in the Member State of import** | This is the VAT-ID number of the partner operator in the Member State of import. The VAT-ID is also used in the exchange of intra-EU-export data among the Member States and allows the Member States to allocate the received data to the importing company in their own country. Reporting units must report on the VAT-ID of the company that declared the intra-Union acquisition of goods in the Member State of import. |

Optionally, you can also set up:

* **Commodity codes**: Customs and tax authorities have established numerical codes that classify items and services. You specify these codes on items.
* **Areas**: Supplementary information about countries and regions.
* **Entry/exit points**: Specify the locations where you ship or receive items to or from other countries. An airport is an example of an entry or exit point. You enter entry or exit points on sales and purchase documents on the **Foreign Trade** FastTab. This information will also be copied from the item entries when you create the Intrastat journal.
* **Supplementary unit of measure**: The quantity of goods for Intrastat reporting can be either net weight (in kilograms) or a supplementary unit. If supplementary units are required, you must configure them for items and fixed assets.

#### Set up transport methods

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transport Methods**, then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

#### Set up transaction nature codes

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transaction Types**, and choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### Other related configurations

Before using the Intrastat reporting feature you need to configure some fields on the item, fixed asset, customer, and vendor cards.

#### Item cards

To set up all necessary information related to Intrastat on item cards:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, then choose the related link.
2. Select the item you want to configure.
3. Expand the **Costs & Posting** FastTab and fill the **Tariff No.**, **Supplementary Unit of Measure**, and **Country/Region of Origin Code** fields.
4. Expand the **Inventory** FastTab and enter the decimal value in the **Net Weight** field.

> [!NOTE]
> You can use different units of measure as your supplementary unit of measure. If this is not the same as the **Base Unit of Measure**, you need to configure this unit of measure on the **Item Units of Measure** page.

#### Fixed asset cards

To set up all necessary information related to Intrastat on fixed assets cards:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, then choose the related link.
2. Select the fixed asset you want to configure.
3. Expand the **Intrastat** FastTab and fill the **Tariff No.**, **Net Weight**, and **Supplementary Unit of Measure** fields.

> [!NOTE]
> You can use different units of measure as your supplementary unit of measure. But whatever **Unit of Measure Code** you choose, its **Quantity** in Intrastat reports will always be 1.

#### Vendor cards

Before using a vendor in Intrastat reporting, you must have a dedicated **Country/Region Code** and **VAT Registration No.** for each of them, in addition to further information on their **Vendor Card** page:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, then choose the related link.
2. Select the vendor you want to configure.
3. On the **Intrastat** FastTab, you can set default values for the **Default Trans. Type**, **Default Trans. Type - Returns**, and **Default Transport Method** fields.
4. Expand the **Payments** FastTab, and choose the option in the **Intrastat Partner Type** field to specify if the vendor is a person or a company in Intrastat reporting.

#### Customer cards

Before using a customer in Intrastat reporting, you must have a dedicated **Country/Region Code** and **VAT Registration No.** for each of them, in addition to further information on their **Customer Card** page:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, then choose the related link.
2. Select the customer you want to configure.
3. On the **Intrastat** FastTab, you can set default values for the **Default Trans. Type**, **Default Trans. Type - Returns**, and **Default Transport Method** fields.
4. Expand the **Payments** FastTab, and choose the option in the **Intrastat Partner Type** field to specify if the vendor is a person or a company in Intrastat reporting.

#### Exclude items and fixed assets from Intrastat reporting

If there is a reason for a specific item or fixed asset to be excluded from Intrastat reporting, you need to change an option on their card.

##### Exclude an item from Intrastat reporting

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, then choose the related link.
2. Select the item you want to configure.
3. Expand the **Cost & Posting** FastTab, then select the **Exclude from Intrastat Report** field.

##### Exclude a fixed asset from Intrastat reporting

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, then choose the related link.
2. Select the fixed asset you want to configure.
3. Expand the **Intrastat** FastTab, then select the **Exclude from Intrastat Report** field.

## Country-specific Intrastat setup

<!-- PM's note: Currently, we will add only the 'Overview' topic; the topic 'Manage Intrastat Country Specifics' and country details will wait until 21.1 when I update with all country-based details -->

The Intrastat requirements are similar in all member states of the EU, although there are important exceptions. In theory, the rules should be uniformly applied in all member states. However, there are differences in implementation because some member states provide guidelines on how the general principles in the regulation should be applied in specific situations (for example, commercial samples, return of goods, etc.). These guidelines may produce different results for various situations in EU member states. Because of that, some countries have some extra specific information separate from other countries, and they also have a different file format for reporting.

## See related training at [Microsoft Learn](/learn/modules/process-intrastat-dynamics-365-business-central/index).

## See also

[Intrastat Reporting in Business Central](finance-how-report-intrastat.md)  
[Financial Management](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
