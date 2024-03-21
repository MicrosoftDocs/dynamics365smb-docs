---
title: Track data and use the IRS 1099 Form [US]
description: Learn how to post document to calculate and report the 1099 tax forms so that you can submit the required reports.
author: altotovi

ms.topic: conceptual
ms.search.keywords: local, 1099, tax, taxes, IRS
ms.search.form: 50, 51, 132, 10036, 10037, 10049
ms.date: 03/21/2024
ms.author: altotovi
ms.reviewer: 

ms.service: dynamics-365-business-central
---

# Use the IRS 1099 Forms in the US Version  

[!INCLUDE[prod_short](../../includes/prod_short.md)] will calculate 1099 forms only for vendors where the **Purchase Invoice** had information about **IRS 1099 Form No.** and **IRS 1099 Form Box No.** on the document header and if the payment is posted and applied to this invoice.  

## Working with purchase documents  

To have all IRS related fields applied to the purchase document, this document must be in the date range, IRS reporting periods and vendors are configured. You need to [create the purchase document](../../purchasing-how-record-purchases.md) and check if the **IRS Reporting Period**, **IRS 1099 Form No.** and **IRS 1099 Form Box No.** fields are populated in the **Shipping and Payment** FastTab. These fields will be prepopulated with default values from the **Vendor** card. You can change these values if this specific document should comply with different 1099 form.  

> [!IMPORTANT]
> If the **Posting Date** of the document is not withing the reporting period date, the IRS fields will be disabled.  

> [!NOTE]
> If you do not see populated IRS fields and you expect values there, check if this document is in the data range you have configured IRS reporting, and also check if you created **IRS Reporting Period** for this year, and if you added this **Vendor** to be 1099 eligible for this reporting year.  

When you [post this purchase document](../../purchasing-how-record-purchases.md), you can see the following fields populated in the (../../purchasing-how-record-purchases.md) related with this posted document: 

- IRS 1099 Reporting Period
- IRS 1099 Form No.
- IRS 1099 Form Box No.
- IRS 1099 Reporting Amount

If you made a mistake and didn’t use **IRS 1099 Form No.** and **IRS 1099 Form Box No.** on the document, or you used the wrong one, you can make corrections. To do this, in the **Vendor Ledger Entries** position the line you want to correct and then you can run the **Edit List** action and change the **IRS 1099 Form Box No.** and **IRS 1099 Reporting Amount** fields. 

All 1099 forms calculation are based on this information in the Vendor Ledger Entries. But make sure that the payment is posted applied to the invoice in the same reporting period.  

## Pre-calculation  

### Amounts Adjustments 

If you have some inaccurate information in the system or missed some document for any of reasons, you can manually adjust values before running calculation. To do so, you need to fillow next steps: 

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
2. When you opened the **IRS Reporting Periods** page, run the **Adjustments** action to open the **IRS 1099 Vendor Form Box Adjustments** page.  
3. You can add here the amount of adjustment to the IRS reporting amount, using information about **Vendor No.**, **Form No.**, **Form Box No.**, and the **Adjustment Amount**.
4. Close pages.

### Vendor Corrections 

If you didn’t configure the vendor properly as you forgot to add specific **Form No.** or **Form Box No.** and already posted documents and/or payments, you can still make corrections. To do this, you need to follow next steps:  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS 1099 Vendor Form Box Setup**, and then choose the related link.  
2. When you open the **IRS 1099 Vendor Form Box Setup** page, you need to configure all necessary information there and to run the **Propagate** action for this vendor.   
3. Running this action, you can choose how the new form box setup will make update. You need to decide for which period you want to propagate this change and if you want to update existing opened purchase documents or vendor ledger entries, or both. 
4. Close the page.   
5. After execution, you can continue with 1099 forms calculations. 

## Create 1099 Form Documents 

To create new 1099 form documents for the reporting years, you need to follow next steps:  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
2. From the **IRS Reporting Periods** page open the documents list running the **Documents** action, or choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS 1009 Form Documents**, and then choose the related link. 
3. From the **IRS 1009 Form Documents** page, you can run the **Create Forms** action to create IRS 1099 forms based on the filters you want to use:   

   - It is required to select the period. The other options are optional.  
   - If you do not select a vendor, then form documents will be created for all vendors. 
   - If you do not select a certain form, then form documents will be created for all forms. 
   - If you do not select an option **Replace** than only new form documents will be created. If you select an option **Replace** than the existing form documents will be replaced. 

4. In the created 1099 form’s documents list you can see the list of all created documents based combination of vendors and form numbers. From this list you can open each of created documents.  
5. Once you open the document, you can find the following information for the document header:  

|  Field Name  |  Description  |  
|--------|-----------------|  
| **Vendor No.** | Specifies the vendor number.  |
| **Form No.** | Specifies the form number used for calculation of this document. |
| **ID** | Specifies the non-editable ID of the document.  |
| **Status** | Specifies the status of the document. Created document has **Open** status, but status can also be **Released** (when user release it) and **Submitted** (after submitting to the IRS). |
| **Receiving 1099 E-Form Consent** | By selecting this field, you acknowledge that your vendor has provided signed consent to receive their 1099 form electronically. This field cannot be changed at the form as this can be done only on the **Vendor** card page. Only 1099 form with this consent can be sent to vendor via email. |
| **Email** | Specifies the e-mail where the form will be sent if the vendor gave the consent for electronically receiving 1099 forms. If this vendor has configured the **E-Mail For IRS** field this value will appear, but if not, the standard **E-Mail** field from the **Vendor** card will be used.  |
| **Copy B Sent** | Specifies if this form copy has been sent. This field will be marked automatically and cannt be edited.  |
| **Copy C Sent** | Specifies if this form copy has been sent. This field will be marked automatically and cannt be edited.  |

6. The lines in documents have the following information:  

|  Field Name  |  Description  |  
|--------|---------------------|
| **Form Box No.** | Specifies the number of the 1099 form box used in this line.   |
| **Calculated Amount** | Specifies the amount per period and IRS code calculated by the **Create Forms** action on the list page. This amount is taken from vendor ledger entries. If you enable the **Collect Details For Line** option then you can drill down this field to see the connected entries. This value cannot be changed. |
| **Adjustment Amount** | Specifies the calculated adjustment amount of the document line, the amount you specified for the period, vendor, and form box. You can drill down to see your setup. This amount cannot be changed manually. |
| **Amount** | Specifies the amount of the document line. The sum of calculated amount and adjustment amount. This value is used for reporting and this amount can be changed manually.  |
| **Minimum Reportable Amount** | The threshold to decide whether the certain form box with the reporting amount must be reported or not.   |
| **Include in 1099** | Specifies if the document line should be included in the 1099. The line is included in 1099 if the amount is more than or equal to the minimum reportable amount. |

7. Close the page.  

## See also 

[United States Local Functionality](united-states-local-functionality.md)  
[How to setup the IRS 1099 forms](how-to-1099-setup.md)
[How to submit and report the IRS 1099](how-to-1099-report.md)
[Register New Vendors](../../purchasing-how-register-new-vendors.md)  
[Record Purchase](../../purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
