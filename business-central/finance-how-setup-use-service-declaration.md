---

title: Set Up and Use the Service Declaration Extension
description: Learn how to set up and use Service Declaration (Intrastat for Services) features to report service trade with companies in other EU countries/regions.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 12/21/2022
ms.custom: bap-template
ms.search.keywords: electronic document, Intrastat, trade, EU, service, declaration, 
ms.search.form: 30, 76, 5010, 5022, 5023, 5024, 5800
---
# The Service Declaration Extension

In some EU countries/regions, authorities require that businesses report the export of services to other EU countries/regions. The **Service Declaration** extension lets you collect information about service trade in the EU and report it to the authorities. Although its name is **Service Declaration**, you can also use it as **Intrastat for Services**. This extension is available for all EU countries/regions as a W1 version, and it can be used as-is in Belgium. For other countries/regions, an extension based on the country/region is required. If a country/region only needs a different format, you can use the report configuration in the **Data Exchange Framework** to change the format.

## Enable the Service Declaration extension

After you install the extension in your environment, you need to enable it.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Set up an IRS 1096 feature**, and then choose the related link.
2. Follow steps in the assisted setup guide. The most of fields are configured by default.
3. Add only **Service Transaction Types** in the second step by choosing the **Open the service transaction types page to specify the list of codes** option.
4. Before you start, check the **Total number of codes** to understand how many service transaction types are already specified.
5. Choose **Finish** in the last step to finish the configuration.

## Set up the Service Declaration extension

You can set up the extension manually, or by using a reporting file on the **Data Exchange Definitions** page.

### To set up Service Declaration manually

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Declaration Setup**, and then choose the related link.
2. On the **General** FastTab, configure the fields described in the following table:

    |Field  |Description  |
    |---------|---------|
    |**Declaration No. Series**     | Specifies the number series to use to assign IDs to new records.        |
    |**Report Item Charges**  | Specifies whether item charges must be reported. If enabled, [!INCLUDE [prod_short](includes/prod_short.md)] checks the service transaction code for item charges and includes them in service declarations.        |
    |**Sell-To/Bill-To Customer No.**     | Specifies the customer to use to compare their country code with the country code on the **Company Information** page. Only documents where these two codes are different are included in the service declaration.<br><br>* **Bill-To.**: Use the country code from the **Bill-to Customer** <br<br>* **Sell-To.**: Use the country code from the **Sell-to Customer**.        |
    |**Buy-From/Pay-To Vendor No.**  | Specifies which vendor to use to compare their country code with the country code from the **Company Information** page. Only documents where these two codes are different are included in the service declaration.<br><br> * **Buy-From.**: Use the country code from the **Buy-From Vendor**. <br><br> * **Pay-To.**: Use the country code from the **Pay-To Vendor**.         |
    |**Data Exch. Def. Code**  | Specifies the data exchange definition code used to generate the exported file for the service declaration.        |
    |**Enable Tax Registration No.**     |  Specifies whether the **Tax Registration No.** is enabled for the service declaration.       |

3. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Transaction Types**, and then choose the related link.
4. On the lines, specify **Codes** and **Descriptions** for the service transaction types you use.

### Set up a reporting file

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Data Exchange Definitions**, and then choose the related link.
2. Choose the **New** action.
3. On the **General** FastTab, describe the data exchange definition by specifying the data file type, column separator, related codeunits, XMLport, and filling in the other fields.
4. On the **Line Definitions** FastTab, describe the formatting of lines in the data file by filling the fields based on the **Line Type** field and where you need to define the number of columns for this line.
5. On the **Column Definitions** FastTab, fill in the line for each planned column.
6. Choose the **Field Mapping** action on the **Line Definitions** FastTab to open the **Field Mapping** page.
7. Create a new entry, and on the **General** FastTab, choose the **Table ID** (for **Service Declaration Line**, choose **5024**), and then fill in the fields as follows:
   1. In the **Key Index** field, specify the key index to sort the source records by before exporting.
   2. Select the **Mapping Codeunit**.
8. On the **Field Mapping** FastTab, add the columns you previously configured in the **Column Definitions** FastTab, and then add the following:
   1. Specify the **Field ID** for each of the columns.
   2. Specify the **Transformation Rule** for each column as needed. The rule transforms imported text to a supported value before it can be mapped to a specified field in [!INCLUDE[prod_short](includes/prod_short.md)]. When you choose a value in this field, the exact value is entered in the **Transformation Rule** field in the **Data Exch. Field Mapping Buf.** table, and vice versa.
9. To group entries based on columns, choose the fields to use for grouping on the **Field Grouping** FastTab.

> [!NOTE]
> [!INCLUDE[prod_long](includes/prod_long.md)] comes with a preconfigured data exchange definition for **Service Declaration** for all localized countries/regioins. Learn more about creating a new data exchange definition at [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).

## Other related configurations

Before using the Service Declaration extension, configure some fields for items, resources, and item charges.

### Items

Set up information related to Service Declaration on Item Card pages:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, then choose the related link.
2. Select the item you want to configure.
3. Expand the **Item** FastTab, and configure the following fields:
   1. In the **Type** field, choose **Service**.
   2. In the **Service Transaction Type Code** field, specify the code for a **Service transaction type**.
   3. If you don’t want to include this service item in service declarations, choose the **Exclude From Service Declaration** field.

### Resources

Set up information related to Service Declaration on Resource Card pages:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Resources**, then choose the related link.
2. Select the resource you want to configure.
3. Expand the **General** FastTab, and configure the following fields:
   1. In the **Service Transaction Type Code** field, specify the code for a **Service transaction type**.
   2. If you don’t want to include this resource in service declarations, choose the **Exclude From Service Declaration** field.

### Item Charges

Set up information related to Service Declaration for item charges:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Charges**, then choose the related link.
2. Select the item charge you want to configure.
3. In the **Service Transaction Type Code** field, specify the code for a **Service transaction type**.
4. If you don’t want to include this item charge in service declarations, select the **Exclude From Service Declaration** field.

## Create new service declaration

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Declarations**, and then choose the related link.
2. Choose the **New** action.
3. On the **General** FastTab, fill in the following fields:
    1. In the **Config. Code** field, specify the configuration code that is used to suggest lines and create files. You need to choose one as a **Service Declaration**.
    2. In the **Starting Date** and **Ending Date** fields, specify the start and end dates of the period to include in the service declaration.
4. Choose the **Suggest lines** action to start a batch job that collects lines from documents and fills in the service declaration lines.

The batch job retrieves all entries from applicable purchase and sales documents in the required period and adds them on the service declaration lines. Hover over fields in lines to read a short description.

## Modify a service declaration

If needed, you can modify the lines or add new ones.

1. On the **Service Declaration** page, choose the **New Line** action in the **Lines** FastTab.
2. In the **Document Type** field, choose the option related to the document you want to use.
3. Based on the **Document Type**, fill in the **Document No.** field.
4. Fill in the remaining fields.

## Overview the service declaration lines

After you create a service declaration, use the **Overview** action to get an overview of the service declaration lines. You can group and summarize the lines in the same way as the exported file. You can also open the lines in Excel.

## Report Service Declaration in a file

You can submit the service declaration as a file based on different local authorities' requirements. To create a file:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Declarations**, then choose the related link.
2. Choose the service declaration you want to report as a file.
3. Fill in the service declaration manually, or choose the **Suggest Lines** action.
4. Choose the **Create File** action.
5. The service declaration file is saved in the required format.

## Other considerations

When you're using the **Service Declaration** extension, there are a few more things to consider. For example, it's important that your groups match requirements from authorities. It's also important that services are included correctly on sales and purchase documents.

### Grouping lines

On service declaration lines, there's no grouping by any field. All entries are copied from the original document as a source.

Grouping required by authorities is provided in the exported file. You must configure the groups in the **Data Exchange Definition**, which is fully configurable. Learn more at [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).

### Using services in document lines

When you create a purchase, sales, or service  invoice, there are two fields related to service declarations on their lines. Both fields are filled in with the default values from your item, resource, or item charge set ups.

- **Service Transaction Type Code** - Specifies the code for a service transaction type.
- **Applicable For Service Declaration** - Specifies whether an item or resource is applicable for a service declaration.

You can change the values in these fields, but if you select the **Applicable For Service Declaration** field, you must specify a value in the **Service Transaction Type Code** field. If you don't, you can't post the document.

If you specify a value in the **Service Transaction Type Code** field but don’t select the **Applicable For Service Declaration** field, you can post the document, but the line isn't calculated.

## Related information

[Set Up Intrastat Reporting](finance-how-setup-report-intrastat.md)
[Intrastat Reporting in Business Central](finance-how-report-intrastat.md)  
[Financial Management](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
