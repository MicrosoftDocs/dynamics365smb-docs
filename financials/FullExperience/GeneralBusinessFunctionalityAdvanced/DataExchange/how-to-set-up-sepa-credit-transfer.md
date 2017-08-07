---
    title: How to Set Up an OCR Service | Microsoft Docs
    description: You use an external provider of OCR services to have PDF or image files turned into electronic documents that can be converted to document records in ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/how-to-use-ocr-to-turn-pdf-and-image-files-into-electronic-documents.md).
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Set Up an OCR Service
You use an external provider of OCR services to have PDF or image files turned into electronic documents that can be converted to document records in ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/how-to-use-ocr-to-turn-pdf-and-image-files-into-electronic-documents.md).  
  
### To set up an OCR service  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **OCR Service Setup**, and then choose the related link.  
  
2.  Fill the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**User Name**|Specify the user name that represents your company’s login to the OCR service.|  
    |**Password**|Specify the password that is used for your company’s login to the OCR service.|  
    |**Authorization Key**|Specify the authorization key that is used for your company’s login to the OCR service.|  
    |**Default OCR Document Template**|Specify the document template that must be used by default for electronic documents that are received from the OCR service. Chose the field to pick a supported document template from the **OCR Service Document Templates** window.<br /><br /> **NOTE:** To see any new document templates that the OCR service supports, choose the **Update Document Templates List** button in the **OCR Service Document Templates** window.|  
    |**Enabled**|Specify if the service is enabled.<br /><br /> **NOTE:** As soon as you enable the service, at least two job queue entries are created to process the traffic of electronic documents in and out of ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/dyn_nav_md.md)]-->. When you disable the service, the job queue entries are deleted.|  
    |**Sign-up URL**|Specify the Web page where you sign up for the OCR service.|  
    |**Service URL**|Specify the address of the OCR service, which will be called when you send and receive files for OCR.|  
    |**Sign-in URL**|Specify the sign in page for the OCR service, which is where you enter your company’s user name, password, and authorization key to sign in to the service.|  
  
> [!NOTE]  
>  It is recommended that you protect the logon information that you enter in the **OCR Service Setup** window. You can encrypt data on the Microsoft Dynamics NAV Server by generating new or importing existing encryption keys that you enable on the Microsoft Dynamics NAV Server instance that connects to the database. This is described in the following procedure.  
  
### To encrypt your login information  
  
1.  In the **OCR Service Setup** window, on the **Home** tab, in the **Encryption** group, choose **Encryption Management**.  
  
2.  In the **Data Encryption Management** window, enable encryption of your data. For more information, see [Manage Data Encryption](../manage-data-encryption.md).  
  
## See Also  
 OCR Service Setup   
 OCR Service Setup   
 [How to: Use OCR to Turn PDF and Image Files into Electronic Documents](../how-to-use-ocr-to-turn-pdf-and-image-files-into-electronic-documents.md)   
 [Manage Data Encryption](../manage-data-encryption.md)   
 [Incoming Documents](../incoming-documents.md)   
 [Business Functionality](../Business%20Functionality.md)