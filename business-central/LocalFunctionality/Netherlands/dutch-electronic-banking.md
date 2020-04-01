---
    title: Dutch Electronic Banking
    description: Electronic banking functionality allows you to create electronic payment files and direct debit files, and to import electronic bank statements from supported bank software.
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
# Dutch Electronic Banking
Electronic banking functionality allows you to create electronic payment files and direct debit files, and to import electronic bank statements from supported bank software.  

## Telebanking  
Using Telebanking, you can export payments, import bank statements, and collect data to forward to the bank. For more information, see [Telebanking](telebanking.md).  

You can create payment proposals and reconcile bank accounts in the cash, bank, and giro journals.  

### Payment Files  
You can make payment proposals for paying open invoices to suppliers. Payment proposals can be edited manually prior to processing to add or remove payment invoices, or to change payment amounts. After processing a proposed payment batch, you can transfer electronic payment files to the bank. If an error occurs in the payment file while importing into the banking software, you can make a copy of the payment file to resubmit to the bank.  

You can make domestic payments and international payments using the designated formats. For more information, see [Telebanking](telebanking.md).  

### Direct Debit Files  
You can create a payment proposal to collect payment from customer bank accounts. You can edit payment proposals manually to add or remove invoices, or to change collection amounts. After processing a proposed payment batch, you can transfer electronic direct debit files to the bank. If an error occurs in the direct debit file while importing into the banking software, you can make a copy of the direct debit file to resubmit to the bank.  

You can only collect payments domestically at this time. For more information, see [Create Proposals](how-to-create-proposals.md).  

### Bank Statement Import  
You can import bank statements from supported bank software, and reconcile them with incoming and outgoing payments. You can also reconcile bank charges and interest earned.  

Electronic bank statement files are supported for the following banks:  

- ABN AMRO Bank \(SWIFT MT940\)  
- ING Bank \(SWIFT MT940, PAYMUL\)  
- Rabobank \(MUT.ASC, VVMUT.ASC, BBV and ASCII\)  
- Postbank \(SWIFT MT940\)  

## See Also  
[Telebanking](telebanking.md)   
[Enter and Post Cash and Bank/Giro Journals](how-to-enter-and-post-cash-and-bank-or-giro-journals.md)     
[Import and Reconcile Bank Statements](how-to-import-and-reconcile-bank-statements.md)
