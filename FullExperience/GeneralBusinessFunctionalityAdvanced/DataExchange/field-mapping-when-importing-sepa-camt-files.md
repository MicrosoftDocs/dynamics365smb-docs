---
title: "Field Mapping When Importing SEPA CAMT Files"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: e381a9cc-dbb5-4558-bf21-b71b2b0ac096
caps.latest.revision: 6
ms.author: "sgroespe"
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
# Field Mapping When Importing SEPA CAMT Files
The generic version of Microsoft Dynamics NAV supports the regional SEPA standard \(Single Euro Payments Area\) for importing SEPA bank statements \(CAMT format\). For more information, see [How to: Import Bank Statements](../../BusinessFunctionality/DataExchange/how-to-import-bank-statements.md).  
  
 The SEPA CAMT standard itself has local variations. Therefore, you may have to modify the generic data exchange definition \(represented by the **SEPA CAMT** code in the **Posting Exchange Definitions** window to adapt it to a local variation of the standard. The following tables show the element\-to\-field mapping for tables 81, 273, and 274 in the SEPA CAMT implementation in [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)].  
  
 For information about creating or adjusting a data exchange definition, see [How to: Set Up Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md).  
  
## CAMT data mapping to fields in the General Journal table \(81\)  
  
|Element Path|Message Element|Data Type|Description|Negative\-Sign Identifier|Field No.|Field Name|  
|------------------|---------------------|---------------|-----------------|-------------------------------|---------------|----------------|  
|Stmt\/Ntry\/Amt|Amount|Decimal|The amount of money in the cash entry||13|Amount|  
|Stmt\/Ntry\/CdtDbtInd|CreditDebitIndicator|Text|Indicates whether the entry is a credit or a debit entry|DBIT|13|Amount|  
|Stmt\/Ntry\/BookgDt\/Dt|Date|Date|The date when an entry is posted to an account on the account servicer's books||5|Posting Date|  
|Stmt\/Ntry\/BookgDt\/DtTm|DateTime|DateTime|The date and time when an entry is posted to an account on the account servicer's books||5|Posting Date|  
|Stmt\/Ntry\/NtryDtls\/TxDtls\/RltdPties\/Dbtr\/Nm|Name|Text|The name of the party that owes an amount of money to the \(ultimate\) creditor||1221|Payer Information|  
|Stmt\/Ntry\/NtryDtls\/TxDtls\/RmtInf\/Ustrd|Unstructured|Text|Information supplied to enable the matching\/reconciliation of an entry with the items that the payment is intended to settle, such as commercial invoices in an accounts\-receivable system, in an unstructured form||8|Description|  
|Stmt\/Ntry\/AddtlNtryInf|AdditionalEntryInformation|Text|Additional information about the entry||1222|Transaction Information|  
  
## CAMT data mapping to fields in the Bank Acc. Reconciliation table \(273\)  
  
|Element Path|Message Element|Data Type|Description|Negative\-Sign Identifier|Field No.|Field Name|  
|------------------|---------------------|---------------|-----------------|-------------------------------|---------------|----------------|  
|Stmt\/CreDtTm|CreationDateTime|Date|The date and time when the message was created||3|Statement Date|  
|Stmt\/Bal\/Amt|Amount|Decimal|The amount resulting from the netted amounts for all debit and credit entries||4|Statement Ending Balance|  
  
## CAMT data mapping to fields in the Bank Acc. Reconciliation Line table \(274\)  
  
|Element Path|Message Element|Data Type|Description|Negative\-Sign Identifier|Field No.|Field Name|  
|------------------|---------------------|---------------|-----------------|-------------------------------|---------------|----------------|  
|Stmt\/Ntry\/Amt|Amount|Decimal|The amount of money in the cash entry||7|Statement Amount|  
|Stmt\/Ntry\/CdtDbtInd|CreditDebitIndicator|Text|Indicates whether the entry is a credit or a debit entry|DBIT|7|Statement Amount|  
|Stmt\/Ntry\/BookgDt\/Dt|Date|Date|The date when an entry is posted to an account on the account servicer's books||5|Transaction Date|  
|Stmt\/Ntry\/BookgDt\/DtTm|DateTime|DateTime|The date and time when an entry is posted to an account on the account servicer's books||5|Transaction Date|  
|Stmt\/Ntry\/ValDt\/Dt|Date|Date|The date when assets become available to the account owner in case of a credit entry, or cease to be available to the account owner in case of a debit entry||12|Value Date|  
|Stmt\/Ntry\/ValDt\/DtTm|DateTime|DateTime|The date and time when assets become available to the account owner in case of a credit entry, or cease to be available to the account owner in case of a debit entry||12|Value Date|  
|Stmt\/Ntry\/NtryDtls\/TxDtls\/RltdPties\/Dbtr\/Nm|Name|Text|The name of the party that owes an amount of money to the \(ultimate\) creditor||15|Payer Information|  
|Stmt\/Ntry\/NtryDtls\/TxDtls\/RmtInf\/Ustrd|Unstructured|Text|Information supplied to enable the matching\/reconciliation of an entry with the items that the payment is intended to settle, such as commercial invoices in an accounts\-receivable system, in an unstructured form||6|Description|  
|Stmt\/Ntry\/AddtlNtryInf|AdditionalEntryInformation|Text|Additional information about the entry||16|Transaction Information|  
  
 Elements in the **Ntry** node that are imported into [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] but not mapped to any fields are stored in the **Posting Exch. Column Def** table. Users can view these elements from the **Payment Reconciliation Journal**, **Payment Application**, and **Bank Acc. Reconciliation** windows by choosing the **Bank Statement Line Details** action. For more information, see [Reconcile Payments Automatically](../../Finance/reconcile-payments-automatically.md).  
  
## See Also  
 [Data Exchange Definitions](../Topic/\($%20N_1211%20Data%20Exchange%20Definitions%20$\).md)   
 [Payment Reconciliation Journal](assetId:///f4e11659-b474-4de0-bfae-2ae0116d0665)   
 [Payment Application](assetId:///9a893306-216c-4a39-b541-9ce96894432d)   
 [Bank Acc. Reconciliation](assetId:///69629c1f-013d-4c91-8175-5420a49876a7)   
 [Data Exchange](../../BusinessFunctionality/DataExchange/data-exchange.md)   
 [How to: Import Bank Statements](../../BusinessFunctionality/DataExchange/how-to-import-bank-statements.md)   
 [How to: Use XML Schemas to Prepare Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-use-xml-schemas-to-prepare-data-exchange-definitions.md)   
 [How to: Reconcile Payments Using Automatic Application](../../Finance/how-to-reconcile-payments-using-automatic-application.md)   
 [How to: Match Bank Statement Lines with Bank Account Ledger Entries](../../Finance/how-to-match-bank-statement-lines-with-bank-account-ledger-entries.md)