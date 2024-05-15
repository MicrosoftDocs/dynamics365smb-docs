---
author: brentholtorf
ms.topic: include
ms.date: 03/20/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

On purchase documents and journals, you can specify a document number that refers to the vendor's numbering system. Use this field to record the number that the vendor assigned to the order, invoice, or credit memo. You can then use the number later if, for some reason, you need to search for the posted entry using this number.

The **Ext. Doc. No. Mandatory** field in the **Purchases & Payables Setup** page specifies whether it's mandatory to enter an external document number in the following situations:

* In the **Vendor Invoice No.** field, **Vendor Order No.** field, or the **Vendor Cr. Memo No.** field on a purchase header

* In the **External Document No.** field on a general journal line, where the **Document Type** field is set to *Invoice*, *Credit Memo*, or *Finance Charge Memo*, and the **Account Type** field is set to *Vendor*.

If you select this field, it will not be possible to post an invoice, a credit memo, or the type of general journal line described above without an external document number.

The external document number is included in posted documents where you can search by the relevant number. You can also search using the external document number when navigating on vendor ledger entries.

A different way to handle external document numbers is to use the **Your Reference** field. If you use the **Your Reference** field, the number will be included in posted documents, and you can search by it in the same way as for values from **External Document No.** fields. But the field isn't available on journal lines.
