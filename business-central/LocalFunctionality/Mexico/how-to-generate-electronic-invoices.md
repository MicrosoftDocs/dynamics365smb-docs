---
title: Generate Electronic Invoices in the Mexican Version [MX]
description: After a sales invoice is posted in the Mexican version, an electronic invoice must be generated and sent to the customer.
author: altotovi
ms.author: altotovi
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 10/20/2026
ms.custom: bap-template
ms.search.keywords: electronic invoice, sales invoice, Mexican version
ms.search.form: 132, 25
ai-usage: ai-assisted
---

# Generate electronic invoices in the Mexican version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], after you post a sales invoice, you must generate an electronic invoice that is sent to the customer. You can also export the electronic invoice as an XML file, which you can save to a specified location.  

The following procedure describes how to generate electronic invoices for sales invoices. The same stamp and send workflow is available for the following posted documents:

* Sales credit memos  
* Service invoices  
* Service credit memos  

For posted sales shipments and transfer shipments, the **Send** action requests a stamp without offering the email options. Export the stamped document as XML or print it as needed.

## Generate electronic invoices for sales invoices  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Posted Sales Invoices**, and then choose the related link.
1. Select the posted invoice.  

    > [!NOTE]
    > To cancel a stamped document, fill in **CFDI Cancellation Reason Code**. Fill in **Substitution Document No.** only when the selected cancellation reason requires a replacement document. Learn more in [Cancel documents](electronic-invoicing.md#cancel-documents).
1. In the **Electronic Document** action group, select **Send**.
1. Select **Request Stamp**, **Send**, or **Request Stamp and Send**.

    If you choose **Request Stamp**, the posted invoice is digitally signed by your PAC, and you can then send the posted invoice afterwards. If you choose **Request Stamp and Send**, the posted invoice is digitally signed and sent in one step.

    **Send** emails a document that already has a stamp. The XML file is attached to the email. If **Send PDF Report** is selected on **General Ledger Setup**, a PDF is attached too.

    View **Electronic Document Status** on the **Electronic Invoice** FastTab.
1. Optionally, choose the **Export E-Document as XML** action. Select the location where you want to save the electronic invoice as an XML file.  

To review sending activity, check **Date/Time Sent** and **No. of E-Documents Sent** on the **Electronic Invoice** FastTab. You can also use **Export E-Document as PDF** after the document receives a stamp.

> [!NOTE]  
> [!INCLUDE[bp_refimplementation](../../includes/bp_refimplementation.md)]  

## Receive payments

You can generate a CFDI 4.0 payment receipt with the Pagos 2.0 payment complement for an applied customer payment. Configure electronic invoicing and the relevant SAT payment information before you request a stamp. You can't stamp a payment that is applied to an invoice that doesn't have a stamp.

> [!IMPORTANT]  
> [!INCLUDE [prod_short](../../includes/prod_short.md)] supports customer payment receipts with the Pagos 2.0 complement. This support doesn't include withholding receipts.

### Stamp the payment  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Customer Ledger Entries**, and then choose the related link.  
1. Find a payment that you applied to the electronic invoice, and then select this line.
1. Choose the **Send** action, and then specify if you want to also request a digital stamp for the payment.

## Register export (Comercio Exterior Complement)

The Comercio Exterior Complement is an annex to the electronic invoice. It identifies importers and exporters and improves the description of the merchandise that is traded. The Comercio Exterior Complement is a key obligation for taxpayers who export merchandise.

To set up Comercio Exterior Complement, follow these steps:  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **General Ledger Setup**, and then choose the related link.  
1. On the **Electronic Invoice** FastTab, in the **USD Currency Code** field, choose the USD currency you want to use. It can be different than *USD*. For example, it might be *USD-CFDI*.  
1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Units of Measure**, and then choose the related link.
1. In the **SAT Customs Unit** field, choose the unit of measure from the **SAT Custom Units** table for foreign trade operations.

To create Comercio Exterior Complement:

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Sales Invoices**, and then choose the related link.
1. Create a sales invoice with all details ready for export.
1. In **CFDI Export Code**, select the code for your export. The code's setup determines whether **Foreign Trade** is selected. Validation also sets **Exchange Rate USD** from the currency specified in **USD Currency Code** on **General Ledger Setup**.
1. If you configure a foreign trade invoice, you must fill in the following fields.

    |Field|Description|  
    |------------------------------------|---------------------------------------|
    |**SAT Address ID**|On the **Electronic Document** FastTab, select the SAT address for the destination. Also assign a SAT address to the invoice's location.|
    |**SAT International Trade Term**|On the **Electronic Document** FastTab, select the relevant SAT Incoterm.|
    |**Exchange Rate USD**|On the **Electronic Document** FastTab, review the USD-to-MXN exchange rate. You can change the value if needed.|

1. After posting the document and getting a stamp, you'll get an XML file with the Comercio Exterior Complement.

> [!NOTE]  
> If you want to create an invoice for foreign trade, the **CFDI Export Code** field must be different from **01** because that value is used for domestic invoices only.  

## Related information

- [Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md)  
- [Electronic Invoicing](electronic-invoicing.md)  
- [Mexico Local Functionality](mexico-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
