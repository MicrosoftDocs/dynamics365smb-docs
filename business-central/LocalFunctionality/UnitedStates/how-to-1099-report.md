---
title: Report and submit the IRS 1099 form [US]
description: Learn how to submit and report the 1099 tax form in the United States version.
author: altotovi
ms.topic: how-to
ms.search.keywords: local, 1099, tax, IRS, IRIS, FIRE
ms.search.form: 100136, 10037, 10048, 10050, 10051
ms.date: 02/04/2025
ms.author: altotovi
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
---

# Submit and report the IRS 1099 forms

This article guides users on how to report and submit IRS 1099 forms using Dynamics 365 Business Central.

## Register with the IRS  

You can't print 1099 reports directly on preprinted forms. You can submit 1099 forms using magnetic media or through integration with the IRIS. If you prefer to manually populate your 1099 forms, you can gather all necessary information from the **IRS 1099 Form Documents** and fill them out manually, outside of [!INCLUDE [prod_short](../../includes/prod_short.md)].

You can print or email 1099 copy substitutes to your vendors, including all the details the original form requires.

### Submit using integration with IRIS  

> [!IMPORTANT]
> Integration via IRIS APIs will be available in one of the upcoming minor releases.  

After you submit the document to the IRS by using the API, the status of the **IRS 1099 Form Document** changes to **Submitted**.  

> [!NOTE]
> More details about the integration will be available when we deliver the new feature.  

### Submit using magnetic media  

Submitting 1099 forms as magnetic media using the FIRE portal is optional for cloud users. However, it's the only available option for on-premises users because the Microsoft security certificate for A2A communication can only be used in the cloud.  

To prepare magnetic media for submission, follow these steps:

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **IRS 1099 FIRE**, and then choose the related link.  
1. On the request page, specify the tax year for the 1099 forms that you want to report in the **Calendar Year** field, and the control code of the transmitter that is used to electronically file 1099 forms in the **Transmitter Control Code** field.
1. Fill in the other fields as necessary, and choose **OK**.

> [!NOTE]
> If you want to test this functionality, select the **Test File** field to print a test file.  

## Print the document  

After calculation, you can use the **Print** action to print the document. When you print the report, you can choose which copy to print. You have the following options:  

- Copy B is for the vendor.
- Copy C is for the sender.
- Copy 2 is the second copy for the vendor.

## Email automation

### Prerequisites

> [!NOTE]
> You can't send the document via email if its **Status** isn't **Submitted**. This restriction helps you avoid sending an unsubmitted document to the vendor.

To send forms to your vendor, you must set up the consent and the email on the **Vendor Card** page. These settings include enabling the **Receiving 1099 E-Form Consent** field to acknowledge that your vendor provided signed consent to receive their 1099 form electronically using email.  

> [!NOTE]
> If your vendor gives consent for delivering 1099 forms via email, you can use the **E-Mail For IRS** field, but you can also keep this field blank and fill-in the standard **E-Mail** field. It will be used for sending instead.  

When the form document is created for a certain vendor, the values are inherited from the vendor card. You can see the
values on the **Email** FastTab of the document if you select **Show more**. After you create the document, you can't change the consent value in the document, but you can change the e-mail if needed. You can also change default values on the **Vendor Card** page. [!INCLUDE [prod_short](../../includes/prod_short.md)] will apply these changes to all open (where the **Status** is **Open**) 1099 form documents if you confirm with **Yes**.

> [!NOTE]
> Before you send emails, you must configure the accounts, you use for email on the **Email Accounts** page.  

### Send emails

To send 1099 form to one specific vendor, you can do so from the chosen **1099 Form Document** by choosing the **Send Email** action. It's also possible to automate this process, and to send emails for multiple 1099 documents. To do that, open the **IRS 1099 Form Documents** list page, select one or more documents, and choose the **Send Email** action.  

After you run the **Send Email** action, select the report type you want to send. You can choose **Copy B** or **Copy 2** (required in some situations). By default, emails are sent only to vendors you haven't already sent them to. If you want to send emails for all selected documents (and resending for some of them), enable the **Resend Email** option on the request page.

After you select **OK**, an email is sent immediately for one document or, if you're sending multiple emails, it will be scheduled through the **Job Queue Entry**. If the email is sent successfully for a certain document, the **Copy B Sent** or **Copy 2 Sent** flag is set on the **IRS 1099 Form Document** page.

If you try to send email for only one document and sending failed, an error dialog displays. If you try to send email for multiple documents and sending fails, the error is logged to the **Email Error Log** field on the **IRS 1099 Form Document** page. When the job for sending multiple documents is finished, the results are recorded in the activity log. To open the **Activity Log** page, choose the **Activity Log** action on the **IRS 1099 Form Documents** page.

## Related information

- [United States Local Functionality](united-states-local-functionality.md)
- [How to setup the IRS 1099 forms](set-up-use-irs1099-form-v24.md)
- [How to use the IRS 1099 forms](how-to-1099-use.md)  
- [Register New Vendors](../../purchasing-how-register-new-vendors.md)
- [Set up Email](../../admin-how-setup-email.md)
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
