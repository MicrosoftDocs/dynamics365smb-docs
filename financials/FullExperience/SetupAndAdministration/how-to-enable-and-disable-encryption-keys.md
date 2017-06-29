---
title: "How to: Enable and Disable Encryption Keys"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 418851b8-3bf4-4535-85cd-c49f5e20d173
caps.latest.revision: 5
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
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
# How to: Enable and Disable Encryption Keys
You can encrypt data on the [!INCLUDE[nav_server](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_server_md.md)] by generating new or importing existing encryption keys that you enable on the server.  
  
> [!NOTE]  
>  If [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] is configured with multiple service tiers, then you must first enable encryption on one server and then export the key so it can be imported to another server where you enable encryption. You cannot generate different keys within one multiple\-server environment.  
  
 You encrypt data by enabling an encryption key on a server where an encryption key exists.  
  
 You can disable data encryption, for example to access a database for which you do not have the encryption key.  
  
> [!IMPORTANT]  
>  If you disable encryption when there is no encryption key available, encrypted data will be deleted.  
  
### To enable data encryption  
  
1.  In the **Search** box, enter Data Encryption Management, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Enable Encryption**.  
  
     On the message about saving a copy of the encryption key, choose **Yes**.  
  
3.  In the **Set Password** window, enter a password that protects the encryption key, and then choose **OK**.  
  
4.  In the **Export File** window, choose **Save**, choose a safe location where the encryption key is stored, and then choose **Save**.  
  
### To disable data encryption  
  
1.  In the **Search** box, enter Data Encryption Management, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Disable Encryption**.  
  
3.  On the warning message about non\-encrypted data, choose **Yes**.  
  
## See Also  
 [How to: Export and Import Encryption Keys](../SetupAndAdministration/how-to-export-and-import-encryption-keys.md)   
 Encryption Enabled   
 Encryption Key Exists   
 [Manage Data Encryption](../SetupAndAdministration/manage-data-encryption.md)   
 [Installation Considerations for Microsoft SQL Server](../Topic/Installation%20Considerations%20for%20Microsoft%20SQL%20Server.md)   
 [How to: Configure the Microsoft Dynamics NAV Web client to Accept Host Names for Tenants](../Topic/How%20to:%20Configure%20the%20Microsoft%20Dynamics%20NAV%20Web%20client%20to%20Accept%20Host%20Names%20for%20Tenants.md)