---
    title: How to Export and Import Encryption Keys | Microsoft Docs
    description: You can encrypt data on the ADD INCLUDE<!--[!INCLUDE[nav_server](../../includes/nav_server_md.md)]--> instance by generating new encryption keys or importing or changing existing encryption keys that you enable on the server instance.
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
# Export and Import Encryption Keys
You can encrypt data on the ADD INCLUDE<!--[!INCLUDE[nav_server](../../includes/nav_server_md.md)]--> instance by generating new encryption keys or importing or changing existing encryption keys that you enable on the server instance.  
  
> [!NOTE]  
>  If ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/nav_server_md.md)]--> instances), then you must first enable encryption on one server instance and then export the key so it can be imported to another server instance where you enable encryption. You cannot generate different keys within one multiple-server instance environment.  
  
## Exporting an Encryption Key  
 You export an encryption key to make a copy of the key or so that it can be imported on another server instance. Exporting an encryption key stores the encryption key that is used by the current server instance to a file on your computer or network.  
  
#### To export an encryption key  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter Data Encryption Management, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Export Encryption Key**.  
  
     On the message about saving the encryption key, choose **Yes**.  
  
3.  In the **Set Password** window, enter the password that will protect the exported key file, and then choose **OK**.  
  
4.  In the **Export File** window, choose **Save**, choose a safe location where the key file is stored, and then choose **Save**.  
  
## Importing an Encryption Key  
 You can import an encryption key to a server instance from an encryption key file that was exported from another server instance or saved as a copy when the encryption was enabled. You cannot import an encryption key on a server instance that already includes an encryption key. In this case, you must change the encryption key instead.  
  
#### To import an encryption key  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter Data Encryption Management, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Import Encryption Key**.  
  
3.  In the **Select a key file to import** window, choose the encryption key file, and then choose **Open**.  
  
4.  In the **Password** window, enter the password that protects the key file, and then choose **OK**.  
  
## Changing an Encryption Key  
 If a server instance already has an encryption key, then you can replace the current encryption key with an encryption key that is stored in an encryption key file that was exported from another server.  
  
> [!NOTE]  
>  If [!INCLUDE[d365fin](includes/d365fin_md.md)] is configured with multiple server instances, when you change the encryption key on a server instance, then the old encryption key is no longer valid on the other server instances. To enable the new encryption key on the other server instances, import it on each server instance.  
  
#### To change an encryption key  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter Data Encryption Management, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Change Encryption Key**.  
  
3.  In the **Select a key file to import** window, choose the encryption key file, and then choose **Open**.  
  
4.  In the **Password** window, enter the password that protects the key file, and then choose **OK**.  
  
## See Also  
 [Enable and Disable Encryption Keys](../how-to-enable-and-disable-encryption-keys.md)   
 Encryption Enabled   
 Encryption Key Exists   
 [Manage Data Encryption](../manage-data-encryption.md)   
 [Installation Considerations for Microsoft SQL Server](../Installation%20Considerations%20for%20Microsoft%20SQL%20Server.md)   
 [Configure the Microsoft Dynamics NAV Web client to Accept Host Names for Tenants](../How%20to:%20Configure%20the%20Microsoft%20Dynamics%20NAV%20Web%20client%20to%20Accept%20Host%20Names%20for%20Tenants.md)