---
    title: Troubleshooting: The File that You Are Trying to Use Is Too Large | Microsoft Docs
    description: If you are trying to upload a large image file that is larger than 30 MB, such as a high-resolution photo, [!INCLUDE[d365fin](includes/d365fin_md.md)] will give you an error message that says that the file that you are trying to upload is too large. This behavior can be changed by modifying the IIS configuration to support large file uploads.
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
# Troubleshooting: The File that You Are Trying to Use Is Too Large
If you are trying to upload a large image file that is larger than 30 MB, such as a high-resolution photo, [!INCLUDE[d365fin](includes/d365fin_md.md)] will give you an error message that says that the file that you are trying to upload is too large. This behavior can be changed by modifying the IIS configuration to support large file uploads.  
  
## Resolution  
 The IIS administrator should make the following changes in the Internet Information Services (IIS) Manager.  
  
1.  Launch IIS Manager.  
  
2.  In the left pane of IIS Manager, select the [!INCLUDE[d365fin](includes/d365fin_md.md)] web site, and choose **Request Filtering**.  
  
3.  In the **Actions** pane of the **Request Filtering** window, choose **Edit Feature Settings**.  
  
4.  Set the field **Maximum allowed content length (Bytes)** to an appropriate value, such as **100000000** and choose the **OK** button.  
  
5.  In the left pane of IIS Manager, select the [!INCLUDE[d365fin](includes/d365fin_md.md)] web site, and choose **Configuration Editor**.  
  
6.  In the **Configuration Editor**, make sure that the **From** field is set to ADD INCLUDE<!--[!INCLUDE[navnowlong](../../includes/navnowlong_md.md)]--> Web Client Web.config.  
  
7.  Set the **Section** field to **system.web/httpRuntime** and now several properties will appear.  
  
8.  Set **maxRequestLength** to an appropriate value, such as **100000** (kilobytes) and choose the **Apply** action on the right.  
  
9. Close IIS Manager.  
  
 The new settings should take effect immediately without refreshing the IIS or the site.  
  
## See Also  
 [Troubleshooting Using Microsoft Dynamics NAV](troubleshooting-using-microsoft-dynamics-nav.md)