---
    title: Electronic Submission of Sales VAT Advance Notifications to ELSTER
    description: In Business Central, you can electronically submit tax documents and VAT statements, such as the sales VAT advance notification, to the tax authorities.

    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Electronic Submission of Sales VAT Advance Notifications to ELSTER
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can electronically submit tax documents and VAT statements, such as the sales VAT advance notification, to the tax authorities.  

## Sales VAT Advance Notifications  
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] creates an XML document containing tax and base amounts, along with company information. You can validate the data before submitting it to the tax authorities. You can set up the XML document using the layout that is defined in the tax authorities' style sheet. You can then transmit the XML document to the tax authorities' Elektronische Steuererklärungen (ELSTER) online portal interface.  

You must first set up [!INCLUDE[d365fin](../../includes/d365fin_md.md)] to be able to submit sales VAT advance notifications to the ELSTER online portal. For more information, see [Set Up Sales VAT Advance Notifications for ELSTER](how-to-set-up-sales-vat-advance-notifications-for-elster.md). You can later create and transmit the sales VAT advance notification. For more information, see [Create and Submit Sales VAT Advance Notifications](how-to-create-and-submit-sales-vat-advance-notifications.md).

The tax authorities' server processes the submitted XML document, and sends an XML document in response. This response document displays codes and descriptions for errors that occurred during the processing of the submitted XML document. The XML documents are encrypted during transmission. For more information, see the [ELSTER online portal](http://go.microsoft.com/fwlink/?LinkId=155998).  

## Architectural Overview  
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] includes an interface to the ELSTER portal, the Microsoft.Dynamics.ElsterTransferHandler.dll assembly. The assembly manages the communication with the ELSTER portal and installs when you install the [!INCLUDE[d365fin](../../includes/d365fin_md.md)] Windows client. For more information, see [ELSTER Transmission Overview](elster-transmission-overview.md).

The ELSTER portal has requirements for computers that will submit documents. This includes a software certificate that you must acquire for each user who will submit documents to ELSTER. You must verify your installation against the information that is available on [ELSTER online portal](http://go.microsoft.com/fwlink/?LinkId=155998). The following section describes installation considerations for your [!INCLUDE[d365fin](../../includes/d365fin_md.md)] implementation.  

### Installation Considerations  
The Microsoft.Dynamics.ElsterTransferHandler.dll assembly installs as part of the installation of [!INCLUDE[d365fin](../../includes/d365fin_md.md)].  

> [!NOTE]  
>  Before you install a new version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)].  

ELSTER requires certificates to identify the company and the person who submits each document. On the computer of each user who will submit a statement to ELSTER, you must install the following certificates:  

- The public certificate of the tax authorities.  
- A personal .pfx certificate for that user.  

You must then list the users and the friendly names of the certificates in the **Certificates** window. For more information about how to install a certificate and how to find the friendly name, see the Help for the operating system.  

If you use a proxy server to submit the ELSTER documents, you must specify the settings in the **Electronic VAT Decl. Setup** window.  

For more information, see [Set Up Sales VAT Advance Notifications for ELSTER](how-to-set-up-sales-vat-advance-notifications-for-elster.md).  

## Certificates and Style Sheets  
Your company must register at the ELSTER online portal so that you can acquire the necessary certificates. If you have already registered, you do not have to register again.  

> [!IMPORTANT]  
> The ELSTER online portal provides three methods of connection, but [!INCLUDE[d365fin](../../includes/d365fin_md.md)] only supports the software certificate that is included in the ELSTER-Basis certification method. The ELSTER-Spezial and ELSTER-Plus methods are not available in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].  

After you have registered at the ELSTER online portal, you must acquire a personal certificate. You must also download the public certificate of the tax authorities and the style sheets that are needed for the data transmissions. When you install the personal certificate on the user’s computer, you will be asked to specify a password.  

The public certificate of the tax authorities is available for download from the ELSTER online portal. The current file name is Coala2019.pem.cer.  

The personal .pfx certificate is required to clearly identify the user who submits the documents to the tax authorities. The personal certificate contains a digital signature that is included in the transmitted XML files. The name of the user who submitted the files is also included.  

You must also download all relevant style sheets that the tax authorities make available. This includes the ustva.xsl style sheet that you must specify in the **Sales VAT Adv. Notif. Card** window, but the tax authorities may require additional style sheets that must be located in the same folder as the ustva.xsl style sheet.  

For more information, see the [ELSTER online portal](http://go.microsoft.com/fwlink/?LinkId=155998)  

## Transmissions  
In the **Sales VAT Adv. Notification List** window, you can create and submit sales VAT advance notifications. When you create a document, you can preview it before submitting it to the ELSTER portal. The documents that are created are based on the XML stylesheets that are published at the ELSTER portal, and on the certificate and other information that you have set up in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].  

After you have submitted a document to ELSTER, an entry is made in the **VAT Transmission Log Entries** window. When the ELSTER online portal processed the submitted document, errors can occur, and [!INCLUDE[d365fin](../../includes/d365fin_md.md)] displays an error message that is based on the error code from ELSTER. In most cases, the error is caused by problems with the user-specific certificate or with network connectivity. For more information, see [Error Messages of the ElsterTransferHandler and ELSTER Transmission Overview](error-messages-of-the-elstertransferhandler.md).

## See Also  
 [Set Up Sales VAT Advance Notifications for ELSTER](how-to-set-up-sales-vat-advance-notifications-for-elster.md)   
 [Create and Submit Sales VAT Advance Notifications](how-to-create-and-submit-sales-vat-advance-notifications.md)   
 [ELSTER online portal](http://go.microsoft.com/fwlink/?LinkId=155998)
