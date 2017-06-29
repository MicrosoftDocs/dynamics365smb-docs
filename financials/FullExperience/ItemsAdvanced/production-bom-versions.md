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
# Production BOM Versions
The production BOMs support the version principle which is explained below.  
  
 The version principle enables various versions of a production BOM to be managed. The structure of the production BOM version corresponds to the structure of the production BOM. The basic difference is in the time validity of the versions. The validity is defined by the starting date.  
  
 The starting date and the status are decisive for using the production BOM version in production.  
  
## Starting Date  
 The starting date indicates the start of the period in which this version is valid. For all other considerations, the starting date is a filter criterion for calculations and evaluations. The BOM version is valid until the next version becomes valid for its starting date.  
  
## Status  
 The status of the version can correspond to the following options:  
  
-   **New**  
  
     The **New** status is automatically filled in when a new version is created. In this status, all changes can be made, and no consideration is made in the calculations.  
  
-   **Certified**  
  
     The status is set to **Certified** when the version of the production BOM has been created completely and correctly. To do this, it must be checked first by appropriately qualified employees. After setting the status to **Certified**, the BOM is considered in calculations \(according to starting date and ending date\). No changes to the version are possible.  
  
-   **Under Development**  
  
     If changes to the production BOM version are necessary, the status is set to **Under Development** to allow changes.  
  
-   **Closed**  
  
     Indicates that the BOM version is no longer valid.  
  
## Calculation Formula  
 The quantity is calculated taking into consideration different dimensions which are also entered on the lines. The dimensions refer to an order unit of the respective item. The length, width, depth and weight can be entered as dimensions.  
  
 The Calculation Formula, Length, Width, Depth and Weight columns are not displayed, because they are only used by some users. If you wish to use the calculation of the quantity, you must first display these columns.  
  
 The relation of the individual components is defined by the calculation formula. The following possibilities are available as a calculation formula:  
  
-   Empty  
  
     No consideration of dimensions. \(Quantity \= Quantity per.\)  
  
-   Length  
  
     Quantity \= Quantity per \* Length  
  
-   Length \* Width  
  
     Quantity \= Quantity per \* Length \* Width  
  
-   Length \* Width \* Depth  
  
     Quantity \= Quantity per \* Length \* Width \* Depth  
  
-   Weight  
  
     Quantity \= Quantity per \* Weight  
  
### Example  
 In a production BOM, seventy metal parts with the dimensions length \= 0.20 m and width \= 0.15 m are required. The values are entered as follows: Calculation Formula \= Length \* Width, Length \= 20, Width \= 15, Quantity per \= 70. The quantity is given by the Quantity per \* Length \* Width, that is, Quantity \= 70 \* 0.20 m \* 0.15 m \= 2.1 m2.  
  
## See Also  
 [Concepts of Production BOMs](../FullExperience/concepts-of-production-boms.md)   
 [How to: Create New Versions of Production BOMs](../FullExperience/how-to-create-new-versions-of-production-boms.md)   
 [How to: Copy Versions of Production BOMs](../FullExperience/how-to-copy-versions-of-production-boms.md)   
 [How to: Compare Material Quantities in All Production BOM Versions](../FullExperience/how-to-compare-material-quantities-in-all-production-bom-versions.md)