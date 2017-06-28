---
title: "Design Details: Posting Engine Structure"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "posting, engine structure"
  - "general journal post line, posting engine structure"
  - "posting engine structure"
ms.assetid: fbedf79b-410e-4009-a3cd-e1891e9f2b27
caps.latest.revision: 2
ms.author: "edupont"
manager: "edupont"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Design Details: Posting Engine Structure
Posting interface and some other functions in codeunit 12 use posting engine functions to prepare and insert general ledger entry and VAT entry records. The posting engine is also responsible for general ledger register creation.  
  
 The functions in the following table provide a standard framework for designing posting procedures \(such as Code, CustPostApplyCustledgEntry, VendPostApplyVendLedgEntry, UnapplyCustLedgEntry, UnapplyVendLedgEntry, and Reverse\) and exclusive access to table 17, G\/L Entry.  
  
|Routine|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|-------------|---------------------------------------|  
|StartPosting|Initializes posting buffer TempGLEntryBuf, locks G\/L Entry and VAT Entry tables, and initializes Accounting Period, G\/L Register, and Exchange Rate. Should be called only once, then NextEntryNo is 0.|  
|ContinuePosting|Checks and posts unrealized VAT for previous transaction increment NextTransactionNo and prepares post of next line.|  
|FinishPosting|Completes posting by inserting G\/L entries from temporary buffer into database table. Always used together with StartPosting. Checks for inconsistencies.|  
|InitGLEntry|Used to initialize new G\/L entry for Gen. Jnl Line. Returns GLEntry as parameter.|  
|InitGLEntryVAT|Same as InitGLEntry, but also assigns Bal. Account No. and SummarizeVAT.|  
|InitGLEntryVATCopy|Similar to InitGLEntryVAT, but also copies posting groups data from VAT Entry before SummarizeVAT.|  
|InsertGLEntry|The only function that inserts G\/L entry into global TempGLEntryBuf table. Always use this function for insert.|  
|CreateGLEntry|Performs an InitGLEntry, assigns Additional Currency Amount, and then performs InsertGLEntry. Replaces several lines of code with a single function call.|  
|CreateGLEntryBalAcc|Same as CreateGLEntry, but also assigns Bal. Account Type and Bal. Account No.|  
|CreateGLEntryVAT|Same as CreateGLEntry, but with additional processing for posting groups and saving to temporary VAT buffer:<br /><br /> `GLEntry.CopyPostingGroupsFromDtldCVBuf(DtldCVLedgEntryBuf,GenJnlLine."Gen. Posting Type");`<br /><br /> `InsertVATEntriesFromTemp(DtldCVLedgEntryBuf,GLEntry);`|  
|CreateGLEntryVATCollectAdj|Same as CreateGLEntry, but with additional collection of adjustments and saving to temporary VAT buffer:<br /><br /> `CollectAdjustment(AdjAmount,GLEntry.Amount,GLEntry."Additional-Currency Amount",OriginalDateSet);`<br /><br /> `InsertVATEntriesFromTemp(DtldCVLedgEntryBuf,GLEntry);`|  
|CreateGLEntryFromVATEntry|Same as CreateGLEntry, but also copies posting groups from VAT entry.|  
  
## See Also  
 [Design Details: Posting Interface Structure](../ApplicationDesign/design-details-posting-interface-structure.md)