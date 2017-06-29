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
# Design Details: Codeunit 408 Dimension Management
Codeunit 408 Dimension Management is a function library that handles common tasks that are related to dimensions, such as copying from one table to another or from one document to another. This topic lists the functions that are modified in FIX INCLUDE HERE<!--[!INCLUDE[navsicily](../ApplicationDesign/includes/navsicily_md.md)] --> and specifies what has to be done to the functions. Many functions are deleted because there is no need for copying between dimension tables.  
  
## Modified Functions  
  
|Function Name|Modification Description|  
|-------------------|------------------------------|  
|CheckDimSetIDComb|New function that substitutes the other check functions and takes a Dimension Set ID as an argument instead of a dimension table.|  
|CheckDimSetIDComb<br /><br /> CheckDocDimComb<br /><br /> CheckServContractDimComb<br /><br /> CheckDimBuffer<br /><br /> CheckDimComb<br /><br /> CheckDimValueComb|Delete. All usage should be changed to CheckDimSetIDComb.|  
|GetDefaultDim|Modify to return an integer Dimension Set ID instead of a set of records.|  
|CopyJnlLineDimToICJnlDim<br /><br /> CopyICJnlDimToJnlLineDim<br /><br /> CopyDocDimtoICDocDim<br /><br /> CopyICDocDimtoICDocDim|Modify to work with DimSetID -\> ICJnlLineDim|  
  
## Deleted Functions  
 Functions that are deleted from codeunit 408 in connection with the Dimension Set Entries feature are listed below.  
  
> [!CAUTION]  
>  During the upgrade of application code from FIX INCLUDE HERE<!--[!INCLUDE[nav_2009_long](../ApplicationDesign/includes/nav_2009_long_md.md)] --> or earlier versions to FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnowlong](../ApplicationDesign/includes/navnowlong_md.md)] --> -->, the following functions are not available in [!INCLUDE[navnowlong](../ApplicationDesign/includes/navnowlong_md.md)]. If you have customizations that use one or more of the functions, you must upgrade that code accordingly. For more information, see [Upgrading the Application Code](../Topic/Upgrading%20the%20Application%20Code.md).  
  
 InsertJnlLineDim  
  
 UpdateJnlLineDefaultDim  
  
 GetJnlLineDefaultDim  
  
 GetPreviousDocDefaultDim  
  
 GetPreviousProdDocDefaultDim  
  
 InsertDocDim  
  
 UpdateDocDefaultDim  
  
 ExtractDocDefaultDim  
  
 InsertProdDocDim  
  
 UpdateProdDocDefaultDim  
  
 InsertServContractDim  
  
 UpdateServcontractDim  
  
 UpdateDefaultDimNewDimValue  
  
 GetDocDim  
  
 GetProdDocDim  
  
 TypeToTableID1  
  
 TypeToTableID2  
  
 TypeToTableID3  
  
 TypeToTableID4  
  
 TypeToTableID5  
  
 DeleteJnlLineDim  
  
 DeleteDocDim  
  
 DeletePostedDocDim  
  
 DeleteProdDocDim  
  
 DeleteServContractDim  
  
 ShowJnlLineDim  
  
 SaveJnlLineDim  
  
 ShowJnlLineNewDim  
  
 SaveJnlLineNewDim  
  
 ShowDocDim  
  
 SaveDocDim  
  
 ShowProdDocDim  
  
 SaveProdDocDim  
  
 ShowTempDim  
  
 SaveTempDim  
  
 ShowTempNewDim  
  
 SaveTempNewDim  
  
 SaveServContractDim  
  
 MoveJnlLineDimToLedgEntryDim  
  
 MoveDocDimToPostedDocDim  
  
 MoveOneDocDimToPostedDocDim  
  
 MoveLedgEntryDimToJnlLineDim  
  
 MoveDimBufToJnlLineDim  
  
 MoveDimBufToLedgEntryDim  
  
 MoveDimBufToPostedDocDim  
  
 MoveDimBufToGLBudgetDim  
  
 CopyJnlLineDimToJnlLineDim  
  
 CopyLedgEntryDimToJnlLineDim  
  
 CopyDocDimToDocDim  
  
 CopyPostedDocDimToPostedDocDim  
  
 CopyDocDimToJnlLineDim  
  
 CopyDimBufToJnlLineDim  
  
 CopyDimBufToDocDim  
  
 CopySCDimToDocDim  
  
 MoveDocDimToLedgEntryDim  
  
 MoveDocDimToDocDim  
  
 MoveDocDimArchvToDocDim  
  
 MoveLedgEntryDimToDocDim  
  
 MoveProdDocDimToProdDocDim  
  
 MoveJnlLineDimToProdDocDim  
  
 MoveJnlLineDimToDocDim  
  
 MoveJnlLineDimToJnlLineDim  
  
 CopyLedgEntryDimToLedgEntryDim  
  
 MoveTempFromDimToTempToDim  
  
 TransferTempToDimToDocDim  
  
 MoveJnlLineDimToBuf  
  
 CopyICJnlDimToICJnlDim  
  
 TestDimValue  
  
 TestNewDimValue  
  
 MoveDimBufToItemBudgetDim. \(Delete because the ItemBudgetDim Table is deleted.  
  
 GetServContractDim  
  
 MoveTempDimToBuf  
  
 UpdateSCInvLineDim  
  
 CopyJnlLineDimToBuffer  
  
 UpdateDocDefaultDim2  
  
## See Also  
 [Design Details: Dimension Set Entries](../ApplicationDesign/design-details-dimension-set-entries.md)   
 [Dimension Set Entries Overview](../ApplicationDesign/dimension-set-entries-overview.md)   
 [Design Details: Searching for Dimension Combinations](../ApplicationDesign/design-details-searching-for-dimension-combinations.md)   
 [Design Details: Table Structure](../ApplicationDesign/design-details-table-structure.md)   
 [Design Details: Code Examples of Changed Patterns in Modifications](../ApplicationDesign/design-details-code-examples-of-changed-patterns-in-modifications.md)