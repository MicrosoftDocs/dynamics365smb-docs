---
title: Set Up PAC Web Services
description: To send electronic invoices and credit memos in Mexico, you need to specify at least one provider for the required electronic stamp.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: PAC, Web services, PAC web services, electronic invoicing, electronic stamp
ms.search.form: 10455, 10456
ms.date: 02/25/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up PAC web services

Before you can send invoices and credit memos electronically, you must specify one or more providers of the electronic stamp that must be included in invoices in Mexico.  

When you send an electronic document, it must receive a digital stamp by an authorized service provider, PAC, before it can be sent to your customer. The communication between [!INCLUDE[prod_short](../../includes/prod_short.md)] and the PAC is managed through web services, and therefore, you must specify technical information about the web services of the PAC that you intend to use.  

To use web services, you must identify the name of the method on the web service that processes requests for digital stamps. Your PAC can give you this information.  

If your PAC offers the service of canceling signed documents, you must specify two web methods: one web method for requesting the digital stamp, and the other for canceling an already signed document.  

Before you can set up the web services, you must upload two certificates:

* A PAC .pfx file
* A SAT .pfx file

These certificates are used by the communication component and configured in the **General Ledger Setup** page. Learn more in [Set up general ledger information](how-to-set-up-electronic-invoicing.md#set-up-general-ledger-information).  

## Add the certificates

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Certificates**, and then choose the related link.  
1. Choose the **New** action, specify the relevant certificate, and then, in the **Certificate** page, fill in the fields as appropriate. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]
1. Repeat step 2 for the second certificate.  
1. Close the page.  

## Set up a PAC web service  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **PAC Web Services**, and then choose the related link.  
1. In the **PAC Web Services** page, add the relevant web services. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

    For each web service, you must specify the relevant certificate. You must also add additional details.  

    1. For the relevant web service, choose the **Related** action, choose the **PAC Web Service** menu item, and then choose the **Details** action.  
    1. Fill in the fields as described in the following table.  

        |Field|Description|
        |------------------------------------|---------------------------------------|
        |**Environment**|Specify if the web service is for a test environment or a production environment.|
        |**Type**|Specify if the web method is for requesting a digital stamp or for canceling.|
        |**Method Name**|Specify the name of the web method, such as *GeneraTimbre* or *CancelaTimbre*.|
        |**Address**|Specify the URL of the web method.|

        Contact your PAC for this information.  

1. Repeat the steps for any additional PAC that you want to set up.  

    > [!IMPORTANT]  
    > SAT has certified more than one PAC in Mexico, and you must obtain the appropriate information for communication with the PAC of your choice.  

## Related information

- [Electronic Invoicing](electronic-invoicing.md)  
- [Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md)  
- [Mexico Local Functionality](mexico-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
