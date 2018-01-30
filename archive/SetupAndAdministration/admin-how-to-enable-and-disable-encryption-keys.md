---
    title: How to Enable and Disable Encryption Keys | Microsoft Docs
    description: You can encrypt data on the ADD INCLUDE<!--[!INCLUDE[nav_server](../../includes/nav_server_md.md)]--> by generating new or importing existing encryption keys that you enable on the server.
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
# Enable and Disable Encryption Keys
You can encrypt data on the ADD INCLUDE<!--[!INCLUDE[nav_server](../../includes/nav_server_md.md)]--> by generating new or importing existing encryption keys that you enable on the server.  
  
> [!NOTE]  
>  If [!INCLUDE[d365fin](includes/d365fin_md.md)] is configured with multiple service tiers, then you must first enable encryption on one server and then export the key so it can be imported to another server where you enable encryption. You cannot generate different keys within one multiple-server environment.  
  
 You encrypt data by enabling an encryption key on a server where an encryption key exists.  
  
 You can disable data encryption, for example to access a database for which you do not have the encryption key.  
  
> [!IMPORTANT]  
>  If you disable encryption when there is no encryption key available, encrypted data will be deleted.  
  
### To enable data encryption  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter Data Encryption Management, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Enable Encryption**.  
  
     On the message about saving a copy of the encryption key, choose **Yes**.  
  
3.  In the **Set Password** window, enter a password that protects the encryption key, and then choose **OK**.  
  
4.  In the **Export File** window, choose **Save**, choose a safe location where the encryption key is stored, and then choose **Save**.  
  
### To disable data encryption  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter Data Encryption Management, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Disable Encryption**.  
  
3.  On the warning message about non-encrypted data, choose **Yes**.  
  
## See Also  
 [Export and Import Encryption Keys](../how-to-export-and-import-encryption-keys.md)   
 Encryption Enabled   
 Encryption Key Exists   
 [Manage Data Encryption](../manage-data-encryption.md)   
 [Installation Considerations for Microsoft SQL Server](../Installation%20Considerations%20for%20Microsoft%20SQL%20Server.md)   
 [Configure the Microsoft Dynamics NAV Web client to Accept Host Names for Tenants](../How%20to:%20Configure%20the%20Microsoft%20Dynamics%20NAV%20Web%20client%20to%20Accept%20Host%20Names%20for%20Tenants.md)