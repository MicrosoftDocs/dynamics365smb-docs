---
title: Track data and use the IRS 1099 form
description: Learn how to post documents to calculate information for your 1099 tax forms.
author: altotovi
ms.topic: how-to
ms.search.keywords: local, 1099, tax, taxes, IRS
ms.search.form: 50, 51, 132, 10036, 10037, 10049
ms.date: 12/30/2025
ms.author: altotovi
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
---

# Use the IRS 1099 forms

[!INCLUDE[prod_short](../../includes/prod_short.md)] calculates 1099 forms only for vendors whose purchase invoices include information about **IRS 1099 Form No.** and **IRS 1099 Form Box No.** on the document header and if the payment is posted and applied to the invoices.  

## Work with purchase documents  

To ensure all IRS-related fields are applied to the purchase document, the document must be within the specified date range, and both IRS reporting periods and vendors must be configured. You need to [create the purchase document](../../purchasing-how-record-purchases.md) and check whether the **IRS Reporting Period**, **IRS 1099 Form No.** , and **IRS 1099 Form Box No.** fields are filled in on the **Shipping and Payment** FastTab. These fields are prepopulated with default values from the **Vendor Card** page. You can change these values if this specific document needs to comply with a different 1099 form.

**Dynamic vendor form box information (based on work date)**

On the **Vendor Card** and **Vendor List** pages, IRS 1099 information is shown based on the current work date. This means that the values you see always reflect the IRS reporting period that applies at the time you're working in [!INCLUDE[prod_short](../../includes/prod_short.md)].

The following fields are updated automatically based on the active reporting period:

- **IRS Reporting Period** – Shows the reporting period that corresponds to the current work date.
- **IRS 1099 Form No.** – Shows the IRS form number assigned to the vendor for that reporting period.
- **IRS 1099 Form Box No.** – Shows the form box number used for the vendor in the current reporting period. You can choose the value to review the complete form box setup.

This behavior replaces earlier versions where vendor fields reflected only the most recently configured reporting period. 

> [!IMPORTANT]
> If the **Posting Date** of the document isn't within the reporting period date, the IRS fields are disabled.
> [!NOTE]
> If the IRS-related fields are blank, verify that the document is within the date range that you configured for IRS reporting. Also, check whether you created an IRS reporting period for this year and set up the vendor to be 1099 eligible for this reporting year.

**Notifications for missing reporting period setup**

[!INCLUDE[prod_short](../../includes/prod_short.md)] helps you maintain consistent IRS 1099 reporting by notifying you when vendor setup is incomplete for the current reporting period.

If a vendor had IRS 1099 reporting set up in a previous reporting period, but no form box is configured for the current period, a notification appears when you work with purchase documents for that vendor. From the notification, you can:

- Select the action in the notification to open the **IRS 1099 Vendor Form Box Setup** page.
- Configure the appropriate IRS 1099 form and form box for the current reporting period.

This notification helps ensure that recurring vendors aren't unintentionally excluded from required IRS 1099 reporting.

**Post purchase document**

When you [post the purchase document](../../purchasing-how-record-purchases.md), the following fields are filled in based on the document:

- **IRS 1099 Reporting Period**
- **IRS 1099 Form No.**
- **IRS 1099 Form Box No.**
- **IRS 1099 Reporting Amount**

If you made a mistake and didn’t use **IRS 1099 Form No.** and **IRS 1099 Form Box No.** on the document, or you used the wrong one, you can make corrections. To make corrections, on the **Vendor Ledger Entries** page, select the line you want to correct, and then choose the **Edit List** action. Change the **IRS 1099 Form Box No.** and **IRS 1099 Reporting Amount** fields.

All 1099 forms are calculated based on the information provided on the **Vendor Ledger Entries** page. But, make sure that the payment is posted and applied to the invoice during the same reporting period.

## Precalculation  

### Review IRS 1099 data by vendor

You can use the **IRS 1099 Vendor Overview** page to review and analyze IRS 1099 information for all vendors in a single view.

The page provides:

- A filtered view by IRS reporting period.
- A summary of vendors with their assigned IRS 1099 forms and form box numbers.
- Aggregated transaction amounts per vendor, form, or form box combination.
- Drill-down access to the underlying vendor ledger entries.

Access this page from **Reports and Analysis** to get a quick overview of your IRS 1099 reporting status.

### Amount adjustments

If you made a mistake, you can manually adjust values before calculation. To do so, follow these steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
1. On the **IRS Reporting Periods** page, choose the **Adjustments** action to open the **IRS 1099 Vendor Form Box Adjustments** page.  
1. Add the amount of adjustment to the IRS reporting amount, using **Vendor No.**, **Form No.**, **Form Box No.**, and the **Adjustment Amount**.

### Vendor corrections

If you didn’t fully configure the vendor before you posted the documents or payments, for example, you forgot to fill in the **Form No.** or **Form Box No.** fields, you can make corrections. To make corrections, follow these steps:  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS 1099 Vendor Form Box Setup**, and then choose the related link.  
1. On the **IRS 1099 Vendor Form Box Setup** page, provide the necessary information, and then choose the **Propagate** action.
1. Choose how the new form box setup makes updates. You need to decide for which period you want to propagate this change and if you want to update existing open purchase documents or vendor ledger entries, or both.
1. Close the page. Now you can continue with the 1099 form calculations.

## Create 1099 form documents

To create new 1099 form documents for the reporting years, follow these steps:  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
1. On the **IRS Reporting Periods** page, choose the **Documents** action.

   or

   Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS 1099 Form Documents**, and then choose the related link.
1. On the **IRS 1099 Form Documents** page, choose the **Create Forms** action to create IRS 1099 forms based on the filters you want to use:

   - You must select the period. The other choices are optional.  
   - If you don't select a vendor, form documents are created for all vendors.
   - If you don't select a form, form documents are created for all forms.
   - If you don't select the option **Replace**, only new form documents are created. If you select the option **Replace**, the existing form documents are replaced.

1. The list of created 1099 form documents shows all created documents based on the combination of vendors and form numbers. From this list, you can open any of the created documents.  
1. The following information is available on the document header:  

   | Field Name | Description |
   |--------|-----------------|  
   | **Vendor No.** | Specifies the vendor number.|
   | **Form No.** | Specifies the form number used for calculation of this document. |
   | **ID** | Specifies the non-editable ID of the document.  |
   | **Status** | Specifies the status of the document. The created document has the status **Open**, but the status can also be **Released** (when a user releases it) and **Submitted** (after you submit it to the IRS). |
   | **Receiving 1099 E-Form Consent** | Shows whether your vendor provided signed consent to receive their 1099 form electronically. You can't change this field on the form. You can change the field only on the **Vendor Card** page. This consent is required if you want to send 1099 forms to the vendor by email. |
   | **Email** | Specifies the email where the form is sent if the vendor consented to electronically receive 1099 forms. If this vendor configured the **E-Mail For IRS** field, this value appears. If not, the address in the **E-Mail** field on the **Vendor Card** page is used.  |
   | **Copy B Sent** | Specifies whether this form copy is sent. This field is marked automatically and can't be edited.  |
   | **Copy C Sent** | Specifies whether this form copy is sent. This field is marked automatically and can't be edited.  |

1. The lines in documents have the following information:  

   |  Field Name  |  Description  |  
   |--------|---------------------|
   | **Form Box No.** | Specifies the number of the 1099 form box used in this line.   |
   | **Calculated Amount** | Specifies the amount per period and IRS code calculated by the **Create Forms** action on the list page. This amount is taken from the **Vendor Ledger Entries** page. If you enable the **Collect Details For Line** option, then you can see the connected entries. This value can't be changed. |
   | **Adjustment Amount** | Specifies the calculated adjustment amount of the document line, the amount you specified for the **Period**, **Vendor**, and **Form Box** during your setup. This amount can't be changed manually. |
   | **Amount** | Specifies the amount of the document line. The sum of calculated amount and adjustment amount. This value is used for reporting and the amount can be changed manually.  |
   | **Minimum Reportable Amount** | The threshold to decide whether the certain form box with the reporting amount must be reported.   |
   | **Include in 1099** | Specifies whether the document line should be included in the 1099. The line is included if the amount is more than or equal to the minimum reportable amount. |

1. Close the page.  

## Related information

- [United States Local Functionality](united-states-local-functionality.md)
- [How to set up the IRS 1099 forms](set-up-use-irs1099-form-v24.md)
- [How to submit and report the IRS 1099](how-to-1099-report.md)
- [Register New Vendors](../../purchasing-how-register-new-vendors.md)
- [Record purchases](../../purchasing-how-record-purchases.md)
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
