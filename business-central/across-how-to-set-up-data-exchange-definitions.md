---
title: Define how data is exchanged electronically
description: Define how Business Central exchange data with external files like electronic documents, bank data, item catalogs and more.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.search.keywords: data exchange, data exchange definition, data exchange mapping
ms.search.form: 1210, 1211, 1213, 1214, 1215, 1216, 1217
ms.date: 10/16/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Set up data exchange definitions

You can set up [!INCLUDE[prod_short](includes/prod_short.md)] to exchange data in specific tables with data on external files. For example to send and receive electronic documents, import and export bank data or other data, such as payroll, and item catalogs. Learn more at [Exchanging Data Electronically](across-data-exchange.md).  

To create a data exchange definition for a data file or stream, you can use the related XML schema to define which data elements to include on the **Column Definitions** FastTab. Refer to step 6 in [To describe the formatting of lines and columns in the file](across-how-to-set-up-data-exchange-definitions.md#to-describe-the-formatting-of-lines-and-columns-in-the-file). Learn more at [Use XML Schemas to Prepare Data Exchange Definitions](across-how-to-use-xml-schemas-to-prepare-data-exchange-definitions.md).  

Normally, you set up data exchange definitions on the **Data Exchange Definition** page. However, for updating currency exchange rates, it's faster to use a currency exchange rate service. Learn more at [Update Currency Exchange Rates](finance-how-update-currencies.md#set-up-a-currency-exchange-rate-service).

> [!NOTE]  
> If the file that's being converted is in the XML format, the term *"column"* in this article should be interpreted as an *"XML element containing data"*.  

This article includes the following procedures:  

* Create a data exchange definition.
* Export a data exchange definition as an XML file for use by others.
* Import an XML file for an existing data exchange definition.

## Create a data exchange definition

Creating a data exchange definition involves two tasks:  

1. On the **Data Exchange Definition** page, describe the formatting of lines and columns in the file. Learn more in the [To describe the formatting of lines and columns in the file](#formatlinescolumns) section.  
2. On the **Data Exchange Mapping** page, map columns in the data file to fields in [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more in the [To map columns in the data file to fields in [!INCLUDE[prod_short](includes/prod_short.md)]](#mapfields) section.  

### <a name=formatlinescolumns></a>To describe the formatting of lines and columns in the file

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Data Exchange Definitions**, then choose the related link.  
2. Choose the **New** action.  
3. On the **General** FastTab, describe the data exchange definition and the data file type by filling the fields as described in the following table.  

    |Field|Definition|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Enter a code to identify the data exchange definition.|  
    |**Name**|Enter a name for the data exchange definition.|  
    |**File Type**|Specify what type of file the data exchange definition is used for. You can select between four file types:<br /><br /> -   **XML**: Layered strings of content and markup surrounded by tags indicating function.<br />-   **Variable Text**: Records have variable length and are separated by a character, such as a comma or semi\-colon, also known as *delimited file*.<br />-   **Fixed Text**: Records have the same length, using pad characters, and each record is on a separate line, also known as *fixed-width file*.<br />- **Json**: Layered strings of content in JavaScript.|  
    |**Type**|Specify what type of business activity the data exchange definition is used for, such as **Payment Export**.|  
    |**Data Handling Codeunit**|Specify the codeunit that transfers data in and out of tables in [!INCLUDE[prod_short](includes/prod_short.md)].|  
    |**Validation Codeunit**|Specify the codeunit that is used to validate data against predefined business rules.|  
    |**Reading/Writing Codeunit**|Specify the codeunit that processes imported data before mapping and the exported data afterward.|  
    |**Reading/Writing XMLport**|Specify the XMLport through which an imported data file or service enters before mapping, and through which exported data is written to a data file or service afterward.|  
    |**Ext. Data Handling Codeunit**|Specify the codeunit that transfers external data in and out of the data exchange framework.|  
    |**User Feedback Codeunit**|Specify the codeunit that does various clean-up after mapping, such as marks the lines as exported and deletes temporary records.|  
    |**File Encoding**|Specify the encoding of the file. **Note:** This field is only relevant for import.|  
    |**Column Separator**|Specify how columns in the data file are separated, if the file is of type **Variable Text**.|  
    |**Header Lines**|Specify how many header lines exist in the file.<br /><br /> This setting makes sure that the header data isn't imported. **Note:** This field is only relevant for import.|  
    |**Header Tag**|If a header line exists in several positions in the file, enter the text of the first column on the header line.<br /><br /> This option makes sure that the header data isn't imported. **Note:** This field is only relevant for import.|  
    |**Footer Tag**|If a footer line exists in several positions in the file, enter the text of the first column on the footer line.<br /><br /> This option makes sure that the footer data isn't imported. **Note:** This field is only relevant for import.|  

   > [!TIP]
   > To review which codeunits Microsoft uses in existing definitions in the standard product, explore the three **Codeunit** fields on the **Field Mapping** page for each definition.  

4. On the **Line Definitions** FastTab, describe the formatting of lines in the data file by filling the fields as described in the following table.  

    > [!NOTE]  
    > For import of bank statements, you only create one line for the single format of the bank statement file that you want to import.  
    >
    > For export of payments, you can create a line for each payment type that you want to export. In that case, the **Column Definitions** FastTab shows different columns for each payment type.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Line Type**|Specifies the type of the line in the file.|  
    |**Code**|Enter a code to identify the line in the file.|  
    |**Name**|Enter a name that describes the line in the file.|  
    |**Column Count**|Specify how many columns the line in the data file has. **Note:** This field is only relevant for import.|  
    |**Data Line Tag**|Specify the position in the related XML schema of the element that represents the main entry of the data file. **Note:** This field is only relevant for import.|  
    |**Namespace**|Specify the namespace that's expected in the file to enable namespace validation. You can leave this field blank if you don't want to enable namespace validation.|  
    |**Parent Code**|Specify the line's parent, as displayed in the **Code** field in cases where the data exchange setup is for files with parent and children entries, such as a document header and lines.

5. Repeat step 4 to create a line for every type of file data that you want to export.  

     Proceed to describe the formatting of columns in the data file by filling the fields on the **Column Definitions** FastTab as described in the table in step 8. You can use a structure file, such as an .xsd file, for the data file to prefill the FastTab with the relevant elements. Learn more at [Use XML Schemas to Prepare Data Exchange Definitions](across-how-to-use-xml-schemas-to-prepare-data-exchange-definitions.md).

6. On the **Column Definitions** FastTab, choose the **Get File Structure** action.  
7. On the **Get File Structure** page, select the related structure file, then choose **OK**. The lines on the **Column Definitions** FastTab are filled according to the structure of the data file.  
8. On the **Column Definitions** FastTab, edit or fill the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Column No.**|Specify the number that reflects the column's position on the line in the file.<br /><br /> For XML files, specify the number that reflects the type of element in the file that contains the data.|  
    |**Name**|Specify the name of the column.<br /><br /> For XML files, specify the markup that marks the data to be exchanged.|  
    |**Data Type**|Specify if the data to be exchanged is of type **Text**, **Date**, or **Decimal**.|  
    |**Data Format**|Specify the format of the data, if any. For example, **MM-dd-yyyy** if the data type is **Date**. **Note:** For export, specify the data format according to [!INCLUDE[prod_short](includes/prod_short.md)]. For import, specify the data format according to the .NET Framework. Learn more at [Standard Date and Time Format Strings](/dotnet/standard/base-types/standard-date-and-time-format-strings).|  
    |**Data Formatting Culture**|Specify the regional data format, if any. For example, **en-US** if the data type is **Decimal** to make sure that comma is used as the 0.000 separator, according to the US format. Learn more at [Standard Date and Time Format Strings](/dotnet/standard/base-types/standard-date-and-time-format-strings). **Note:** This field is only relevant for import.|  
    |**Length**|Specify the length of the fixed-width line that holds the column if the data file is of type **Fixed Text**.|  
    |**Description**|Specifies a description of the column, for informational purposes.|  
    |**Path**|Specify the position of the element in the related XML schema.|  
    |**Negative-Sign Identifier**|Enter the value that is used in the data file to identify negative amounts, in data files that can't contain negative signs. This identifier is then used to reverse the identified amounts to negative signs during import. **Note:** This field is only relevant for import.|  
    |**Constant**|Specify any data that you want to export in this column, such as extra information about the payment type. **Note:** This field is only relevant for export.|  
    |**Text Padding Required**|Specify that the data must include text padding.|  
    |**Pad Character**|Specify the text padding character.|  
    |**Justification**|Specify if the column justification is left or right.|  

9. Repeat step 8 for every column or XML element in the data file that has data that you want to exchange with [!INCLUDE[prod_short](includes/prod_short.md)].  

The next step in creating a data exchange definition is to decide which columns or XML elements in the data file map to which fields in [!INCLUDE[prod_short](includes/prod_short.md)].  

> [!NOTE]  
> The specific mapping depends on the business purpose of the data file to be exchanged and on local variations. Even the SEPA bank standard has local variations. [!INCLUDE[prod_short](includes/prod_short.md)] supports import of SEPA CAMT bank statement files out\-of\-the\-box. This is represented by the **SEPA CAMT** data exchange definition record code on the **Data Exchange Definitions** page. To learn more about the specific field mapping of this SEPA CAMT support, go to [Field Mapping When Importing SEPA CAMT Files](across-field-mapping-when-importing-sepa-camt-files.md).  

### <a name=mapfields></a>To map columns in the data file to fields in [!INCLUDE[prod_short](includes/prod_short.md)]

> [!TIP]
> Sometimes the values in the fields that you want to map are different. For example, in one business app the language code for the United States is "U.S.," but in another it's "US." That means you must transform the value when you exchange data. This happens through transformation rules that you define for the fields. Learn more at [Transformation Rules](across-how-to-set-up-data-exchange-definitions.md#transformation-rules).

You can also group by any field, use the key index to sort results, and the new transformation types **Rounding** and **Field Lookup**.

1. On the **Line Definitions** FastTab, select the line for which you want to map columns to fields, then choose **Field Mapping**. The **Data Exchange Mapping** page opens.  
2. On the **General** FastTab, specify the mapping setup by filling the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Table ID**|Specify the table that holds the fields to or from which data is exchanged according to the mapping.|  
    |**Use as Intermediate Table**|Specify if the table that you select in the **Table ID** field is an intermediate table where the imported data is stored before it's mapped to the target table.<br/><br/> You typically use an intermediate table when the data exchange definition imports and converts electronic documents in [!INCLUDE[prod_short](includes/prod_short.md)]. For example, documents such as vendor invoices into purchase invoices. Learn more at [Exchanging Data Electronically](across-data-exchange.md).|  
    |**Name**|Enter a name for the mapping setup.|  
    |**Key Index**|Specify the key index to sort the source records before exporting.|
    |**Pre-Mapping Codeunit**|Specify the codeunit that prepares the mapping between fields in [!INCLUDE[prod_short](includes/prod_short.md)] and external data.|  
    |**Mapping Codeunit**|Specify the codeunit that is used to map the specified columns or XML data elements to fields in [!INCLUDE[prod_short](includes/prod_short.md)].|  
    |**Post-Mapping Codeunit**|Specify the codeunit that completes the mapping between fields in [!INCLUDE[prod_short](includes/prod_short.md)] and external data. **Note:** When you use the AMC Banking 365 Fundamentals extension, the codeunit converts exported data from [!INCLUDE[prod_short](includes/prod_short.md)] to a generic format that's ready for export. For import, the codeunit converts external data to a format that's ready for import into [!INCLUDE[prod_short](includes/prod_short.md)].|

3. On the **Field Mapping** FastTab, specify which columns map to which fields in [!INCLUDE[prod_short](includes/prod_short.md)] by filling the fields as described in the following tables, depending on whether the **Use as Intermediate Table** field is enabled.  
   * With the **Use as Intermediate Table** toggle off:

     |Field|Description|  
     |--------------------------------- |---------------------------------------|  
     |**Column No.**|Specify which column in the data file that you want to define a map for.<br /><br /> You can only select columns that are represented by lines on the **Column Definitions** FastTab on the **Data Exchange Definition** page.|
     |**Column Caption**|Specify the caption of the column in the external file that is mapped to the field in the **Target Table ID** field when you're using an intermediate table for data import.|
     |**Field ID**|Specify which field the column in the **Column No.** field maps to.<br /><br /> You can only select from fields that exist in the table that you specified in the **Table ID** field on the **General** FastTab.|
     |**Field Caption**|Specify the caption of the field in the external file that is mapped to the field in the **Target Table ID** field, when you're using an intermediate table for data import.|
     |**Optional**|Specify if the map should be skipped if the field is empty. If you don't select this option, then an export error occurs if the field is empty.|  
     |**Transformation Rule**|Specify the rule that transforms imported text to a supported value before it can be mapped to a specified field. When you choose a value in this field, the same value is entered in the **Transformation Rule** field in the **Data Exch. Field Mapping Buf.** table and vice versa. To learn more about how to apply transformation rules, go to [Transformation Rules](#transformation-rules).|
     |**Overwrite Value**|Specify that the new value can overwrite the current value.|
     |**Priority**|Specify the order that the field mappings must be processed. The field mapping with the highest priority number is processed first.|
     |**Multiplier**|Specify a multiplier to be applied on numeric data, including negative values.|

   * With the **Use as Intermediate Table** toggle enabled:

     |Field|Description|  
     |---------------------------------|---------------------------------------|  
     |**Column No.**|Specify which column in the data file that you want to define a map for.<br /><br /> You can only select columns that are represented by lines on the **Column Definitions** FastTab on the **Data Exchange Definition** page.|
     |**Column Caption**|Specify the caption of the column in the external file that is mapped to the field in the **Target Table ID** field when you're using an intermediate table for data import.|
     |**Target Table ID**|Specify the table that the value in the **Column Caption** field is mapped to, when you're using an intermediate table for data import.|
     |**Table Caption**|Specify the name of the table in the **Target Table ID** field, which is the table that the value in the **Column Caption** field is mapped to, when you're using an intermediate table for data import.|
     |**Target Field ID**|Specify the field in the target table that the value in the **Column Caption** field is mapped to, when you're using an intermediate table for data import.|
     |**Field Caption**|Specify the name of the field in the target table that the value in the **Column Caption** field is mapped to, when you're using an intermediate table for data import.|
     |**Validate Only**|Specify that the element-to-field map isn't used to convert data, but only to validate data.|
     |**Transformation Rule**|Specify the rule that transforms imported text to a supported value before it can be mapped to a specified field. When you choose a value in this field, the same value is entered in the **Transformation Rule** field in the **Data Exch. Field Mapping Buf.** table and vice versa. To learn more about transformation rules, go to [Transformation Rules](#transformation-rules).|
     |**Priority**|Specify the order that the field mappings must be processed. The field mapping with the highest priority number is processed first.|

4. On the **Field Grouping** FastTab, specify rules you want to use to group your fields when you create the file by filling the fields as described in the following table.  

     |Field|Description|  
     |--------------------------------- |---------------------------------------|  
     |**Field ID**|Specify the number of the field in the external file that is used for grouping, and that the user must set this field.|
     |**Field Caption**|Specify the caption of the field in the external file that is used for grouping.|

## Transformation Rules

If the values in the fields you're mapping differ, you must use transformation rules for data exchange definitions to make them the same. You define transformation rules for data exchange definitions by opening an existing definition, or creating a new definition, and then on the **Line Definitions** FastTab, choosing **Manage**, and then **Field Mapping**. Predefined rules are provided, but you can also create your own. The following table describes the types of transformations that you can perform.

|Option|Description|
|---------|---------|
|**Uppercase**|Capitalize all letters.|
|**Lowercase**|Make all letters lowercase.|
|**Title Case**|Capitalize the first letter of each word.|
|**Trim**|Remove empty spaces before and after the value.|
|**Substring**|Transform a specific portion of a value. To specify where to start the transformation, choose either a **Start Position** or **Starting Text**. The starting position is a number that represents the first character to transform. The starting text is the letter immediately before the letter to replace. If you want to start with the first letter in the value, use a starting position instead. To specify where to stop the transformation, you choose either **Length**, which is the number of characters to replace, or the **Ending Text**, which is the character that is immediately after the last character to transform.|
|**Replace**|Find a value and replace it with another. This transformation is useful for replacing simple values, such as a particular word.|
|**Regular Expression - Replace**|Use a regular expression as part of a find and replace operation. This transformation is useful for replacing multiple, or more complex, values.|
|**Remove Non-Alphanumeric Characters**|Delete characters that aren't letters or numbers, such as symbols or special characters.|
|**Date Formatting**|Specify how to display dates. For example, you can transform DD-MM-YYYY to YYYY-MM-DD.|
|**Decimal Formatting**|Define rules for decimal placement and rounding precision.|
|**Regular Expression - Match**|Use a regular expression to find one or more values. This rule is similar to the **Substring** and **Regular Expression - Replace** options.|
|**Custom**|This transformation rule is an advanced option that requires assistance from a developer. It enables an integration event that you can subscribe to if you want to use your own transformation code. If you're a developer and want to use this option, go to [Tip for developers: Example of the custom option](#tip-for-developers-example-of-the-custom-option).|
|**Date and Time Formatting**|Define how to display the current date and the time of day.|
|**Field Lookup**|Use fields from different tables. To use it, you need to follow some rules. First, use **Table ID** to specify the ID of the table that contains the record for the field lookup. Then, in the **Source Field ID** field, specify the ID of the field that contains the record for the field lookup. Finally, in the **Target Field ID** field, specify the ID of the field to find the record for the field lookup. Optionally, use the **Field Lookup Rule** field to specify the type of the field lookup. For the **Target** field, the value from the **Target Field ID** is used, even if it's blank. For the **Original If Target Is Blank** field, the original value is used if the target is blank.|
|**Round**|Round the value in this field using some extra rules. First, in the **Precision** field, specify a rounding precision. Then, in the **Direction** field, specify the rounding direction.|

> [!NOTE]  
> TO learn more about date and time formatting, go to [Standard Date and Time Format Strings](/dotnet/standard/base-types/standard-date-and-time-format-strings).

### Tip for developers: Example of the custom option

The following example shows how to implement your own transformation code.

```AL
codeunit 60100 "Hello World"
{
    [EventSubscriber(ObjectType::Table, Database::"Transformation Rule", 'OnTransformation', '', false, false)]
    procedure OnTransformation(TransformationCode: Code[20]; InputText: Text; var OutputText: Text)
    begin
        if TransformationCode = 'CUST' then
            OutputText := InputText + ' testing';
    end;
}
```

After you define your rules, you can test them. In the **Test** FastTab, enter an example of a value that you want to transform, then check the results by choosing **Update**.

## Export a data exchange definition as an XML file for use by others

After you create the data exchange definition for a specific data file, you can export the data exchange definition as an XML file that you can import. This task is described in the following procedure.  

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Data Exchange Definitions**, then choose the related link.  
2. Select the data exchange definition that you want to export.  
3. Choose the **Export Data Exchange Definition** action.  
4. Save the XML file that represents the data exchange definition in an appropriate location.  

    If a data exchange definition was already created, you just have to import the XML file into the Data Exchange Framework. This task is described in the following procedure.  

## Import an existing data exchange definition

1. Save the XML file that represents the data exchange definition in an appropriate location.  
2. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Data Exchange Definitions**, then choose the related link.  
3. Choose the **Import Data Exchange Definition** action.  
4. Choose the file that you saved in step 1.  

## Related information

[Set Up Data Exchange](across-set-up-data-exchange.md)  
[Set Up Electronic Document Sending and Receiving](across-how-to-set-up-electronic-document-sending-and-receiving.md)  
[Collect Payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md)  
[Make Payments with AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)  
[Incoming Documents](across-income-documents.md)  
[General Business Functionality](ui-across-business-areas.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
