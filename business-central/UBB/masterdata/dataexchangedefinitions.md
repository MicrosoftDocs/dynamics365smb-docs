---
title: Data Exchange Definitions
hide_title: true
sidebar_label: Data Exchange Definitions
slug: /ubb/masterdata/dataexchangedefinitions
---

# Data Exchange Definitions
This is a standard functionality of Business Central, which is explained in <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/across-how-to-set-up-data-exchange-definitions" title="Set Up Data Exchange Definitions">this part</a> of the Microsoft documentation. However, since it is fundamental to the import and subsequent processing of usage data, at least the aspects relevant to **DYCE Usage Base Billing** will be summarized again here.

:::info Example
The Data Exchange Definition described here as an example refers to an import file for usage data, which is a CSV file in UTF-8 encoding with column separators as semicolons. <br/>
However, the Data Exchange Definitions provide much more functionality beyond that, such as exporting data.
:::


## Definition for data import
For later billing usage data must first be [imported](/docs/ubb/processing-usage-data/imports-processing.md#process-import-usage-data) and then [processed](/docs/ubb/processing-usage-data/imports-processing.md#process-process-usage-data). In order for the system to properly extract the data from the reconciliation file, it needs a schema of exactly how the data exists. This schema is stored at the [usage data supplier](/docs/ubb/masterdata/suppliers.md#settings-on-the-supplier).

:::note Note
With the installation of **DYCE Usage Based Billing** the Data Exchange Definition *DYCE-UBB* is delivered as a sample. However, this must be adapted to your own circumstances. Data Exchange Definitions can be exported and imported via the respective actions.
:::

The Data Exchange Definitions can be called up via the menu or the search (*Alt+Q*). <br/>
The page consists of three parts:
* **General** <br/>
    In this part, settings are made that affect the import file itself. The most important fields are: <br/>
    * **File Type** <br/>
    For the import of usage data, *Variable Text* is usually selected here.
    * **Type** <br/>
    For the import of usage data, *Generic Import* is usually selected here.
    * **File Encoding** <br/>
    The encoding of unicode characters for the import file is selected here.
    * **Column Separator** <br/>
    This specifies the separator character used to separate the columns in the import file. This is only relevant for the *Variable Text* file type.
    * **Header Lines** <br/>
    This sets how many header lines the import file contains. This ensures that the header data is not imported.
* **Column Definitions** <br/>
    Inexperienced users of Data Exchange Definitions may find it confusing that this fast tab is displayed *at the bottom* of the page, as this must be filled *prior* to the related line definitions. <br/>
    This is where the columns to be imported are defined:
    * The **Column No.** field specifies the number of the column in the import file.
    * The **Name** field specifies the name of the column. For reasons of clarity, it is advisable to use the same name as in the header of the import file.
    * The **Data Type** specifies whether the data to be imported is of type *Text*, *Date* or *Decimal*.
    * The **Data Format** refers primarily to data of type=*Date*. The formatting of the date in the associated field is specified here. For a date in US format, the value *MM-DD-YYYY* must be specified here.
    * In the field **Data Formatting Culture** the culture of the data format is specified, if necessary. For example, *en-US* for the data type *decimal* indicates that the period is used as decimal separator according to US format.
    * The field **Length** is only relevant if the file type is set to *Fixed Text*.
    * The remaining fields are not required for the import described here.
* **Line Definitions** <br/>
    In this fast tab only one line has to be defined, so that afterwards the mapping between the columns of the import file and the fields of the target table can be done via the **Field Mapping**. As **Line Type** *Detail* is selected, a unique **Code** and a **Description** are assigned and the number of columns to be processed (imported) is specified in **Column Count**. The automatically created line of **Line Type**=*Header* is deleted. <br/>
    Subsequently, the following settings must be made via the **Field Mapping** action: <br/>
    * First, a new mapping must be created via the *PLUS* icon.
    * As **Table ID** the number *70921110* is entered. This is the *Imported Lines* for the *Generic* import type.
    * In the field **Name** a speaking name should be assigned.
    * The number *70921104* is entered as the **Mapping Codeunit**. The codeunit will be used for the *Generic* import type when generating the *Imported Lines*.
    * In the **Column No.** field, a column specified via the *Column Definitions* can be selected and assigned to a target field via the **Field ID** (in the table specified in **Table ID**).
    * The **Overwrite Value** field indicates that field contents in the target table can be overwritten if necessary. It is recommended that this be set for the *Subscription ID*, *Product ID*, *Product Name*, and *Quantity* fields.
    * The remaining fields are not required for the import described here.