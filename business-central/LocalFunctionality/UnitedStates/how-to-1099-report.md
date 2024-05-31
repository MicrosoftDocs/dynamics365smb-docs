---
title: Submit and report the IRS 1099 form [US]
description: Learn how to submit and report the 1099 tax forms in the United States version.
author: altotovi
ms.topic: conceptual
ms.search.keywords: local, 1099, tax, IRS, IRIS, FIRE
ms.search.form: 100136, 10037, 10048, 10050, 10051
ms.date: 05/27/2024
ms.author: altotovi
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
---

# Submit and report the IRS 1099 forms

## Register with IRS  

> [!IMPORTANT]
> Before **2024 release wave 2**, the integration functionality via IRS APIs will be ready.  

Once the document is submitted to the IRS via API, the *IRS 1099 Form Document* changes the **Status** to **Submitted**.  

## To print  

After calculation, you can print the document using the **Print** action. When running the report, you can choose which copy you want to print, as you have the following options:  

- Copy B is for the vendor.
- Copy C is for the sender.
- Copy 2 is the second copy for the vendor.

## Email automation

### Prerequisites

To prevent sending an unsubmitted document to the vendor, you can't email the document if its **Status** isn't **Submitted**.

To send form documents to your vendor, you need to set up the consent and email on the **Vendor Card** page. Enable the **Receiving 1099 E-Form Consent** field to acknowledge that your vendor provided signed consent to receive their 1099 form electronically using email.  

If you have consent from your vendor to deliver 1099 forms via email, you can use the **E-Mail For IRS** field if needed. However, you can also leave this field blank and use the standard **E-Mail** field for sending.  

When a form document is created for a specific vendor, the values are inherited from the vendor card. You can see them on the **Email** FastTab of the document by selecting **Show more**. After the document is created, the consent value can't be changed, but you can update the e-mail, if needed. If you want to change the default values on the **Vendor Card** page, you can do so. The system will then copy these updated values to all 1099 form documents with the **Status** of **Open**, if you confirm **Yes** after making the changes.  

> [!NOTE]
> Before sending emails, make sure that the email you will use for sending is configured on the **Email Accounts** page.  

### To send emails

If you want to send a 1099 form to a specific vendor, you can do so directly from the selected *1099 Form Document* by selecting the **Send Email** action. But it's also possible to automate this process to send emails for multiple 1099 documents. To do so, open the **IRS 1099 Form Documents** list page, select all documents or specific ones, and then choose the **Send Email** action.  

Once you run the **Send Email** action, you need to select the report type you want to send. You can choose **Copy B** or **Copy 2** (required in some situations). By default, emails are sent to vendors who haven't received them previously. If you want to send emails for all selected documents enable the **Resend Email** option on the request page.

After you select **OK**, the email is sent immediately for one document or, if you send multiple emails, scheduled through the **Job Queue Entry**. If the email is sent successfully for a specific document, the flag **Copy B Sent** or **Copy 2 Sent** is set on the **IRS 1099 Form Document** page.

If you try to send an email for only one document and sending fails, the error dialog opens. If you try to send the email for multiple documents and sending fails, the error is logged to the **Email Error Log** field on the **IRS 1099 Form Document** page. When the job for sending multiple documents is finished, the results are written on the activity log. To open the **Activity Log** page, choose the **Activity Log** action on the **IRS 1099 Form Documents** page.

## See also

[United States Local Functionality](united-states-local-functionality.md)
[How to setup the IRS 1099 forms](set-up-use-irs1099-form-v24.md)  
[How to use the IRS 1099 forms](how-to-1099-use.md)  
[Register New Vendors](../../purchasing-how-register-new-vendors.md)
[Set up Email](../../admin-how-setup-email.md)
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
