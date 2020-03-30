---
    title: Create XMLports based on XML schemas | Microsoft Docs
    description: Use XML schemas to set yup the document exchange framework.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Use XML Schemas to Prepare Data Exchange Definitions
To enable import/export of data in XML files through the data exchange framework in [!INCLUDE[d365fin](includes/d365fin_md.md)], you can use XML schemas to define which data elements you want to exchange with [!INCLUDE[d365fin](includes/d365fin_md.md)]. You perform this work on the **XML Schema Viewer** page by loading the XML schema file, selecting the relevant data elements, and then initializing either a data exchange definition or an XMLport.  

 When you have defined which data elements to include based on the XML schema, you can use the **Generate XMLport** action to create the XMLport object.  

 Alternatively, you can use the **Generate Data Exchange Definition** action to initialize a data exchange definition based on the selected data elements, which you then complete in the Data Exchange Framework. This creates a record on the **Posting Exchange Definition** page where you continue by defining which elements in the file map to which fields in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).  

 This topic contains the following procedures:  

-   To load an XML schema file  

-   To select or clear nodes in an XML schema  

-   To generate a data exchange definition that is based on an XML schema  

-   To generate an XMLport for the file that is based on an XML schema  

-   To import an XMLport into the Object Designer  

### To load an XML schema file  

1.  Make sure that the relevant XML schema file is available. The file extension is .xsd.  

2.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **XML Schemas**, and then choose the related link.  

3.  Choose the **New** action.  

4.  Fill the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify a code to identify the XML schema.|  
    |**Description**|Specify a description of the XML schema.|  

     The **Target Namespace** field specifies any namespace in the XML schema file that has been loaded for the line.  

5.  Choose the **Load Schema** action, and then select the XML schema file.  

     When the file is loaded, the rest of the fields on the line are filled with information from the file, and the **Schema is Loaded** check box is selected.  

    > [!NOTE]  
    >  The tree of the loaded XML schema is collapsed by default. You expand each node by choosing the **+** button on the node. To expand all nodes, choose **Expand All** on the ribbon.  

### To select or clear nodes in an XML schema  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **XML Schema Viewer**, and then choose the related link.  

2.  Fill the fields on the header as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**XML Schema Code**|Specify the XML schema file that you loaded in step 5 in the “To load an XML schema file” section.|  
    |**New XMLport No.**|Specify the number of the XMLport that is created from this XML schema when you choose the **Generate XMLport** action.|  

     The lines are now filled with nodes representing all elements in the XML schema. Nodes for elements that are mandatory according to the XML schema are selected by default.  

3.  On the first line, in the **Node Name** column, expand the **Document** node, and then gradually expand underlying nodes that you want to review.  

     Alternatively, right-click on a node and then choose **Expand All**.  

4.  Choose either of the following actions to change which nodes are displayed.  

    |**Action**|Description|  
    |----------------|---------------------------------------|  
    |**Show All**|All nodes are shown.|  
    |**Hide Non-Mandatory**|Only nodes representing elements that are required according to the XML schema are shown. These nodes are typically indicated by a **1** in the **MinOccurs** field.<br /><br /> Choose **Show All** to reverse the view.|  
    |**Hide Non-Selected**|Only nodes where the **Selected** check box is selected are shown.<br /><br /> Choose **Show All** to reverse the view.|  

5.  Choose the **Edit** action.  

6.  In the **Selected** check box, specify for each node if you want the element to be supported in the data exchange definition for the related SEPA bank file.  

    > [!NOTE]  
    >  When you select a mandatory child node, all parent nodes above it are also selected.  

7.  Choose the **Select All Mandatory Elements** action to reselect all nodes that represent elements that are mandatory according to the XML schema.  

8.  Choose the **Deselect All** action to clear all selections.  

     The **Choice** field specifies that the node has two or more sibling nodes that function as options.  

### To generate a data exchange definition that is based on an XML schema  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter  **XML Schemas**, and then choose the related link.  

2.  Select the relevant XML schema, and then choose the **Open XML Schema Viewer** action.  

3.  Make sure the relevant nodes are selected. For more information, see the “To select or clear nodes in an XML schema” section.  

4.  On the **XML Schema Viewer** page, choose the **Generate Data Exchange Definition** action.  

 A data exchange definition is created on the **Posting Exchange Definition** page, which you can complete by specifying which elements in the file map to which fields in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).  

> [!NOTE]  
>  You can also use the **Get File Structure** function from the **Posting Exchange Definition** page, which uses the functionality of the **XML Schema Viewer** page to prefill the **Column Definitions** TastTab.  

### To generate an XMLport that is based on an XML schema  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter  **XML Schemas**, and then choose the related link.  

2.  Select the relevant XML schema, and then choose the **Open XML Schema Viewer** action.  

3.  In the **New XMLport No.** field, specify the number that the new XMLport object will be given when it is generated.  

4.  Make sure the relevant nodes are selected. For more information, see the “To select or clear nodes in an XML schema” section.  

5.  Choose the **Generate XMLport** action, and then save the object as a .txt file in an appropriate location.  

6. Import the new XMLport into the [!INCLUDE[d365fin](includes/d365fin_md.md)] development environment and compile it.

## See Also  
[Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md)   
[Export Payments to a Bank File](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file)   
[Collect Payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md)   
[About the Data Exchange Framework](across-about-the-data-exchange-framework.md)
