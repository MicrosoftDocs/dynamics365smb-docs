---
author: brentholtorf
ms.topic: include
ms.date: 11/10/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

On purchase documents and journals, you can specify a document number that refers to the vendor's numbering system. Use this field to record the number that the vendor assigned to the order, invoice, or credit memo. You can then use the number later if, for some reason, you need to search for the posted entry using this number.

The **Ext. Doc. No. Mandatory** field in the **Purchases & Payables Setup** page specifies whether it's mandatory to enter an external document number in the following situations:

* In the **Vendor Invoice No.** field when you invoice a purchase order or post a purchase invoice.

* In the **Vendor Cr. Memo No.** field when you invoice a purchase return order or post a purchase credit memo.

* In the **External Document No.** field on a nonrecurring general journal line, where the **Document Type** field is set to **Invoice**, **Credit Memo**, **Finance Charge Memo**, or **Reminder**, and the **Account Type** field is set to **Vendor**.

If you select this field, you can't post an invoice, a credit memo, or the type of general journal line described earlier without an external document number. A value in **Vendor Order No.** doesn't satisfy this requirement.

The external document number is included in posted documents where you can search by the relevant number. You can also search using the external document number when navigating on vendor ledger entries.

Use the **Your Reference** field to store an additional reference on purchase documents. The value is copied to posted document headers, but it doesn't replace the required **Vendor Invoice No.** or **Vendor Cr. Memo No.** value. **Find Entries** doesn't use **Your Reference** when you search by external document number. The field isn't available on standard general journal pages.
