---
title: Field mapping when importing SEPA CAMT files | Microsoft Docs
description: Import bank statement files in the regional SEPA (Single Euro Payments Area) format for European markets.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.search.keywords: field mapping, SEPA CAMT, SEPA bank statements, CAMT format, data exchange definition
ms.service: dynamics-365-business-central
ms.topic: article
ms.date: 10/14/2025
ms.custom: bap-template
---

# Field mapping when importing SEPA CAMT files

[!INCLUDE[prod_short](includes/prod_short.md)] supports the regional SEPA standards (Single Euro Payments Area) for importing SEPA bank statements (CAMT format). Learn more in [Use the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md).  

The SEPA CAMT standard itself has local variations. Therefore, you may have to modify the generic data exchange definition (represented by the **SEPA CAMT** code on the **Data Exchange Definitions** page) to adapt it to a local variation of the standard. The following tables show the element-to-field mapping for tables 81, 273, and 274 in the SEPA CAMT implementation in [!INCLUDE[prod_short](includes/prod_short.md)].  

Learn more in [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md) for information about creating or adjusting a data exchange definition.  

> [!NOTE]
> Starting in November 2025, most countries/regions in the European Union (including Switzerland) are mandating the SEPA CAMT.053.001.08 format (based on the updated ISO 20022 XML standard).
>
> To set up a corresponding SEPA CAMT.053.001.08 format in [!INCLUDE [prod_short](includes/prod_short.md)], open the **Bank Import/Export Setup** page and choose the **Setup/SEPA CAMT 053.001.08** action. Then, you can open a **Bank Account Card** page for an account and choose **SEPA CAMT 053.001.08** in the **Bank Statement Import Setup** field.

## CAMT data mapping to fields in the General Journal table (81)  

|Element Path|Message Element|Data Type|Description|Negative-Sign Identifier|Field No.|Field Name|  
|------------------|---------------------|---------------|-----------------|-------------------------------|---------------|----------------|  
|Stmt/Ntry/Amt|Amount|Decimal|The amount of money in the cash entry||13|Amount|  
|Stmt/Ntry/CdtDbtInd|CreditDebitIndicator|Text|Indicates whether the entry is a credit or a debit entry|DBIT|13|Amount|  
|Stmt/Ntry/BookgDt/Dt|Date|Date|The date when an entry is posted to an account on the account servicer's books||5|Posting Date|  
|Stmt/Ntry/BookgDt/DtTm|DateTime|DateTime|The date and time when an entry is posted to an account on the account servicer's books||5|Posting Date|  
|Stmt/Ntry/NtryDtls/TxDtls/RltdPties/Dbtr/Nm|Name|Text|The name of the party that owes an amount of money to the (ultimate) creditor||1221|Payer Information|  
|Stmt/Ntry/NtryDtls/TxDtls/RmtInf/Ustrd|Unstructured|Text|Information supplied to enable the matching/reconciliation of an entry with the items that the payment is intended to settle, such as commercial invoices in an accounts-receivable system, in an unstructured form||8|Description|  
|Stmt/Ntry/AddtlNtryInf|AdditionalEntryInformation|Text|Additional information about the entry||1222|Transaction Information|  

## CAMT data mapping to fields in the Bank Acc. Reconciliation table (273)  

|Element Path|Message Element|Data Type|Description|Negative-Sign Identifier|Field No.|Field Name|  
|------------------|---------------------|---------------|-----------------|-------------------------------|---------------|----------------|  
|Stmt/CreDtTm|CreationDateTime|Date|The date and time when the message was created||3|Statement Date|  
|Stmt/Bal/Amt|Amount|Decimal|The amount resulting from the netted amounts for all debit and credit entries||4|Statement Ending Balance|  

## CAMT data mapping to fields in the Bank Acc. Reconciliation Line table (274)  

|Element Path|Message Element|Data Type|Description|Negative-Sign Identifier|Field No.|Field Name|  
|------------------|---------------------|---------------|-----------------|-------------------------------|---------------|----------------|  
|Stmt/Ntry/Amt|Amount|Decimal|The amount of money in the cash entry||7|Statement Amount|  
|Stmt/Ntry/CdtDbtInd|CreditDebitIndicator|Text|Indicates whether the entry is a credit or a debit entry|DBIT|7|Statement Amount|  
|Stmt/Ntry/BookgDt/Dt|Date|Date|The date when an entry is posted to an account on the account servicer's books||5|Transaction Date|  
|Stmt/Ntry/BookgDt/DtTm|DateTime|DateTime|The date and time when an entry is posted to an account on the account servicer's books||5|Transaction Date|  
|Stmt/Ntry/ValDt/Dt|Date|Date|The date when assets become available to the account owner in case of a credit entry, or cease to be available to the account owner in case of a debit entry||12|Value Date|  
|Stmt/Ntry/ValDt/DtTm|DateTime|DateTime|The date and time when assets become available to the account owner in case of a credit entry, or cease to be available to the account owner in case of a debit entry||12|Value Date|  
|Stmt/Ntry/NtryDtls/TxDtls/RltdPties/Dbtr/Nm|Name|Text|The name of the party that owes an amount of money to the (ultimate) creditor||15|Payer Information|  
|Stmt/Ntry/NtryDtls/TxDtls/RmtInf/Ustrd|Unstructured|Text|Information supplied to enable the matching/reconciliation of an entry with the items that the payment is intended to settle, such as commercial invoices in an accounts-receivable system, in an unstructured form||6|Description|  
|Stmt/Ntry/AddtlNtryInf|AdditionalEntryInformation|Text|Additional information about the entry||16|Transaction Information|  

 Elements in the **Ntry** node that are imported into [!INCLUDE[prod_short](includes/prod_short.md)] but not mapped to any fields are stored in the **Posting Exch. Column Def** table. Users can view these elements from the **Payment Reconciliation Journal**, **Payment Application**, and **Bank Acc. Reconciliation** pages by choosing the **Bank Statement Line Details** action. Learn more in [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).

> [!IMPORTANT]
> In an import of CAMT bank statements, [!INCLUDE[prod_short](includes/prod_short.md)] expects each transaction to be unique, which means that the **Transaction ID** field that comes from the *Stmt/Ntry/NtryDtls/TxDtls/Refs/EndToEndId* tag in the CAMT file, must be unique within the open bank account reconciliation. If the information is not present, [!INCLUDE[prod_short](includes/prod_short.md)] ignores the payment. If an earlier bank reconciliation on the same bank account was posted with the same transaction ID as on the current import, the current transaction will not automatically reconcile but can still be imported.

## Related information  

[Set Up Data Exchange](across-set-up-data-exchange.md)  
[Exchange Data Electronically](across-data-exchange.md)  
[Use the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md)  
[Use XML Schemas to Prepare Data Exchange Definitions](across-how-to-use-xml-schemas-to-prepare-data-exchange-definitions.md)  
[Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
