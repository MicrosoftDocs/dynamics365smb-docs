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
# Fixed Asset Locations and Employees
The fixed assets locations and the fixed assets employees feature enable you to:  
  
-   Control the movement of fixed assets and to keep the history of the movements of fixed assets between locations and responsible employees.  
  
-   Enter the fixed assets location and responsible employee in documents and journals for fixed asset posting. This information is reflected in fixed assets operations.  
  
-   Create reports and calculations that use the history of the movements of fixed assets. You can also connect employees \(by default\), locations \(item location\), and regions in an official classification \(OKATO code\) to any fixed assets location.  
  
## Setup  
 The following procedure shows how to enter the data in the **FA Location Code** field.  
  
1.  In **Financial Management**, click **Fixed Assets**, click **Setup**, and then click **FA Setup**.  
  
2.  On the **General** tab, select the **FA Location Mandatory** field.  
  
> [!NOTE]  
>  When this field is selected, fixed asset posting procedures are controlled as long as they generate fixed asset operations with a non-zero value in the **Quantity** field.  
  
 The following procedure shows how to enter the data in the **Employee No** field.  
  
1.  In **Financial Management**, click **Fixed Assets**, click **Setup**, and then click **FA Setup**.  
  
2.  On the **General** tab, select the **Employee No. Mandatory** field.  
  
> [!NOTE]  
>  When this field is selected, fixed asset posting procedures are controlled as long as they generate fixed asset operations with a non-zero value in the **Quantity** field.  
  
## Added Fields  
 Fields with references to fixed asset locations and responsible employees have been added to the following:  
  
-   Lines of purchase documents  
  
-   Fixed asset journals  
  
-   Fixed asset G\/L journals  
  
-   Fixed asset reclassification journals  
  
-   Fixed asset acts  
  
 If the **Employee No. Mandatory** or the **FA Location Mandatory** field is selected in the Fixed Asset Setup window, then the fields with references to corresponding tables must be filled in for fixed asset operations. If you enter a value in the **FA Location Code** field in a line, then the **Employee No.** field and **Location Code** field \(if it exists in the line\) are filled with the corresponding default values from the Fixed Asset Location table. Then the values of the fields can be changed manually.  
  
 When posting the documents and journals, the values of these fields are transferred to the corresponding new fixed asset operations and to corresponding fields in the Fixed Asset cards.  
  
## See Also  
 [Fixed Asset Inventory](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/fixed-asset-inventory.md)