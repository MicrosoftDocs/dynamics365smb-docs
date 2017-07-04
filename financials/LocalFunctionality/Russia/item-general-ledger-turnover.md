---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Item General Ledger Turnover
The following form and reports enable the creation of turnover sheet for goods and materials.  
  
-   Item General Ledger Turnover form - Form 12449  
  
-   Item Turnover (Qty.) - Report 12469  
  
-   Item Turnover Checklist - Report 12489  
  
## Item General Ledger Turnover Form (12449)  
 The Item General Ledger Turnover form shows the turnover for items in quantities and costs, the balance at the beginning of the month, positive and negative adjustment, and the balance at the end of the month.  
  
 The Item General Ledger Turnover form is usually created monthly, and can also be created for the date of inventory. The data on the Item General Ledger Turnover form is checked with the warehouse accounting data. The cost data is checked with the net changes and balances of:  
  
-   Account 41, Items  
  
-   Account 10, Materials  
  
 To access the Item General Ledger Turnover form  
  
-   In **Financial Management**, click **Inventory** and then click **Item G/L Turnover**. On the **Options** tab, you can specify the format options listed in the following table.  
  
|||  
|-|-|  
|Field|Description|  
|**Date Filter**|Enter the period the data is analyzed for. You can use the buttons in the lower left of the form, or you can specify the period manually.|  
|**Location Filter**|Enter the location code that the information must be filtered for. You can enter a maximum of 10 characters, both numbers and letters.|  
|**Global Dimension 1 Filter**|Enter the filter value for the analysis on the Global Dimension 1 filter.|  
|**Global Dimension 2 Filter**|Enter the filter value for the analysis on the Global Dimension 2 filter.|  
  
 The form contains fields with the information listed in the following table. You cannot edit the fields.  
  
|||  
|-|-|  
|Field|Definition|  
|**No.**|This field displays the item number.|  
|**Description**|This field displays the description of the item.|  
|**Base Unit of Measure**|This field displays the base unit of measure of the item. The unit of measure is specified in the Item card as the Base.|  
|**Starting Quantity**,<br /><br /> **Ending Quantity**,<br /><br /> **Debit Quantity**,<br /><br /> **Credit Quantity**|These fields provide information about the quantity of the item—item quantity at the beginning and at the end of the period, and positive and negative correction in quantities of the item. Quantities are specified in base units of measure.|  
|**Starting Cost**,<br /><br /> **Ending Cost**,<br /><br /> **Debit Cost**,<br /><br /> **Credit Cost**|These fields provide information about the cost of the item—cost at the beginning and at the end of the period, and the item positive and negative adjustments in financial amounts. These field values are calculated on the basis of the cost amounts posted in the general ledger entry.|  
  
 To display the selected Item card  
  
-   Click the **Item** button and then **Card** (Shift+F5 Hot Key).  
  
 To print the Item Turnover (Qty.) or Item Turnover Checklist reports  
  
-   Click **Print**, and then click **Turnover Sheet** or **Turnover Checklist**.  
  
## Item Turnover (Qty.) Report (12469)  
 To analyze net changes and balances of items and materials, you can print the Item Turnover (Qty.) report and export it to Microsoft Office Excel. The report prints the following data from the Item General Ledger Turnover form:  
  
-   Item number and description  
  
-   Balance at the beginning of the specified period (quantity and cost)  
  
-   Positive adjustment (quantity and cost)  
  
-   Negative adjustment (quantity and cost)  
  
-   Balance at the end of the specified period (quantity and cost )  
  
-   Unit of measure  
  
 The following procedure shows how to access the turnover sheet.  
  
1.  In **Financial Management**, click **Inventor**y, and then click **Item General Ledger Turnover**.  
  
2.  Click **Print** and then click **Turnover Sheet**.  
  
 The turnover sheet is printed monthly and on the date of inventory, but it can be printed for any given period.  
  
 The **Item** tab of the request form contains fields with the information listed in the following table.  
  
|||  
|-|-|  
|Field|Description|  
|**No.**|Enter an item number or a range of item numbers to print an item general ledger turnover for one item or for a group of items.|  
|**Location Filter**|Enter the location code that the information must be filtered for, to print the Item General Ledger Turnover form for one or several locations.<br /><br /> You can enter a maximum of 10 characters, both numbers and letters. The field value is entered automatically in the **Location Filter** field|  
|**Date Filter**|Enter the period that the report is printed for.|  
  
 On the **Options** tab, you can specify the format options listed in the following table.  
  
|||  
|-|-|  
|Parameter|Description|  
|**Rounding Precision**|Choose the required rounding precision:<br /><br /> 0.001, 0.01, 1, or 1000.|  
|**Replace zero values by blanks**|Select this field if you want to replace zero values with blanks.|  
|**Skip accounts without net changes**|Select this field to exclude from the report the accounts with zero turnovers for the given period.|  
|**Skip accounts with zero ending balance**|Select this field to exclude from the report the accounts with zero ending balance at the end of the period.|  
|**Skip zero lines**|Select this field to exclude from the report the lines with zero values.|  
|**Unit of Measure**|Choose a unit of measure for calculating report quantities:<br /><br /> -   **Base** – In base units of measure<br />-   **Sale** – In units of measure for sales<br />-   **Purchase** – In units of measure for purchases|  
|**Print Quantity**|Select this field to print the quantity that is mentioned in the report.|  
|**Print Cost**|Select this field to print the costs that are mentioned in the report.|  
|**Export to Excel**|Select this field to export the report to Microsoft Office Excel.|  
  
## Item Turnover Checklist Report (12489)  
 The Item Turnover Checklist report provides accounting for the expected costs of items and materials that are received but not paid for.  
  
 The Item Turnover Checklist report prints all the data about items and materials that are in the Item Turnover (Qty.) report and in addition, it prints expected cost balances:  
  
-   Item number and description  
  
-   Balance at the beginning of the specified period (quantity, expected cost, and balance)  
  
-   Item positive adjustment (quantity, expected cost, and balance)  
  
-   Item negative adjustment (quantity, expected cost, and balance)  
  
-   Net change at the end of the specified period (quantity, expected cost, and balance)  
  
-   Unit of measure  
  
 The following procedure shows how to access the turnover checklist.  
  
1.  In **Financial Management**, click **Inventory**, and then click **Item General Ledger Turnover**.  
  
2.  Click **Print**, and then click **Turnover Checklist**.  
  
 The turnover checklist is printed monthly and on the date of inventory, but can be printed for any given period.  
  
 The **Item** tab of the request form contains the fields with the information listed in the following table.  
  
|||  
|-|-|  
|Field|Description|  
|**No.**|Enter the item number or a range of item numbers if you want to print the report for one item or for a group of items.|  
|**Item Category Code**|Enter the Item Category code. This code specifies the following default values:<br /><br /> -   Standard General Product Posting Group<br />-   Standard Inventory Posting Group<br />-   Standard VAT Product Posting Group<br />-   Standard Costing Method|  
|**Product Group Code**|Enter the Product group code specifying the product type the item belongs to (such as paint, tools, and batteries).|  
|**Global Dimension 1 Filter**|Enter a filter value for analysis on the Global Dimension 1 filter.|  
|**Global Dimension 2 Filter**|Enter a filter value for analysis on the Global Dimension 2 filter.|  
|**Date Filter**|Enter the period that the report is printed for. The field is required.|  
  
 On the **Parameters** tab, you can specify the format options listed in the following table.  
  
|||  
|-|-|  
|Parameter|Description|  
|**Rounding Precision**|Choose the required rounding precision:<br /><br /> 0.001, 0.01, 1, or 1000.|  
|**Replace zero values by blanks**|Select this field to replace zero values with blanks.|  
|**Skip accounts without net changes**|Select this field to exclude from the report the accounts with zero turnovers for the period.|  
|**Skip accounts with zero ending balance**|Select this field to exclude from the report the accounts with zero ending balance at the end of the period.|  
|**Skip zero lines**|Select this field to exclude from the report the lines with zero values.|  
|**Print horizontal grid**|Select this field to print the horizontal grid in the report.|  
|**Unit of Measure**|Choose a unit of measure for calculating report quantities:<br /><br /> -   **Base** – In base units of measure<br />-   **Sale** – In units of measure for sales<br />-   **Purchase** – In units of measure for purchases|  
|**Print Quantity**|Select this field to print the quantity that is mentioned in the report.|  
|**Print Cost**|Select this field to print the costs that are mentioned in the report.|  
|**Print Group Totals**|Select this field to print preliminary group totals.|  
  
## See Also  
 [Item Obligatory Acts](item-obligatory-acts.md)