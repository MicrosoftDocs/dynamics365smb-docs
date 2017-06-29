---
title: "How to: Set Up an OCR Service"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 4d17ca9a-0717-4c17-9aba-f004e1fa0df9
caps.latest.revision: 10
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Set Up an OCR Service
You use an external provider of OCR services to have PDF or image files turned into electronic documents that can be converted to document records in FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] --> -->. For more information, see [How to: Use OCR to Turn PDF and Image Files into Electronic Documents](../../BusinessFunctionality/DataExchange/how-to-use-ocr-to-turn-pdf-and-image-files-into-electronic-documents.md).  
  
### To set up an OCR service  
  
1.  In the **Search** box, enter **OCR Service Setup**, and then choose the related link.  
  
2.  Fill the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**User Name**|Specify the user name that represents your company’s login to the OCR service.|  
    |**Password**|Specify the password that is used for your company’s login to the OCR service.|  
    |**Authorization Key**|Specify the authorization key that is used for your company’s login to the OCR service.|  
    |**Default OCR Document Template**|Specify the document template that must be used by default for electronic documents that are received from the OCR service. Chose the field to pick a supported document template from the **OCR Service Document Templates** window.<br /><br /> **NOTE:** To see any new document templates that the OCR service supports, choose the **Update Document Templates List** button in the **OCR Service Document Templates** window.|  
    |**Enabled**|Specify if the service is enabled.<br /><br /> **NOTE:** As soon as you enable the service, at least two job queue entries are created to process the traffic of electronic documents in and out of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)]. When you disable the service, the job queue entries are deleted.|  
    |**Sign\-up URL**|Specify the Web page where you sign up for the OCR service.|  
    |**Service URL**|Specify the address of the OCR service, which will be called when you send and receive files for OCR.|  
    |**Sign\-in URL**|Specify the sign in page for the OCR service, which is where you enter your company’s user name, password, and authorization key to sign in to the service.|  
  
> [!NOTE]  
>  It is recommended that you protect the logon information that you enter in the **OCR Service Setup** window. You can encrypt data on the Microsoft Dynamics NAV Server by generating new or importing existing encryption keys that you enable on the Microsoft Dynamics NAV Server instance that connects to the database. This is described in the following procedure.  
  
### To encrypt your login information  
  
1.  In the **OCR Service Setup** window, on the **Home** tab, in the **Encryption** group, choose **Encryption Management**.  
  
2.  In the **Data Encryption Management** window, enable encryption of your data. For more information, see [Manage Data Encryption](../../SetupAndAdministration/manage-data-encryption.md).  
  
## See Also  
 OCR Service Setup   
 OCR Service Setup   
 [How to: Use OCR to Turn PDF and Image Files into Electronic Documents](../../BusinessFunctionality/DataExchange/how-to-use-ocr-to-turn-pdf-and-image-files-into-electronic-documents.md)   
 [Manage Data Encryption](../../SetupAndAdministration/manage-data-encryption.md)   
 [Incoming Documents](../../BusinessFunctionality/IncomingDocuments/incoming-documents.md)   
 [Business Functionality](../Topic/Business%20Functionality.md)