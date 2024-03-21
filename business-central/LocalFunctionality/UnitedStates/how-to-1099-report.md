---
title: Report and Submit the IRS 1099 Form [US]
description: Learn how submit and report the 1099 tax forms in the United States localization.
author: altotovi

ms.topic: conceptual
ms.search.keywords: local, 1099, tax, IRS, IRIS, FIRE
ms.search.form: 100136, 10037, 10048, 10050, 10051
ms.date: 03/21/2024
ms.author: altotovi
ms.reviewer: 

ms.service: dynamics-365-business-central
---

# Submit and report the IRS 1099 Forms in the US Version

## Register with IRS  

> [!IMPORTANT]
> This integration functionality via IRIS APIs will be ready in period before **2024 release wave 2**.  

Once the document is submitted to the IRS via API, the **IRS 1099 Form Document** will change the **Status** to **Submitted**.  

> [!NOTE]
> More details about integration part will be added when new feature is delivered. 

## Printing   

After calculation you can print the document using the **Print** action. When running the report printing, you can choose which copy you want to print, as you have the following options:  

- Copy B is for the vendor.
- Copy C is for the sender.
-	Copy 2 is the second copy for the vendor.

## Email automation 

### Prerequisites 

> [!NOTE]
> You cannot send the document via email if its **Status** is not **Submitted** to prevent sending not-submitted document to the vendor. 

To be able to send form documents to your vendor, you need to set up the consent and the email in the vendor card, enabling the **Receiving 1099 E-Form Consent** field to acknowledge that your vendor has provided signed consent to receive their 1099 form electronically using email.  

> [!NOTE]
> If you have consent from your vendor for delivering 1099 forms via email, you can use the **E-Mail For IRS** field if needed, but you can also keep this field blank and fill-in the standard **E-Mail** field. It will be used for sending instead.  

When the form document is created for a certain vendor, the values are inherited from the vendor card. You can see them on the **Email** FastTab of the document if you click **Show more**. After document creation, you cannot change the consent value in the document, but you can change the e-mail if needed. If you want to change some of these default values in the **Vendor** card, you can do it, and the system will copy their values to all 1099 form documents where the **Status** has a value **Open**, if you confirm **Yes** after changing.  

> [!NOTE]
> Before you send emails, you must have configured email you will use for sending in the **Email Accounts** page.  

### Sending emails 

If you want to send 1099 form to one specific vendor you can do it from the chosen **1099 Form Document**, running the **Send Email** action. But it is also possible to automate this process and to send emails for multiple 1099 documents. To do this, open the **IRS 1099 Form Documents** list page, select all documents or only some of them, and run the **Send Email** action.  

Once you run the **Send Email** action, you need to select the report type you want to send, as you can choose **Copy B** or **Copy 2** (required in some situations). By default, emails will be sent only to those vendors to whom they have not been sent before. If you want to send emails for all selected documents (and resending for some of them), enable the **Resend Email** option at the request page. 

After you press **OK**, email will be sent immediately for one document or, if you send multiple emails, it will be scheduled through the **Job Queue Entry**. If email is sent successfully for a certain document, the flag **Copy B Sent** or **Copy 2 Sent** will be set at the **IRS 1099 Form Document** page.   

If you try to send email for only one document and sending failed, the error dialog will be shown. If you try to send email for multiple documents and sending failing, the error will be logged to the **Email Error Log** field in the **IRS 1099 Form Document** page. When the job for sending multiple documents is finished, its results will be written on the activity log. To open the **Activity Log** page, run the **Activity Log** action form the **IRS 1099 Form Documents** page. 

## See also 

[United States Local Functionality](united-states-local-functionality.md)  
[How to setup the IRS 1099 forms](how-to-1099-setup.md)
[How to use the IRS 1099 forms](how-to-1099-use.md)
[Register New Vendors](../../purchasing-how-register-new-vendors.md)  
[Set up Email](../../admin-how-setup-email.md)  
[Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
