---
title: Set up and use the IRS 1096 form [US]
description: Learn how to set up the 1096 tax form boxes so that you can submit the required reports.
author: altotovi
ms.topic: how-to
ms.workload: na
ms.search.keywords: local, 1096, irs
ms.search.form: 10019, 10020, 10021
ms.date: 12/12/2023
ms.author: altotovi
ms.reviewer: 
---

# Set up and use the IRS 1096 form in the US version

Form 1096 is used to transmit paper tax forms to the Internal Revenue Service (IRS) in the United States. This feature lets you run the Form 1096 report in [!INCLUDE[prod_short](../../includes/prod_short.md)] and send it to the IRS, if necessary. The feature is only related to already transmitted 1099 paper forms.

> [!NOTE]
> 1096 Form reporting supports only the IRS codes supported for 1099 Form reporting in [!INCLUDE[prod_short](../../includes/prod_short.md)]. If you add manually other IRS codes to the 1096 Form lines, those codes will not be printed on the report.

## Enable the extension

Form 1096 is an extension. After you install the extension in your environment you must enable it, as described in the following steps.

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Feature management**, and then choose the related link.
2. Find **Feature: Enable using Form 1096 to transmit paper Tax Forms to the IRS in the United States** and in the **Enabled for** field, choose **All Users**.
3. When you enable the feature, use the setup guide to set it up. The only information required is to specify the **IRS 1096 Form No. Series** to use. This is the code for the number series that is used to assign numbers for 1096 forms per certain period.

If you didn’t use the setup guide to configure **IRS 1096 Form No. Series**, you can do so on the **Purchases & Payables Setup** page. Fill in the **IRS 1096 Form No. Series** field on the **Number Series** FastTab.

Complete the following steps to set up more required fields for reporting.

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then select the related link.   
2. To specify the EIN number to show on the report, on the **Communication** FastTab in the **EIN Number** field, enter the number you registered with IRS.  
3. To specify who communicates with the IRS, in the **IRS Contact No.** field, select the employee responsible for this communication.  

## To create a new 1096 form

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1096 Forms**, and then choose the related link.
2. Choose the **Create forms…** action to create a new entry.
3. In the **Starting Date** and **Ending Date** fields, specify a date range for the calculations. Vendor ledger entries with posting dates within this period will be considered.
4. If you want to replace existing forms with new forms, for example, if you've made corrections, choose the **Replace** option. If you don't select this option, new forms are created and existing forms remain the same.
5. After you create the new forms, choose **OK**. A confirmation displays the message, **IRS 1096 forms have been created**.

> [!NOTE]
> The system automatically creates a 1096 form for each of the IRS codes posted in vendor ledger entries during the period you defined.

You can open the forms to check their details make corrections if needed.

The General FastTab contains the following information.

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
- **Vendor no.** – Specifies the vendor number.
- **Calculated Amount** – Specifies the amount per period and IRS code calculated by the **Create Forms** action. You can't change this value. You can check amounts in the **Vendor Ledger Entries** field for each record.
- **Calculated Adjustment Amount** – Specifies the adjustment amount per period and IRS code calculated by the **Create Forms** action. You can check amounts in the **IRS 1099 Adjustments** field for each record.
- **Manually changed** - Specifies that the line has been changed manually. This field is marked automatically if a record is changed manually.
- **Amount** - Specifies the amount used for printing the form. This value matches the calculated amount minus the calculated adjustment amount after choosing the **Create Forms** action. You can change this value. If you change this amount manually, the **Manually changed** field is marked.

## To make corrections in a 1096 form

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1096 Forms**, and then choose the related link.
2. Open the form you want to edit.
3. If you want to update an amount:

   * Locate the line you want to update and mark the **Amount** field.
   * Enter the value you want to report. The **Manually changed** field is marked and the **Total Amount to Report** field on the header is updated.

4. If you want to add a new record, enter a new line, and fill in values you need for reporting in the **IRS Code**, **Vendor no.**, and **Amount** fields. The **Total Amount to Report** field on the header will be updated.
5. In both of situations, when you make a change in the **1096 Form**, the system will automatically fill in the following fields on the **History** FastTab:

   * **Changed By** – Specifies the ID of the last user who changed the form.
   * **Changed Date-Time** – Specifies the date and time when the last change was made in the form.

## To print the 1096 form

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **1096 Forms**, and then choose the related link.
2. Open the form you want to print.
3. If the status is **Open**, choose **Release** action to release the form and make it ready for printing.
4. Choose **Print** actions to print the single form.
5. If you didn't add the **IRS Contact No.** in the **Company Information**, enter details about the **Person to contact** on the request page, and then select **Print**.
6. After printing, the following fields at the **History** FastTab will be updated:

    * **Printed by** – Specifies the ID of the last user who printed the form.
    * **Printed Date-Time** – Specifies the date and time of the last time that the form was printed.
    * **Printed** – Specifies that the form has been printed.

## See also

[United States Local Functionality](united-states-local-functionality.md)

