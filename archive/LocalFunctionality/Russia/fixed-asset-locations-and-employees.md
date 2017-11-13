---
    title: Fixed Asset Locations and Employees
    description: The fixed assets locations and the fixed assets employees feature enable you, among other things, to control the movement of fixed assets and to keep the history of the movements of fixed assets between locations and responsible employees.

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
# Fixed Asset Locations and Employees
The fixed assets locations and the fixed assets employees feature enable you to:  

- Control the movement of fixed assets and to keep the history of the movements of fixed assets between locations and responsible employees.  

- Enter the fixed assets location and responsible employee in documents and journals for fixed asset posting. This information is reflected in fixed assets operations.  

- Create reports and calculations that use the history of the movements of fixed assets. You can also connect employees (by default), locations (item location), and regions in an official classification (OKATO code) to any fixed assets location.  

## Setup  
The following procedure shows how to make sure the **FA Location Code** and **Employee No.** fields are always filled in for fixed assets.  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **FA Setup*, and then choose the related link.
2.  On the **General** FastTab, select the **FA Location Mandatory** check box.  

> [!NOTE]  
>  When this field is selected, fixed asset posting procedures are controlled as long as they generate fixed asset operations with a non-zero value in the **Quantity** field.  

3.  Select the **Employee No. Mandatory** check box.  

> [!NOTE]  
>  When this field is selected, fixed asset posting procedures are controlled as long as they generate fixed asset operations with a non-zero value in the **Quantity** field.  

## Added Fields  
Fields with references to fixed asset locations and responsible employees have been added to the following:  

- Lines of purchase documents  
- Fixed asset journals  
- Fixed asset G/L journals  
- Fixed asset reclassification journals  
- Fixed asset acts  

If the **Employee No. Mandatory** or the **FA Location Mandatory** check box is selected in the **Fixed Asset Setup** window, then the fields with references to corresponding tables must be filled in for fixed asset operations. If you enter a value in the **FA Location Code** field in a line, then the **Employee No.** field and **Location Code** field (if it exists in the line) are filled with the corresponding default values from the Fixed Asset Location table. Then the values of the fields can be changed manually.  

 When posting the documents and journals, the values of these fields are transferred to the corresponding new fixed asset operations and to corresponding fields in the Fixed Asset cards.  

## See Also  
 [Fixed Asset Inventory](fixed-asset-inventory.md)
