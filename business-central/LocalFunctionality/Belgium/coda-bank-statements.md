---
title: Belgian CODA Bank Statements [BE]
description: The Coded Statement of Account is a national banking standard, designed by the Belgian Banker's Association to automatically process electronic bank statements.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 2000040, 2000041, 2000042, 2000043, 2000045
ms.date: 02/08/2022
ms.author: bholtorf

---
# Belgian CODA Bank Statements in the Belgian Version

The Coded Statement of Account (CODA) is a national banking standard, designed by the Belgian Banker's Association, which allows you to automatically process electronic bank statements.  

Each type of transaction in a CODA statement is assigned a unique code. [!INCLUDE[prod_short](../../includes/prod_short.md)] uses this code to interpret transactions and apply them to the corresponding ledger entries.  

## Applying Statement Lines

When you have imported a CODA statement, you can apply the statement lines to existing ledger entries, based on the information in the **Transaction Coding** table.  

If the transaction coding of the statement line is not found, [!INCLUDE[prod_short](../../includes/prod_short.md)] will stop processing and continue with the next statement line. If you select the **Default Posting** field, the statement line will be used as a default posting.  

If the transaction coding of the statement line is found, the statement lines will be matched to the following account types and corresponding account numbers:  

- General ledger - If the account type is a general ledger account, the statement line is posted on the corresponding general ledger account.  

- Customer or vendor - If the account type is customer or vendor, a matching customer or vendor ledger entry is found based on the following criteria:  

  - If a ledger entry is found using the standard format, the ledger entry will be matched to the statement line, and the application status will be set to **Applied**. If the ledger entry does not use the standard format, the bank account number of the customer or vendor is used to find the customer or vendor.  

  - If no ledger entry with a matching remaining amount is found, the customer or vendor account is used, and the application status will be set to **Partly Applied**.  

  - If the bank account number is used to find the customer or vendor, a matching ledger entry is found based on the amount of the statement line. If the amount is found, the statement line is matched to the corresponding ledger entry, and the application status will be set to **Applied**.  

  - If the bank account number cannot be used to find the customer or vendor, [!INCLUDE[prod_short](../../includes/prod_short.md)] will either stop processing the current line or use the line as a default posting, before continuing with the next statement line.  

You can run the process as many times as you like. Only statement lines with a blank application status will be applied.  

When you have applied all statement lines to a general ledger account or to a matching customer ledger entry or vendor ledger entry, you are ready to post the CODA statement lines. For more information, see [Automatically Transfer and Post CODA Statements](how-to-manually-transfer-and-post-coda-statements.md).  

## Extending the CODA integration

The current support for CODA bank statements can be used in [!INCLUDE [prod_short](../../includes/prod_short.md)] online and on-premises. However, partners cannot extend the capabilities in an app for [!INCLUDE [prod_short](../../includes/prod_short.md)] online. The code is not deprecated but can only be extended or customized for on-premises deployments.  

## See Also

[Belgian Electronic Banking](belgian-electronic-banking.md)   
[Set Up Bank Accounts for CODA](how-to-set-up-bank-accounts-for-coda.md)   
[Set Up IBLC-BLWI Transaction Codes](how-to-set-up-iblc-blwi-transaction-codes.md)   
[Import CODA Statements](how-to-import-coda-statements.md)   
[Apply CODA Statements](how-to-apply-coda-statements.md)   
[Create Financial Journals](how-to-create-financial-journals.md)   
[Automatically Transfer and Post CODA Statements](how-to-automatically-transfer-and-post-coda-statements.md)   
[Manually Transfer and Post CODA Statements](how-to-manually-transfer-and-post-coda-statements.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]