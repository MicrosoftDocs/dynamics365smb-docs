---
title: Track data and use the IRS 1099 form [US]
description: Learn how to post documents to calculate and report the 1099 tax forms so that you can submit the required reports.
author: altotovi
ms.topic: how-to
ms.search.keywords: local, 1099, tax, taxes, IRS
ms.search.form: 50, 51, 132, 10036, 10037, 10049
ms.date: 02/04/2025
ms.author: altotovi
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
---

# Use the IRS 1099 forms

[!INCLUDE[prod_short](../../includes/prod_short.md)] calculates 1099 forms only for vendors whose Purchase Invoice includes information about **IRS 1099 Form No.** and **IRS 1099 Form Box No.** on the document header and if the payment is posted and applied to this invoice.  

## Work with purchase documents  

To ensure all IRS-related fields are applied to the purchase document, the document must fall within the specified date range, and both IRS reporting periods and vendors must be configured. You need to [create the purchase document](../../purchasing-how-record-purchases.md) and check if the **IRS Reporting Period**, **IRS 1099 Form No.** , and **IRS 1099 Form Box No.** fields are populated in the **Shipping and Payment** FastTab. These fields are prepopulated with default values from the **Vendor Card** page. You can change these values if this specific document needs to comply with a different 1099 form.  

> [!IMPORTANT]
> If the **Posting Date** of the document isn't within the reporting period date, the IRS fields are disabled.
> [!NOTE]
> If you don't see populated IRS fields and you expect values there, verify that the document is within the date range that you configured for IRS reporting. Also, check if you created an IRS reporting period for this year and added this vendor to be 1099 eligible for this reporting year.  

When you [post this purchase document](../../purchasing-how-record-purchases.md), you can see the following fields populated in relation to this [posted document](../../purchasing-how-record-purchases.md):

- **IRS 1099 Reporting Period**
- **IRS 1099 Form No.**
- **IRS 1099 Form Box No.**
- **IRS 1099 Reporting Amount**

If you made a mistake and didn’t use **IRS 1099 Form No.** and **IRS 1099 Form Box No.** on the document, or you used the wrong one, you can make corrections. To make corrections, on the **Vendor Ledger Entries** page, select the line you want to correct, and then choose the **Edit List** action. Change the **IRS 1099 Form Box No.** and **IRS 1099 Reporting Amount** fields.

All 1099 forms are calculated based on the information provided on the **Vendor Ledger Entries** page. But, make sure that the payment is posted and applied to the invoice during the same reporting period.  

## Precalculation  

### Amount adjustments

If you have some inaccurate information in the system or missed some document, you can manually adjust values before calculation. To do so, follow these steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
1. On the **IRS Reporting Periods** page, choose the **Adjustments** action to open the **IRS 1099 Vendor Form Box Adjustments** page.  
1. Add the amount of adjustment to the IRS reporting amount, using **Vendor No.**, **Form No.**, **Form Box No.**, and the **Adjustment Amount**.
1. Close the page.

### Vendor corrections

If you didn’t configure the vendor properly, and forgot to add specific **Form No.** or **Form Box No.** but posted the documents or payments already, you can still make corrections. To make corrections, follow these steps:  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS 1099 Vendor Form Box Setup**, and then choose the related link.  
1. On the **IRS 1099 Vendor Form Box Setup** page, configure all necessary information and then choose the **Propagate** action for this vendor.
1. Choose how the new form box setup makes updates. You need to decide for which period you want to propagate this change and if you want to update existing opened purchase documents or vendor ledger entries, or both.
1. Close the page. Now you can continue with 1099 forms calculations.

## Create 1099 form documents

To create new 1099 form documents for the reporting years, follow these steps:  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
1. On the **IRS Reporting Periods** page, open the documents list, and then choose the **Documents** action.

   or

   Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS 1099 Form Documents**, and then choose the related link.
1. On the **IRS 1099 Form Documents** page, choose the **Create Forms** action to create IRS 1099 forms based on the filters you want to use:

   - Selecting the period is required. The other choices are optional.  
   - If you don't select a vendor, then form documents are created for all vendors.
   - If you don't select a certain form, then form documents are created for all forms.
   - If you don't select the option **Replace**, then only new form documents are created. If you select the option **Replace**, then the existing form documents are replaced.

1. In the created 1099 form’s documents list you can see the list of all created documents based on the combination of vendors and form numbers. From this list, you can open any of the created documents.  
1. Once you open the document, you can find the following information on the document header:  

   |  Field Name  |  Description  |  
   |--------|-----------------|  
   | **Vendor No.** | Specifies the vendor number.  |
   | **Form No.** | Specifies the form number used for calculation of this document. |
   | **ID** | Specifies the noneditable ID of the document.  |
   | **Status** | Specifies the status of the document. Created document has **Open** status, but status can also be **Released** (when user releases it) and **Submitted** (after submitting to the IRS). |
   | **Receiving 1099 E-Form Consent** | By selecting this field, you acknowledge that your vendor has provided signed consent to receive their 1099 form electronically. This field can't be changed on the form as this can be done only on the **Vendor Card** page. Only a 1099 form with this consent can be sent to a vendor via email. |
   | **Email** | Specifies the email where the form is sent if the vendor consented to electronically receive 1099 forms. If this vendor configured the **E-Mail For IRS** field, this value appears; if not, the standard **E-Mail** field from the **Vendor Card** page is used.  |
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
