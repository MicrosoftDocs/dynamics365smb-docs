---
    title: How to Set Up Electronic Invoicing
    description: Before you can send electronic documents, you must set up Business Central to ensure that the tax identification number (RFC), personal identification number (CURP), and state inscription IDs are available for your company and all your customers and vendors.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Set Up Electronic Invoicing
Before you can send electronic documents, you must set up [!INCLUDE[d365fin](../../includes/d365fin_md.md)] to ensure that the tax identification number (RFC), personal identification number (CURP), and state inscription IDs are available for your company and all your customers and vendors. You also need to set up the parameters that are needed for sending electronic invoices to customers and vendors. These parameters include the certificate thumbprint, which is the certificate that you received from the Mexico tax authority (SAT).  

> [!IMPORTANT]  
>  The certificate that you received from the Mexico tax authority must be installed for each user who sends electronic invoices. For more information, see the [Servicio de Administracíon Tributaria](https://go.microsoft.com/fwlink/?LinkId=242772) website.  
>   
>  Your company must also have SMTP mail set up for emailing electronic invoices. Depending on the configuration in your company, you may need to grant explicit SMTP permissions to each relevant user and computer. The documents will be sent from the address that is specified on the **Company Information** page.  

## To set up company information  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Company Information**, and then choose the related link.  
2.  On the **Company Information** page, on the **Tax** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|  
    |**SAT Certificate Thumbprint**|Enter the friendly name of the certificate that you want to use for issuing electronic invoices. **Note:**  A certificate is needed for each user who sends electronic invoices. To get the certificate thumbprint, see the Help for the operating system.|  
    |**Send PDF Report**|Select to include a PDF when you email electronic invoices to customers or vendors. Electronic invoices are always sent as an XML file, this option allows you to include a PDF with the XML file.|  
    |**PAC Code**|Specify the authorized service provider, PAC, that you want apply digital stamps to your electronic invoices. **Note:**  To use a PAC, you must set up web services. For more information, see [Set Up PAC Web Services](how-to-set-up-pac-web-services.md).|  
    |**PAC Environment**|Specify if your company uses electronic invoices, and if you are using the web services of your authorized service provider, PAC, in a test environment or a production environment.|  

Optionally, you can ask your Microsoft Certified Partner to modify the text that is included in the email that is sent when you send electronic invoices. The text is stored as text variables in codeunit 10145.  

## See Also  
 [Electronic Invoicing](electronic-invoicing.md)   
 [Generate Electronic Invoices](how-to-generate-electronic-invoices.md)   
 [Mexico Local Functionality](mexico-local-functionality.md)
