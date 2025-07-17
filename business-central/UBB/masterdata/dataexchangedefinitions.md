---
title: Data exchange definitions
description: You can use data exchange definitions in usage-based billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Data exchange definitions

Data exchange is a standard feature in [!INCLUDE [prod_short](../../includes/prod_short.md)]. To learn more about data exchange and data exchange definitions, go to [Set up data exchange definitions](../../across-how-to-set-up-data-exchange-definitions.md). 

Data exchange definitions are fundamental to import and process data in usage-based billing. This article summarizes the key aspects.

The data exchange definition example in this article refers to an import file for usage data. It's a CSV file in UTF-8 encoding with column separators as semicolons. To learn more, go to [Import data in usage-based billing](../processing-usage-data/imports-processing.md).

## Definition for data import

For billing, you must first import and process data. To learn more, go to [Imports and processing](../processing-usage-data/imports-processing.md). For [!INCLUDE [prod_short](../../includes/prod_short.md)] to extract the data from the CSV file, it needs the data's schema. The schema is available on the [usage data supplier](suppliers.md).

> [!NOTE]
> Usage-based billing provides the **USAGEBASED** data exchange definition as an example. You can use the definition, but you must adapt it to your setup. You can import and export data exchange definitions on the **Data Exchange Definition** page by using the **Import Data Exchange Definition** and **Export Data Exchange Definition** actions.

The **Data Exchange Definitions** page has the following FastTabs:

* General
* Line Definitions
* Column Definitions

> [!NOTE]
> Although the **Line Definitions** FastTab is higher on the page, fill in the fields on the **Column Definitions** FastTab before you enter information on the **Line Definitions** FastTab.

## Settings on the General FastTab

These settings affect the import file. The following table describes the important fields.

|Field  |Description  |
|---------|---------|
|File Type|For importing usage data, businesses typically choose **Variable Text**.|
|Type|For importing usage data, businesses typically choose **Generic Import**.|
|File Encoding|The encoding of unicode characters for the import file.|
|Column Separator|Specifies the character that separates the columns in the import file. This is only relevant for the **Variable Text** file type.|
|Header Lines|Sets how many header lines the import file contains. This ensures that the header data isn't imported.|

## Settings on the Line Definitions FastTab

On this FastTab, you only have to define one line, so that you can use the **Field Mapping** action to create the mapping between the columns of the import file and the fields of the target table. If you choose **Detail** in the **Line Type** field, a unique **Code** and a **Description** are assigned and the number of columns to process (import) is specified in **Column Count**. The default line with the **Header** line type is deleted.


## Settings on the Field Mapping page

After you fill in the fields on the **Column Definitions** FastTab, and create a line on the **Line Definitions** FastTab, you can set up the field mappings. On the **Line Definitions** FastTab, choose the **Field Mapping** action, and enter the following settings on the **Field Mapping** page. 

On the **General** FastTab, fill in the fields as follows:

   * The **Table ID** field should contain **8018**. This is the **Usage Data Generic Import** table.
   * The **Name** field should contain a name.
   * The **Mapping Codeunit** field should contain **8030**. This is the **Generic Import Mappings** codeunit to use for the generic import type when you generate imported lines.
    
On the **Field Mapping** FastTab, fill in the fields as follows:
    
   * The **Column No.** field specifies a column definition, and the **Field ID** field specifies a target field from the table specified in the **Table ID** field.
   * The **Overwrite Value** checkbox indicates that field contents in the target table can be overwritten, if needed. We recommended that you select this checkbox for the **Subscription ID**, **Product ID**, **Product Name**, and **Quantity** fields, as described in the following table.

The following table provides a complete example of a setup on the **Field Mapping** FastTab on the **Field Mapping** page.

|Column No.  |Column Caption  |Field ID  |Field Caption  |Optional  |Transformation Rule  |Overwrite Value  |Priority  |
|---------|---------|---------|---------|---------|---------|---------|---------|
|2    | Customer ID   |  7       |   Customer ID      | |No |No | 0|
|3    | Customer Name |  8       |   Customer Name      | |No | No| 0|
|7    | Subscription ID |10      |   Subscription ID      | |No | Yes | 0|
|8    | Product ID    |  17      |   Product ID      | |No | Yes| 0|
|10   | Product Name |   18      |    Product Name     | |No | Yes| 0|
|11   | Subscription Start Date  |  13  | Subscription Start Date| |No | No| 0|
|12   | Subscription End Date    | 14  | Subscription End Date  | |No | No| 0|
|13   | Billing Period Start Date| 15 | Billing Period Start Date | |No | No| 0|
|14   | Billing Period End Date  | 16  | Billing Period End Date  | |No | No| 0|
|16   | Cost        |  19      |   Unit Cost      | |No | No| 0|
|17   | Quantity    |  21      |  Quantity        | |No | Yes| 0|
|18   | Price       |  20      |  Unit Price      | |No | No| 0|
|19   | Amount      |  24      |  Amount          | |No | No| 0|
|22   | Cost Amount |   27     |  Cost Amount     | |No | No| 0|
|23   | Currency    |  25      |  Currency        | |No | No| 0|
|24   | Text1       | 20       |  Text1           | | No| No| 0|

## Settings on the Column Definitions FastTab

The following table describes the settings that define the columns to import.

|Field  |Description  |
|---------|---------|
|Column No.     | Specifies the number of the column in the import file.        |
|Name     |  Specifies the name of the column. To keep things simple, we recommend that you use the name from the header of the import file.       |
|Data Type     | Specifies whether the data to import is a **Text**, **Date** or **Decimal**.        |
|Data Format     | Refers primarily to data of the **Date** data type. The field specifies how to format dates. For example, for a date in US format, the value should be **MM-DD-YYYY**.        |
|Data Formatting Culture     | Specifies the culture of the data format, if needed. For example, **en-US** for the **Decimal** data type indicates that a period is used as decimal separator according to US format.        |
|Length     | Only relevant if the file type is set to **Fixed Text**.        |

## Related information

[Imports and processing](../processing-usage-data/imports-processing.md)
