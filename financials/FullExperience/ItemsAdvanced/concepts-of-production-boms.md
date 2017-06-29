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
# Concepts of Production BOMs
Manufacturers use production bills of material to supervise the use of items and components used for intermediate and finished products.  
  
 The products to be produced consist of items and possibly of sub-assemblies, so that the production BOM consists of single items, sub-assemblies and other production BOMs \(phantom BOMs\).  
  
 Production bills of material can consist of several levels, and you can use a maximum of 50 BOM levels. One production BOM corresponds to one level. The use of other item production BOMs defines the lower levels. The production BOMs are assigned to the item in the Production BOM No. field on the Manufacturing FastTab of the item card.  
  
 The production BOMs of this program exclusively manage the production material needs. Resources are managed in the routings.  
  
 A production BOM can only be defined after the items of which it consists have been set up.  
  
## Example  
 Item 1100 Front Wheel consists of the following items:  
  
-   1110 Rim  
  
-   1120 Spokes  
  
-   1150 Front Hub, which consists of 1151 Axle Front Wheel and 1155 Socket front  
  
-   1160 Tire  
  
## See Also  
 [How to: Create Production BOMs](../DesignAndEngineering/how-to-create-production-boms.md)   
 [How to: Create New Versions of Production BOMs](../DesignAndEngineering/how-to-create-new-versions-of-production-boms.md)   
 [How to: Copy Versions of Production BOMs](../DesignAndEngineering/how-to-copy-versions-of-production-boms.md)   
 [How to: Enter Comments for Production BOMs](../DesignAndEngineering/how-to-enter-comments-for-production-boms.md)   
 [How to: Enter Comments for Production BOM Components](../DesignAndEngineering/how-to-enter-comments-for-production-bom-components.md)   
 [How to: Compare Material Quantities in All Production BOM Versions](../DesignAndEngineering/how-to-compare-material-quantities-in-all-production-bom-versions.md)   
 [How to: Find Where Production BOMs Are Used](../DesignAndEngineering/how-to-find-where-production-boms-are-used.md)   
 [How to: Find Where Production BOM Components Are Used](../DesignAndEngineering/how-to-find-where-production-bom-components-are-used.md)   
 [How to: Copy Production BOMs](../DesignAndEngineering/how-to-copy-production-boms.md)   
 [How to: Delete Expired Components](../DesignAndEngineering/how-to-delete-expired-components.md)   
 [How to: Print List of Items Needed for Production BOMs](../DesignAndEngineering/how-to-print-list-of-items-needed-for-production-boms.md)   
 [How to: Print Production Costs](../Finance/how-to-print-production-costs.md)   
 [How to: Create Routing Links](../DesignAndEngineering/how-to-create-routing-links.md)   
 [How to: Use the Manufacturing Batch Unit of Measure](../DesignAndEngineering/how-to-use-the-manufacturing-batch-unit-of-measure.md)