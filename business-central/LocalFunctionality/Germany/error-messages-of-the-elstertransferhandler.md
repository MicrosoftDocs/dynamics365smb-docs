---
    title: Error Messages of the ElsterTransferHandler
    description: When Business Central submits sales VAT advance notifications, errors can occur.

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
# Error Messages of the ElsterTransferHandler
When [!INCLUDE[d365fin](../../includes/d365fin_md.md)] submits sales VAT advance notifications, errors can occur.  

For example, if the configuration file for the Microsoft.Dynamics.ElsterTransferHandler.dll assembly does not contain the correct friendly name of the public certificate, the ELSTER portal returns error 3400, and [!INCLUDE[d365fin](../../includes/d365fin_md.md)] displays the corresponding error message.  

## Error Messages  
The following table lists the error messages that the ELSTER portal sends to [!INCLUDE[d365fin](../../includes/d365fin_md.md)].  

|**Error number**|**Description**|  
|----------------------|-------------------------------------------|  
|1000|ELSTER cannot identify the sender as [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. The Microsoft.Dynamics.ElsterTransferHandler.dll assembly can only be used with Microsoft Dynamics products.|  
|2000|No connection could be made to the OFD servers while transmitting data. This can be a problem with your network connection. Check your network configuration, or try again later.|  
|2100|The XML file could not been sent because the connection was lost unexpectedly.|  
|2200|No connection could be made to the OFD servers while receiving data. This can be a problem with your network connection. Check your network configuration, or try again later.|  
|2300|The response document could not been received because the connection was lost unexpectedly.|  
|3000|ELSTER could not access the user-specific certificate. You must make sure that the certificate is installed correctly.|  
|3100|You have submitted a document but you do not have access to the certificate store. You must make sure that the certificate is installed correctly.|  
|3200|The user-specific certificate could not be found. You must make sure that the certificate is installed correctly.|  
|3300|The specified certificate does not have a private key, or the password for the private key is incorrect. You must make sure that the certificate is installed correctly.|  
|3400|The public certificate of the OFD could not be opened. You must make sure that the certificate is installed correctly.|  
|4000|The response document could not be decrypted because the private key does not match the public key that was used for encryption.|  
|4100|The response document could not be decrypted. Data can have been damaged during transmission. You must submit the document again.|  
|5000|The document could not be compressed. This can be caused by a lack of sufficient memory on the computer, or that the operating system has stopped the compression process. You must submit the document again.|  
|5100|The document could not be decompressed. You must submit the document again.|  
|6000|The proxy server does not respond. You must make sure that the setup of sales VAT advance notifications is correct in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
|6100|The user is not able to connect to the server. You must make sure that the setup of sales VAT advance notifications is correct in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
|6200|The user could not be registered on the proxy server. You must make sure that the setup of sales VAT advance notifications is correct in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
|7000|The data could not be signed because the configured certificate cannot be used for signing data. You must make sure that the setup of sales VAT advance notifications is correct in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
|7100|The XML document could not be signed. This can be caused by a lack of sufficient memory on the computer, or that the operating system has stopped the compression process.|  
|9000|An error occurred when the ELSTER portal was trying to read the configuration of the certificate. You must verify the content of the generated XML document.|  

## See Also  
 [ELSTER Transmission Overview](elster-transmission-overview.md)   
 [Set Up Sales VAT Advance Notifications for ELSTER](how-to-set-up-sales-vat-advance-notifications-for-elster.md)
