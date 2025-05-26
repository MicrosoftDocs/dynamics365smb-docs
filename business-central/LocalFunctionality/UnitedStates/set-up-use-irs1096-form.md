---
title: Set up and use the IRS 1096 form [US]
description: Learn how to set up the 1096 tax form boxes so that you can submit the required reports.
author: altotovi
ms.topic: how-to
ms.search.keywords: local, 1096, IRS
ms.search.form: 10019, 10020, 10021
ms.date: 02/04/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up and use the IRS 1096 form in the US version

Form 1096 is used to transmit paper tax forms to the Internal Revenue Service (IRS) in the United States. This feature lets you run the Form 1096 report in [!INCLUDE[prod_short](../../includes/prod_short.md)] and send it to the IRS, if necessary. The feature is only related to already transmitted paper 1099 forms.

> [!NOTE]
> Form 1096 reporting supports only the IRS codes that are supported for Form 1099 reporting in [!INCLUDE[prod_short](../../includes/prod_short.md)]. If you add other IRS codes to lines on the Form 1096, the report doesn't include them.
> [!IMPORTANT]
> The IRS 1096 feature is compatible only with the [legacy 1099 functionality](set-up-use-irs1099-form.md), which lets you submit printed 1099 forms. The [new IRS 1099 feature](set-up-use-irs1099-form-v24.md) supports only electronic submissions, and not printed forms, so the 1096 form isn't required and this feature isn't compatible with the IRS 1099 feature.

## Enable the extension

Form 1096 is an extension. After you install the extension in your environment you must enable it, as described in the following steps.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Feature management**, and then choose the related link.
1. Find **Feature: Enable using Form 1096 to transmit paper Tax Forms to the IRS in the United States** and in the **Enabled for** field, choose **All Users**.
1. When you enable the feature, use the setup guide to set it up. The only information required is to specify the **IRS 1096 Form No. Series** to use. This number series is used to assign numbers for 1096 forms per certain period.

If you didn't use the setup guide to configure **IRS 1096 Form No. Series**, you can do so on the **Purchases & Payables Setup** page. Fill in the **IRS 1096 Form No. Series** field on the **Number Series** FastTab.

Complete the following steps to set up more required fields for reporting.

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then select the related link.
1. To specify the EIN number to show on the report, on the **Communication** FastTab in the **EIN Number** field, enter the number you registered with IRS.  
1. To specify who communicates with the IRS, in the **IRS Contact No.** field, select the employee responsible for this communication.  

## Create a new 1096 form

> [!NOTE]
> The IRS 1096 report layout currently supports reporting for the year 2023.  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1096 Forms**, and then choose the related link.
1. Choose the **Create forms…** action to create a new entry.
1. In the **Starting Date** and **Ending Date** fields, specify a date range for the calculations. Vendor ledger entries with posting dates in this period are considered.
1. If you want to replace existing forms with new forms, for example, if you made corrections, choose the **Replace** option. If you don't select this option, new forms are created and existing forms remain the same.
1. After you create the new forms, choose **OK**. A confirmation displays the message, **IRS 1096 forms have been created**.

> [!NOTE]
> [!INCLUDE [prod_short](../../includes/prod_short.md)] automatically creates a 1096 form for each of the IRS codes posted in vendor ledger entries during the period you defined.

You can open the forms to review and correct them if necessary.

The **General** FastTab contains the following information.

- **Starting Date** - Specifies the starting date of the period specified for the form.
- **Ending Date** - Specifies the ending date of the period specified for the form.
- **Status** - Specifies the status of the form. Only released forms can be printed. Only opened forms can be changed.
- **IRS Code** - Specifies the IRS code of the form.
- **Calculated Total Number of Forms** - Specifies the total number of forms per period and IRS code calculated by the **Create Forms** action. You can't change this value.
- **Total Number of Forms** - Specifies the number of forms used for printing the form. This value matches the calculated number of forms after you choose the **Create Forms** action. You can change this value.
- **Calculated Amount** - Specifies the amount per period and IRS code calculated by the **Create Forms** action. You can't change this value.
- **Calculated Adjustment Amount** - Specifies the adjustment amount per period and IRS code calculated by the **Create Forms** action.
- **Total Amount to Report** - Specifies the adjustment amount per period and IRS code calculated by the **Create Forms** action.

The lines contain the following information. Amounts are summarized per **Vendors** and **IRS Codes**.

- **IRS Code** - Specifies the IRS code.
- **Vendor no.** - Specifies the vendor number.
- **Calculated Amount** - Specifies the amount per period and IRS code calculated by the **Create Forms** action. You can't change this value. You can check amounts in the **Vendor Ledger Entries** field for each record.
- **Calculated Adjustment Amount** - Specifies the adjustment amount per period and IRS code calculated by the **Create Forms** action. You can check amounts in the **IRS 1099 Adjustments** field for each record.
- **Manually changed** - Specifies that the line was changed manually. This field is marked automatically if a record is changed manually.
- **Amount** - Specifies the amount used for printing the form. This value matches the calculated amount minus the calculated adjustment amount after choosing the **Create Forms** action. You can change this value. If you change this amount manually, the **Manually changed** field is marked.

## Make corrections in a 1096 form

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1096 Forms**, and then choose the related link.
1. Open the form you want to edit.
1. If you want to update an amount:

   - Locate the line you want to update and mark the **Amount** field.
   - Enter the value you want to report. The **Manually changed** field is marked and the **Total Amount to Report** field on the header is updated.

1. If you want to add a new record, enter a new line, and fill in values you need for reporting in the **IRS Code**, **Vendor no.**, and **Amount** fields. The **Total Amount to Report** field on the header are updated.
1. In both of situations, when you make a change in the **1096 Form**, [!INCLUDE [prod_short](../../includes/prod_short.md)] automatically fills in the following fields on the **History** FastTab:

   - **Changed By** - Specifies the ID of the last user who changed the form.
   - **Changed Date-Time** - Specifies the date and time when the last change was made in the form.

## Print the 1096 form

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1096 Forms**, and then choose the related link.
1. Open the form you want to print.
1. If the status is **Open**, choose **Release** action to release the form and make it ready for printing.
1. Choose **Print** actions to print the single form.
1. If you didn't add the **IRS Contact No.** in the **Company Information**, enter details about the **Person to contact** on the request page, and then select **Print**.
1. After you print, the following fields at the **History** FastTab are updated:

    - **Printed by** - Specifies the ID of the last user who printed the form.
    - **Printed Date-Time** - Specifies the date and time of the last time that the form was printed.
    - **Printed** - Specifies that the form was printed.

## Related information

- [Set Up and Use the IRS 1099 Form](set-up-use-irs1099-form.md)  
- [United States Local Functionality](united-states-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
