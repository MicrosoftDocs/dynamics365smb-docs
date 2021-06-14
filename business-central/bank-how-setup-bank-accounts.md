---
title: Set Up Bank Accounts| Microsoft Docs
description: You can reconcile bank accounts with statements from the bank.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Yodlee, feed, stream
ms.date: 04/01/2021
ms.author: edupont

---
# Set Up Bank Accounts
You use bank accounts in [!INCLUDE[prod_short](includes/prod_short.md)] to keep track of your banking transactions. Accounts can be denominated in your local currency or in a foreign currency. After you have set up bank accounts, you can also use the check printing option. The bank accounts includes extra functionality for [Payment Reconciliation](receivables-apply-payments-auto-reconcile-bank-accounts.md), [Bank Reconciliation](bank-how-reconcile-bank-accounts-separately.md) and import/export of bank files. The bank accounts can also be included in transactions in the general journals. Each bank account is linked to an account in the chart of accounts through the Bank Account Posting Group.
Using a bank account in a payment transaction will automatically create an entry in both the bank account and the connected G/L Account.<br><br>
The bank accounts handle differently weather the currency code is filled or not.
If the currency code is blank, all transactions in the bank account will be in the local currency (LCY). This also applies to currency transactions made to the account. In that case, they will be posted to the account in local currency (LCY) amount using the currency rate used in the transaction. Any checks issued from this account must be issued in the local currency (LCY) though. Using the bank account in a journal will automatically default the blank currency code.<br><br>
If a currency code has been applied to the account, all transactions made to this account must be in the same currency. All checks issued from this account, must also follow the same currency.
<br><br>
A bank account is usually monitored daily to ensure that any new payments from customers are registered as quickly as possible. This is to ensure that the actual status of the customer is reflected in [!INCLUDE[prod_short](includes/prod_short.md)], and it helps to provide relevant and up-to-date information to sales people, accountants and other employees. This also prevents unnecessary calls to the customer regarding overdue invoices or delay in shipments. Likewise, it is necessary to import the vendor currency payments with the realized currency rates, to ensure that the actual status of the vendors is up-to-date. The easiest way to ensure that the bank account is updated is using the [Payment Reconciliation](receivables-apply-payments-auto-reconcile-bank-accounts.md). In the Payment Reconciliation Journal it is possible to import bank transactions directly from the on-line bank application and have them posted more or less automatically. The Payment Reconciliation Journal is able to automatically identify and post the following:
<br>

- Direct Debit Payments from customers
- Customer Payments of single invoices
- Lump-sum Payments from customers
- Customer Payments in foreign currencies
- Vendor payments
- Vendor payments in foreign currency
- Recurring vendor payments and subscriptions
- Bank charges and interests
<br>

This can provide massive time savings in posting the incoming and outgoing payments, however we cannot be sure that the transactions on the bank account in [!INCLUDE[prod_short](includes/prod_short.md)] is 100% correct until a bank reconciliation has been performed.
The bank reconciliation is the way to ensure that the bank account in [!INCLUDE[prod_short](includes/prod_short.md)] matches the external account at the bank.

 ![Bank Account Reconciliation](media/Set-Up-Bank-Accounts/BankReconciliation.png)

Above the left side represents the bank account in [!INCLUDE[prod_short](includes/prod_short.md)] and the right side represents the transactions imported from the account in the bank through the on-line bank application. The bank reconciliation window in the middle shows the transactions from both sides.
<br><br>
From the bank account in [!INCLUDE[prod_short](includes/prod_short.md)], most transactions should be known to physical bank. The only exceptions (marked in red) could be:
- Corrections posted in [!INCLUDE[prod_short](includes/prod_short.md)] 
- Checks issued that has not been cashed yet 
- or vendor payments that been approved by the bank.

From the physical Account in the bank unknown transactions ,that wasn't identified in the Payment Reconciliation journal, come all the time:
- New vendor subscriptions 
- Customer payments without description
- Bank interests
- Bank Charges
- Credit card charges that hasn't been reported yet
- 
The better mapping information in the payment reconciliation journal, the more transactions are posted automatically and the easier the periodic bank reconciliation becomes.

<br><br>

> [!Video https://www.microsoft.com/videoplayer/embed/RE3Vhpl?rel=0]

<br><br>

## To set up bank accounts

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. On the **Bank Accounts** page, choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] or refer to the table below for an explanation.
<br><br> 
> [!TIP]
> Some of the fields might only be visible clicking the **Show More fields** or by retrieving the fields by Personalizing the page. |PERSONALIZATION Personalize the User Interface.

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**General FastTab**||
|No.|Specifies the number of the bank account, according to the specified number series. If the number series allow manual numbering, any alphanumeric code up to 20 characters can be used.|
|Name|The Name of the bank holding the bank account.|
|Bank Branch No.|The Bank Branch No. is usually used to identify the bank branch in domestic payments. The Bank Branch No. is very often considered a sensitive field. Read more about [Monitoring Sensitive Fields](across-log-changes#monitoring-sensitive-fields).|
|Bank Account No.|Bank Account No. is usually used to identify the bank account no. in domestic payments. The Bank Account No. is very often considered a sensitive field. Read more about [Monitoring Sensitive Fields](across-log-changes#monitoring-sensitive-fields).|
|Balance|Shows the Balance of the bank account in the account currency.|
|Balance (LCY)|Shows the Balance of the bank account in the local currency (LCY).|
|Our Contact Code|Specifies a code to specify the employee who is responsible for this bank account. The employee must be created in the **Salesperson/Purchaser** table.|
|Blocked|Specifies that the related record is blocked from being posted in transactions, for example the account is obsolete after a bank change.|
|SEPA Direct Debit Exp. Format|Specifies the SEPA format of the bank file that will be exported when you choose the **Create Direct Debit File** button in the **Direct Debit Collect. Entries** window. Read more in [SEPA Direct Debit in Business Central](finance-collect-payments-with-sepa-direct-debit.md).|
|Credit Transfer Msg. Nos.|Specifies the number series for bank instruction messages that are created with the export file that you create from the Direct Debit Collect. Entries window. Read more in [SEPA Direct Debit in Business Central](finance-collect-payments-with-sepa-direct-debit.md).|
|Direct Debit Msg. Nos.|Specifies the number series that will be used on the direct debit file that you export for a direct-debit collection entry in the Direct Debit Collect. Entries window. Read more in [SEPA Direct Debit in Business Central](finance-collect-payments-with-sepa-direct-debit.md).|
|Creditor No.|Specifies your company as the creditor in connection with payment collection from customers using SEPA Direct Debit. Read more in [SEPA Direct Debit in Business Central](finance-collect-payments-with-sepa-direct-debit.md).|
|Bank Clearing Standard|The national bank names register used for the sender bank account.|
|Bank Clearing Code|Specifies the code for bank clearing that is required according to the format standard that you selected in the Bank Clearing Standard field. The bank clearing code can be used as an alternative to SWIFT and IBAN to identify your bank as sender of a bank transfer.|
|Last Date Modified|Date of the latest modification of the bank account.|
|**Payment Matching**||
|Disable Automatic Payment Matching|Specifies whether to disable automatic payment matching after importing bank transactions for this bank account. Read more in [Payment Reconciliation](receivables-apply-payments-auto-reconcile-bank-accounts.md).|
|**Payment Match Tolerance**||
|Match Tolerance Type|Specifies by which tolerance the automatic payment application function will apply the Amount Incl. Tolerance Matched rule for this bank account. Read more in [Payment Reconciliation](receivables-apply-payments-auto-reconcile-bank-accounts.md).|
|Match Tolerance Value|Specifies if the automatic payment application function will apply the Amount Incl. Tolerance Matched rule by Percentage or Amount. Read more in [Payment Reconciliation](receivables-apply-payments-auto-reconcile-bank-accounts.md).|
|**Hidden Fields**||
|Search Name|Specifies an alternate name that you can use to search for the record in question when you cannot remember the value in the Name field.|
|Min. Balance|Specifies a minimum balance for the bank account. This field is for information purposes only.|
|Positive Pay Export Code|Specifies a code for the data exchange definition that manages the export of positive-pay files. Read more in [ Export Positive Pay Files](finance-how-positive-pay.md).|
|**Communication FastTab**||
|Address|The address of the bank branch.|
|Address 2|An additional address field for the bank branch.|
|Post Code|The post code of the bank branch.|
|City|The city of the bank branch.|
|Country/Region Code|The Country/Region Code of the bank branch.|
|Phone No.|The Phone No. of the bank branch.|
|Mobile Phone No.|The Mobile Phone No. of the bank branch.|
|Contact|The main contact in the bank branch. Additional contacts can be created in the Contacts module.|
|Fax No.|The Fax No. of the bank branch.|
|Email|The Email of the bank branch.|
|Home Page|The Home Page of the bank branch.|
|**Posting FastTab**||
|Currency Code|Specifies the relevant currency code for the bank account. Applying a currency code to a bank account will limit all transactions to only use the applied currency code. Leaving the currency code blank will allow transactions in all currencies, however, the amount will be converted to the local currency (LCY) using the applied currency rate. Checks issued from this account will also follow the same rules.|
|Last Check No.|The number of the latest check issued from this account.|
|Transit No.|Specifies a bank identification number of your own choice.|
|Last Statement No.|The number of the latest bank reconciliation posted to this account. Read more in [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md).|
|Last Payment Statement No.|The number of the latest payment reconciliation posted to this account. Read more in [Payment Reconciliation](receivables-apply-payments-auto-reconcile-bank-accounts.md).|
|Last Bank Statement|The ending-balance of the last bank statement. Read more in [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md).|
|Bank Acc. Posting Group|Specifies a code for the bank account posting group for the bank account. The Bank Acc. Posting Group connects the bank account to the G/L Account in the balance sheet.|
|**Transfer**||
|Transit No.|Specifies a bank identification number of your own choice.|
|SWIFT Code|Specifies the international bank identifier code (SWIFT) of the bank where you have the account. The SWIFT Code is very often considered a sensitive field. Read more about [Monitoring Sensitive Fields](across-log-changes#monitoring-sensitive-fields).|
|IBAN|Specifies the bank account's international bank account number. The IBAN Code is very often considered a sensitive field. Read more about [Monitoring Sensitive Fields](across-log-changes#monitoring-sensitive-fields).|
|Bank Statement Import Format|Specifies the format of the bank statement file that can be imported into this bank account. The format is being used in both the payment reconciliation journals and the bank account reconciliations.|
|Payment Export Format|Specifies the format of the bank file that will be exported when you choose the Export Payments to File button in the Payment Journal window.|

> [!NOTE]
> To fill in the **Balance** field with an opening balance, you must post a bank account ledger entry with the amount in question. You can do this by performing a bank account reconciliation. For more information, see [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md). Alternatively, you can implement the opening balance as a part of general data creation in new companies by using the **Migrate Business Data** assisted setup guide. For more information, see [Getting Ready for Doing Business](ui-get-ready-business.md) or for creating opening balances in [!INCLUDE[prod_short](includes/prod_short.md)] see [How to Create Journal Opening Balances](admin-how-to-create-journal-opening-balances.md).

## To set up your bank account for import or export of bank files
Fields on the **Transfer** FastTab on the **Bank Account Card** page are related to import and export of bank feeds and files. For more information, see [Using the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md) and [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. Open the card for a bank account that you will export or import bank files for.
3. On the **Transfer** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
>   Different file export services and their formats require different setup values on the **Bank Account Card** page. You will be informed about wrong or missing setup values as you try to export the file. So read the short descriptions of the fields carefully or refer to the related procedure topics. For example, exporting a payment file for North American electronic funds transfer (EFT) requires that both the **Last Remittance Advice No.** field and the **Transit No.** field are filled in. For more information, see [Export Payments to a Bank File](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).

## To set up vendor bank accounts for export of bank files

Fields on the **Transfer** FastTab on the **Vendor Bank Account Card** page are related to export of bank feeds and files. For more information, see [Using the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md) and [Export Payments to a Bank File](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the card for a vendor whose bank account you will export payment bank files to.
3. Choose the **Bank Accounts** action.
4. From the **Vendor Bank Accounts List**, choose the relevant bank account, or add a new bank account.  
5. On the **Vendor Bank Account Card** page, on the **Transfer** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## See Also

[Setting Up Banking](bank-setup-banking.md)  
[Setting Up Posting Groups](finance-posting-groups.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]