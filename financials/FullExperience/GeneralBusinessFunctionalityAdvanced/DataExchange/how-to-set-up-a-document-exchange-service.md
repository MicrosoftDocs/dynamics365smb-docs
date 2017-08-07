---
    title: How to Set Up a Document Exchange Service | Microsoft Docs
    description: You use an external service provider to exchange electronic documents with your trading partners. For more information, see [Data Exchange](../data-exchange.md).
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
# How to: Set Up a Document Exchange Service
You use an external service provider to exchange electronic documents with your trading partners. For more information, see [Data Exchange](../data-exchange.md).  
  
### To set up a document exchange service  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Doc. Exch. Service Setup**, and then choose the related link.  
  
2.  Fill the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**User Agent**|Enter any text that can be used to identify your company in document exchange processes.|  
    |**Doc. Exch. Tenant ID**|Enter the tenant in the document exchange service that represents your company. This is provided by the document exchange service provider.|  
    |**Enabled**|Specify if the service is enabled. **Note:**  As soon as you enable the service, at least two job queue entries are created to process the traffic of electronic documents in and out of ADD INCLUDE<!--[!INCLUDE[dyn_nav](includes/dyn_nav_md.md)]-->. When you disable the service, the job queue entries are deleted.|  
    |**Signup URL**|Specify the web page where you sign up for the document exchange service.|  
    |**Service URL**|Specify the address of the document exchange service, which will be called when you send and receive electronic documents.|  
    |**Login URL**|Specify the logon page for the document exchange service, which is where you enter your company’s user name and password to log on to the service.|  
    |**Consumer Key**|Enter the 3-legged OAuth key for the consumer key. This is provided by the document exchange service provider.|  
    |**Consumer Secret**|Enter the secret that protects the consumer key. This is provided by the document exchange service provider.|  
    |**Token**|Enter the 3-legged OAuth key for the token. This is provided by the document exchange service provider.|  
    |**Token Secret**|Enter the secret that protects the token. This is provided by the document exchange service provider.|  
  
> [!NOTE]  
>  It is recommended that you protect the logon information that you enter in the **VAN Service Setup** window. You can encrypt data on the Microsoft Dynamics NAV Server by generating new or importing existing encryption keys that you enable on the Microsoft Dynamics NAV Server instance that connects to the database. This is described in the following procedure.  
  
### To encrypt your logon information  
  
1.  In the **VAN Service Setup** window, on the **Home** tab, in the **Encryption** group, choose **Encryption Management**.  
  
2.  In the **Data Encryption Management** window, enable encryption of your data. For more information, see [Manage Data Encryption](../manage-data-encryption.md).  
  
## See Also  
 Doc. Exch. Service Setup   
 [How to: Set Up the Tradeshift Service to Dispatch Electronic Documents](../how-to-set-up-a-document-exchange-service.md)   
 [How to: Send Electronic Documents](../how-to-send-electronic-documents.md)   
 [How to: Receive and Convert Electronic Documents](../how-to-receive-and-convert-electronic-documents.md)   
 [Data Exchange](../data-exchange.md)   
 [Incoming Documents](../incoming-documents.md)   
 [Business Functionality](../Business%20Functionality.md)