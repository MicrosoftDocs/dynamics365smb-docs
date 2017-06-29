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
# How to: Create Routing Links
You can create routing links to connect components to specific operations in order to retain their relationship even though the production BOM or routing is modified. It also facilitates just-in-time flushing of components, namely when the specific linked operation starts, not when the complete production order is released. For more information see [How to: Flush Components According to Operation Output](../Production/how-to-flush-components-according-to-operation-output.md).  
  
 Another important benefit is that linked components and operations are displayed in a logical process structure when you use the **Production Journal** window for output and consumption posting.  
  
 To create a new routing link, you must start in the routing and connect the links in the production BOM.  
  
### To create a routing link  
  
1.  In the **Search** box, enter **Routings**, and then choose the related link.  
  
2.  Open the routing that contains the operations that you want to link.  
  
     Make sure the routing status is **Under Development**.  
  
3.  On the relevant routing line, in the **Routing Link Code** field, select a code. ADD INCLUDE<!--[!INCLUDE[bp_choose_columns](../DesignAndEngineering/includes/bp_choose_columns_md.md)]--> For information about how to create routing link codes, see [How to: Set Up Routing Link Codes](../DesignAndEngineering/how-to-set-up-routing-link-codes.md).  
  
4.  Proceed to add different routing link codes to other operations in the routing, if relevant.  
  
    > [!NOTE]  
    >  You should not use the same routing link code in different operations on a routing because you may incorrectly link a component to two different operations, so that it is consumed two times.  
    >   
    >  It is a good idea to name the routing link code after the operation in order to ensure operation-specific routing links.  
  
5.  Set the routing status to **Certified**.  
  
     Routing link codes are now assigned to operations. Next, you must create the actual link by assigning the same codes to specific components in the relevant production BOM.  
  
6.  Open the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[production BOM](DynamicsNAV:////runpage?Page=99000787)** that contains the components that you want to link to the above operations.  
  
7.  Make sure the BOM status is **Under Development**.  
  
8.  On the relevant production BOM line, in the **Routing Link Code** field, select the code that you have just assigned to the relevant operation.  
  
9. Proceed to add routing link codes to other components according to the unique operations where they are used.  
  
10. Set the production BOM status to **Certified**.  
  
    > [!NOTE]  
    >  To enable the routing links on an existing production order, you must first refresh. For more information, see [How to: Refresh Production Orders](../OperationsPlanning/how-to-refresh-production-orders.md).  
  
 The selected components will now be linked to the selected operations when you create or refresh a production order using the production BOM and routing in question. This is visible in the **Prod. Order Components** window under the production order, and here you can also remove and add the defined routing link codes at any time.  
  
## See Also  
 Production Journal   
 Prod. Order Components   
 Routing Link Code   
 [How to: Set Up Routing Link Codes](../DesignAndEngineering/how-to-set-up-routing-link-codes.md)   
 [How to: Refresh Production Orders](../OperationsPlanning/how-to-refresh-production-orders.md)   
 [How to: Flush Components According to Operation Output](../Production/how-to-flush-components-according-to-operation-output.md)