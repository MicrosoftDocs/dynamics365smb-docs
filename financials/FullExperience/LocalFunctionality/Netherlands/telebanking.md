---
title: "Telebanking"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "F_332_1000007"
helpviewer_keywords: 
  - "electronic banking"
  - "telebanking"
ms.assetid: 9fba84c2-e9ee-47cc-b9b7-ec1fca33b765
caps.latest.revision: 9
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# Telebanking
Based on both sales and purchase transactions, telebanking enables you to generate your payments and collections and interchange them with your bank electronically. This includes the export of payment and collection data that need to be forwarded to the bank as well as the import of bank statements sent to you by the bank.  
  
## Transactions  
 In general, all financial interactions with vendors and customers are done through either purchase or sales invoices and credit memos. As soon as these transactions have been registered and posted, payments or collections can be carried out by your company.  
  
## Proposals  
 Based on vendor and customer ledger entries, telebanking enables you to generate payment and collection proposals. This can be done for any bank that has been set up for your company. Both domestic and foreign payments and collections are possible.  
  
 You can set up ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> to combine payments to or collections from the same bank account automatically.  
  
 When a proposal has been agreed upon, it should be processed into a payment history.  
  
> [!NOTE]  
>  In general, for any open vendor and customer ledger entries, a proposal can be generated if it meets a number of criteria. For more information, see [How to: Create Proposals](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-create-proposals.md).  
  
## Payment Histories  
 A payment history is nothing more than a proposal except for the fact that data on a payment history cannot be modified. The payment or collection data is ready to be exported and forwarded to the bank.  
  
 For more information, see [How to: Create and Export Payment History](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-create-and-export-payment-history.md).  
  
## Bank Statements  
 For all your financial interactions through your bank, the bank can send you electronic bank statements. These statements can be imported into the Bank\/Giro Journals. If you want, you can have ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> automatically reconcile these statements during this import process and determine whether a statement can be applied to open ledger entries for the relevant vendor\/customer.  
  
 For more information, see [How to: Import and Reconcile Bank Statements](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-import-and-reconcile-bank-statements.md).  
  
## Exchange Protocols  
 For both exporting and importing, a number of protocols have been defined. ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> supports the following protocols:  
  
-   CLIEOP3 \(export\)  
  
-   BTL91 \(export\)  
  
-   BBV \(export\)  
  
-   PAYMUL \(export\)  
  
-   Rabobank mut.asc \(import\)  
  
-   Rabobank vvmut.asc \(import\)  
  
-   Rabobank ASCII \(import\)  
  
-   SEPA CAMT  
  
## See Also  
 [How to: Invoice Sales](../../Finance/how-to-invoice-sales.md)   
 [How to: Record Purchases](../../Finance/how-to-record-purchases.md)   
 [How to: Create Proposals](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-create-proposals.md)   
 [How to: Create and Export Payment History](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-create-and-export-payment-history.md)