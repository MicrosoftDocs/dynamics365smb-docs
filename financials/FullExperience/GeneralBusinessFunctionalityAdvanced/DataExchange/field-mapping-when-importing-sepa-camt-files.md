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
# Field Mapping When Importing SEPA CAMT Files
The generic version of Microsoft Dynamics NAV supports the regional SEPA standard \(Single Euro Payments Area\) for importing SEPA bank statements \(CAMT format\). For more information, see [How to: Import Bank Statements](../FullExperience/how-to-import-bank-statements.md).  
  
 The SEPA CAMT standard itself has local variations. Therefore, you may have to modify the generic data exchange definition \(represented by the **SEPA CAMT** code in the **Posting Exchange Definitions** window to adapt it to a local variation of the standard. The following tables show the element-to-field mapping for tables 81, 273, and 274 in the SEPA CAMT implementation in ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/dyn_nav_md.md)]-->.  
  
 For information about creating or adjusting a data exchange definition, see [How to: Set Up Data Exchange Definitions](../FullExperience/how-to-set-up-data-exchange-definitions.md).  
  
## CAMT data mapping to fields in the General Journal table \(81\)  
  
|Element Path|Message Element|Data Type|Description|Negative-Sign Identifier|Field No.|Field Name|  
|------------------|---------------------|---------------|-----------------|-------------------------------|---------------|----------------|  
|Stmt\/Ntry\/Amt|Amount|Decimal|The amount of money in the cash entry||13|Amount|  
|Stmt\/Ntry\/CdtDbtInd|CreditDebitIndicator|Text|Indicates whether the entry is a credit or a debit entry|DBIT|13|Amount|  
|Stmt\/Ntry\/BookgDt\/Dt|Date|Date|The date when an entry is posted to an account on the account servicer's books||5|Posting Date|  
|Stmt\/Ntry\/BookgDt\/DtTm|DateTime|DateTime|The date and time when an entry is posted to an account on the account servicer's books||5|Posting Date|  
|Stmt\/Ntry\/NtryDtls\/TxDtls\/RltdPties\/Dbtr\/Nm|Name|Text|The name of the party that owes an amount of money to the \(ultimate\) creditor||1221|Payer Information|  
|Stmt\/Ntry\/NtryDtls\/TxDtls\/RmtInf\/Ustrd|Unstructured|Text|Information supplied to enable the matching\/reconciliation of an entry with the items that the payment is intended to settle, such as commercial invoices in an accounts-receivable system, in an unstructured form||8|Description|  
|Stmt\/Ntry\/AddtlNtryInf|AdditionalEntryInformation|Text|Additional information about the entry||1222|Transaction Information|  
  
## CAMT data mapping to fields in the Bank Acc. Reconciliation table \(273\)  
  
|Element Path|Message Element|Data Type|Description|Negative-Sign Identifier|Field No.|Field Name|  
|------------------|---------------------|---------------|-----------------|-------------------------------|---------------|----------------|  
|Stmt\/CreDtTm|CreationDateTime|Date|The date and time when the message was created||3|Statement Date|  
|Stmt\/Bal\/Amt|Amount|Decimal|The amount resulting from the netted amounts for all debit and credit entries||4|Statement Ending Balance|  
  
## CAMT data mapping to fields in the Bank Acc. Reconciliation Line table \(274\)  
  
|Element Path|Message Element|Data Type|Description|Negative-Sign Identifier|Field No.|Field Name|  
|------------------|---------------------|---------------|-----------------|-------------------------------|---------------|----------------|  
|Stmt\/Ntry\/Amt|Amount|Decimal|The amount of money in the cash entry||7|Statement Amount|  
|Stmt\/Ntry\/CdtDbtInd|CreditDebitIndicator|Text|Indicates whether the entry is a credit or a debit entry|DBIT|7|Statement Amount|  
|Stmt\/Ntry\/BookgDt\/Dt|Date|Date|The date when an entry is posted to an account on the account servicer's books||5|Transaction Date|  
|Stmt\/Ntry\/BookgDt\/DtTm|DateTime|DateTime|The date and time when an entry is posted to an account on the account servicer's books||5|Transaction Date|  
|Stmt\/Ntry\/ValDt\/Dt|Date|Date|The date when assets become available to the account owner in case of a credit entry, or cease to be available to the account owner in case of a debit entry||12|Value Date|  
|Stmt\/Ntry\/ValDt\/DtTm|DateTime|DateTime|The date and time when assets become available to the account owner in case of a credit entry, or cease to be available to the account owner in case of a debit entry||12|Value Date|  
|Stmt\/Ntry\/NtryDtls\/TxDtls\/RltdPties\/Dbtr\/Nm|Name|Text|The name of the party that owes an amount of money to the \(ultimate\) creditor||15|Payer Information|  
|Stmt\/Ntry\/NtryDtls\/TxDtls\/RmtInf\/Ustrd|Unstructured|Text|Information supplied to enable the matching\/reconciliation of an entry with the items that the payment is intended to settle, such as commercial invoices in an accounts-receivable system, in an unstructured form||6|Description|  
|Stmt\/Ntry\/AddtlNtryInf|AdditionalEntryInformation|Text|Additional information about the entry||16|Transaction Information|  
  
 Elements in the **Ntry** node that are imported into ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/reconcile-payments-automatically.md).  
  
## See Also  
 Data Exchange Definitions   
 Payment Reconciliation Journal   
 Payment Application   
 Bank Acc. Reconciliation   
 [Data Exchange](../FullExperience/data-exchange.md)   
 [How to: Import Bank Statements](../FullExperience/how-to-import-bank-statements.md)   
 [How to: Use XML Schemas to Prepare Data Exchange Definitions](../FullExperience/how-to-use-xml-schemas-to-prepare-data-exchange-definitions.md)   
 [How to: Reconcile Payments Using Automatic Application](../FullExperience/how-to-reconcile-payments-using-automatic-application.md)   
 [How to: Match Bank Statement Lines with Bank Account Ledger Entries](../FullExperience/how-to-match-bank-statement-lines-with-bank-account-ledger-entries.md)