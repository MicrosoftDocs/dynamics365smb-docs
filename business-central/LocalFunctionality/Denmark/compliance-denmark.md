---
title: Compliance with the bookkeeping act in Denmark
description: Learn how Business Central complies with the bookkeeping act in Denmark.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: bookkeeping, law, compliance, e-vat, e-document, nemhandel, denmark, dk
ms.search.form: 
ms.date: 03/03/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Compliance with the bookkeeping act in Denmark

[!INCLUDE[prod_short](../../includes/prod_short.md)] (cloud) is registered as a digital bookkeeping system in Denmark.  

> [!IMPORTANT]
> Dynamics 365 Business Central is registered as a digital bookkeeping system only as a standard solution without customizations (as-is). If the system is customized, it is on partner or customer to prove that this system is still a standard solution, as Microsoft can't provide opinion if customizations break parts of a digital bookkeeping system DBA certified.  

Registration certificate is based on cf. §4 subsection 1 of the executive order no. 98 of January 26, 2023, regarding the notification and registration of digital standard bookkeeping systems according to which the digital standard bookkeeping system [!INCLUDE[prod_short](../../includes/prod_short.md)], has been registered by the Danish Business Authority on December 21, 2023, with the **registration number fob467715**.  

> [!NOTE]
> The following document doesn't provide official documentation in the process of certification with DBA. This is just an explanation that Dynamics 365 Business central complies all requirements and eventually instruction for partners or customers if they want to certify their solution outside of Microsoft.  

## How does [!INCLUDE[prod_short](../../includes/prod_short.md)] ensure compliance?

To achieve this registration certificate, [!INCLUDE[prod_short](../../includes/prod_short.md)] had to comply with different requirements by Danish Business Authorities based on the Executive order no. 97.  

## Main requirements - § 15, no. 1

Support a continuous registration of the company's transactions with the indication of appendices for each registration and safe storage of registrations and appendices for five years.  

### Annex 1, 1, a – e  

**Requirement**: The standard digital bookkeeping system must contain fields for the company to provide information on the following matters when recording each individual transaction:  

* Transaction date (for example, payment date, purchase date, etc.)  
* Amount
* Receipt number  
* Transaction text  
* Exchange rate on the day of the transaction or other conversion factor if registration is made in a currency other than DKK.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

All transactions entered within [!INCLUDE[prod_short](../../includes/prod_short.md)] contain a transaction date, amount, receipt number/document number, and transaction text/description. All entries in general ledger transactions are stored exclusively in DKK. If the original document has currency other than DKK, this information exists in subledger connected with general ledger entry. All this information can be found on the **G/L Register** page. The **G/L Register** page provides details about each transaction, including the register number, the creation date and time, the user ID of who created the transaction, and its source code.  

### Annex 1, 2, a – e

**Requirement**: The digital standard bookkeeping system must ensure:  

* That the system assigns a registration date for each recorded transaction.  
* That the system assigns a consecutive transaction number or ID for each recorded transaction.
* That the system assigns initials or similar to the person who has recorded a transaction.
* That the system saves changes to the recording, for example, in that incorrect entries must be corrected with new entries.
* That recorded transactions can't be changed, backdated or deleted.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

An audit trail record is created for every transaction (**G/L Register**) upon posting that registers the **Created Date** and even **Creation Time** together with **User ID** as a person who recorded a transaction. For each audit trail record - register, you can also view the No. column, which specifies the system-created number of the general ledger register.  

**G/L Register** and **General Ledger Entries** and all subledgers have unique system-based entry numbers, which allows each number sequence to be defined as consecutive.  

After a transaction is posted, the transaction can't be edited or deleted after posting. Corrections to the transaction must be made through a reversing entry and then a new entry to register the changes. Correction can be done manually or using **Reverse** action from the **G/L Register** for reversing completely transaction. But in any case, reversing transaction is created as a new transaction without changing original values. Learn more in the [Understand the general ledger and Chart of Accounts](../../finance-general-ledger.md) article, which provides information on the chart of accounts.

### Annex 1, 3, a – b

**Requirement**: The digital standard bookkeeping system must support the storage of receipts covered by § 3 which document the company's recorded purchase and sale transactions:  

* Receipts relating to purchase transactions can be stored digitally in the system.
* Receipts relating to sales transactions are either automatically generated in the system and stored digitally or can be stored digitally in the system, for example, as an image or a scanned file.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports the storage of files as attachments to purchase and sales invoices and any other record of a table that is accessible by users of [!INCLUDE[prod_short](../../includes/prod_short.md)] via user interface. However, to support mandatory attachments for purchase and sales transactions, [!INCLUDE[prod_short](../../includes/prod_short.md)] has a more default set up for digital vouchers, where it requires mandatory attachment for sales and purchase transactions and doesn't allow posting these documents without having attachments. For more automation, sales transactions automatically create sales documents and attach them to this transaction without user interaction. But the user can add more documents if they want. Learn more in the [Set up digital vouchers in Denmark](how-to-digital-vouchers-dk.md) article, which provides information on mandatory digital vouchers.

### Annex 1, 4 and 1, 4, a-d

**Requirement**: The digital standard bookkeeping system must support the storage of the company´s recorded transactions and receipts covered by § 3 for 5 years from the end of the financial year the material concerns. The digital standard bookkeeping system must support:

* That recorded transactions are preserved so that they can't be changed, backdated or deleted by the company.
* That all recorded transactions are stored in a structured and machine-readable format for five years from the end of the financial year the recorded transaction relates to, regardless of any termination of customer relations with the company or the company's bankruptcy or forced dissolution.
* That all receipts covered by section 3 are kept for five years from the end of the financial year that the receipt concerns, regardless of any termination of customer relations with the company or the company's bankruptcy or forced dissolution.

That encrypted bookkeeping data can be decrypted into a structured and machine-readable format and that encrypted receipts covered by section 3 can be decrypted into a readable format.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports the storage of the company’s recorded transactions and digital vouchers. Transactional records once created can't be deleted or modified via the user interface of [!INCLUDE[prod_short](../../includes/prod_short.md)], and the **Company** also can't be deleted from the moment when the company is proclaimed as the production company and registered with Nemhandel. [!INCLUDE[prod_short](../../includes/prod_short.md)] also prevents backdating of the recorded transaction, meaning that posted transaction date can't be edited and changed. Standard functionality of [!INCLUDE[prod_short](../../includes/prod_short.md)] allows users to post transactions dated in the past period (date, week, month ago), but in this situation there's information about **Created Date** and **Created Time** of a record.  

[!INCLUDE[prod_short](../../includes/prod_short.md)] also supports the storage of files as attachments (receipts or digital vouchers) to purchase and sales invoices and any other record of a table that is accessible by users of [!INCLUDE[prod_short](../../includes/prod_short.md)] via user interface. All attached documents are stored in the database, so database backup keeps attachments as well. These kinds of attachments ([mandatory digital vouchers](how-to-digital-vouchers-dk.md)) can't be deleted once when the document is posted, and general ledger entries are created.  

During the time of usage of the system, authorities can get access to all transactions and digital vouchers directly through the user interface from users as the database is always active and available. Even if the user doesn’t want to provide access to the transactional records, or in the event of termination of customer relations with Microsoft, or the company's bankruptcy or forced dissolution, Microsoft can still provide transactional and digital voucher details.

All this transactional data and the original documents existing in the accounting system are used as a source of daily data export in the account-protected Azure storage environment where they can't be changed, backdated, or deleted by the company, as this process is on the platform level without any user access. Storage account credentials are kept in Azure Key Vault and the data in the storage is protected against potential tampering. Learn more in [Keep transactional data for five years in Denmark](how-to-keep-data-5years.md).

## Main requirements - § 15, no. 2

Meet recognized standards for IT security, including for user and access management, and ensure automatic backup of records and appendixes.  

### § 8, par. 4, no. 1 - 7

**Requirements**: Network security, Access management, Supplier management, Backup, Logging, Preparedness and re-establishment, and Data protection.  

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

Microsoft provided the following documents: _**Certificate of Registration for Information Security Management System - ISO/IEC 27001:2022**_ and _**Microsoft Products and Services Data Protection Addendum**_. These documents confirm that the system has a high IT-security level and that security level is based upon a risk assessment.

## Main requirements - § 15, no. 3  

Support the automatization of administrative processes, including the automatic sending and receiving of e-invoices and the possibility of entering in accordance with a public standard chart of accounts in registered accounting systems.

### Annex 2, 1, a – e and 2, 2, a – f

**Requirement**: The digital standard bookkeeping system supports the automatic sending and receiving of e-invoices via Nemhandel in OIOUBL format in the following way:

* The customer can send electronic invoices in OIOUBL format.
* The customer can receive electronic invoices in OIOUBL format.
* The customer can send electronic credit notes in OIOUBL format.
* The customer can receive electronic credit notes in OIOUBL format.
* The customer can send an application response upon receipt of an electronic invoice.

The digital standard bookkeeping system supports the automatic sending and receiving of e-invoices in Peppol BIS format in the following way:

* The customer can send electronic invoices in Peppol BIS format.
* The customer can receive electronic invoices in Peppol BIS format.
* The customer can send electronic credit notes in Peppol BIS format.
* The customer can receive electronic credit notes in Peppol BIS format.
* The customer can send a message level response upon receipt of an electronic invoice.
* The customer can send an invoice response upon receipt of an electronic invoice.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

[Electronic invoicing functionality](../../finance-edocuments-overview.md) in [!INCLUDE[prod_short](../../includes/prod_short.md)] provides the possibility to generate electronic analogs of business documents (customer invoices or customer credit memo) in required formats (OUOUBL and Peppol BIS) and perform post-processing of generated electronic documents, for example, send it to various destinations, as well as, to import vendor electronic documents (vendor invoices or vendor credit memo) into the system from various external sources. As users need to send electronic documents directly, they can do it via Access Point service provider(s) where [!INCLUDE[prod_short](../../includes/prod_short.md)] is acting as transportation layer for sending created PEPPOL and OIOUBL standard compliant XML e-invoices as well as receiving, parsing, and importing XML received in before-mentioned formats as required by the law. In this scenario [!INCLUDE[prod_short](../../includes/prod_short.md)] e-documents exchange functionality works by the 4-corner model.  

Messaging is based on combination of synchrony and asynchrony API communication with an Access Point Service Provider. All types of information regarding ability to process incoming invoices, and business users’ notifications of approval or rejections of documents, are working based on predefined proper message processing. Learn more in [Set up electronic invoicing with NemHandel](how-to-edocuments-nemhadel.md).  

### Annex 2, 3, a  

**Requirement**: The digital standard bookkeeping system supports the possibility of reconciling the company's bookkeeping with the company's bank account by importing a CSV file with bank entries into the bookkeeping system.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

[!INCLUDE[prod_short](../../includes/prod_short.md)] provides a comprehensive solution that meets the requirement of the digital standard bookkeeping system supporting the possibility of reconciling the company’s bookkeeping with the company’s bank account. It supports advanced bank reconciliation, allowing you to import electronic bank statements in various formats, including CSV, and automatically reconcile them with bank transactions in the system. Learn more in [Payments and Reconciliations (DK) Extension](../../ui-extensions-payments-reconciliation-formats-dk.md) and [FIK Details in the Payment Reconciliation Journal](fik-details-in-the-payment-reconciliation-journal.md) in Denmark.

### Annex 2, 3, 2. a– b  

**Requirement**: The bookkeeping system supports, in addition to previous requirement, the possibility of reconciling the company's bookkeeping with the company's bank account by:

* The bookkeeping system ensures that the bank account is represented in the chart of accounts and that it can be reconciled with the loaded bank entries.
* A clear difference is being shown in the bookkeeping system if items entered from the bank aren't reconciled.  

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

Users use bank accounts in [!INCLUDE[prod_short](../../includes/prod_short.md)] to keep track of their banking transactions. Accounts can be denominated in the local currency (DKK) or in the foreign currency. Each bank account is linked to an account in the chart of accounts through the assigned bank account posting group. Using a bank account in a payment transaction automatically creates an entry in both the bank account and the connected general ledger (G/L) account.  

Bank reconciliation is how users make sure that the bank account in [!INCLUDE[prod_short](../../includes/prod_short.md)] matches the external account at the bank. Bank account reconciliation compares and matches entries in the bank accounts users set up in [!INCLUDE[prod_short](../../includes/prod_short.md)] with bank transactions at their bank. Reconciliation can then post the balances to their bank accounts in [!INCLUDE[prod_short](../../includes/prod_short.md)] to make them available to finance managers. Bank reconciliation is also a practical way to discover and resolve missing payments and bookkeeping errors.

If users find a mistake in a posted bank reconciliation, they can use the **Undo** action on the **Bank Account Statement List** page to correct it. When they undo a posted bank reconciliation, the entries are moved to the **Bank Reconciliation** page and marked as **Open**, meaning they aren't reconciled. They can then correct the bank reconciliation and post it again.

A clear difference is being shown in the bookkeeping system if items entered from the bank aren't reconciled.

Find out more about how reconciliation works in [!INCLUDE[prod_short](../../includes/prod_short.md)]:

* [Reconcile Payments Using Automatic Application](../../receivables-how-reconcile-payments-auto-application.md)   
* [Reconcile Payments that Can't be Applied Automatically](../../receivables-how-reconcile-payments-cannot-apply-auto.md)  
* [Reconcile Customer Payments from a List of Unpaid Sales Documents](../../receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md)

### Annex 2, 4, a – c  

**Requirement**: The digital standard bookkeeping system supports the possibility of using a public standard chart of accounts:

* The company uses the public standard chart of accounts directly in the bookkeeping system.
* Mapping the bookkeeping system's standard chart of accounts to the public standard chart of accounts.
* The bookkeeping system provides a tool that enables the customer to map their own chart of accounts to the common public standard chart of accounts in a simple way.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

In [!INCLUDE[prod_short](../../includes/prod_short.md)], one company can use only one **Chart of Accounts** for posting into **General Ledger Entries**. Users can set up **Chart of Accounts** to be the same as Danish public standard chart of accounts manually or during the initialization of the SAF-T app.  

But if users already created a main chart of accounts different from the public standard chart of accounts, or they want to use one different from other reasons, they can always have mapped chart of accounts with the public standard chart of accounts. Danish [public standard chart of accounts is initialized by default in the system in the **Standard Accounts** page](how-to-set-up-standard-coa.md).

### Annex 2, 4, 2. a

**Requirement**: The bookkeeping system provides a tool that enables the customer to map to standard VAT codes in a simple way.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

[!INCLUDE[prod_short](../../includes/prod_short.md)] provides user interface to map VAT codes used in tax transactions to public standard VAT codes (public standard VAT chart of accounts) in a simple way for reporting of Standard Audit File for Tax (SAF-T). To use this feature, on the **VAT Posting Setup SAF-T** page, associate a VAT posting group setup with **Sales VAT Reporting Code** and **Purchase VAT Reporting Code**.  

### Annex 2, 5, a – c  

**Requirement**: The digital standard bookkeeping system supports correct bookkeeping through the bookkeeping guide or accounting guide:

* A bookkeeping wizard/assistant having been incorporated into the bookkeeping system to help the company record.  
* The bookkeeping system contains accounting instructions and/or linking/referring to accounting instructions/guides from third parties.
* The bookkeeping system having to support the function that users can enter an accounting guide for the individual account.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

[!INCLUDE[prod_short](../../includes/prod_short.md)] has published the bookkeeping guide on its official Learning website with an outline of bookkeeping processes, including the rules, procedures, and other guidelines in [!INCLUDE[prod_short](../../includes/prod_short.md)]: [Accounting and Bookkeeping](../../learn-accounting-bookkeeping-guide.md).  

But more important is that [!INCLUDE[prod_short](../../includes/prod_short.md)] has a context-based assistant incorporated into the product. This assistant contains links to information that's related to the current page and instructions for working with the relevant process.  

A key element in educating users about [!INCLUDE[prod_short](../../includes/prod_short.md)] pages and concepts is the tour. A tour is a sequence of teaching tips. Teaching tips can be defined at the page level, the page teaching tip, and be followed by teaching tips at the control level, the control teaching tips.

It's also possible to connect the system with the community support and instructions using the link to the **Community** in the **Help** pane. It's also possible to add more content through users’ or partner’s content, but this extending requires another configuration.

### Annex 2, 6, a – c  

**Requirement**: The digital standard bookkeeping system supports the sharing of the company's bookkeeping data by:

* The bookkeeping system is making it possible to generate a standard file, as defined by the authorities.
* The bookkeeping system exports a standard file, as defined by the authorities, to another provider of bookkeeping systems.  
* The bookkeeping system can load the information included in a standard file defined by the authorities so that it's available to the customer.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports generation of Standard Audit File for Tax (SAF-T) in XML format introduced by the Danish Bookkeeping Act in July 2022 according to schema defined by “_Danish SAF-T Financial data, version 1.0_”, published by Erhvervsstyrelsen, 11/2022. [!INCLUDE[prod_short](../../includes/prod_short.md)] also can load existing SAF-T files got from external systems and keep in inside the database as a file. Learn more in [Export the SAF-T audit file format in Denmark](how-to-use-saft-audit-files-export.md).

### Annex 2, 7, a

**Requirement**: The bookkeeping system creating a CSV file with the companies' bookkeeping data to Regnskab Basis.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports generation of CSV file with the company’s bookkeeping data according to "Vejledning til upload af regnskabsfil i Regnskab Basis". Learn more in [Export accounting data to Regnskab Basis in Denmark](how-to-use-regnskabbasis-export.md)  

### Annex 2, 7, b  

**Requirement**: The bookkeeping system can support the reporting of VAT via the Danish Tax Agency's VAT API.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports reporting of VAT return via the Danish Tax Agency's VAT API and update statuses given by authorities, but also enables downloading response messages. Reade more how to [Submit VAT returns electronically](how-to-evat-statement-dk.md).  

### Annex 2, 8 – 9

**Requirement**: Message about registration in Nemhandelsregistrere and Registration functionality to Nemhandelsregistrere:  

* The digital standard bookkeeping system must issue a message to the system's existing customers after the system is registered with the Danish Business Authority and when new customers are registered in the system, alerting them to the possibility to be registered in the NemHandelsregisteret.
* When setting up the system or by direct message to the system's existing customers, the digital standard bookkeeping system must be able to display information about and registration functionality for the NemHandelsregisteret. Customers must be able to indicate that they wish to be registered in NemHandelsregisteret and consent to this and thus be registered therein. The approved bookkeeping system must then handle the registration of the system's customers in NemHandelsregisteret based on the standard functions and requirements in NemHandel in force at any time.

**How does [!INCLUDE[prod_short](../../includes/prod_short.md)] comply?**

If the company isn't registered with the NemHandelsregisteret, notification about that appears at the top of screen, together with instructions on how to register. If the company is registered, [!INCLUDE[prod_short](../../includes/prod_short.md)] checks if the CVR number in the Company Information page exists as registered in NemHandelsregisteret, and if it exists, the message doesn't appear, and this company is marked as ‘registered in NemHandelsregisteret’.

To start registration, the user needs to select on the Register in NemHandelsregisteret link. After the user finishes the registration with the NemHandelsregisteret, the notification disappears. Learn more in [Notification and registration for the NemHandelsregisteret in Denmark](how-to-nemhandel-register.md).

## Related information

- [Denmark Local Functionality](denmark-local-functionality.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

## [!INCLUDE[prod_short](../../includes/free_trial_md.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
