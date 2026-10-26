---
title: Set Up PAC Web Services in Mexico
description: To send electronic invoices and credit memos in Mexico, you need to specify at least one provider for the required electronic stamp.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: PAC, Web services, PAC web services, electronic invoicing, electronic stamp
ms.search.form: 10455, 10456
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up PAC web services

Before you can send invoices and credit memos electronically, you must specify one or more providers of the electronic stamp that must be included in invoices in Mexico.  

When you send an electronic document, it must receive a digital stamp by an authorized service provider, PAC, before it can be sent to your customer. The communication between [!INCLUDE[prod_short](../../includes/prod_short.md)] and the PAC is managed through web services, and therefore, you must specify technical information about the web services of the PAC that you intend to use.  

To use web services, you must identify the name of the method on the web service that processes requests for digital stamps. Your PAC can give you this information.  

Configure the methods your PAC provides for requesting stamps, submitting cancellations, and retrieving cancellation status. The **Type** field distinguishes these operations.

Before you can set up the web services, you must upload two certificates:

* A PAC .pfx file
* A SAT .pfx file

Assign the PAC certificate in **Certificate** on **PAC Web Services**. Assign the SAT certificate in **SAT Certificate** on **General Ledger Setup**. Learn more in [Set up general ledger information](how-to-set-up-electronic-invoicing.md#set-up-general-ledger-information).

## Add the certificates

Have your administrator or partner add the certificates before you configure the PAC and SAT certificate fields. If **New** is available on **Certificates**, you can use it to upload the files. Otherwise, use the list to review the certificates that your administrator or partner added.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Certificates**, and then choose the related link.  
1. Open the relevant certificate card and review **Name**, **Available To**, **Has Private Key**, and **Expiry Date**. The availability must include the users who send electronic documents.
1. To replace an existing certificate file, select **Upload Certificate** and enter **Password** if prompted.
1. Repeat the review for the second certificate.
1. Close the page.  

## Set up a PAC web service  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **PAC Web Services**, and then choose the related link.  
1. On **PAC Web Services**, enter the provider's **Code**, **Name**, and **Certificate**.

    For each web service, you must specify the relevant certificate. You must also add additional details.  

    1. For the relevant web service, choose the **Related** action, choose the **PAC Web Service** menu item, and then choose the **Details** action.  
    1. Fill in the fields as described in the following table.  

        |Field|Description|
        |------------------------------------|---------------------------------------|
        |**Environment**|Specify if the web service is for a test environment or a production environment.|
        |**Type**|Select **Request Stamp** to obtain a stamp, **Cancel** to submit a cancellation, or **Cancel Request** to retrieve the cancellation status.|
        |**Method Name**|Specify the name of the web method, such as *GeneraTimbre* or *CancelaTimbre*.|
        |**Address**|Specify the URL of the web method.|

        Contact your PAC for this information.  

1. Repeat the steps for each required operation and environment.
1. On **General Ledger Setup**, select the provider in **PAC Code** and the matching **PAC Environment**.
1. Repeat the PAC setup for any additional providers.

    > [!IMPORTANT]  
    > SAT has certified more than one PAC in Mexico, and you must obtain the appropriate information for communication with the PAC of your choice.  

> [!NOTE]
> The default integration expects specific request parameters and response XML. Changing the URL and method name might not be enough to use a different PAC. Work with your partner to confirm compatibility or adapt the integration.

## Related information

- [Electronic Invoicing](electronic-invoicing.md)  
- [Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md)  
- [Mexico Local Functionality](mexico-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
