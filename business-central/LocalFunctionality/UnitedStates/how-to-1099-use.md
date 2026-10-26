---
title: Track and Review Vendor Data for IRS 1099 Forms
description: Learn how to track IRS 1099 vendor payments, review reporting amounts, make adjustments, and create form documents in Business Central.
author: altotovi
ms.topic: how-to
ms.search.keywords: local, 1099, tax, taxes, IRS
ms.search.form: 50, 51, 132, 10036, 10037, 10049
ms.date: 10/19/2026
ai-usage: ai-assisted
ms.author: altotovi
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
---

# Use the IRS 1099 forms

[!INCLUDE[prod_short](../../includes/prod_short.md)] calculates IRS 1099 forms from applied payments and refunds in the reporting period, using the 1099 information on the related vendor ledger entries. For purchase invoices, specify **IRS 1099 Form No.** and **IRS 1099 Form Box No.** on the document header and review which lines are **1099 Liable** before posting.

## Work with purchase documents  

To populate the IRS-related fields on a purchase document, configure the reporting period and the vendor's form box setup for that period. When you [create the purchase document](../../purchasing-how-record-purchases.md), check **IRS 1099 Reporting Period**, **IRS 1099 Form No.**, and **IRS 1099 Form Box No.** on the **Shipping and Payment** FastTab. The defaults come from the vendor's setup for the document's **Posting Date**. You can change the form and box for the document.

On the document lines, clear **1099 Liable** for amounts that shouldn't contribute to 1099 reporting. Only lines marked **1099 Liable** contribute to the reporting amount posted from a purchase invoice.

### Review vendor form box information by work date

On the **Vendor Card** and **Vendor List** pages, IRS 1099 information is shown for the reporting period that includes the work date. The work date can differ from today's date.

The following fields are updated automatically based on the active reporting period:

- **IRS Reporting Period**: Shows the reporting period that corresponds to the current work date.
- **IRS 1099 Form No.**: Shows the IRS form number assigned to the vendor for that reporting period.
- **IRS 1099 Form Box No.**: Shows the form box number used for the vendor in the current reporting period. You can choose the value to review the complete form box setup.

> [!IMPORTANT]
> If no reporting period includes the document's **Posting Date**, the **IRS 1099 Form No.** and **IRS 1099 Form Box No.** fields aren't editable.

> [!NOTE]
> If the IRS-related fields are blank, verify that the document is within the date range that you configured for IRS reporting. Also, check whether you created an IRS reporting period for this year and set up the vendor to be 1099 eligible for this reporting year.

### Complete missing vendor setup

[!INCLUDE[prod_short](../../includes/prod_short.md)] helps you maintain consistent IRS 1099 reporting by notifying you when vendor setup is incomplete for the current reporting period.

A vendor might have IRS 1099 reporting set up in a previous reporting period, but no form box configured for the period that includes the document's posting date. In that situation, a notification appears when you work with purchase documents for that vendor. From the notification, you can:

- Select the action in the notification to open the **IRS 1099 Vendor Form Box Setup** page.
- Configure the appropriate IRS 1099 form and form box for the current reporting period.

This notification helps ensure that recurring vendors aren't unintentionally excluded from required IRS 1099 reporting.

### Post purchase documents and correct entries

When you [post the purchase document](../../purchasing-how-record-purchases.md), the following fields are filled in based on the document:

- **IRS 1099 Reporting Period**
- **IRS 1099 Form No.**
- **IRS 1099 Form Box No.**
- **IRS 1099 Reporting Amount**

If you omitted the 1099 information or used the wrong form or box, you can correct the vendor ledger entry. On the **Vendor Ledger Entries** page, choose **Edit List** and review **IRS 1099 Reporting Period**, **IRS 1099 Form No.**, **IRS 1099 Form Box No.**, and **IRS 1099 Reporting Amount**.

Changing the period clears the form, and changing the form clears the box and reporting amount. Fill in the fields in that order, and enter the reporting amount last. For an invoice, the amount must be negative; for a credit memo, it must be positive. Its absolute value can't exceed the entry's **Amount**. Reversed entries use the opposite sign.

> [!NOTE]
> You can't change the IRS fields on a vendor ledger entry that is linked to a form document through collected line details.

The calculation selects payments and refunds by their **Posting Date** in the reporting period and follows their applications to invoices and credit memos. The invoice doesn't have to be posted in the same reporting period as the payment. For a partial payment, the calculation includes a proportion of the invoice's **IRS 1099 Reporting Amount**.

## Review data before calculation

### Review IRS 1099 data by vendor

You can use the **IRS 1099 Vendor Overview** page to review and analyze IRS 1099 information for all vendors in a single view.

The page provides:

- A filtered view by IRS reporting period.
- A summary of vendors with their assigned IRS 1099 forms and form box numbers.
- Aggregated transaction amounts per vendor, form, or form box combination.
- Drill-down access to the underlying vendor ledger entries.

Use search to open **IRS 1099 Vendor Overview**. Select **Reporting Period No.** to review another period, and choose an **Amount** value to review the underlying vendor ledger entries.

### Amount adjustments

If you made a mistake, you can manually adjust values before calculation. To do so, follow these steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
1. On the **IRS Reporting Periods** page, choose the **Adjustments** action to open the **IRS 1099 Vendor Form Box Adjustments** page.  
1. Specify **Vendor No.**, **Form No.**, and **Form Box No.**, and enter the adjustment in **Amount**. This adjustment is added to the amount calculated from vendor ledger entries.

### Vendor corrections

If you didn’t fully configure the vendor before you posted the documents or payments, for example, you forgot to fill in the **Form No.** or **Form Box No.** fields, you can make corrections. To make corrections, follow these steps:  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS 1099 Vendor Form Box Setup**, and then choose the related link.  
1. On the **IRS 1099 Vendor Form Box Setup** page, provide the necessary information, and then choose the **Propagate** action.
1. Specify **Starting Date** and **Ending Date**, and choose whether to update **Purchase Documents**, **Vendor Ledger Entries**, or both. Only open purchase documents are updated.
1. Close the page. Now you can continue with the 1099 form calculations.

> [!IMPORTANT]
> Propagating to vendor ledger entries resets **IRS 1099 Reporting Amount** to the entry's full **Amount**. Review any entries whose reporting amount was previously adjusted.

## Create 1099 form documents

To create new 1099 form documents for the reporting years, follow these steps:  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **IRS 1099 Form Documents**, and then choose the related link.
1. On the **IRS 1099 Form Documents** page, choose the **Create Forms** action to create IRS 1099 forms based on the filters you want to use:

   - You must select the period. The other choices are optional.  
   - If you don't select a vendor, form documents are created for all vendors.
   - If you don't select a form, form documents are created for all forms.
   - If you don't select **Replace**, existing documents are skipped. **Replace** recalculates existing documents, but skips **Submitted** documents. Documents linked to a transmission can't be deleted and replaced.

1. Choose **OK**, and then open a created document to review its header and lines.

A form document is created only when at least one line meets its minimum reportable amount. You can also open the documents for a period through **Documents** on **IRS Reporting Periods**.

The following information is available on the document header:

| Field name | Description |
|--------|-----------------|
| **Vendor No.** | Specifies the vendor number.|
| **Form No.** | Specifies the form number used for calculation of this document. |
| **ID** | Specifies the noneditable ID of the document. |
| **Status** | A new document is **Open**. The other statuses are:<br><br>- **Released**: ready to add to an IRIS transmission or email to the vendor.<br>- **In Progress**: sent through IRIS and awaiting acceptance of the submission.<br>- **Submitted**: set when the IRS accepts the submission, or when you choose **Mark as Submitted** after submitting outside the integration.<br>- **Abandoned**: excluded from further reporting. |
| **Receiving 1099 E-Form Consent** | Shows whether your vendor provided signed consent to receive their 1099 form electronically. You can't change this field on the form. You can change the field only on the **Vendor Card** page. This consent is required if you want to send 1099 forms to the vendor by email. |
| **Vendor E-Mail** | Specifies the recipient address for vendor copies. The address comes from **E-Mail For IRS**, or from the vendor's standard **Email** address if **E-Mail For IRS** is blank. |
| **Copy B Sent** | Specifies whether this form copy is sent. This field is marked automatically and can't be edited. |
| **Copy 2 Sent** | Specifies whether this form copy is sent. This field is marked automatically and can't be edited. |

The lines in documents have the following information:

| Field name | Description |
|--------|---------------------|
| **Form Box No.** | Specifies the number of the 1099 form box used in this line. |
| **Calculated Amount** | Specifies the amount per period and form box calculated by **Create Forms**. If you turn on **Collect Details For Line**, choose this value to review the connected vendor ledger entries. This value can't be changed manually. |
| **Adjustment Amount** | Specifies the adjustment entered for this period, vendor, and form box on **IRS 1099 Vendor Form Box Adjustments**. This amount can't be changed manually on the form document. |
| **Amount** | Initially equals **Calculated Amount** plus **Adjustment Amount**. This value is used for reporting and can be changed manually. |
| **Minimum Reportable Amount** | Specifies the threshold used to determine whether to include the line in 1099 reporting. |
| **Include in 1099** | Specifies whether to include the line. The line is included when **Amount** is greater than or equal to **Minimum Reportable Amount**. |

To submit or send vendor copies, go to [Submit and report the IRS 1099 forms](how-to-1099-report.md).

## Related information

- [United States Local Functionality](united-states-local-functionality.md)
- [How to set up the IRS 1099 forms](set-up-use-irs1099-form-v24.md)
- [How to submit and report the IRS 1099](how-to-1099-report.md)
- [Register New Vendors](../../purchasing-how-register-new-vendors.md)
- [Record purchases](../../purchasing-how-record-purchases.md)
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
