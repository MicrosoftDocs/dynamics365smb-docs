---
title: Design Details - Posting Engine Structure
description: The posting interface uses posting engine functions to prepare and insert general ledger entry and VAT entry records. 
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.date: 06/15/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design Details: Posting Engine Structure
Posting interface and some other functions in codeunit 12 use posting engine functions to prepare and insert general ledger entry and VAT entry records. The posting engine is also responsible for general ledger register creation.  
  
 The functions in the following table provide a standard framework for designing posting procedures (such as Code, CustPostApplyCustledgEntry, VendPostApplyVendLedgEntry, UnapplyCustLedgEntry, UnapplyVendLedgEntry, and Reverse) and exclusive access to table 17, G/L Entry.  
  
|Routine|Description|  
|-------------|---------------------------------------|  
|StartPosting|Initializes posting buffer TempGLEntryBuf, locks G/L Entry and VAT Entry tables, and initializes Accounting Period, G/L Register, and Exchange Rate. Should be called only once, then NextEntryNo is 0.|  
|ContinuePosting|Checks and posts unrealized VAT for previous transaction increment NextTransactionNo and prepares post of next line.|  
|FinishPosting|Completes posting by inserting G/L entries from temporary buffer into database table. Always used together with StartPosting. Checks for inconsistencies.|  
|InitGLEntry|Used to initialize new G/L entry for Gen. Jnl Line. Returns GLEntry as parameter.|  
|InitGLEntryVAT|Same as InitGLEntry, but also assigns Bal. Account No. and SummarizeVAT.|  
|InitGLEntryVATCopy|Similar to InitGLEntryVAT, but also copies posting groups data from VAT Entry before SummarizeVAT.|  
|InsertGLEntry|The only function that inserts G/L entry into global TempGLEntryBuf table. Always use this function for insert.|  
|CreateGLEntry|Performs an InitGLEntry, assigns Additional Currency Amount, and then performs InsertGLEntry. Replaces several lines of code with a single function call.|  
|CreateGLEntryBalAcc|Same as CreateGLEntry, but also assigns Bal. Account Type and Bal. Account No.|  
|CreateGLEntryVAT|Same as CreateGLEntry, but with additional processing for posting groups and saving to temporary VAT buffer:<br /><br /> `GLEntry.CopyPostingGroupsFromDtldCVBuf(DtldCVLedgEntryBuf,GenJnlLine."Gen. Posting Type");`<br /><br /> `InsertVATEntriesFromTemp(DtldCVLedgEntryBuf,GLEntry);`|  
|CreateGLEntryVATCollectAdj|Same as CreateGLEntry, but with additional collection of adjustments and saving to temporary VAT buffer:<br /><br /> `CollectAdjustment(AdjAmount,GLEntry.Amount,GLEntry."Additional-Currency Amount",OriginalDateSet);`<br /><br /> `InsertVATEntriesFromTemp(DtldCVLedgEntryBuf,GLEntry);`|  
|CreateGLEntryFromVATEntry|Same as CreateGLEntry, but also copies posting groups from VAT entry.|  
  
## Related information  
 [Design Details: Posting Interface Structure](design-details-posting-interface-structure.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
