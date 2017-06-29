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
# Fixed Asset Inventory
The fixed assets inventory feature enables you to:  
  
-   Process inventory auditing of fixed assets in accordance with legal requirements.  
  
-   Generate electronic inventory lists of fixed assets that are to be inventoried with calculated quantities and amounts.  
  
-   Divide the inventory lists by the physical locations of fixed assets \(by Fixed Asset Location code\).  
  
-   Filter the inventory lists by other analytics \(such as responsible employee\).  
  
-   Print the forms with inventory lists that show all inventoried fixed assets, as well as lists that show the fixed assets with differences only in quantities or amounts.  
  
-   Print unified fixed asset forms.  
  
## Inventory Lists of Fixed Assets  
 You must create inventory lists of fixed assets with calculated quantities and amounts for inventory auditing. The lists are divided by analytics such as physical locations and employees responsible for certain fixed assets.  
  
 You can create special templates in the Fixed Asset journal.  
  
 The following procedure shows how to open a Fixed Asset journal.  
  
1.  In **Financial Management**, click **Fixed Assets**, and then click **Fixed Asset Journals**.  
  
2.  Select the appropriate fixed asset journal template.  
  
 The following procedure shows how to generate a list of fixed assets that are to be inventoried.  
  
1.  Click **Calculate FA** from the **Functions** button. The request form of a report that makes fixed asset inventory lists is displayed.  
  
2.  On the **Fixed Asset** tab, filter the fixed assets.  
  
    > [!NOTE]  
    >  They can be filtered by any parameter from the Fixed Asset card, such fixed asset location or responsible employee.  
  
 The parameters listed in the following table are on the **Options** tab.  
  
|Parameter|Description|  
|---------------|-----------------|  
|**Fixed Asset Journal Template**|Select the fixed asset journal template to work with the fixed assets list during the inventory auditing process. It is filled by default with the Fixed Asset Journal template.|  
|**Depreciation Book Code**|Select the depreciation book with the records, which will be calculated by quantities and amounts.|  
|**Starting Document No.**|Specify the document number used to make lines in the Fixed Asset journal.|  
|**Document Date**|Specify the document date.|  
|**Posting Date**|Specify the posting date. The quantities and amounts are calculated on this date. The **Posting Date** field is also filled with this value.|  
|**Show Fixed Asset with Book Value \= 0**|Select this field to create fixed asset journal lines for fixed assets which have a book value of zero.|  
  
 The report creates one batch in the Fixed Asset Journal template for every fixed asset location that is filtered in the request form. For every fixed asset that is filtered, one journal line is created in the batch according to its location. A journal batch is created for fixed assets in each fixed asset location.  
  
 The following procedure shows how to begin inventory auditing by fixed asset locations.  
  
1.  Select the batch according to the fixed asset location, and click **ОК**.  
  
    > [!NOTE]  
    >  You can view the fixed assets lines that are filtered in the report and the lines that are in this fixed asset location.  
  
2.  Place the columns of the fixed asset journal so that you can view calculated and actual quantities and amounts. They are reflected in the following fields:  
  
    -   **Actual Quantity**  
  
    -   **Calc. Quantity**  
  
    -   **Actual Amount**  
  
    -   **Calc. Amount**  
  
    > [!NOTE]  
    >  The amount value is the book value of the fixed asset.  
  
## Inventory Auditing of Fixed Assets  
 To begin inventory auditing of fixed assets, create the list of fixed assets to be inventoried in certain fixed asset locations, with calculated quantities and amounts, on the basis of system records.  
  
## Fixed Asset Physical Inventory INV-1 Report  
 You can print the Fixed Asset Physical Inventory INV-1 report, which shows the list of fixed asset journal lines with all inventoried fixed assets filtered in the request form of the report. The report shows the calculated and actual quantities and amounts of inventoried fixed assets.  
  
 The following procedure shows how to print the Fixed Asset Physical Inventory INV-1 report.  
  
1.  On the **FA Journal Line** tab of the request form, filter the fixed asset journal lines to be included in the report.  
  
    > [!NOTE]  
    >  You can filter them by location code to see all fixed assets in a certain physical location, or you can filter them by employee number to see all fixed assets that a certain employee is responsible for.  
  
2.  The filters on the **Journal Template Name** and **Journal Batch Name** fields are filled in by default with the corresponding values from the journal batch from where the report is called.  
  
3.  On the **Options** tab, set other parameters for the report. All the parameters on this tab are shown on the printing form.  
  
## Fixed Asset Comparative Sheet INV-18 Report  
 The Fixed Asset Comparative Sheet INV-18 report shows the list of fixed asset journal lines, but only those that have differences between calculated and actual quantities or amounts of inventoried fixed assets. The journal lines with inventoried fixed assets can be filtered in the request form of the report. The report shows the calculated and actual quantities and amounts of the inventoried fixed assets. You can print the Fixed Asset Comparative Sheet INV-18 report.  
  
 The procedure to print the Fixed Asset Comparative Sheet INV-18 report is similar to the Fixed Asset Comparative Sheet INV-1 report.  
  
## See Also  
 [Fixed Asset Locations and Employees](../FullExperience/fixed-asset-locations-and-employees.md)