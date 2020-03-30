---
    title: Design Details - Codeunit 12 Changes in Mapping Global Variables for General Journal Post Line | Microsoft Docs
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
# Codeunit 12 Changes: Mapping Global Variables for General Journal Post Line
The following changes have been implemented in this release of [!INCLUDE[d365fin](includes/d365fin_md.md)].  

|**Microsoft Dynamics NAV 2009 R2**|**Microsoft Dynamics NAV 2013 R2**|**Comment**|  
|----------------------------------------|----------------------------------------|-----------------|  
|GLSetup@1009 : Record 98;|GLSetup@1009 : Record 98;|Unchanged|  
|SalesSetup@1010 : Record 311;||Changed to Local|  
|PurchSetup@1011 : Record 312;||Changed to Local|  
|AccountingPeriod@1012 : Record 50;||Changed to Local|  
|GLAcc@1013 : Record 15;||Changed to Local|  
|GLEntry@1014 : Record 17;|GlobalGLEntry@1014 : Record 17;|Renamed|  
|GLEntryTmp@1015 : TEMPORARY Record 17;|TempGLEntryBuf@1010 : TEMPORARY Record 17;|Renamed|  
|TempGLEntryVAT@1016 : TEMPORARY Record 17;|TempGLEntryVAT@1016 : TEMPORARY Record 17;|Unchanged|  
|OrigGLEntry@1017 : Record 17;||Deleted|  
|VATPostingSetup@1019 : Record 325;||Changed to Local|  
|Cust@1020 : Record 18;||Changed to Local|  
|Vend@1021 : Record 23;||Changed to Local|  
|GenJnlLine@1022 : Record 81;||Changed to Local|  
|GLReg@1029 : Record 45;|GLReg@1029 : Record 45;|Unchanged|  
|CustPostingGr@1030 : Record 92;||Changed to Local|  
|VendPostingGr@1031 : Record 93;||Changed to Local|  
|Currency@1032 : Record 4;||Changed to Local|  
|AddCurrency@1033 : Record 4;|AddCurrency@1033 : Record 4;|Unchanged|  
|ApplnCurrency@1034 : Record 4;||Changed to Local|  
|CurrExchRate@1035 : Record 330;|CurrExchRate@1035 : Record 330;|Unchanged|  
|VATEntry@1038 : Record 254;|VATEntry@1038 : Record 254;|Unchanged|  
|BankAcc@1039 : Record 270;||Changed to Local|  
|BankAccLedgEntry@1040 : Record 271;||Changed to Local|  
|CheckLedgEntry@1041 : Record 272;||Changed to Local|  
|CheckLedgEntry2@1042 : Record 272;||Changed to Local|  
|BankAccPostingGr@1043 : Record 277;||Changed to Local|  
|GenJnlTemplate@1044 : Record 80;||Changed to Local|  
|TaxJurisdiction@1045 : Record 320;||Changed to Local|  
|TaxDetail@1046 : Record 322;|TaxDetail@1046 : Record 322;|Unchanged|  
|FAGLPostBuf@1047 : TEMPORARY Record 5637;||Changed to Local|  
|UnrealizedCustLedgEntry@1084 : Record 21;|UnrealizedCustLedgEntry@1084 : Record 21;|Unchanged|  
|UnrealizedVendLedgEntry@1085 : Record 25;|UnrealizedVendLedgEntry@1085 : Record 25;|Unchanged|  
|GLEntryVATEntryLink@1087 : Record 253;|GLEntryVATEntryLink@1087 : Record 253;|Unchanged|  
|TempVATEntry@1088 : TEMPORARY Record 254;|TempVATEntry@1088 : TEMPORARY Record 254;|Unchanged|  
|ReversedGLEntryTemp@1089 : TEMPORARY Record 17;||Moved to Codeunit17|  
|CostAccSetup@1092 : Record 1108;||Changed to Local|  
|GenJnlCheckLine@1048 : Codeunit 11;|GenJnlCheckLine@1001 : Codeunit 11;|Unchanged|  
|ExchAccGLJnlLine@1049 : Codeunit 366;||Changed to Local|  
|FAJnlPostLine@1050 : Codeunit 5632;||Changed to Local|  
|SalesTaxCalculate@1051 : Codeunit 398;||Changed to Local|  
|GenJnlApply@1052 : Codeunit 225;||Changed to Local|  
|DimMgt@1053 : Codeunit 408;||Changed to Local|  
|JobPostLine@1028 : Codeunit 1001;||Changed to Local|  
|TransferGlEntriesToCA@1091 : Codeunit 1105;||Changed to Local|  
||PaymentToleranceMgt@1002 : Codeunit 426;|Added|  
||AddCurrencyCode@1117 : Code[10];|Added|  
|FiscalYearStartDate@1054 : Date;|FiscalYearStartDate@1011 : Date;|Unchanged|  
|NextEntryNo@1055 : Integer;|NextEntryNo@1022 : Integer;|Unchanged|  
|BalanceCheckAmount@1056 : Decimal;|BalanceCheckAmount@1056 : Decimal;|Unchanged|  
|BalanceCheckAmount2@1057 : Decimal;|BalanceCheckAmount2@1057 : Decimal;|Unchanged|  
|BalanceCheckAddCurrAmount@1058 : Decimal;|BalanceCheckAddCurrAmount@1058 : Decimal;|Unchanged|  
|BalanceCheckAddCurrAmount2@1059 : Decimal;|BalanceCheckAddCurrAmount2@1059 : Decimal;|Unchanged|  
|CurrentBalance@1060 : Decimal;|CurrentBalance@1060 : Decimal;|Unchanged|  
|SalesTaxBaseAmount@1061 : Decimal;||Changed to Local|  
|TotalAddCurrAmount@1062 : Decimal;|TotalAddCurrAmount@1062 : Decimal;|Unchanged|  
|TotalAmount@1063 : Decimal;|TotalAmount@1063 : Decimal;|Unchanged|  
|UnrealizedRemainingAmountCust@1086 : Decimal;|UnrealizedRemainingAmountCust@1086 : Decimal;|Unchanged|  
|UnrealizedRemainingAmountVend@1074 : Decimal;|UnrealizedRemainingAmountVend@1074 : Decimal;|Unchanged|  
|NextVATEntryNo@1064 : Integer;|NextVATEntryNo@1064 : Integer;|Unchanged|  
|FirstNewVATEntryNo@1065 : Integer;|FirstNewVATEntryNo@1065 : Integer;|Unchanged|  
|NextTransactionNo@1066 : Integer;|NextTransactionNo@1066 : Integer;|Unchanged|  
|NextConnectionNo@1067 : Integer;|NextConnectionNo@1067 : Integer;|Unchanged|  
|InsertedTempGLEntryVAT@1068 : Integer;|InsertedTempGLEntryVAT@1027 : Integer;|Unchanged|  
|LastDocNo@1069 : Code[20];|LastDocNo@1023 : Code[20];|Unchanged|  
|LastLineNo@1070 : Integer;||Deleted|  
|LastDate@1071 : Date;|LastDate@1021 : Date;|Unchanged|  
|LastDocType@1072 : ' ,Payment,Invoice,Credit Memo,Finance Charge Memo,Reminder';|LastDocType@1025 : ' ,Payment,Invoice,Credit Memo,Finance Charge Memo,Reminder';|Unchanged|  
|NextCheckEntryNo@1073 : Integer;|NextCheckEntryNo@1028 : Integer;|Unchanged|  
|AddCurrGLEntryVATAmt@1075 : Decimal;|AddCurrGLEntryVATAmt@1017 : Decimal;|Unchanged|  
|CurrencyDate@1076 : Date;|CurrencyDate@1020 : Date;|Unchanged|  
|CurrencyFactor@1077 : Decimal;|CurrencyFactor@1019 : Decimal;|Unchanged|  
|UseCurrFactorOnly@1078 : Boolean;|UseCurrFactorOnly@1078 : Boolean;|Unchanged|  
|NonAddCurrCodeOccured@1079 : Boolean;|NonAddCurrCodeOccured@1079 : Boolean;|Unchanged|  
|FADimAlreadyChecked@1080 : Boolean;|FADimAlreadyChecked@1080 : Boolean;|Unchanged|  
|AllApplied@1081 : Boolean;||Changed to Local|  
|OverrideDimErr@1018 : Boolean;|OverrideDimErr@1018 : Boolean;|Unchanged|  
|JobLine@1036 : Boolean;|JobLine@1036 : Boolean;|Unchanged|  
|Prepayment@1037 : Boolean;||Deleted|  
|CheckUnrealizedCust@1082 : Boolean;|CheckUnrealizedCust@1082 : Boolean;|Unchanged|  
|CheckUnrealizedVend@1083 : Boolean;|CheckUnrealizedVend@1083 : Boolean;|Unchanged|  
|GLEntryNo@1090 : Integer;|GLEntryNo@1026 : Integer;|Unchanged|  
||GLSetupRead@1015 : Boolean;|Added|  
||AmountRoundingPrecision@1012 : Decimal;|Added|  
||CrCardTransactionEntryNo@1013 : Integer;|Added|  

## See Also  
 [Design Details: Codeunit 12 Changes: Changes in General Journal Post Procedures](design-details-codeunit-12-changes-changes-in-general-journal-post-procedures.md)
