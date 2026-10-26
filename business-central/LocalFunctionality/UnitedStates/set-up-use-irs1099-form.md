---
title: Legacy IRS 1099 Forms Setup and Reporting [US]
description: Learn how to use legacy IRS 1099 form boxes, vendor defaults, posted-entry corrections, printed reports, and magnetic media exports.
author: altotovi
ms.topic: how-to
ms.search.keywords: local, 1099
ms.search.form: 26, 29, 50, 51, 10015, 10016, 10018, 10900
ms.date: 10/19/2026
ai-usage: ai-assisted
ms.author: altotovi
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
---

# Set up and use the IRS 1099 form

> [!IMPORTANT]
> This article describes the legacy IRS 1099 workflow, not the IRS Forms app. The replacement was introduced as a feature update in version 24.0 and automatically enabled in version 27.0. For the replacement workflow, go to [Introduction to the IRS 1099 tax forms](introduction-to-the-irs-forms.md). The legacy procedures below apply to versions where that workflow is still available.

Use the legacy IRS 1099 workflow in [!INCLUDE[prod_short](../../includes/prod_short.md)] to identify reportable vendor payments, print forms, or export filing data. Confirm filing requirements and deadlines with the IRS or your tax adviser for the reporting year.

## Set up legacy 1099 reporting

Before you start using [!INCLUDE[prod_short](../../includes/prod_short.md)], you must set up **1099 Form Boxes** and **Vendors** as 1099 liable. The most common 1099 codes are already set up for you, and they're defined on the **1099 Form Box** page, where you can also add new 1099 codes. Before you prepare your reporting for the new year, you must first update your [!INCLUDE[prod_short](../../includes/prod_short.md)] to handle the new requirements.

### Update the 1099 form boxes

To support form changes, the legacy workflow offers **Update Form Boxes** to update codes and other requirements. For historical changes, go to [Regulatory 1099 format changes and details](tax-1099-changes.md).

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1099 Form Boxes**, and then choose the related link.
1. Choose the **Update Form Boxes** action.  

> [!NOTE]
> Don't fill out the 1099 form boxes manually. Instead, select **Update Form Boxes**.

> [!IMPORTANT]
> Running the action **Update Form Boxes** makes reporting for the previous year impossible, since some boxes change their meaning. Make sure that you have done all your reporting for the previous year before you update the form boxes to prepare your system for reporting for the new year.

### Set up a vendor as 1099 liable

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
1. Open the relevant vendor's card.
1. On the **Payments** FastTab, in the **IRS 1099 Code** field, choose the relevant IRS 1099 code.
1. Repeat these steps for each additional vendor.

## Documents and entries

### Process a document as 1099 liable

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoice**, and then choose the related link.
1. Create a new entry, and then, in the **Vendor Name** field on the **Purchase Invoice** header, specify a vendor with the relevant IRS 1099 code.
1. Optionally, on the **Shipping and Payment** FastTab, in the **IRS 1099 Code** field, override the default value with another code, or delete it to have transaction without an IRS 1099 code.

1. Enter all information into the required fields for purchase invoice and post the document. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

The **IRS 1099 Code** field is prepopulated with the value from the vendor card.

After the document is posted, you can go to the **Vendor Ledger Entries** list page and find that the **IRS 1099 Code** and **IRS 1099 Amount** fields are automatically populated.  

> [!TIP]
> Instead of a purchase invoice, you can also use a purchase order as the document, but in this case, the **IRS 1099 Code** field will be on the **Invoice Details** FastTab.

### Correct posted entries

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
1. Open the relevant vendor's card.
1. On the **Vendor Card** page, choose the **Ledger Entries** action to open the **Vendor Ledger Entries** page. Here, you can review a list of all transactions for your vendor.  
1. Locate the entry that you want to correct.  
1. If you want to change the IRS code, find the **IRS 1099 Code** field, and then change the code for the relevant entry.  
1. If you want to change the amount, find the **IRS 1099 Amount** field, and then update the existing amount.  

## Report legacy 1099 amounts

### Find the IRS 1099 statistics

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
1. Open the relevant vendor's card.
1. On the **Vendor Card** page, choose the **1099 Statistics** action to open the **Vendor 1099 Statistics** page.

### Review IRS 1099 amounts for a specific vendor

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
1. Open the relevant vendor's card.
1. On the **Vendor Card** page, choose the **Vendor 1099 Information** action to open the **Vendor 1099 Information** report.  
1. Set filters for vendor number and date, and then choose to print or preview the report.

### Print the 1099 tax forms

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1099 Form Boxes**, and then choose the related link.
1. On the **1099 Form Boxes** page, choose the **Reports** action, and then choose one of vendor 1099 reports for printing:

   - **Vendor 1099 Div** - Prints the federal form 1099-DIV for dividends and distribution. You can print all or specific 1099-DIV forms. The report uses the codes that apply to the DIV form amount boxes from the **1099 Form Boxes** page.
   - **Vendor 1099 Int** - Prints the federal form 1099-INT for interest income. You can print all or specific 1099-INT forms. The report uses the codes that apply to the INT form amount boxes from the **1099 Form Boxes** page.
   - **Vendor 1099 Misc** - Prints the federal form 1099-MISC for miscellaneous income. You can print all or specific 1099-MISC forms. The report uses the codes that apply to the MISC form amount boxes from the **1099 Form Boxes** page.
   - **Vendor 1099 Nec** – Prints the federal form 1099-NEC for nonemployee compensation. You can print all or specific 1099-NEC forms. The report uses the codes that apply to the NEC form amount boxes from the **1099 Form Boxes** page.

> [!NOTE]
> Regulatory changes affecting this report and the table data are handled in end-of-year updates. For more information, see [Regulatory 1099 Form Box Changes](tax-1099-changes.md).

### Submit the 1099 tax forms electronically

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1099 Form Boxes**, and then choose the related link.
1. On the **1099 Form Boxes** page, choose the **Vendor 1099 Magnetic Media** action.
1. Specify the 1099 forms to export.

The report uses the codes that apply to the form amount boxes from the **1099 Form Boxes** page. The codes are mapped to the form boxes in the file layouts of this report, therefore the table data, and report version for a particular tax year must be in agreement. If any custom codes are added to the table, these codes must be mapped to the form boxes inside this object.

> [!NOTE]
> - The form information exported by this report is the same as the reports that print 1099 forms that are described in the previous section.
>
> - Regulatory changes affecting this report and the table data are handled in end-of-year updates.

## Related information

- [Regulatory 1099 Format Changes and Details](tax-1099-changes.md)  
- [United States Local Functionality](united-states-local-functionality.md)  
- [Register New Vendors](../../purchasing-how-register-new-vendors.md)  
- [Record Purchase](../../purchasing-how-record-purchases.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
