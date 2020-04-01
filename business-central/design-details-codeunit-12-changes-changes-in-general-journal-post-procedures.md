---
    title: Design Details - Codeunit 12 Changes in General Journal Post Procedures | Microsoft Docs
    description: The following changes have been implemented in this release of Business Central.
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
# Codeunit 12 Changes: Changes in General Journal Post Procedures
The following changes have been implemented in this release of [!INCLUDE[d365fin](includes/d365fin_md.md)].  

|**Microsoft Dynamics NAV 2009 R2**|**Microsoft Dynamics NAV 2013 R2**|**Comment**|  
|----------------------------------------|----------------------------------------|-----------------|  
|GetGLReg|GetGLReg|Updated|  
|RunWithCheck|RunWithCheck|Updated|  
|RunWithoutCheck|RunWithoutCheck|Updated|  
|Code|Code|Updated|  
||PostGenJnlLine|Added|  
||InitAmounts|Added|  
||InitLastDocDate|Added|  
|InitVAT|InitVAT|Updated|  
|PostVAT|PostVAT|Updated|  
|InsertVAT|InsertVAT|Updated|  
|SummarizeVAT|SummarizeVAT|Updated|  
|InsertSummarizedVAT|InsertSummarizedVAT|Updated|  
|PostGLAcc|PostGLAcc|Updated|  
|PostCust|PostCust|Updated|  
|PostVend|PostVend|Updated|  
|PostBankAcc|PostBankAcc|Updated|  
|PostFixedAsset|PostFixedAsset|Updated|  
|PostICPartner|PostICPartner|Updated|  
|InitCodeUnit|StartPosting|Updated|  
||ContinuePosting|Added|  
|FinishCodeunit|FinishPosting|Updated|  
||PostUnrealizedVAT|Added|  
||CheckPostUnrealizedVAT|Added|  
||ExchangeAccounts|Added|  
|InitGLEntry|InitGLEntry|Updated|  
||InitGLEntryVAT|Added|  
||InitGLEntryVATCopy|Added|  
|InsertGLEntry|InsertGLEntry|Updated|  
||CreateGLEntry|Added|  
||CreateGLEntryBalAcc|Added|  
||CreateGLEntryVAT|Added|  
||CreateGLEntryVATCollectAdj|Added|  
||CreateGLEntryFromVATEntry|Added|  
||UpdateCheckAmounts|Added|  
|ApplyCustLedgEntry|ApplyCustLedgEntry|Updated|  
||CalcPmtDiscPossible|Added|  
||CalcPmtTolerancePossible|Added|  
|CalcPmtTolerance|CalcPmtTolerance|Updated|  
|CalcPmtDisc|CalcPmtDisc|Updated|  
|CalcPmtDiscIfAdjVAT|CalcPmtDiscIfAdjVAT|Updated|  
|CalcPmtDiscTolerance|CalcPmtDiscTolerance|Updated|  
||CalcPmtDiscVATBases|Added|  
||CalcPmtDiscVATAmounts|Added|  
||InsertPmtDiscVATForVATEntry|Added|  
||InsertPmtDiscVATForGLEntry|Added|  
|CalcCurrencyApplnRounding|CalcCurrencyApplnRounding|Updated|  
|FindAmtForAppln|FindAmtForAppln|Updated|  
|CalcCurrencyUnrealizedGainLoss|CalcCurrencyUnrealizedGainLoss|Updated|  
|CalcCurrencyRealizedGainLoss|CalcCurrencyRealizedGainLoss|Updated|  
|CalcApplication|CalcApplication|Updated|  
|CalcRemainingPmtDisc|CalcRemainingPmtDisc|Moved to Codeunit 426 Payment Tolerance Management|  
|CalcAmtLCYAdjustment|CalcAmtLCYAdjustment|Added|  
|InitNewCVLedgEntry|InitFromGenJnlLine|Moved to Table 383 Detailed CV Ledg. Entry Buffer|  
|InitOldCVLedgEntry|CopyFromCVLedgEntryBuf|Moved to Table 383 Detailed CV Ledg. Entry Buffer|  
|InsertDtldCVLedgEntry|InsertDtldCVLedgEntry|Moved to Table 383 Detailed CV Ledg. Entry Buffer|  
||InitBankAccLedgEntry|Added|  
||InitCheckLedgEntry|Added|  
||InitCustLedgEntry|Added|  
||InitVendLedgEntry|Added|  
||InsertDtldCustLedgEntry|Added|  
||InsertDtldVendLedgEntry|Added|  
|CustUnrealizedVAT|CustUnrealizedVAT|Updated|  
|CustPostApplyCustLedgEntry|CustPostApplyCustLedgEntry|Updated|  
||PrepareTempCustLedgEntry|Added|  
|UnapplyCustLedgEntry|UnapplyCustLedgEntry|Updated|  
|TransferCustLedgEntry|CopyFromGenJnlLine|Moved to Table 21 Cust. Ledger Entry|  
|PostDtldCustLedgEntries|PostDtldCustLedgEntries|Updated|  
||PostDtldCustLedgEntry|Added|  
||PostDtldCustLedgEntryUnapply|Added|  
||GetDtldCustLedgEntryAccNo|Added|  
|ZeroTransNoDtldCustLedgEntries|SetZeroTransNo|Moved to Table 379 Detailed Cust. Ledg. Entry|  
|AutoEntrForDtldCustLedgEntries||Refactored to PostDtldCustLedgEntryUnapply|  
|CustUpdateDebitCredit|UpdateDebitCredit|Moved to Table 379 Detailed Cust. Ledg. Entry|  
|ApplyVendLedgEntry|ApplyVendLedgEntry|Updated|  
||PrepareTempVendLedgEntry|Added|  
|VendPostApplyVendLedgEntry|VendPostApplyVendLedgEntry|Updated|  
|UnapplyVendLedgEntry|UnapplyVendLedgEntry|Updated|  
|TransferVendLedgEntry|CopyFromGenJnlLine|Moved to Table 25 Vendor Ledger Entry|  
|PostDtldVendLedgEntries|PostDtldVendLedgEntries|Updated|  
||PostDtldVendLedgEntry|Added|  
||PostDtldVendLedgEntryUnapply|Added|  
||GetDtldVendLedgEntryAccNo|Added|  
||PostDtldCVLedgEntry|Added|  
||PostDtldCustVATAdjustment|Added|  
||PostDtldVendVATAdjustment|Added|  
|ZeroTransNoDtldVendLedgEntries|SetZeroTransNo|Moved to Table 380 Detailed Vend. Ledg. Entry|  
|AutoEntrForDtldVendLedgEntries||Refactored to PostDtldVendLedgEntryUnapply|  
|VendUpdateDebitCredit|UpdateDebitCredit|Moved to Table 380 Detailed Vend. Ledg. Entry|  
|VendUnrealizedVAT|VendUnrealizedVAT|Updated|  
||PostUnrealVATEntry|Added|  
||PostApply|Added|  
|PostUnrealVATByUnapply|PostUnrealVATByUnapply|Updated|  
||PostUnapply|Added|  
||InsertDtldCustLedgEntryUnapply|Added|  
||InsertDtldVendLedgEntryUnapply|Added|  
||InsertTempVATEntry|Added|  
||ProcessTempVATEntry|Added|  
||UpdateCustLedgEntry|Added|  
||UpdateVendLedgEntry|Added|  
|UpdateCalcInterest|UpdateCalcInterest|Updated|  
|UpdateCalcInterest2|UpdateCalcInterest2|Updated|  
|GLCalcAddCurrency|GLCalcAddCurrency|Updated|  
|HandleAddCurrResidualGLEntry|HandleAddCurrResidualGLEntry|Updated|  
|CalcLCYToAddCurr|CalcLCYToAddCurr|Updated|  
|CalcAddCurrFactor||Deleted|  
|GetCurrencyExchRate|GetCurrencyExchRate|Updated|  
|ExchAmount|ExchangeAmount|Moved to Table 330 Currency Exchange Rate|  
|ExchangeAmtLCYToFCY2|ExchangeAmtLCYToFCY2|Updated|  
|CalcAddCurrForUnapplication|CalcAddCurrForUnapplication|Updated|  
|CheckNonAddCurrCodeOccurred|CheckNonAddCurrCodeOccurred|Updated|  
|CheckCalcPmtDisc||Moved to Codeunit 426 Payment Tolerance Management|  
|CheckCalcPmtDiscCVCust||Moved to Codeunit 426 Payment Tolerance Management|  
|CheckCalcPmtDiscCust||Moved to Codeunit 426 Payment Tolerance Management|  
|CheckCalcPmtDiscGenJnlCust||Moved to Codeunit 426 Payment Tolerance Management|  
|CheckCalcPmtDiscCVVend||Moved to Codeunit 426 Payment Tolerance Management|  
|CheckCalcPmtDiscVend||Moved to Codeunit 426 Payment Tolerance Management|  
|CheckCalcPmtDiscGenJnlVend||Moved to Codeunit 426 Payment Tolerance Management|  
|Reverse|Reverse|Moved to Codeunit 17 Gen. Jnl.-Post Reverse|  
|ReverseCustLedgEntry|ReverseCustLedgEntry|Moved to Codeunit 17 Gen. Jnl.-Post Reverse|  
|ReverseVendLedgEntry|ReverseVendLedgEntry|Moved to Codeunit 17 Gen. Jnl.-Post Reverse|  
|ReverseBankAccLedgEntry|ReverseBankAccLedgEntry|Moved to Codeunit 17 Gen. Jnl.-Post Reverse|  
|ReverseVAT|ReverseVAT|Moved to Codeunit 17 Gen. Jnl.-Post Reverse|  
|SetReversalDescription|SetReversalDescription|Moved to Codeunit 17 Gen. Jnl.-Post Reverse|  
|ApplyCustLedgEntryByReversal|ApplyCustLedgEntryByReversal|Moved to Codeunit 17 Gen. Jnl.-Post Reverse|  
|ApplyVendLedgEntryByReversal|ApplyVendLedgEntryByReversal|Moved to Codeunit 17 Gen. Jnl.-Post Reverse|  
|PostPmtDiscountVATByUnapply|PostPmtDiscountVATByUnapply|Moved to Codeunit 17 Gen. Jnl.-Post Reverse|  
||CheckDimComb|Added in Codeunit 17 Gen. Jnl.-Post Reverse|  
||CopyCustLedgEntry|Added in Codeunit 17 Gen. Jnl.-Post Reverse|  
||CopyVendLedgEntry|Added in Codeunit 17 Gen. Jnl.-Post Reverse|  
||CopyBankAccLedgEntry|Added in Codeunit 17 Gen. Jnl.-Post Reverse|  
|HandlDtlAddjustment|HandleDtldAdjustment|Updated|  
|CollectAddjustment|CollectAdjustment|Updated|  
|SetOverDimErr|SetOverDimErr|Updated|  
|PostJob|PostJob|Updated|  
|InsertVATEntriesFromTemp|InsertVATEntriesFromTemp|Updated|  
|CaptureOrRefundCreditCardPmnt|CaptureOrRefundCreditCardPmnt|Updated|  
|UpdateDOPaymentTransactEntry|UpdateDOPaymentTransactEntry|Updated|  
|ABSMin|ABSMin|Updated|  
|GetApplnRoundPrecision|GetApplnRoundPrecision|Updated|  
|CheckDimValueForDisposal|CheckDimValueForDisposal|Updated|  
|CalculateCurrentBalance|CalculateCurrentBalance|Updated|  
|IncludeVATAmount||Moved to Table 81 Gen. Journal Line|  
|CalcVATAmountFromVATEntry|CalcVATAmountFromVATEntry|Updated|  
||TotalVATAmountOnJnlLines|Added|  
||SetGLRegReverse|Added|  
||GetGLSetup|Added|  
||ReadGLSetup|Added|  
||CheckSalesExtDocNo|Added|  
||CheckPurchExtDocNo|Added|  
||CheckGLAccDimError|Added|  
||GetCurrency|Added|  
||PostDtldAdjustment|Added|  
||GetNextEntryNo|Added|  
||GetNextTransactionNo|Added|  
||GetNextVATEntryNo|Added|  
||IncrNextVATEntryNo|Added|  
||IsNotPayment|Added|  
||IsTempGLEntryBufEmpty|Added|  
||IsVATAdjustment|Added|  
||IsVATExcluded|Added|  
||UpdateDimensions|Added|  
||UpdateDimensionsFromCustLedgEntry|Added|  
||UpdateDimensionsFromVendLedgEntry|Added|  
||UpdateTotalAmounts|Added|  
||CreateGLEntriesForTotalAmounts|Added|  

## See Also  
 [Design Details: Codeunit 12 Changes: Mapping Global Variables for General Journal Post Line](design-details-codeunit-12-changes-mapping-global-variables-for-general-journal-post-line.md)
