---
title: 'QR-Bill Management | Microsoft Docs'
description: Set up the QR-Bill Management extension extension and easily generate, send, and import QR-bills.
author: sorenfriisalexandersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: QR-bill, invoice, incoming documents, payment reference
ms.date: 03/25/2020
ms.author: soalex

---
## QR-Bill Management in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]
From July 1st 2020, companies in Switzerland must be able to receive QR-bills. QR-bills are payment slips that follow invoices, and are a country-wide initiative to streamline payment processes. QR-bills replace all existing payment slips and ESR-related functionality. They contain all of the information needed to make payments, and a QR code on the payment slip makes it easy to import the information into [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. All relevant information is imported and used to generate payments for the vendor who sent the QR-bill, including the payment reference, which automatically gets included in Vendor Ledger Entries and exported in payment files to the bank.

## Get started with QR-Bill Management
The QR-Bill Management extension is included and automatically installed in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. To get started with the extension, you must make a few configuration changes in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. An easy way to that is to use the Set Up QR-Bill assisted setup guide. The guide will help you enter information, such as:

* Specify whether to use your IBAN or QR-IBAN.
* Define how to display names and address on QR-bills, including the German Umlaut Chars Encoding. We recommend that you use the default values.
* Select the layout for QR-bills. The layout determines whether to use IBAN or QR-IBAN, whether the reference type is creditor or QR reference, and whether to include billing information in the SWICO format.
* Enable sales and service invoice types, and payment methods, for the QR-bills.
* Specify the journal template and journal batch to use when generating purchase journals from scanned or imported QR-bills.

If needed, you can change these settings on the following pages: 

* **QR-Bill Setup** to change general settings.
* **QR-Bill Layout** to change layout settings.

<!-- Suggest that we remove these. Typically, we don't give step by step guidance for setup guides. I did provide an edited version though, just in case you really want it.

1. Choose the ![Settings](../../media/ui-experience/settings_icon_small.png) icon, and then choose **Assisted Setup**.
2. Find the group named **Get ready for the first invoice**.
3. Choose **Set up QR-Bill**. This starts an assisted setup guide that will help us configure the QR-Bill Management extension.
4. The first step of the setup is an introduction to the feature. Choose **Next**.
5. In the next step , You will now see *QR-Bill setup step 1 of 6: Generating and issuing QR-Bills*. This page shows your **Company Information**, on which you need to fill in the new field **QR-IBAN**. When done, choose **Next**.
6. You will now see *QR-Bill setup step 2 of 6: Generating and issuing QR-Bills*. Here you must specify **Address Type** and **German Umlaut Chars Encoding**. Both have to do with how addresses and names are displayed on the QR-Bill. Recommended values are the defaults. When done, choose **Next**.
7. You will now see *QR-Bill setup step 3 of 6: Generating and issuing QR-Bills*. Here you must select the **Default QR-Bill Layout**. This determines several things for the QR-Bill, like **IBAN type** (QR-IBAN or regular IBAN), **Reference type** (Creditor Reference or QR Reference) and whether or not to include **Billing Information** in SWICO format for passing more information to the receiver, like the invoice number, VAT amount etc. All of this can be changed in the QR-Bill Layout page as well. Recommended value is the default. When done, choose **Next**.
8. You will now see *QR-Bill setup step 4 of 6: Generating and issuing QR-Bills*. In this step you must select which payment methods to enable for QR-Bills. QR-Bills are generated for a sales or service invoice if the invoice type is enabled for QR-Bills (next step) and the invoice is using a **Payment Method** enabled for QR-Bills. When done, choose **Next**.
9. You will now see *QR-Bill setup step 5 of 6: Generating and issuing QR-Bills*. In this step you must select the document types to enable for QR-Bills. You can select to enable Sales Invoices and Service Invoices. When done, choose **Next**.
10. You will now see *QR-Bill setup step 6 of 6: Receiving QR-Bills*. In this step you must select the Journal Template and Journal Batch to use for generating purchase journals from scanned or imported QR-Bills. When done, choose **Next**.

1. Choose the ![Settings](../../media/ui-experience/settings_icon_small.png) icon, and then choose **Assisted Setup**.
2. Under **Get ready for the first invoice**, choose **Set up QR-Bill**.
4. Read the introduction to the feature, and then choose **Next**.
5. Step 1 shows your **Company Information**. Fill in the **QR-IBAN** field, and then choose **Next**.
6. In Step 2, specify the **Address Type** and **German Umlaut Chars Encoding**. These settings are related to how addresses and names are displayed on the QR-Bill. We recommend that you use the default values. When done, choose **Next**.
7. In Step 3, choose the **Default QR-bill Layout**. This determines several things for the QR-bill, such as the **IBAN type** (IBAN or QR-IBAN), **Reference type** (Creditor Reference or QR Reference), and whether to include **Billing Information** in the SWICO format for passing additional information, such as the invoice number, VAT amount, and so on, to the receiver. We recommended that you use the default values. When you're done, choose **Next**.
8. In Step 4, choose the payment methods to enable for QR-bills. QR-bills are generated for a sales or service invoice if the invoice type and payment method are enabled for QR-bills (we will enable it next step) and the invoice uses a **Payment Method** that is enabled for QR-bills. When done, choose **Next**.
9. You will now see *QR-bill setup step 5 of 6: Generating and issuing QR-bills*. In this step you must select the document types to enable for QR-bills. You can select to enable Sales Invoices and Service Invoices. When done, choose **Next**.
10. You will now see *QR-bill setup step 6 of 6: Receiving QR-bills*. In this step you must select the Journal Template and Journal Batch to use for generating purchase journals from scanned or imported QR-bills. When done, choose **Next**.

If you want to change these settings later, use the following pages:

* **QR-Bill Setup** to change general settings.
* **QR-Bill Layout** to change layout settings.
-->
## Issuing QR-Bills
You can enable QR-bills for sales and service invoices. This adds an entry to **Report Selection - Sales** that generates an extra PDF with the QR-bill when invoices are generated. 

## Adding billing information to QR-Bills
When you create a QR-bill you can include billing information in the SWICO format as advocated by SIX, the Swiss payment infrastructure provider. Ideally, business applications that either produce or import a QR-bill should also be able to process information, such as the VAT amount, the vendor's invoice number, and so on, because it can be valuable for the payable invoice. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], this information is imported on the QR-bill. A key piece of information that is used by default is the vendor's invoice number. <!--why is this key information?--> The other information is also imported but not currently used. It can be used be an customization extension.  

## Understanding the Payment Reference
The most important thing in a payment process is to pay the correct amount to the correct party, and allowg this party to reconcile payments easily to close outstanding accounts. The QR-Bill Management extension handles this by generating a payment reference for every QR-bill. The payment reference is unique for all invoices <!-- in a single [!INCLUDE[d365fin](../../includes/d365fin_md.md)] instance. -->, which means issue the same payment reference twice. If your customer is also using [!INCLUDE[d365fin](../../includes/d365fin_md.md)], the payment reference is imported when receiving QR-bills, transferred to the Vendor Ledger Entries page, and used as a reference when creating vendor payments. For more information, see [Receiving QR-Bills](ui-extensions-swiss-qr-bill.md#receiving-qr-bills). <!--As with the previous ESR Reference.--> Eventually, payment files (pain.001) will be sent from the customer's business app to their bank with the message to transfer the amounts to the vendor's account. The bank will produce a customer statement file (camt.054) that the vendor can import to reconcile accounts. This file will include the payment reference and is imported through the Data Exchange Framework that is updated by the QR-Bill Management extension to import camt.054 files.  

Previously, you could add logical <!--logical?--> information to the ESR Reference. This is not the case with the payment reference in QR-bills. There will always be a 1:1 relation between an issued QR-bill and a payment, which makes reconciliation easy and eliminates the need to include logical <!--logical?--> information. Instead, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] uses a unique counter for the payment reference, making sure it is unique. Additionally, logic is in place to block import or scan of the same payment reference twice, rendering it impossible to use it twice by mistake.  <!--Not sure that we need this paragraph. It repeats a lot of things stated in the previous paragraph.-->

## Receiving QR-Bills
You can receive QR-bills in several places in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]:

* **Incoming Documents**, when you want a QR-bill to initiate the creation of a new purchase document or purchase journal.
* **Purchase Orders and Purchase Invoices**, when you want to import information from a QR-bill to an existing purchase document and use it to validate the amount and currency and to store the payment reference (This functionality is planned for the May 2020 update of [!INCLUDE[d365fin](../../includes/d365fin_md.md)]).
* **Purchase Journals**, when you want to create new purchase journal lines based on QR-bills (This functionality is planned for the May 2020 update of [!INCLUDE[d365fin](../../includes/d365fin_md.md)]). 

### Receiving a QR-Bill through Incoming Documents
Receiving a QR-bill through incoming documents is useful in several scenarios, one of them being automated solutions. You can also manually receive a QR-bill through incoming documents.

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Incoming Documents**, and then choose the related link.
2. In the **Incoming Documents** list, create a new entry by choosing **New**, and then **New**. 
3. On the **Incoming Document** page, enter a description in the **Description** field.
4. To import the QR-bill, choose **Actions**, then **QR-Bill**, and then **Scan QR-Bill** to scan a QR-bill into the incoming document entry.
 
> [!TIP]
> After you import the QR-bill, you can check the **Matching Details** Fasttab for errors.

From the incoming document you can create a purchase journal or a purchase invoice, and the payment reference from the QR-bill will be assigned to both.

> [!Note]
> When you import QR-bills, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] will try to find a vendor bank account that has a matching IBAN or QR-IBAN. When importing QR-bills on incoming documents, and thereby creating a document or purchase journal, the vendor bank account will determine the vendor to use. The incoming document approach helps ensure that the correct vendor is assigned.

### Receiving a QR-Bill through Purchase Order or Purchase Invoice (Planned for May 2020)
Receiving a QR-bill through a purchase order or purchase invoice validates the invoice amount and adds the payment reference to the ledgers. Like incoming document, you can scan or import a QR-bill into an existing document. This process will attempt to find the vendor through the Vendor Bank Account with a matching IBAN or QR-IBAN on the purchase document. If no match is found, the scan or import is blocked. If a vendor bank account is not found, you can create it and then allow the QR-bill to be attached to the purchase document. When the QR-bill is scanned or imported into the purchase document it will store the amount, payment reference, and other information from the QR-bill on the purchase document. This is used for validation before posting the purchase document. Posting will be blocked if the amount of the order or invoice does not match the amount from the QR-bill. Validation also happen at the moment of the scan or import. For example, if you scan or import a QR-bill that has a payment reference that is already used on a vendor ledger entry for a vendor, an error will display. Vendors cannot issue multiple QR-bills with the same payment reference. Similarly, an error will display if the QR-bill and payment reference has already been imported a into an open purchase document. 

### Receiving a QR-Bill through a Purchase Journal (Planned for May 2020)
You can scan or import QR-bills directly into a **Purchase Journal**. This is useful when you want to create new journal lines based on a QR-bill. Scanning or importing directly into a purchase journal creates a new **Purchase Journal Line** using the vendor and amount from the QR-bill, and tries to identify the vendor by finding a **Vendor Bank Account** that has a matching IBAN or QR-IBAN. For example, using purchase journals is useful if you do not want to use purchase orders or invoices.  

### General information about scanning QR-bills
You can scan QR-bills into [!INCLUDE[d365fin](../../includes/d365fin_md.md)] by using an input scanner, which is a scanner that simulates the keyboard and "copy/pastes" the decoded value in a field. 

### General information about importing QR-bills 
You can import QR-bills that have been scanned, decoded, and saved to a .txt file. For example, this is useful if your scanner solution produces .txt files and places them in a folder. <!--Seems like this information should be above the procedures above.-->

> [!Note]
> You cannot import QR-bills received as PDF files directly into [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] cannot interpret QR-codes. A received QR-bill must first be scanned with a scanner that can interpret the QR-code displayed on the QR-bill. Some scanners create .txt files and place them in a folder. These files can be imported into [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. Some scanners - called input scanners - simulate the keyboard and can scan directly into a field in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].

## Reconciliation
When importing bank transactions (camt) on the Payment Reconciliation Journal page, the file is assumed to include the payment reference, which will automatically find the corresponding **Customer Ledger Entries** to settle.    

## See Also
[Switzerland Local Functionality](switzerland-local-functionality.md)  
