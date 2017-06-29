---
title: "How to: Set Up Electronic Invoicing"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic invoices, setting up"
ms.assetid: 0333ca30-915f-4eb4-a7b4-e1e5c9ac5794
caps.latest.revision: 15
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "es-mx"
---
# How to: Set Up Electronic Invoicing
Before you can send electronic documents, you must set up FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] --> to ensure that the tax identification number \(RFC\), personal identification number \(CURP\), and state inscription IDs are available for your company and all your customers and vendors. You also need to set up the parameters that are needed for sending electronic invoices to customers and vendors. These parameters include the certificate thumbprint, which is the certificate that you received from the Mexico tax authority \(SAT\).  
  
> [!IMPORTANT]  
>  The certificate that you received from the Mexico tax authority must be installed for each user who sends electronic invoices. For more information, see the [Servicio de Administracíon Tributaria](http://go.microsoft.com/fwlink/?LinkId=242772) website.  
>   
>  Your company must also have SMTP mail set up for emailing electronic invoices. Depending on the configuration in your company, you may need to grant explicit SMTP permissions to each relevant user and computer. The documents will be sent from the address that is specified in the **Company Information** window.  
  
### To set up company information  
  
1.  In the **Search** box, enter **Company Information**, and then choose the related link.  
  
2.  In the **Company Information** window, on the **Tax** FastTab, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] --> --> --> -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] --> --> --> -->|  
    |---------------------------------|---------------------------------------|  
    |**Tax Scheme**|Enter the tax scheme that your company uses complies with.<br /><br /> Commonly used tax schemes are Régimen General, Régimen intermedio, and Régimen de pequeños contribuyentes \(REPECOS\). **Important:**  You cannot send an electronic invoice unless you have specified the tax scheme.|  
    |**RFC No.**|Enter the federal registration number for taxpayers.<br /><br /> The Registro Federal de Contribuyentes \(RFC\) tax identification type can be applied to companies and to people. An RFC number for a company is 12 characters, while an RFC number for a person is 13 characters.|  
    |**CURP No.**|Enter the unique fiscal card identification number.<br /><br /> The Cédula de identification fiscal con clave única de registro de población \(CURP\) tax identification type can only be applied to people. A CURP number is 18 characters.|  
    |**State Inscription**|Enter the tax ID number that is assigned by state tax authorities to every person or corporation.|  
  
### To set up customer information  
  
1.  In the **Search** box, enter **Customer Card**, and then choose the related link.  
  
2.  In the **Customer Card** window, on the **Invoicing** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**RFC No.**|Enter the federal registration number for taxpayers. The RFC number must contain 12 digits.|  
    |**CURP No.**|Enter the unique fiscal card identification number. The CURP number must contain 18 digits|  
    |**State Inscription**|Enter the tax ID number that is assigned by state tax authorities to every person or corporation.|  
  
    > [!NOTE]  
    >  If you select the Prices Including VAT field for a customer, the electronic documents will include VAT in all amounts, including unit prices. The electronic documents will also contain a separate element for VAT. If you want to avoid any possible confusion about the amounts including VAT, you can choose to not select the **Prices Including VAT** field.  
  
3.  On the **Payments** FastTab, in the **Payment Method Code** field, specify the payment method that you want to use for this customer.  
  
### To set up vendor information  
  
1.  In the **Search** box, enter **Vendor Card**, and then choose the related link.  
  
2.  On the **Payments** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**RFC No.**|Enter the federal registration number for taxpayers. The RFC number must contain 12 digits.|  
    |**CURP No.**|Enter the unique fiscal card identification number. The CURP number must contain 18 digits|  
    |**State Inscription**|Enter the tax ID number that is assigned by state tax authorities to every person or corporation.|  
  
### To set up general ledger information  
  
1.  In the **Search** box, enter **General Ledger Setup**, and then choose the related link.  
  
2.  In the **General Ledger Setup** window, on the **Electronic Invoice**  FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**SAT Certificate Thumbprint**|Enter the friendly name of the certificate that you want to use for issuing electronic invoices. **Note:**  A certificate is needed for each user who sends electronic invoices. To get the certificate thumbprint, see the Help for the operating system.|  
    |**Send PDF Report**|Select to include a PDF when you email electronic invoices to customers or vendors. Electronic invoices are always sent as an XML file, this option allows you to include a PDF with the XML file.|  
    |**PAC Code**|Specify the authorized service provider, PAC, that you want apply digital stamps to your electronic invoices. **Note:**  To use a PAC, you must set up web services. For more information, see [How to: Set Up PAC Web Services](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Mexico/how-to-set-up-pac-web-services.md).|  
    |**PAC Environment**|Specify if your company uses electronic invoices, and if you are using the web services of your authorized service provider, PAC, in a test environment or a production environment.|  
  
 Optionally, you can ask your Microsoft Certified Partner to modify the text that is included in the email that is sent when you send electronic invoices. The text is stored as text variables in codeunit 10145.  
  
## See Also  
 [Electronic Invoicing](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Mexico/electronic-invoicing.md)   
 [How to: Generate Electronic Invoices](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Mexico/how-to-generate-electronic-invoices.md)   
 Company Information   
 Customer Card   
 Vendor Card   
 General Ledger Setup