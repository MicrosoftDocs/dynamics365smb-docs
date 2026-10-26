---
title: IRS 1096 Forms Setup and Reporting [US]
description: Learn how to configure IRS 1096 form numbering, review and correct legacy form amounts, release forms, and print reports in Business Central.
author: altotovi
ms.topic: how-to
ms.search.keywords: local, 1096, IRS
ms.search.form: 10019, 10020, 10021
ms.date: 10/19/2026
ai-usage: ai-assisted
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Set up and use the IRS 1096 form in the US version

Form 1096 is used to transmit paper tax forms to the Internal Revenue Service (IRS) in the United States. This feature lets you run the Form 1096 report in [!INCLUDE[prod_short](../../includes/prod_short.md)] and send it to the IRS, if necessary. The feature is only related to already transmitted paper 1099 forms.

> [!NOTE]
> Form 1096 reporting supports only the IRS codes that are supported for Form 1099 reporting in [!INCLUDE[prod_short](../../includes/prod_short.md)]. If you add other IRS codes to lines on the Form 1096, the report doesn't include them.

> [!IMPORTANT]
> This article describes the IRS 1096 workflow that accompanies the [legacy 1099 functionality](set-up-use-irs1099-form.md). Don't use these steps for the [IRS Forms electronic filing workflow](set-up-use-irs1099-form-v24.md). IRS Forms can print substitute vendor copies, but those copies aren't preprinted forms for paper submission to the IRS.

## Set up the extension

Form 1096 is an extension. If your version requires activation, enable **Feature: Enable using Form 1096 to transmit paper Tax Forms to the IRS in the United States** for **All Users** on **Feature Management**. If the extension is already enabled, continue with setup.

Use the setup guide to specify **IRS 1096 Form No. Series**, or open **Purchases & Payables Setup** and fill in that field on the **Number Series** FastTab. The number series assigns numbers to 1096 forms.

Complete the following steps to set up more required fields for reporting.

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then select the related link.
1. To specify the EIN number to show on the report, on the **Communication** FastTab in the **EIN Number** field, enter the number you registered with IRS.  
1. To specify who communicates with the IRS, in the **IRS Contact No.** field, select the employee responsible for this communication.  

## Create a new 1096 form

> [!NOTE]
> The legacy report layout previously documented here was for reporting year 2023. Confirm that the layout in your installed version is appropriate for the year you're reporting before printing.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1096 Forms**, and then choose the related link.
1. Choose **Create Forms**.
1. In the **Starting Date** and **Ending Date** fields, specify a date range for the calculations. Vendor ledger entries with posting dates in this period are considered.
1. If you want to replace existing forms with new forms, for example, if you made corrections, choose the **Replace** option. If you don't select this option, new forms are created and existing forms remain the same.
1. Choose **OK** to create the forms.

> [!NOTE]
> [!INCLUDE [prod_short](../../includes/prod_short.md)] automatically creates a 1096 form for each of the IRS codes posted in vendor ledger entries during the period you defined.

You can open the forms to review and correct them if necessary.

The **General** FastTab contains the following information.

- **Starting Date**: Specifies the starting date of the period specified for the form.
- **Ending Date**: Specifies the ending date of the period specified for the form.
- **Status**: Specifies the status of the form. Only released forms can be printed. Only open forms can be changed.
- **IRS Code**: Specifies the IRS code of the form.
- **Calculated Total Number of Forms**: Specifies the total number of forms per period and IRS code calculated by the **Create Forms** action. You can't change this value.
- **Total Number of Forms**: Specifies the number of forms used for printing the form. This value matches the calculated number of forms after you choose the **Create Forms** action. You can change this value.
- **Calculated Amount**: Specifies the amount per period and IRS code calculated by the **Create Forms** action. You can't change this value.
- **Calculated Adjustment Amount**: Specifies the adjustment amount per period and IRS code calculated by the **Create Forms** action.
- **Total Amount to Report**: Specifies the amount used for printing. After calculation, it matches the calculated amount minus the calculated adjustment amount. You can change it manually.

The lines contain the following information. Amounts are summarized per **Vendors** and **IRS Codes**.

- **IRS Code**: Specifies the IRS code.
- **Vendor No.**: Specifies the vendor number.
- **Calculated Amount**: Specifies the amount per period and IRS code calculated by the **Create Forms** action. You can't change this value. You can check amounts in the **Vendor Ledger Entries** field for each record.
- **Calculated Adjustment Amount**: Specifies the adjustment amount per period and IRS code calculated by the **Create Forms** action. You can check amounts in the **IRS 1099 Adjustments** field for each record.
- **Manually Changed**: Specifies that the line was changed manually. This field is marked automatically if a record is changed manually.
- **Amount**: Specifies the amount used for printing the form. This value matches the calculated amount minus the calculated adjustment amount after choosing the **Create Forms** action. You can change this value. If you change this amount manually, **Manually Changed** is selected.

## Make corrections in a 1096 form

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1096 Forms**, and then choose the related link.
1. Open the form you want to edit.
1. If the form is **Released**, choose **Reopen** before changing it.
1. If you want to update an amount:

   - Locate the line you want to update and mark the **Amount** field.
   - Enter the value you want to report. The **Manually Changed** field is selected and the **Total Amount to Report** field on the header is updated.

1. If you want to add a new record, enter a new line, and fill in **IRS Code**, **Vendor No.**, and **Amount**. The **Total Amount to Report** field on the header is updated.

When you change a **1096 Form**, the following fields on the **History** FastTab are updated:

- **Changed By**: Specifies the ID of the last user who changed the form.
- **Changed Date-Time**: Specifies the date and time when the last change was made in the form.

## Print the 1096 form

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1096 Forms**, and then choose the related link.
1. Open the form you want to print.
1. If the status is **Open**, choose **Release** action to release the form and make it ready for printing.
1. Choose **Print** to print the single form.
1. If you didn't add the **IRS Contact No.** in the **Company Information**, enter details about the **Person to contact** on the request page, and then select **Print**.

> [!TIP]
> Use **Test Print** to check the layout on blank paper before printing on dedicated forms. Test printouts use sample totals rather than your reported amounts.

The print action updates the following fields on the **History** FastTab:

- **Printed By**: Specifies the ID of the last user who printed the form.
- **Printed Date-Time**: Specifies the date and time of the last time that the form was printed.
- **Printed**: Specifies that the print action was run.

## Related information

- [Set Up and Use the IRS 1099 Form](set-up-use-irs1099-form.md)  
- [United States Local Functionality](united-states-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
