---
    title: Manage Data Encryption | Microsoft Docs
    description: You can encrypt data on the ADD INCLUDE<!--[!INCLUDE[nav_server](../../includes/nav_server_md.md)]--> instance that connects to the database.
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
# Manage Data Encryption
You can encrypt data on the ADD INCLUDE<!--[!INCLUDE[nav_server](../../includes/nav_server_md.md)]--> instance that connects to the database.  
  
 If ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/nav_server_md.md)]--> instances), then you must first enable encryption on one server instance, and then export the key so it can be imported to other server instances where you enable encryption.  
  
> [!IMPORTANT]  
>  If you export companies and other data that is secured by data encryption, then remember to also export the encryption key so that you can access the data after you import it into another database, for example when you restore a backup. Creating a backup of encrypted data involves the following high-level steps.  
>   
>  1.  Export the data from one database. For more information, see [Export and Import Companies and Other Data in Clients](../How%20to:%20Export%20and%20Import%20Companies%20and%20Other%20Data%20in%20Clients.md).  
> 2.  Export the data encryption key. For more information, see [Export and Import Encryption Keys](../how-to-export-and-import-encryption-keys.md).  
> 3.  Import the data into another database. For more information, see [Export and Import Companies and Other Data in Clients](../How%20to:%20Export%20and%20Import%20Companies%20and%20Other%20Data%20in%20Clients.md).  
> 4.  Import the data encryption key. For more information, see [Export and Import Encryption Keys](../how-to-export-and-import-encryption-keys.md).  
  
 The following table describes a sequence of tasks, with links to the topics that describe them.   
  
|**To**|**See**|  
|------------|-------------|  
|Export a configuration key from one ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/how-to-export-and-import-encryption-keys.md)|  
|Enable data encryption on a ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/how-to-enable-and-disable-encryption-keys.md)|  
  
## See Also  
 Encryption Enabled   
 Encryption Key Exists   
 [Manage Data Encryption](../manage-data-encryption.md)   
 [Exporting and Importing Companies and Other Data](../Exporting%20and%20Importing%20Companies%20and%20Other%20Data.md)   
 [Installation Considerations for Microsoft SQL Server](../Installation%20Considerations%20for%20Microsoft%20SQL%20Server.md)   
 [Configure the Microsoft Dynamics NAV Web client to Accept Host Names for Tenants](../How%20to:%20Configure%20the%20Microsoft%20Dynamics%20NAV%20Web%20client%20to%20Accept%20Host%20Names%20for%20Tenants.md)