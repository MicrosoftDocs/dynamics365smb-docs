---
title: "How to: Import Bank Statements"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "bank statements, importing"
  - "importing, bank statements"
ms.assetid: d9d0d0f5-ab95-48f4-8ea0-cd32ba2e79d1
caps.latest.revision: 19
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
# How to: Import Bank Statements
You can import electronic bank statements from your bank to quickly populate [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] with data about actual bank transactions.  
  
 You can use three different features to import bank statements from your bank.  
  
-   Use the Bank Statement service to import the bank statement directly as a bank feed. For setup information, see [How to: Set Up the Bank Statement Service](../../Finance/how-to-set-up-the-bank-statement-service.md) and [How to: Link Bank Accounts to Online Bank Accounts](../../Finance/how-to-link-bank-accounts-to-online-bank-accounts.md).  
  
-   Use the Bank Data Conversion service to convert bank statement files in any format to a data stream that you can import. For setup information, see [How to: Set Up the Bank Data Conversion Service](../../BusinessFunctionality/DataExchange/how-to-set-up-the-bank-data-conversion-service.md).  
  
-   Use the predefined data exchange definition for SEPA CAMT bank statements or set up a new definition for another bank format using the Data Exchange Framework. For setup information, see [How to: Set Up Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md).  
  
> [!NOTE]  
>  For all three features, you start the import by choosing the **Import Bank Transactions** action in the **Payment Reconciliation Journal** window.  
  
 You can import bank statement files in the following scenarios:  
  
-   As the first step in reconciling payments with open entries in the **Payment Reconciliation Journal** window. For more information, see [How to: Reconcile Payments Using Automatic Application](../../Finance/how-to-reconcile-payments-using-automatic-application.md).  
  
-   As the first step in reconciling bank accounts in the **Bank Acc. Reconciliation** window. For more information, see [How to: Match Bank Statement Lines with Bank Account Ledger Entries](../../Finance/how-to-match-bank-statement-lines-with-bank-account-ledger-entries.md).  
  
### To import bank transactions into the Payment Reconciliation Journal Window  
  
1.  In the **Search** box, enter **Payment Reconciliation Journals**, and then choose the related link.  
  
2.  To work in a new payment reconciliation journal, on the **Home** tab, in the **New** group, choose **New Journal** or **Import Bank Statement**.  
  
3.  In the **Payment Bank Account List** window, select the bank account that you want to reconcile payments for, and then choose **OK**.  
  
     The **Payment Reconciliation Journal** window opens prepared for the selected bank account.  
  
4.  On the **Home** tab, in the **Application** group, choose **Import Bank Transactions**.  
  
     If the bank account for the selected journal is not set up for importing bank statements, then a dialog will open to help you fill the relevant fields. For more information, see [Bank Statement Import Format](assetId:///374c6ddb-872c-452f-9f61-8d86d3d8c503).  
  
5.  In the **Select a file to import** window, select the file that contains the bank transactions for payments that you want to reconcile, and then choose **Open**.  
  
6.  If the Bank Statement service is enabled, in the **Bank Statement Filter** window, specify the date interval for the bank statements to be imported as a bank feed.  
  
 You can now proceed to review the automatic payment applications automatically or manually apply. For more information, see [How to: Reconcile Payments Using Automatic Application](../../Finance/how-to-reconcile-payments-using-automatic-application.md) and [How to: Review or Apply Payments After Automatic Application](../../Finance/how-to-review-or-apply-payments-after-automatic-application.md).  
  
### To import bank statements into the Bank Acc. Reconciliation window  
  
1.  In the **Search** box, enter **Bank Account Reconciliation**, and then choose the related link.  
  
2.  In the **Bank Acc. Reconciliation** window, on the **Home** tab, in the **Bank** group, choose **Import Bank Statement**.  
  
3.  Select the bank statement file, and then choose **Open**.  
  
     The bank statement lines are filled into the left pane of the **Bank Acc. Reconciliation** window.  
  
 You can now proceed to automatically or manually match bank entries to reconcile the bank account. For more information, see [How to: Match Bank Statement Lines with Bank Account Ledger Entries](../../Finance/how-to-match-bank-statement-lines-with-bank-account-ledger-entries.md).  
  
## See Also  
 [Payment Reconciliation Journal](assetId:///f4e11659-b474-4de0-bfae-2ae0116d0665)   
 [Bank Acc. Reconciliation](assetId:///69629c1f-013d-4c91-8175-5420a49876a7)   
 [How to: Reconcile Payments Using Automatic Application](../../Finance/how-to-reconcile-payments-using-automatic-application.md)   
 [How to: Match Bank Statement Lines with Bank Account Ledger Entries](../../Finance/how-to-match-bank-statement-lines-with-bank-account-ledger-entries.md)   
 [How to: Set Up the Bank Statement Service](../../Finance/how-to-set-up-the-bank-statement-service.md)   
 [How to: Link Bank Accounts to Online Bank Accounts](../../Finance/how-to-link-bank-accounts-to-online-bank-accounts.md)   
 [How to: Set Up the Bank Data Conversion Service](../../BusinessFunctionality/DataExchange/how-to-set-up-the-bank-data-conversion-service.md)   
 [How to: Set Up Data Exchange Definitions](../../BusinessFunctionality/DataExchange/how-to-set-up-data-exchange-definitions.md)