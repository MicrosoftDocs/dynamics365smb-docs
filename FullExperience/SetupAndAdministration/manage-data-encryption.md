---
title: "Manage Data Encryption"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 51765249-7315-4373-a2ce-e298f8147c00
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
# Manage Data Encryption
You can encrypt data on the [!INCLUDE[nav_server](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_server_md.md)] by generating new or importing existing encryption keys that you enable on the [!INCLUDE[nav_server](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_server_md.md)] instance that connects to the database.  
  
 If [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] is configured with multiple service tiers \([!INCLUDE[nav_server](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_server_md.md)] instances\), then you must first enable encryption on one server instance, and then export the key so it can be imported to other server instances where you enable encryption.  
  
> [!IMPORTANT]  
>  If you export companies and other data that is secured by data encryption, then remember to also export the encryption key so that you can access the data after you import it into another database, for example when you restore a backup. Creating a backup of encrypted data involves the following high\-level steps.  
>   
>  1.  Export the data from one database. For more information, see [How to: Export and Import Companies and Other Data in Clients](../Topic/How%20to:%20Export%20and%20Import%20Companies%20and%20Other%20Data%20in%20Clients.md).  
> 2.  Export the data encryption key. For more information, see [How to: Export and Import Encryption Keys](../SetupAndAdministration/how-to-export-and-import-encryption-keys.md).  
> 3.  Import the data into another database. For more information, see [How to: Export and Import Companies and Other Data in Clients](../Topic/How%20to:%20Export%20and%20Import%20Companies%20and%20Other%20Data%20in%20Clients.md).  
> 4.  Import the data encryption key. For more information, see [How to: Export and Import Encryption Keys](../SetupAndAdministration/how-to-export-and-import-encryption-keys.md).  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Export a configuration key from one [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] server instance so that it can be imported on another server instance or to make a copy of the key.|[How to: Export and Import Encryption Keys](../SetupAndAdministration/how-to-export-and-import-encryption-keys.md)|  
|Enable data encryption on a [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] server instance where an encryption key exists. Disable data encryption, for example to access a database for which you do not have the encryption key.|[How to: Enable and Disable Encryption Keys](../SetupAndAdministration/how-to-enable-and-disable-encryption-keys.md)|  
  
## See Also  
 [Encryption Enabled](../Topic/\($%20N_9905_2%20Encryption%20Enabled%20$\).md)   
 [Encryption Key Exists](../Topic/\($%20N_9905_3%20Encryption%20Key%20Exists%20$\).md)   
 [Manage Data Encryption](../SetupAndAdministration/manage-data-encryption.md)   
 [Exporting and Importing Companies and Other Data](../Topic/Exporting%20and%20Importing%20Companies%20and%20Other%20Data.md)   
 [Installation Considerations for Microsoft SQL Server](../Topic/Installation%20Considerations%20for%20Microsoft%20SQL%20Server.md)   
 [How to: Configure the Microsoft Dynamics NAV Web client to Accept Host Names for Tenants](../Topic/How%20to:%20Configure%20the%20Microsoft%20Dynamics%20NAV%20Web%20client%20to%20Accept%20Host%20Names%20for%20Tenants.md)