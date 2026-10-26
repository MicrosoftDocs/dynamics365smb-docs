---
title: Set Up IRS 1099 Forms Reporting in Business Central
description: Learn how to set up IRS 1099 reporting periods, form boxes, vendor defaults, email consent, and printed vendor copies in Business Central.
author: altotovi
ms.topic: how-to
ms.search.keywords: local, 1099, IRS, Tax
ms.search.form: 26, 10030, 10031, 10033, 10034
ms.date: 10/19/2026
ai-usage: ai-assisted
ms.author: altotovi
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
---

# Set up IRS 1099 forms

Set up IRS 1099 forms in [!INCLUDE [prod_short](../../includes/prod_short.md)] to calculate reportable vendor payments and prepare forms for submission. Reporting periods, forms, form boxes, and vendor defaults determine which 1099 information is added to purchase documents. Confirm filing requirements and deadlines with the IRS or your tax adviser for the reporting year.

This article describes setup for the IRS Forms app. For the earlier workflow, go to [Set up and use the IRS 1099 form](set-up-use-irs1099-form.md).

## Set up IRS 1099 forms with the guide

Use **Set up IRS 1099 forms** on **Assisted Setup** to open the **IRS Forms Guide**. The guide creates reporting periods and their form setup for the reporting year.

> [!IMPORTANT]
> In earlier versions that require feature activation, first enable **Feature Update: Enable using 1099 forms to transmit the tax data to the IRS in the United States** on **Feature Management**. Those versions can offer **Create New Setup** and **Transfer Existing Data** in the guide. These toggles aren't available in the current guide. Migration options depend on your installed version; don't assume that every historical reporting year was transferred automatically.

When upgrading from the legacy workflow, review which reporting years were migrated before creating forms. The IRS Forms automatic upgrade targets eligible legacy data for 2025 and 2026, rather than every historical year. Review earlier years separately and confirm the migration options available in your installed version.

In older versions of the guide that show **Create New Setup** and **Transfer Existing Data**, choose **Create New Setup** for a new configuration. To migrate an existing configuration, choose **Transfer Existing Data**, review the affected data, and choose whether to use a background job before accepting the update.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Assisted Setup**, and then choose the related link.
1. Choose **Set up IRS 1099 forms**.
1. Become familiar with the feature, and then choose **Next**.
1. In the **Reporting Year** field, specify the year for which you want to include data.
1. Choose **Next**. To retain links to the vendor ledger entries behind calculated form amounts, turn on **Collect Details For Line**.
1. Optionally, use **Protect TIN** to mask taxpayer identification numbers on printed reports for vendors, or for both vendors and your company.
1. In **Business Name Control**, enter the control name your company registered in the IRS's National Account Profile (NAP) database.
1. Choose **Next**, and then **Finish**.

> [!NOTE]
> **Collect Details For Line** supports drill-down into calculated amounts, but requires additional database space. If you leave it off, the app still calculates totals without storing the individual entry details. **Protect TIN** retains the last four characters and adds a mask, such as `****-1234`. Masking helps protect identification numbers on printed or emailed copies. It doesn't change the identification numbers submitted electronically.

## Review general IRS setup

To review or change the general setup, follow these steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Forms Setup**, and then choose the related link.
1. On the **General** FastTab, you can change the setup for the **Collect Details For Line** and **Protect TIN** fields.  
1. On the **IRIS** FastTab, you can change the **Business Name Control**.
1. You can also use the **Email Content Setup** action to set up or edit the email you want to send to your recipients:

   * Change the subject on the **Email Subject** FastTab.  
   * Change the email body text in the **Email Body** FastTab.  

1. Close the page.

## Copy IRS reporting setup across companies

If you manage multiple companies, you can copy an IRS 1099 reporting period setup from one company to other companies. This helps ensure that IRS forms and form box configurations are consistent across all legal entities.

When you copy a setup, [!INCLUDE [prod_short](../../includes/prod_short.md)] copies forms, form boxes, vendor setup, form statements, and adjustment records to the destination period in the selected companies. Copied adjustment records have an amount of zero, so you must enter any adjustments needed for the new period.

Before copying, create the destination reporting period. Choose a destination that doesn't already contain form setup. The copy report requires consecutive reporting years.

1. Go to the **IRS Reporting Periods** page, select the period you want to copy from, and run the **Copy Setup** action.
1. In **From Period**, select the source reporting period.
1. In **To Period**, select the destination reporting period.
1. Select the companies to which you want to copy the setup in the **Companies** field.
1. Select **OK** to run the report.

After the report runs, the selected companies use the same IRS 1099 forms and form box setup as the source reporting period.

## Set up reporting periods and 1099 forms

To configure reporting periods and forms, follow the steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS Reporting Periods**, and then choose the related link.  
1. Enter a period number, and then specify the **Starting Date** and **Ending Date**.
1. To set up specific 1099 forms for this period, use the **Forms** action to open the **IRS 1099 Forms** page. To learn more about the forms, go to [Types of IRS forms](introduction-to-the-irs-forms.md#types-of-irs-forms).
1. On the **IRS 1099 Forms** page, specify form types, such as MISC or NEC. For each form, choose **Form Boxes** to open **IRS 1099 Form Boxes**.
1. On the **IRS 1099 Form Boxes** page, set up sources for your form type using the **No.** and **Description** fields. You must fill in the **Minimum Reportable Amount** field based on the IRS instructions for the reporting year.
1. Close the **IRS 1099 Form Boxes** page.
1. Close the **IRS 1099 Forms** page.

For IRIS submission, use the four-digit reporting year as the period number.

> [!TIP]
> Create a reporting period for each year. Use **Copy Setup** on **IRS Reporting Periods** to reuse the previous year's setup. Review the copied form boxes and enter new adjustment amounts before creating form documents.

## Set up 1099 reporting for vendors

On the **IRS Reporting Periods** page, you can run the **Vendor Setup** action to open the **IRS 1099 Vendor Form Box Setup** page. Use the page to map the form boxes to each vendor in the period. When you create a document for a vendor, [!INCLUDE [prod_short](../../includes/prod_short.md)] uses this setup to fill in the form boxes. To do so, follow the steps:

1. In the **Vendor No.** field, choose the vendor.  
1. In the **Form No.** field, specify the type of 1099 form.
1. In the **Form Box No.** field, specify the number of the 1099 form box that payments should go to.

You don't need to set up vendors manually, and you can use the **Suggest** action to run **IRS 1099 Suggest Vendors** automation. This action lets you choose different types of filters to apply to the vendors in the list. Afterward, you just need to add the default **Form No.** and **Form Box No.** for the list of vendors.  

> [!NOTE]
> This vendor setup is related to the specific period you configured on the **IRS Reporting Periods** page.  

You can also open **IRS 1099 Vendor Form Box Setup** from **Vendors** or **Vendor Card** by choosing **IRS 1099 Setup**.

You might need to do some more setup on the **Vendor Card** page. To do so, follow the steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
1. On the **Vendor Card** page, the fields related to 1099 reporting are on the **Payments** FastTab. The fields contain default values from the **IRS 1099 Vendor Form Box Setup** configuration:

   * **IRS Reporting Period**
   * **IRS 1099 Form No.**
   * **IRS 1099 Form Box No.**

1. To confirm that your vendor provided signed consent to receive their 1099 form electronically using email, turn on **Receiving 1099 E-Form Consent**. First provide an address in either **E-Mail For IRS** or **Email**.
1. To use a different email address for IRS-related emails, you can enter the address in the **E-Mail For IRS** field on the **Payments** FastTab. Otherwise, [!INCLUDE [prod_short](../../includes/prod_short.md)] uses the address in the **Email** field on the **Address & Contact** FastTab.
1. If the vendor is set up to require FATCA filing, turn on the **FATCA Requirement** toggle.

Before you send an IRIS transmission, review the company and vendor taxpayer identification numbers, company contact name and telephone number, and address details. The system validates these values before sending. If multiple vendors share a taxpayer identification number within the same form type, each vendor must have a **Preferred Bank Account Code** that points to a unique **Bank Account No.**

## Create 1099 form documents

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **IRS 1099 Form Documents**, and then choose the related link.
1. Select **Create Forms**.
1. In the **Period** field, select the reporting period.
1. Fill in the remaining fields as necessary, and then select **OK**. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

For calculation details and document review, go to [Use the IRS 1099 forms](how-to-1099-use.md).

## Print report configuration

To print the form substitute documents, there are a few things to set up. A **Form Statement** is already configured for each form, but you can change or update them if needed. To do so, follow the steps:  

1. To configure or customize the printed form, choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter the **IRS Reporting Periods**, and then choose the related link.
1. Use the **Forms** action to open the **IRS 1099 Forms** page.
1. Choose the form, and then choose the **Edit Statement** action.  
1. On the **IRS 1099 Form Statement** page, you can set up filters and rules that apply to the form document lines when you print. You can use the following fields to set up the 1099 form statement:  

   * **Row No.**: Specifies a number that identifies the line. The number is used as a form box number on the printed report.
   * **Description**: Specifies a description of the 1099 form box on the printed report.
   * **Print Value Type**: Specifies the print value type of the statement. If you select **Amount**, the report prints the amount calculated by the filter expression. If you select **Yes/No**, the report prints either **Yes** or **No** based on the condition.
   * **Filter Expression**: Specifies the filter expression of the statement.
   * **Row Totaling**: Specifies a row-number interval or a series of row numbers.
   * **Print with**: Specifies whether amounts on the 1099 form box are printed with their original sign using **Sign** or with the sign reversed using **Opposite Sign**.

1. Close the page.
1. On the **IRS 1099 Forms** page, select a form, and then select **Edit Instructions** to open **IRS 1099 Form Instructions**. Fill in **Header** for bold text and **Description** for regular text.

> [!NOTE]  
> Instructions explain the purpose of each box for recipients. In the standard report layout, recipient instructions start on the second page. Confirm the required wording with the IRS for the reporting year.

## Related information

- [United States local functionality](united-states-local-functionality.md)
- [Submit and report the IRS 1099 forms](how-to-1099-report.md)
- [Register new vendors](../../purchasing-how-register-new-vendors.md)
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
