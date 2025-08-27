---
title: Set up the IRS 1099 form for version 24 [US]
description: Learn how to set up the 1099 tax forms so that you can calculate and submit the required reports.
author: altotovi
ms.topic: how-to
ms.search.keywords: local, 1099, IRS, Tax
ms.search.form: 26, 10030, 10031, 10033, 10034
ms.date: 02/04/2025
ms.author: altotovi
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
---

# Set up the IRS 1099 forms

The Internal Revenue Service (IRS) requires one or more versions of the 1099 tax form for payments to vendors. Copies of these forms must be sent to vendors annually on or before the last day of January. On your purchase documents, you can specify that the document is 1099 liable, and you can specify the 1099 code for the vendor.

## Enable the feature to send tax data using the 1099 form

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Feature Management**, and then choose the related link.
1. Find **Feature Update: Enable using 1099 forms to transmit the tax data to the IRS in the United States**.
1. In the **Enabled for** column, choose **All Users**, and then choose **Yes** to confirm your choice.
1. Become familiar with the feature, and then choose the **Next** button.
1. Specify the relevant **Reporting Year**.
1. Define the setup data you use for IRS forms.
1. By selecting the **Create new setup** field, you can choose to create a new default setup data in an app.
1. To transfer the existing data from the 1099 base application, select the **Transfer Existing Data** field.  

   > [!NOTE]
   > If you’re setting up [!INCLUDE[prod_short](../../includes/prod_short.md)] for the first time, choose **Create New Setup** to create the forms and associated setups. Afterward, you can fill in the appropriate fields in the forms and print them. If you’re upgrading and already have data for your 1099 form, you can choose **Transfer Existing Data** from the previous solution.

1. Specify how the IRS forms work with documents, because you can decide to choose the **Collect Details For Line** field. If you select this field, details are collected from the **IRS 1099 Form Doc Line Details** page for each of **Calculated Amounts** in the **IRS 1099 Form Document**. This option requires extra space in the database.

> [!NOTE]
> If you don't select this field, the total amount is calculated without the details.

1. You can choose one or more options during setup.

   * **Protect TIN** (Taxpayer Identification Number) to mask or protect TIN for vendors or for both vendors and your company. You can also choose not to protect TIN numbers.

   > [!NOTE]
   > This protection option lets you print only the last four digits on your printing forms. The first five digits of the nine-digit number are truncated and replaced with Xs, following IRS regulations (example: XXXXX1234). This format provides more security when sending documents via email and helps protect the recipient from identity theft.  

 1. Finish the setup.

## Manual setup  

If you couldn't finish the setup when you enabled this feature, or you want to modify or add configurations, follow these steps:  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Forms Setup**, and then choose the related link.
1. On the **General** FastTab, you can change the setup for the **Collect Details For Line** and **Protect TIN** fields.  
1. You can also use the **Email Content Setup** action to set up the email you want to send to your recipients:

   * Change the subject on the **Email Subject** FastTab.  
   * Change the email body text in the **Email Body** FastTab.  

1. Close the page.

## Reporting periods and forms set up  

To configure reporting periods and forms, follow the steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
1. To specify the time period that the report applies to, enter dates in the **Starting** and **Ending Date** fields.
1. To set up specific 1099 forms for this period, use the **Forms** action to open the **IRS Reporting Forms** page. To learn more about the forms, go to [Types of IRS forms](introduction-to-the-irs-forms.md#types-of-irs-forms).
1. On the **IRS 1099 Forms** page, specify 1099 form types, such as MISC, NEC, and so on. Because these form types have more than one source with different rules, you must set them up. To do so, run the **Form Boxes** action to open the **IRS 1099 Form Boxes** page.
1. On the **IRS 1099 Form Boxes** page, set up sources for your form type using the **No.** and **Description** fields. You must fill in the **Minimum Reportable Amount** field based on the IRS instructions for this reporting year.
1. Close the **IRS 1099 Form Boxes** page.
1. Close the **IRS 1099 Forms** page.

> [!NOTE]
> Every year, you must create a new reporting period. We recommend that you use the **Copy Setup From** action on the **IRS Reporting Periods** page, and choose the reporting period you want to copy from. With this process, all forms, form boxes, vendor setup, adjustment and form statement, except the form documents are copied to the selected period.  

## Vendors setup  

On the **IRS Reporting Periods** page, you can run the **Vendor Setup** action to open the **IRS 1099 Vendor Form Box Setup** page. Use the page to map the form boxes to each vendor in the period. When you create a document for a vendor, [!INCLUDE [prod_short](../../includes/prod_short.md)] uses this setup to fill in the form boxes. To do so, follow the steps:

1. In the **Vendor No.** field, specify the vendor number.  
1. In the **Form No.** field, specify the vendor number.
1. In the **Form Box No.** field, specify the number of the 1099 form box.

You don't need to set up vendors manually, and you can use the **Suggest** action to run **IRS 1099 Suggest Vendors** automation. This action lets you choose different types of filters to apply to the vendors in the list. Afterward, you just need to add the default **Form No.** and **Form Box No.** for the list of vendors.  

By choosing the **IRS Setup** action in the **Related** menu, you can do the same setup on the **Vendor list** page.

> [!NOTE]
> This vendor setup is related to the specific period you configured on the **IRS Reporting Periods** page.  

You might need to do some more setup on the **Vendor Card** page. To do so, follow the steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
1. The fields related to 1099 reporting are on the **Payments** FastTab. You can find default values for the following fields, based on the **IRS 1099 Vendor Form Box Setup** configuration:

   * **IRS Reporting Period**
   * **IRS 1099 Form No.**
   * **IRS 1099 Form Box No.**

1. To configure more required information, you can:  

   * To confirm that your vendor provided signed consent to receive their 1099 form electronically using email, turn on the **Receiving 1099 E-Form Consent** toggle. To turn on this toggle, you must have an email address for the vendor in the **Email** field on the **Address & Contact** FastTab.
   * To use a different email address for IRS-related emails, you can enter the address in the **E-Mail For IRS** field. Otherwise, [!INCLUDE [prod_short](../../includes/prod_short.md)] uses the address in the **Email** field.  
   * If the vendor is set up to require FATCA filing, turn on the **FATCA Requirement** toggle.

## Print report configuration

To print the form substitute documents, you must have a few setups. A **Form Statement** is already configured for each form, but you can change or update them if needed. To do so, follow the steps:  

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

> [!NOTE]  
> For every form, you can set up the recipient instructions. These instructions are printed on the second page of the report layout. The IRS requires this for printing the form because the instructions explain the meaning of each form box.
>
> To do so, on the **IRS 1099 Forms** page, choose a form and then choose the **Edit instructions** action to open the **IRS 1099 Form Instructions** page. On the **IRS 1099 Form Instructions** page, fill in the **Header** (prints as a bold text) and **Description** (prints as regular text) fields.  

## Related information

[United States Local Functionality](united-states-local-functionality.md)  
[How to submit and report the IRS 1099](set-up-use-irs1099-form-v24.md#print-report-configuration)  
[Register New Vendors](../../purchasing-how-register-new-vendors.md)  
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
