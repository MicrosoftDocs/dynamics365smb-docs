---
title: 'QR Bill Management | Microsoft Docs'
description: Easily generate, send, and import QR-bills in Microsoft Dynamics 365 Business Central. This article describes how to set up and use these features.
author: sorenfriisalexandersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: qr bill, invoice, incoming documents, payment reference
ms.date: 03/25/2020
ms.author: soalex

---
## QR Bill Management in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]
From July 1st 2020 it is mandatory for companies in Switzerland to be able to receive QR Bills. QR Bills are new payment slips that must follow invoices and is a country wide initiative to streamline payment processes. QR Bills replace all existing payment slips in Switzerland and also replaces existing ESR related functionality. There are many advantages to the new QR Bills. They contain all information needed to make the payment and a QR code on the payment slip makes it easy to import all this information into [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. All relevant information is imported and used for generating the correct payments for the vendor from whom the QR Bill was received, including the payment reference which automatically gets included in Vendor Ledger Entries and exported in payment files to the bank. See more details in the descriptions below.

### Get started with QR Bill Management
QR Bill Management is included in [!INCLUDE[d365fin](../../includes/d365fin_md.md)] as an extension and automatically installed in existing and new customer environments. All you need to do to get started with this functionality is to do the necessary configuration changes in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. 

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Assisted Setup**, and then choose the related link. Alternatively, you can select **Assisted Setup** from the settings icon in the top right corner.
2. Find the group called **Get ready for the first invoice**.
3. Select **Set up QR-Bill**. This will start the assisted setup for QR Bill Management.
4. The first step of the setup is an introduction to the feature. Choose **Next**.
5. You will now see **QR-Bill setup step 1 of 6: Generating and issuing QR-Bills**. This page shows your **Company Information**, on which you need to fill in the new field **QR-IBAN**. When done, choose **Next**.
6. You will now see **QR-Bill setup step 2 of 6: Generating and issuing QR-Bills**. Here you must specify **Address Type** and **German Umlaut Chars Encoding**. Both have to do with how addresses and names are displayed on the QR-Bill. Recommended values are the defaults. When done, choose **Next**.
7. You will now see **QR-Bill setup step 3 of 6: Generating and issuing QR-Bills**. Here you must select the **Default QR-Bill Layout**. This determines several things for the QR-Bill, like **IBAN type** (QR-IBAN or regular IBAN), **Reference type** (Creditor Reference or QR Reference) and whether ot not to include **Billing Information** in SWICO format for passing more information to the receiver, like the invoice number, VAT amount etc. All of this can be changed in the QR-Bill Layout page as well. Recommended value is the default. When done, choose **Next**.
8. You will now see **QR-Bill setup step 4 of 6: Generating and issuing QR-Bills**. In this step you must select which payment methods to enable for QR-Bills. QR-Bills are generated for a sales or service invoice if the invoice type is enabled for QR-Bills (next step) and the invoice is using a **Payment Method** enabled for QR-Bills. When done, choose **Next**.
9. You will now see **QR-Bill setup step 5 of 6: Generating and issuing QR-Bills**. In this step you must select the document types to enable for QR-Bills. You can select to enable Sales Invoices and Service Invoices. When done, choose **Next**.
10. You will now see **QR-Bill setup step 6 of 6: Receiving QR-Bills**. In this step you must select the Journal Template and Journal Batch to use for generating purchase journals from scanned or imported QR-Bills. When done, choose **Next**.
11. This consludes the setup of QR Bill Management for [!INCLUDE[d365fin](../../includes/d365fin_md.md)] and you are redy to use the features.

If you want to change settings after completing the assisted setup, please use the pages:
* **QR-Bill Setup** to change general settings.
* **QR-Bill Layout** to change layout settings.

### Issuing QR Bills
QR-Bills can be enabled for Sales Invoices and Service Invoices. It works by adding an additional entry to **Report Selection - Sales**, which will generate an extra PDF with the QR Bill every time an invoice is generated. 

### Adding billing information to QR Bills
As part of creating the QR Bill it is possible to include **Billing information** in the SWICO format as advocated by SIX, the Swiss payment infrastructre provider. Ideally, ERP and payemnts systems that can either produce or import a QR Bill should be able to process this information, as it can include valuable additional information for the payable invoice, like VAT amount, vendor's invoice number etc. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)] this information is imported if present on the QR Bill. A key piece of information that is used by default is the vendor's invoice number. The other information is also imported but not currently used. It can be used be an customization extension.  

### Understanding the Payment Reference
The single most important thing in a payment process is the ability to pay the correct amount, to the correct party, and allowing this party to reconcile payments easily to close outstanding accounts. In the QR Bill solution this is handled by a Payment Reference that is generated for every QR Bill. The Payment Reference is unique accross all invoices in a single [!INCLUDE[d365fin](../../includes/d365fin_md.md)] instance. This means that you cannot deliberately or by mistake issue the same payment reference twice. If the paying customer is also using [!INCLUDE[d365fin](../../includes/d365fin_md.md)] the payment reference is imported when receiving QR Bills (see **Receiving QR Bills**) and transferred to the Vendor Ledger Entries and used as a reference when creating the Vendor Payments. Just as was the case with the previous ESR Reference. Eventually, payment files (pain.001) will be sent from the customer's ERP system to their bank with the message to transfer amounts to the vendor's account. Ultimately, the bank will produce a customer statement file (camt.054) the vendor can import to reconcile accounts. This file will include the payment reference and get imported through the Data Exchange Framework that is updated by the QR Bill Management extension to handle correct import of the camt.054 file.  
Previously, it was possible to add logical information to the ESR Reference. This is not the case with the payment reference in QR Bills. There will always be a 1:1 relation between an issued QR Bill and a payment, which makes it easy to reconcile and eliminates the need for including logical information. Instead, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] uses a unique counter for the payment reference, making sure it is unique. Additionally, logic is in place to block import or scan of the same payment reference twice, rendering it impossible to use it twice by mistake.  

### Receiving QR Bills
QR Bills can be received in several places in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]:
* Incoming Documents, when you want a QR Bill to initiate the creation of a new purchase document or purchase journal.
* Purchase Orders & Purchase Invoices, when you want to import information from a QR Bill to an existing purchase document and use it to validate amount, currency and store the payment reference (This functionality is planned for the May 2020 update of [!INCLUDE[d365fin](../../includes/d365fin_md.md)]).
* Purchase Journal, when you want to create new Purchase Journal Lines based on QR Bills (This functionality is planned for the May 2020 update of [!INCLUDE[d365fin](../../includes/d365fin_md.md)]). 

#### Receiving a QR Bill through Incoming Documents
Receving a QR Bill through Incoming Documents is useful in several scenarios, one of them being automated solutions. You can manually receive a QR Bill through Incoming Documents as well:

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Incoming Documents**, and then choose the related link.
2. In the **Incoming Documents** list, create a new by choosing **New**, **New**. This will create a new entry and displaying it in the **Incoming Document** page.
3. On the **Incoming Document** page, enter a description in the **Description** field.
4. To import the QR-Bill, choose **Actions**, **QR-Bill**, **Scan QR-Bill** to scan a QR Bill into the incoming document entry.
5. The QR-Bill will be imported. Check the **Matching Details** Fasttab for errors.

From the incoming document you can create a Purchase Journal or Purchase Invoice, both of which will carry the payment reference from the QR Bill.

> [!Note]
> When importing QR-Bills, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] will first try to find a Vendor Bank Account with a matching IBAN or QR-IBAN account no. When importing QR-Bills on Incoming Documents and thereby creating a document or purchase journal from scratch, the Vendor Bank Account will determine the vendor to use. The Incoming Document approach provides more validation scenarios to match and validate that the vendor is correct.

#### Receiving a QR Bill through Purchase Order or Purchase Invoice (Planned for May 2020)
Receiving a QR Bill through a Purchase Order or Purchase invoice is meant for validation of the invoice amount and for carrying the payment reference. Similar to the Incoming Document you can scan or import a QR Bill into an *existing* document. This process will attempt to find the Vendor through the Vendor Bank Account with a matching IBAN or QR-IBAN and block the scan/import if the vendor does not match the vendor on the purchase document. If a Vendor Bank Account is not found you can create it and then allow the QR Bill to get attached to the purchase document. When the QR Bill is scanned or imported into the purchase document it will store the amount, payment reference and other information from the QR Bill on the purchase document. This is used for validation before posting of the purchase document. Posting the purchase document will be blocked if the amount of the order/invoice does not match the amount from the QR Bill. Validation will also happen at the moment of scan/import. For example, when attempting to scan or import a QR Bill the system will error if the payment reference is already used on an existing Vendor Ledger Entry for the same vendor. This is because vendors cannot issue multiple QR bills with the same payment reference. Equally, the system will also check if the QR Bill and payment reference has already been imported a into an open purchase document, to minimize the risk of mistakes. 

#### Receiving a QR Bill through a Purchase Journal (Planned for May 2020)
QR Bills can be scanned or imported directly into a **Purchase Journal**. This is useful when you want to create new journal lines based on a QR Bill. Contrary to the above scenario with receiving QR Bills through purchase documents to be used for validation, scanning or importing directly into a purchase journal will create a new **Purchase Journal Line** using the vendor and amount from the QR Bill, trying to identify the vendor by finding a **Vendor Bank Account** with a matching IBAN or QR-IBAN.This enables a very productive payment scenario if you do not want to use the Purchase Order/Invoice module.  

#### General information about scanning QR Bills
QR Bills can be scanned into [!INCLUDE[d365fin](../../includes/d365fin_md.md)] using an input scanner, a scanner that simulates the keyboard and "copy/pastes" the decoded value into a field into [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. 

#### General information about importing QR Bills 
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] can import a QR Bill that have been scanned, decoded and saved to a .txt file. This is usable if your scanner solution produces .txt files and places them in a folder.

> [!Note]
> You cannot import a PDF file with a QR Bill. PDF files can be scanned directly into [!INCLUDE[d365fin](../../includes/d365fin_md.md)] or saved to a .txt file and then imported.

### Reconciliation
When importing bank transactions (camt) in the Payment Reconciliation Journal page, this file is assumed to include the payment reference, which will automatically find the corresponding **Customer Ledger Entries** to settle.    

## See Also
[Switzerland Local Functionality](switzerland-local-functionality.md)  
