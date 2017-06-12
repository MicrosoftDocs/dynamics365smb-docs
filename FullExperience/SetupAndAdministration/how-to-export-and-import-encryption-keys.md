---
title: "How to: Export and Import Encryption Keys"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: d9fa6b1e-2c78-4ef9-9a37-4eaf7c031299
caps.latest.revision: 6
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
# How to: Export and Import Encryption Keys
You can encrypt data on the [!INCLUDE[nav_server](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_server_md.md)] instance by generating new encryption keys or importing or changing existing encryption keys that you enable on the server instance.  
  
> [!NOTE]  
>  If [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] is configured with multiple service tiers \([!INCLUDE[nav_server](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_server_md.md)] instances\), then you must first enable encryption on one server instance and then export the key so it can be imported to another server instance where you enable encryption. You cannot generate different keys within one multiple\-server instance environment.  
  
## Exporting an Encryption Key  
 You export an encryption key to make a copy of the key or so that it can be imported on another server instance. Exporting an encryption key stores the encryption key that is used by the current server instance to a file on your computer or network.  
  
#### To export an encryption key  
  
1.  In the **Search** box, enter Data Encryption Management, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Export Encryption Key**.  
  
     On the message about saving the encryption key, choose **Yes**.  
  
3.  In the **Set Password** window, enter the password that will protect the exported key file, and then choose **OK**.  
  
4.  In the **Export File** window, choose **Save**, choose a safe location where the key file is stored, and then choose **Save**.  
  
## Importing an Encryption Key  
 You can import an encryption key to a server instance from an encryption key file that was exported from another server instance or saved as a copy when the encryption was enabled. You cannot import an encryption key on a server instance that already includes an encryption key. In this case, you must change the encryption key instead.  
  
#### To import an encryption key  
  
1.  In the **Search** box, enter Data Encryption Management, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Import Encryption Key**.  
  
3.  In the **Select a key file to import** window, choose the encryption key file, and then choose **Open**.  
  
4.  In the **Password** window, enter the password that protects the key file, and then choose **OK**.  
  
## Changing an Encryption Key  
 If a server instance already has an encryption key, then you can replace the current encryption key with an encryption key that is stored in an encryption key file that was exported from another server.  
  
> [!NOTE]  
>  If [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] is configured with multiple server instances, when you change the encryption key on a server instance, then the old encryption key is no longer valid on the other server instances. To enable the new encryption key on the other server instances, import it on each server instance.  
  
#### To change an encryption key  
  
1.  In the **Search** box, enter Data Encryption Management, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Change Encryption Key**.  
  
3.  In the **Select a key file to import** window, choose the encryption key file, and then choose **Open**.  
  
4.  In the **Password** window, enter the password that protects the key file, and then choose **OK**.  
  
## See Also  
 [How to: Enable and Disable Encryption Keys](../SetupAndAdministration/how-to-enable-and-disable-encryption-keys.md)   
 [Encryption Enabled](../Topic/\($%20N_9905_2%20Encryption%20Enabled%20$\).md)   
 [Encryption Key Exists](../Topic/\($%20N_9905_3%20Encryption%20Key%20Exists%20$\).md)   
 [Manage Data Encryption](../SetupAndAdministration/manage-data-encryption.md)   
 [Installation Considerations for Microsoft SQL Server](../Topic/Installation%20Considerations%20for%20Microsoft%20SQL%20Server.md)   
 [How to: Configure the Microsoft Dynamics NAV Web client to Accept Host Names for Tenants](../Topic/How%20to:%20Configure%20the%20Microsoft%20Dynamics%20NAV%20Web%20client%20to%20Accept%20Host%20Names%20for%20Tenants.md)