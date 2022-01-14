---
title: Set Up Bank Accounts (contains video)
description: Learn how bank accounts are used in Business Central, and how you can reconcile amounts with your bank.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Yodlee, feed, stream
ms.search.form: 370, 371, 372, 373, 375, 423, 424, 425, 426, 1240, 1280
ms.date: 06/22/2021
ms.author: edupont

---
# Set Up Bank Accounts

You use bank accounts in [!INCLUDE[prod_short](includes/prod_short.md)] to keep track of your banking transactions. Accounts can be denominated in your local currency or in a foreign currency. After you have set up bank accounts, you can also use the check printing option. The bank accounts includes extra functionality for [payment reconciliation](receivables-apply-payments-auto-reconcile-bank-accounts.md), [bank reconciliation](bank-how-reconcile-bank-accounts-separately.md), and the import and export of bank files. The bank accounts can also be included in transactions in the general journals. Each bank account is linked to an account in the chart of accounts through the assigned bank account posting group. Using a bank account in a payment transaction will automatically create an entry in both the bank account and the connected G/L account.  

Bank accounts work differently depending on whether a currency code is specified:

- Currency code is blank

  All transactions in the bank account will be in the local currency (LCY) for the current company. If a transaction is made to the account in another currency, the amounts are posted to the account in LCY based on the relevant currency exchange rate. Any checks that are issued from this account must be issued in LCY. If the bank account is used in a journal, the journal line will automatically inherit the blank currency code.  
- Currency code is specified

  All transactions that are made to this account must be in the same currency as is specified on the account. All checks that are issued from this account must also have this currency.  

A bank account is an integrated part of [!INCLUDE[prod_short](includes/prod_short.md)] and plays a role in many other capabilities. The following illustration shows the most important relations:

![Illustration of bank account relations.](media/Set-Up-Bank-Accounts/Bank_Account_Relations.png)

This means that creating a bank account, makes it available in all the places shown above as well as being mirrored in for the relevant G/L account and in the **Company Information** page.

A bank account is usually monitored daily to make sure that any new payments from customers are registered as quickly as possible. This helps make sure that the actual status of the customers is reflected in [!INCLUDE[prod_short](includes/prod_short.md)] so that sales people, accountants, and other employees have access to relevant and up-to-date information. This way, they avoid unnecessary calls to the customer regarding overdue invoices or delay in shipments.  

![Illustration of bank payment.](media/Set-Up-Bank-Accounts/Bank-payment-flow.png)

Another task is to import the vendor currency payments with the realized currency rates to make sure that the actual status of the vendors is up-to-date. The easiest way to make sure that the bank account is updated is using the [payment reconciliation](receivables-apply-payments-auto-reconcile-bank-accounts.md) capability. In the **Payment Reconciliation Journal**, you can import bank transactions directly from an online bank application and have them posted more or less automatically. The journal automatically identifies and posts the following:  

- Direct debit payments from customers  
- Customer payments of single invoices  
- Lump-sum payments from customers  
- Customer payments in foreign currencies  
- Vendor payments  
- Vendor payments in foreign currency  
- Recurring vendor payments and subscriptions  
- Bank charges and interests  

Payment reconciliation provides massive time savings in posting incoming and outgoing payments. However, the transactions on the bank account in [!INCLUDE[prod_short](includes/prod_short.md)] is not considered 100% correct until you run a bank reconciliation.  

Bank reconciliation is how you make sure that the bank account in [!INCLUDE[prod_short](includes/prod_short.md)] matches the external account at the bank.  

 ![Illustration of bank account reconciliation.](media/Set-Up-Bank-Accounts/BankReconciliation.png)

In the illustration above, the left side represents the bank account in [!INCLUDE[prod_short](includes/prod_short.md)], and the right side represents the transactions imported from the bank through the online bank application. The diagram in the middle shows the transactions from both sides, which is the bank reconciliation.

From the bank account in [!INCLUDE[prod_short](includes/prod_short.md)], most transactions should be known to the physical bank. The only exceptions include the following cases:  

- Corrections posted in [!INCLUDE[prod_short](includes/prod_short.md)]  
- Checks issued that has not been cashed yet  
- Vendor payments that have not been approved by the bank  

From the physical account in the bank, unknown transactions that were not identified in the payment reconciliation journal arrive all the time, such as the following:  

- New vendor subscriptions  
- Customer payments without description
- Bank interests
- Bank Charges
- Credit card charges that haven't been reported yet

The better mapping information that you do in the payment reconciliation journal, the more transactions are posted automatically and the easier the periodic bank reconciliation becomes.

<br><br>

> [!Video https://www.microsoft.com/videoplayer/embed/RE3Vhpl?rel=0]

<br><br>

> [!WARNING]
> Some fields may contain sensitive data, such as the **Bank Branch No.**, **Bank Account No.**, **SWIFT Code**, and **IBAN Code** fields. For more information, see [Monitoring Sensitive Fields](across-log-changes.md#monitoring-sensitive-fields).

## To set up bank accounts

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. On the **Bank Accounts** page, choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> Some fields are hidden until you choose the **Show more** action, typically because they are used rarely. Others must be added through personalization. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

You can create as many bank accounts as you need for your business. For each bank account, you must specify information that makes the bank account uniquely identifiable. This information includes the bank's geographical address, number series for different types of transactions, such as direct debit and credit transfers, the currency that amounts are specified in, and information that is used for importing bank statements. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
<!--
The following table explains key fields.

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**General FastTab**||
|No.|Specifies the number of the bank account, according to the specified number series. If the number series allow manual numbering, any alphanumeric code up to 20 characters can be used.|
|Name|The Name of the bank holding the bank account.|
|Bank Branch No.|The Bank Branch No. is usually used to identify the bank branch in domestic payments. The Bank Branch No. is very often considered a sensitive field. Read more about [Monitoring Sensitive Fields](across-log-changes.md#monitoring-sensitive-fields).|
|Bank Account No.|Bank Account No. is usually used to identify the bank account no. in domestic payments. The Bank Account No. is very often considered a sensitive field. Read more about [Monitoring Sensitive Fields](across-log-changes.md#monitoring-sensitive-fields).|
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
|Positive Pay Export Code|Specifies a code for the data exchange definition that manages the export of positive-pay files. Read more in [Export Positive Pay Files](finance-how-positive-pay.md).|
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
|SWIFT Code|Specifies the international bank identifier code (SWIFT) of the bank where you have the account. The SWIFT Code is very often considered a sensitive field. Read more about [Monitoring Sensitive Fields](across-log-changes.md#monitoring-sensitive-fields).|
|IBAN|Specifies the bank account's international bank account number. The IBAN Code is very often considered a sensitive field. Read more about [Monitoring Sensitive Fields](across-log-changes.md#monitoring-sensitive-fields).|
|Bank Statement Import Format|Specifies the format of the bank statement file that can be imported into this bank account. The format is being used in both the payment reconciliation journals and the bank account reconciliations.|
|Payment Export Format|Specifies the format of the bank file that will be exported when you choose the Export Payments to File button in the Payment Journal window.|
-->
> [!NOTE]
> To fill in the **Balance** field with an opening balance, you must post a bank account ledger entry with the amount in question. You can do this by performing a bank account reconciliation. For more information, see [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md). Alternatively, you can implement the opening balance as a part of general data creation in new companies by using the **Migrate Business Data** assisted setup guide. For more information, see [Getting Ready for Doing Business](ui-get-ready-business.md). To learn about how to create opening balances in [!INCLUDE[prod_short](includes/prod_short.md)], see [How to Create Journal Opening Balances](admin-how-to-create-journal-opening-balances.md).

## To set up your bank account for import or export of bank files

Fields on the **Transfer** FastTab on the **Bank Account Card** page are related to import and export of bank feeds and files. For more information, see [Using the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md) and [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. Open the card for a bank account that you will export or import bank files for.
3. On the **Transfer** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
> Different file export services and their formats require different setup values on the **Bank Account Card** page. You will be informed about wrong or missing setup values as you try to export the file. So read the short descriptions of the fields carefully or refer to the related procedure topics. For example, exporting a payment file for North American electronic funds transfer (EFT) requires that both the **Last Remittance Advice No.** field and the **Transit No.** field are filled in. For more information, see [Export Payments to a Bank File](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).

The fields on the **Transit** FastTab on the bank account serve different purposes, depending on whether the payment is inbound or outbound.

The illustration shows the route of inbound payments:

:::row:::
    :::column:::
        1. The transactions are exported from the bank account in either a human-readable .csv format or the bank's own format.
        <br><br>
2. The *data exchange definition* maps the information in the file to the fields in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Set Up Data Exchange](across-set-up-data-exchange.md)
<br><br>
3. The *data export/import setup* defines the export or import, and it links to the data exchange definition.
<br><br>
4. The *bank statements import format* links the import setup to the bank account.
<br><br>
5. The payments are imported through the **Payment Reconciliation Journal** or the **Bank Account Reconciliation** page.
    :::column-end:::
    :::column:::
        ![Illustration of payments received from the bank into bank accounts.](media/Set-Up-Bank-Accounts/payments-in-and-out-1.png)
    :::column-end:::
:::row-end:::

Incoming payments are always imported through the **Payment Reconciliation Journal** or directly in the **Bank Account Reconciliation** page. In contrast, outgoing payments can originate from any payment journal. The only prerequisite is that the **Allow Payment Export** field in the relevant payment journal batch must be selected.

The illustration shows the route of outbound payments:

:::row:::
    :::column:::
        6. The transactions populated in a payment journal that has been prepared for exporting payments to file.
        <br><br>
        7. The *bank statements import format* links the import setup to the bank account
        <br><br>
        8. The *data export/import setup* defines the export or import and links to the data exchange definition.
        <br><br>
        9. The *data exchange definition* maps the information in the file to the fields in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Set Up Data Exchange](across-set-up-data-exchange.md)
        <br><br>
        10. The payments are exported from the payment journal and imported into the bank account
    :::column-end:::
    :::column:::
        ![Illustration of payments from bank accounts that are sent to the bank.](media/Set-Up-Bank-Accounts/payments-in-and-out-2.png)
    :::column-end:::
:::row-end:::

## To set up vendor bank accounts for export of bank files

Fields on the **Transfer** FastTab on the **Vendor Bank Account Card** page are related to export of bank feeds and files. For more information, see [Using the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md) and [Export Payments to a Bank File](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the card for a vendor whose bank account you will export payment bank files to.
3. Choose the **Bank Accounts** action.
4. From the **Vendor Bank Accounts List**, choose the relevant bank account, or add a new bank account.  
5. On the **Vendor Bank Account Card** page, on the **Transfer** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!WARNING]
> Some fields on the vendor bank account contain sensitive data, such as the **Bank Branch No.**, **Bank Account No.**, **SWIFT Code**, and **IBAN Code** fields. For more information, see [Monitoring Sensitive Fields](across-log-changes.md#monitoring-sensitive-fields).

## Changing your bank account

If you want to use a different bank account for your business, you must create the new bank account in [!INCLUDE[prod_short](includes/prod_short.md)]. We recommend that you do not simply replace the information about the account you are currently using because that can cause incorrect data. For example, your opening balance might be incorrect or your bank feed might stop working correctly. It's important that you keep the current and new accounts separate.

After you create the new bank account, you should also create a new bank posting group and assign it to a new general ledger account. You can reuse an existing bank posting group, and bank transactions will be posted to the same general ledger accounts as the other bank accounts that share the bank posting group. However, we recommend that you create a new bank posting group and general ledger account so that reconciliations are easier to do.

> [!NOTE]
> Remember that the bank account information on open sales invoices still shows the original bank account. Accordingly, payments are likely to still be posted to that account. We recommend that you keep both accounts active for a period of time after the change.

To get a more condensed view of your cash accounts in financial reporting, use the **Begin-Total** and **End-Total** accounts in your chart of accounts, the **Totaling** rows in account schedules, or G/L account categories. For more information, see the [Business Intelligence and Financial Reporting](bi.md) section.

## See Also

[Setting Up Banking](bank-setup-banking.md)  
[Setting Up Posting Groups](finance-posting-groups.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md)  
[SEPA Direct Debit in Business Central](finance-collect-payments-with-sepa-direct-debit.md)  
[To set up your bank account for SEPA direct debit](finance-collect-payments-with-sepa-direct-debit.md#to-set-up-your-bank-account-for-sepa-direct-debit)  
[To set up a bank account for SEPA Credit Transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#to-set-up-a-bank-account-for-sepa-credit-transfer)  
[Make Payments with the AMC Banking 365 Fundamentals extension or SEPA Credit Transfer](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md)  
[Payment Reconciliation](receivables-apply-payments-auto-reconcile-bank-accounts.md)  
[Understanding the General Ledger and the COA](finance-general-ledger.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
