---
title: IRS 1099 Forms Reporting and Submission [US]
description: Learn how to submit IRS 1099 forms through IRIS, review transmission statuses, correct submissions, and print or email vendor copies.
author: altotovi
ms.topic: how-to
ms.search.keywords: local, 1099, tax, IRS, IRIS, FIRE
ms.search.form: 100136, 10037, 10048, 10050, 10051
ms.date: 10/19/2026
ai-usage: ai-assisted
ms.author: altotovi
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
---

# Submit and report the IRS 1099 forms

This article describes how to report and submit IRS 1099 forms in [!INCLUDE [prod_short](../../includes/prod_short.md)].

## Register with the IRS  

You can't print 1099 reports directly on preprinted forms. You can submit 1099 forms using magnetic media or through integration with the IRIS. If you prefer to manually populate your 1099 forms, you can gather all necessary information from the **IRS 1099 Form Documents** and fill them out manually, outside of [!INCLUDE [prod_short](../../includes/prod_short.md)].

You can print or email 1099 copy substitutes to your vendors, including all the details the original form requires.

### Submit using integration with IRIS  

[!INCLUDE [prod_short](../../includes/prod_short.md)] provides an API that integrates the IRS's Information Returns Intake System (IRIS) so that you can electronically file your returns. To learn more about IRIS, go to the [IRS website](https://go.microsoft.com/fwlink/?linkid=2334210).

#### Set up your IRIS User ID

Before you can send transmissions, every [!INCLUDE [prod_short](../../includes/prod_short.md)] user who submits 1099 forms must register with the IRS Consent App and connect their IRIS User ID to [!INCLUDE [prod_short](../../includes/prod_short.md)]. Open the **Setup IRIS User ID** page from **IRS Forms Setup** and follow the in-product instructions.

> [!IMPORTANT]
> The IRIS User ID is stored per [!INCLUDE [prod_short](../../includes/prod_short.md)] user, not per company. The same user configuration applies across companies. Each user who sends transmissions must configure their own IRIS User ID. If you need to keep different IRIS User IDs configured for different companies, use separate Business Central users for those IDs.

> [!NOTE]
> Posting more invoices or applying payments doesn't automatically recalculate existing 1099 form documents. Review the amounts before submission. If you already created a transmission, use **Update Transmission** to review and apply recalculated amounts.

To submit your 1099 form using IRIS, follow these steps:

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **IRS 1099 Form Documents**, and then choose the related link.
1. Choose the **Create Forms** action.
1. On the **IRS 1099 Create Form Documents** page, select the reporting period in the **Period** field.
1. Fill in the remaining fields as necessary, and then choose **OK**. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]
1. Open the form document and review the **Amount** on each line.
1. Choose the **Release** action.
1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **IRIS Transmissions**, and then choose the related link.
1. To combine released 1099 documents for submission, choose **Create IRIS Transmission**.
1. On the **Create Transmission IRIS** page, fill in the **Reporting Period** field, and then choose **OK**.
1. On the **IRIS Transmissions** page, choose the value in the **Period No.** field to open the **IRIS Transmission** page, where you can review the information before you submit it.
1. If the information is correct, choose the **Send** action.

After a successful send request, released form documents change to **In Progress**. A form document changes to **Submitted** when the IRS returns **Accepted** for its submission. Review both the transmission status and the submission statuses before treating the filing as complete.

> [!TIP]
> To release multiple documents, select them on the **IRS 1099 Form Documents** page, and then choose **Release All**.

> [!TIP]
> If amounts change after you create a transmission, or new released documents appear for the period, choose **Update Transmission**. On **Update 1099 Form Documents**, compare **Current Amount** and **New Amount**, select **Process Line** for the changes to apply, and choose **OK**. This action isn't available for a rejected transmission.

### Submit using magnetic media  

The **IRS 1099 FIRE** report exports a file for submission outside [!INCLUDE [prod_short](../../includes/prod_short.md)]. The built-in IRIS transmission actions are available only in online environments. Confirm the filing service and format supported by the IRS for your reporting year before submitting an exported file.

To prepare magnetic media for submission, follow these steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS 1099 FIRE**, and then choose the related link.  
1. On the request page, specify the tax year for the 1099 forms that you want to report in the **Calendar Year** field, and the control code of the transmitter that is used to electronically file 1099 forms in the **Transmitter Control Code** field.
1. Fill in the other fields as necessary, and choose **OK**.

> [!NOTE]
> If you want to test this feature, select the **Test File** field to print a test file.  

## Print the document  

After calculation, release the document before you choose **Print**. Printing is available for documents with the **Released**, **In Progress**, or **Submitted** status. You can choose which copy to print:

- **Copy B** is for the vendor.
- **Copy C** is for the sender.
- **Copy 2** is the second copy for the vendor.

## Correct IRS transmission errors

Before sending, [!INCLUDE [prod_short](../../includes/prod_short.md)] checks the required data. The IRS then returns a processing result, which can include rejected submissions or accepted submissions with errors. To learn more about rejections, go to [Correct a rejected transmission](#correct-a-rejected-transmission).

These checks don't establish that the reported amounts are correct. If you discover that you submitted an incorrect amount in an accepted transmission, you can correct the amount and resubmit. To learn more, go to [Correct an accepted transmission](#correct-an-accepted-transmission).

### Transmission statuses

After you send a transmission, the IRS returns one of the following statuses on the **IRIS Transmission** page:

- **Accepted**: The IRS successfully processed and accepted the transmission.
- **Rejected**: The IRS rejected the transmission because it couldn't process it successfully. For an original transmission, use **Send Replacement** when available. If a correction was rejected, correct it and use **Send Correction** again.
- **Processing**: The IRS is still processing the transmission. Check the status again later.
- **Partially Accepted**: The IRS accepted some submissions and rejected others. **Send Replacement** includes only the rejected submissions for this status.
- **Accepted with Errors**: The IRS successfully processed and accepted the transmission, but with errors on one or more submissions.
- **Not Found**: The IRS didn't find the Receipt ID or the UTID in the request.

In addition to the statuses returned by the IRS, the **IRIS Transmission** page can show the following internal statuses:

- **None**: The transmission is created in [!INCLUDE [prod_short](../../includes/prod_short.md)] but isn't sent yet.
- **Unknown**: The status returned by the IRS couldn't be interpreted.

### Refresh the transmission status

If the transmission is in the **Processing** state, or the status didn't update automatically after sending, you can request the current status from the IRS on the **IRIS Transmission** page:

- **Request Status** uses the **Receipt ID** that the IRS returned when you sent the transmission. Use this action in most cases.
- **Request Status by UTID** uses the **Unique Transmission ID** instead of the Receipt ID. Use this action when the Receipt ID is missing, for example, after a prereceipt XML schema validation error. The UTID is selected automatically from the latest transmission history entry.

### Recover a lost receipt ID

If the **Receipt ID** is missing because the session was interrupted or the value was deleted, contact the IRIS help desk. Provide the **Unique Transmission ID** from **Transmission History** to request the Receipt ID. Then, on **IRIS Transmission**, choose **Assign Receipt ID** and enter the value. After the Receipt ID is assigned, use **Request Status** to refresh the transmission status.

### Troubleshoot authentication errors

If a **Send** or **Request Status** action fails with **401 Unauthorized**, your IRIS OAuth tokens might be stale. To recover:

1. On the **IRIS Transmission** page, choose **Clear OAuth Tokens**. The action is hidden by default; use page personalization to show it.
1. Try the action again. [!INCLUDE [prod_short](../../includes/prod_short.md)] requests new tokens automatically the next time you send or request status.
1. If the error persists, on the **Setup IRIS User ID** page, reenter your **IRIS User ID**.

### Review transmission history

The **Transmission History** page lists every send, replacement, correction, and status request for the period, together with the **Unique Transmission ID** assigned by [!INCLUDE [prod_short](../../includes/prod_short.md)] and the **Receipt ID** returned by the IRS. From this page, you can also download the raw payloads exchanged with the IRS for support and audit purposes:

- **Download Transmission Content**: the XML file that [!INCLUDE [prod_short](../../includes/prod_short.md)] sent to the IRS.
- **Download Response Content**: the immediate response returned by the IRS for the send request, in XML or JSON format.
- **Download Acknowledgement Content**: the acknowledgment returned by the IRS when processing is complete, in XML or JSON format. The acknowledgment contains the transmission and submission statuses, together with any errors reported by the IRS.

### Correct a rejected transmission

If an original transmission is **Rejected**, use the **Show error(s)** link on the **IRIS Transmission** page to open **Error Information** and review what to fix. After you correct the error, choose **Send Replacement** when available. For a **Partially Accepted** transmission, the replacement includes only rejected submissions. If a correction transmission was rejected, fix the correction and use **Send Correction** again. To review earlier attempts, choose **Transmission History**.

If a prereceipt error left the transmission without a Receipt ID, use **Request Status by UTID** to investigate the result before deciding whether to send again.

### Correct an accepted transmission

If you discover a mistake after the IRS accepted your submission, for example, you submitted incorrect amounts for some vendors, you can correct the error and resubmit.

To correct a mistake and resubmit, follow these steps:

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **IRIS Transmissions**, and then choose the related link.
1. Open the transmission, and then open the related 1099 form document that you want to correct. Choose **Allow Correction**.
1. Choose the **Reopen** action, make your correction, choose the **Release** action, and then close the page.
1. On the **IRIS Transmission** page, the **Needs Correction** checkbox is selected for the lines you corrected. 
1. To resubmit the lines, choose the **Send Correction** action. [!INCLUDE [prod_short](../../includes/prod_short.md)] only sends the lines you corrected. 

> [!TIP]
> The **Corrected** field indicates that a correction was sent. Check the returned **Submission Status** as well to confirm acceptance.

> [!NOTE]
> Use **Send Replacement** for a rejected original transmission or rejected submissions in a partially accepted transmission. Use **Send Correction** for accepted records that need changes, or to retry a rejected correction. Corrections include only form documents marked **Needs Correction**.

#### Choose the right correction action

The **IRIS Transmission** page provides three correction actions, depending on what you need to fix:

| Action | When to use it |
|--------|----------------|
| **Send Correction** | A line was accepted with the wrong vendor name, TIN, or amount. [!INCLUDE [prod_short](../../includes/prod_short.md)] sends only the lines you marked with **Allow Correction** and re-released, with the corrected values. |
| **Send Zero Amounts Correction** | You shouldn't have filed a 1099 form for a vendor at all. [!INCLUDE [prod_short](../../includes/prod_short.md)] sends the marked lines as a correction with zero amounts. Review the IRS response to confirm the result. |
| **Two-Step Correction** | The form type itself was wrong. For example, you filed a 1099-MISC instead of a 1099-NEC. **Step 1: Send Zero Amounts Correction** sends all eligible lines with zero amounts, except open and abandoned ones. Wait for acceptance, and then use **Update Transmission** to add the corrected form documents. **Step 2: Send Corrected** submits the updated transmission as an original transmission. |

> [!TIP]
> The **Two-Step Correction** group on the **IRIS Transmission** page also includes a **Help** action that describes the process inside the product.

## Email 1099 vendor copies

### Prepare to email vendor copies

> [!NOTE]
> You can only send the document via email if its **Status** is **Released** or **Submitted**. This restriction helps you avoid sending an unreleased document to the vendor.

To send forms to your vendor, you must set up the consent and the email on the **Vendor Card** page. These settings include enabling the **Receiving 1099 E-Form Consent** field to acknowledge that your vendor provided signed consent to receive their 1099 form electronically using email.  

> [!NOTE]
> To use a different recipient address for 1099 forms, fill in **E-Mail For IRS**. If that field is blank, the vendor's standard **Email** address is used.

When the form document is created for a certain vendor, the values are inherited from the vendor card. You can see the
values on the **Email** FastTab of the document if you select **Show more**. You can't edit consent directly on the document, but you can change its email address. When you change the email address or consent on the **Vendor Card** page, you can confirm separate prompts to apply the change to **Open**, **Released**, and **Submitted** form documents.

> [!NOTE]
> Before you send emails, you must configure your email accounts on the **Email Accounts** page.  

### Send emails

To send 1099 form to a specific vendor, you can do so from the chosen **1099 Form Document** by choosing the **Send Email** action. It's also possible to automate this process, and to send emails for multiple 1099 documents. To do that, open the **IRS 1099 Form Documents** list page, select one or more documents, and choose the **Send Email** action.  

After you run **Send Email**, select **Copy B** or **Copy 2** as the report type. When you select multiple documents, the process skips copies already marked as sent unless you turn on **Resend Email**. For a single document, the email is sent immediately, even if that copy was sent before.

After you select **OK**, an email is sent immediately for one document or, if you're sending multiple emails, it will be scheduled through the **Job Queue Entry**. If the email is sent successfully for a certain document, the **Copy B Sent** or **Copy 2 Sent** flag is set on the **IRS 1099 Form Document** page.

If you try to send email for only one document and sending failed, an error dialog displays. If you try to send email for multiple documents and sending fails, the error is logged to the **Email Error Log** field on the **IRS 1099 Form Document** page. When the job for sending multiple documents is finished, the results are recorded in the activity log. To open the **Activity Log** page, choose the **Activity Log** action on the **IRS 1099 Form Documents** page.

## Related information

- [United States Local Functionality](united-states-local-functionality.md)
- [Set up IRS 1099 forms](set-up-use-irs1099-form-v24.md)
- [How to use the IRS 1099 forms](how-to-1099-use.md)  
- [Register New Vendors](../../purchasing-how-register-new-vendors.md)
- [Set up Email](../../admin-how-setup-email.md)
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
