---
    title: Telebanking
    description: Based on both sales and purchase transactions, telebanking enables you to generate your payments and collections and interchange them with your bank electronically.
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
# Telebanking
Based on both sales and purchase transactions, telebanking enables you to generate your payments and collections and interchange them with your bank electronically. This includes the export of payment and collection data that need to be forwarded to the bank as well as the import of bank statements sent to you by the bank.  

## Transactions  
In general, all financial interactions with vendors and customers are done through either purchase or sales invoices and credit memos. As soon as these transactions have been registered and posted, payments or collections can be carried out by your company.  

## Proposals  
Based on vendor and customer ledger entries, telebanking enables you to generate payment and collection proposals. This can be done for any bank that has been set up for your company. Both domestic and foreign payments and collections are possible.  

You can set up [!INCLUDE[d365fin](../../includes/d365fin_md.md)] to combine payments to or collections from the same bank account automatically.  

When a proposal has been agreed upon, it should be processed into a payment history.  

> [!NOTE]  
>  In general, for any open vendor and customer ledger entries, a proposal can be generated if it meets a number of criteria. For more information, see [Create Proposals](how-to-create-proposals.md).  

## Payment Histories  
A payment history is nothing more than a proposal except for the fact that data on a payment history cannot be modified. The payment or collection data is ready to be exported and forwarded to the bank.  

 For more information, see [Create and Export Payment History](how-to-create-and-export-payment-history.md).  

## Bank Statements  
 For all your financial interactions through your bank, the bank can send you electronic bank statements. These statements can be imported into the Bank/Giro Journals. If you want, you can have [!INCLUDE[d365fin](../../includes/d365fin_md.md)] automatically reconcile these statements during this import process and determine whether a statement can be applied to open ledger entries for the relevant vendor/customer.  

 For more information, see [Import and Reconcile Bank Statements](how-to-import-and-reconcile-bank-statements.md).  

## Exchange Protocols  
 For both exporting and importing, a number of protocols have been defined. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] supports the following protocols:  

- BTL91 (export). This cross-border protocol is no longer accepted in the Netherlands as of May 1st 2019. This protocol is replaced by the Generic Payment File protocol.
- BBV (export)  
- PAYMUL (export)  
- Generic Payment File (export). Can be used for cross-border Non-EUR transfers.
- Rabobank mut.asc (import)  
- Rabobank vvmut.asc (import)  
- Rabobank ASCII (import)  
- SEPA CAMT  

## See Also  
 [Invoice Sales](../../sales-how-invoice-sales.md)   
 [Record Purchases](../../purchasing-how-record-purchases.md)   
 [Create Proposals](how-to-create-proposals.md)   
 [Create and Export Payment History](how-to-create-and-export-payment-history.md)
