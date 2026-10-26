---
title: New Zealand IRD Numbers and Adjustment Notes
description: Learn how IRD numbers and credit memo adjustment fields support tax reporting and corrections in the New Zealand version of Business Central.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: IRD number, adjustment notes, credit memos
ms.date: 10/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# New Zealand Inland Revenue Department numbers and adjustment notes

An IRD number identifies a person or organisation for New Zealand tax purposes.

IRD numbers and adjustment notes, or credit memos, support tax reporting and corrections.

## IRD number

Companies, trusts, partnerships, and other businesses need their own IRD numbers. Learn more in [IRD numbers](https://www.ird.govt.nz/managing-my-tax/ird-numbers) on the Inland Revenue website.

## Adjustment notes

Suppliers provide *supply correction information* to correct errors in taxable supply information or a filed return. Corrections can include returned goods, incorrect details, or changes to the GST amount.

A correction can increase or decrease your net GST for the tax period. Include the correction in the GST return for the period in which the correction information was provided. For the information you must retain, see [Supply correction information](https://www.ird.govt.nz/gst/tax-invoices-for-gst/supply-correction-information) on the Inland Revenue website.

Adjustment notes—or credit memos—should be connected to an invoice.  

In Business Central, use credit memos for adjustment notes. Record the original invoice reference and the credit memo's document date, and retain the supply correction information that Inland Revenue requires. The following fields support the adjustment:

- **Adjustment Applies-to**: The number of the document to which the adjustment note applies. When GST functionality is enabled, **Copy Document** fills in this field for a sales credit memo or return order. You can also select a paid or closed transaction.

- **No.**: The credit memo number. The posted credit memo receives its number from the posting number series.

- **Document Date**: The date of the credit memo.
- **Reason Code**: Required before posting a credit memo or return order when GST functionality and **Adjustment Mandatory** are enabled in **General Ledger Setup**.
- **Adjustment**: Set automatically for a new sales credit memo or return order when GST functionality is enabled. The **Adjustment Applies-to** field identifies a single document.

## Related information

- [Enter New Zealand IRD Numbers](how-to-enter-new-zealand-business-numbers.md)
- [New Zealand Local Functionality](new-zealand-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
