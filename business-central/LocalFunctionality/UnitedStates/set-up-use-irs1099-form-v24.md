---
title: Set up IRS 1099 forms
description: Learn how to set up the 1099 tax forms so that you can calculate and submit the required reports.
author: altotovi
ms.topic: how-to
ms.search.keywords: local, 1099, IRS, Tax
ms.search.form: 26, 10030, 10031, 10033, 10034
ms.date: 08/28/2025
ms.author: altotovi
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
---

# Set up IRS 1099 forms

The Internal Revenue Service (IRS) requires businesses to fill in and submit one or more versions of the 1099 tax form for payments to vendors. You must send copies of these forms to vendors annually, on or before the last day of January. On your purchase documents, you can specify that the document is 1099 liable, and you can specify the 1099 code to use for the vendor.

This article describes how to enable the features related to 1099 forms.

## Enable the feature to send tax data using the 1099 form

To use 1099 forms in [!INCLUDE [prod_short](../../includes/prod_short.md)], you must enable **Feature Update: Enable using 1099 forms to transmit the tax data to the IRS in the United States**. When you do, you can use the **IRS Forms Guide** to set up the basics for 1099 forms. The following steps describe the settings in the guide.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Feature Management**, and then choose the related link.
1. Find **Feature Update: Enable using 1099 forms to transmit the tax data to the IRS in the United States**.
1. In the **Enabled for** column, choose **All Users**, and then choose **Yes** to confirm your choice.
1. Become familiar with the feature, and then choose **Next**.
1. In the **Reporting Year** field, specify the year for which you want to include data.
1. Depending on whether you're setting up 1099 features for the first time or already have the required setups, for example, if you're upgrading, turn on one of the following toggles:

   1. If you’re setting up 1099 forms for the first time, turn on the **Create New Setup** toggle, and then continue with the steps in the guide.
   1. If you already have data for your 1099 form, for example, if you're upgrading to the latest version, turn on the **Transfer Existing Data** toggle. On the next step in the guide, you can specify whether to use a background job to transfer your data, and accept the data update. After that, you can review and edit, if needed, the settings described in the next steps.

1. To collect details from vendor ledger entries, such as amounts, from the **IRS 1099 Form Doc Line Details** page for each calculated amount on the IRS 1099 form document, turn on the **Collect Details For Line** toggle.

   > [!NOTE]
   > Collecting details about vendor ledger entries is helpful for reviewing amounts, but it can take up space in your database. If you don't turn on the toggle, the total amount is calculated without listing each amount from the the vendor ledger entries.

1. Optionally, in the **Protect TIN** field, specify whether to mask the taxpayer identification number (TIN) for vendors, or for both vendors and your company. You can also choose not to protect TIN numbers.

   > [!NOTE]
   > These options let you print only the last four digits on your printing forms. The first five digits of the nine-digit number are truncated and replaced with Xs, following IRS regulations (example: XXXXX1234). This format provides more security when sending documents via email and helps protect the recipient from identity theft.  

 1. In the **Business Name Control** field, enter the control name your company registered in the IRS's National Account Profile (NAP) database.
 1. Finish the guide.

## Manual setup  

If you couldn't finish the setup when you enabled this feature, or you want to edit or add configurations, follow these steps:  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Forms Setup**, and then choose the related link.
1. On the **General** FastTab, you can change the setup for the **Collect Details For Line** and **Protect TIN** fields.  
1. On the **IRIS** FastTab, you can change the **Business Name Control**.
1. You can also use the **Email Content Setup** action to set up or edit the email you want to send to your recipients:

   * Change the subject on the **Email Subject** FastTab.  
   * Change the email body text in the **Email Body** FastTab.  

1. Close the page.

## Set up reporting periods and 1099 forms

To configure reporting periods and forms, follow the steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
1. To specify the time period that the report applies to, enter dates in the **Starting** and **Ending Date** fields.
1. To set up specific 1099 forms for this period, use the **Forms** action to open the **IRS 1099 Forms** page. To learn more about the forms, go to [Types of IRS forms](introduction-to-the-irs-forms.md#types-of-irs-forms).
1. On the **IRS 1099 Forms** page, specify 1099 form types, such as MISC, NEC, and so on. Because these form types have more than one source with different rules, you must set them up. To do so, run the **Form Boxes** action to open the **IRS 1099 Form Boxes** page.
1. On the **IRS 1099 Form Boxes** page, set up sources for your form type using the **No.** and **Description** fields. You must fill in the **Minimum Reportable Amount** field based on the IRS instructions for the reporting year.
1. Close the **IRS 1099 Form Boxes** page.
1. Close the **IRS 1099 Forms** page.

> [!TIP]
> You must create a new reporting period for each year. The **Copy Setup From** action on the **IRS Reporting Periods** page makes that easy to do. Just choose the reporting period you want to copy from, and [!INCLUDE [prod_short](../../includes/prod_short.md)] copies all forms, form boxes, vendor setup, adjustment, and form statement to the selected period.

## Set up 1099 reporting for vendors

On the **IRS Reporting Periods** page, you can run the **Vendor Setup** action to open the **IRS 1099 Vendor Form Box Setup** page. Use the page to map the form boxes to each vendor in the period. When you create a document for a vendor, [!INCLUDE [prod_short](../../includes/prod_short.md)] uses this setup to fill in the form boxes. To do so, follow the steps:

1. In the **Vendor No.** field, choose the vendor.  
1. In the **Form No.** field, specify the type of 1099 form.
1. In the **Form Box No.** field, specify the number of the 1099 form box that payments should go to.

You don't need to set up vendors manually, and you can use the **Suggest** action to run **IRS 1099 Suggest Vendors** automation. This action lets you choose different types of filters to apply to the vendors in the list. Afterward, you just need to add the default **Form No.** and **Form Box No.** for the list of vendors.  

> [!NOTE]
> This vendor setup is related to the specific period you configured on the **IRS Reporting Periods** page.  

You can also set this up from the **Vendor list** page by choosing the **IRS Setup** action.

You might need to do some more setup on the **Vendor Card** page. To do so, follow the steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
1. On the **Vendor Card** page, the fields related to 1099 reporting are on the **Payments** FastTab. The fields contain default values from the **IRS 1099 Vendor Form Box Setup** configuration:

   * **IRS Reporting Period**
   * **IRS 1099 Form No.**
   * **IRS 1099 Form Box No.**

1. To confirm that your vendor provided signed consent to receive their 1099 form electronically using email, turn on the **Receiving 1099 E-Form Consent** toggle. To turn on this toggle, you must have an email address for the vendor in the **Email** field on the **Address & Contact** FastTab.
1. To use a different email address for IRS-related emails, you can enter the address in the **E-Mail For IRS** field on the **Payments** FastTab. Otherwise, [!INCLUDE [prod_short](../../includes/prod_short.md)] uses the address in the **Email** field on the **Address & Contact** FastTab.
1. If the vendor is set up to require FATCA filing, turn on the **FATCA Requirement** toggle.

## Create 1099 form documents

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **IRS 1099 Form Documents**, and then choose the related link.
1. In the **Period** field, select the reporting period.
1. Fill in the remaining fields as necessary. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

## Print report configuration

To print the form substitute documents, there are a few things to set up. A **Form Statement** is already configured for each form, but you can change or update them if needed. To do so, follow the steps:  

1. To configure or customize the printed form, choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter the **IRS Reporting Periods**, and then choose the related link.
1. Use the **Forms** action to open the **IRS 1099 Forms** page.
1. Choose the form, and then choose the **Edit Statement** action.  
1. On the **IRS 1099 Form Statement** page, you can set up filters and rules that apply to the form document lines when you print. You can use the following fields to set up the 1099 form statement:  

   * **Row No.** – Specifies a number that identifies the line. The number is used as a form box number on the printed report.  
   * **Description** – Specifies a description of the 1099 form box on the printed report.  
   * **Print Value Type** – Specifies the print value type of the statement. If **Amount** is selected, the amount calculated by the filter expression is printed. If the **Yes/No** option is selected, then either **Yes** or **No** is printed based on the **Yes/No** condition.
   * **Filter Expressions** - Specifies the filter expression of the statement.
   * **Row Totaling** – Specifies a row-number interval or a series of row numbers.  
   * **Print with** – Specifies whether amounts on the 1099 form box are printed with their original sign using the option **Sign** or with the sign reversed using the option **Opposite Sign**.

1. Close the page.
1. On the **IRS 1099 Forms** page, choose a form, and then choose the **Edit instructions** action to open the **IRS 1099 Form Instructions** page. On the **IRS 1099 Form Instructions** page, fill in the **Header** (prints as a bold text) and **Description** (prints as regular text) fields.

> [!NOTE]  
> Instructions explain the purpose of each box for recipients. Instructions print on the second page of the report layout. The IRS requires instructions.

## Related information

[United States Local Functionality](united-states-local-functionality.md)  
[How to submit and report the IRS 1099](set-up-use-irs1099-form-v24.md#print-report-configuration)  
[Register New Vendors](../../purchasing-how-register-new-vendors.md)  
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
