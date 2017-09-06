---
    title: Troubleshooting: Compression Option in IIS | Microsoft Docs
    description: Users may experience slow mobile client responses especially noticeable when they are running with a slow network connection. The reason for the mobile client running slowly can be that the dynamic compression is not enabled on the IIS server.
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
# Troubleshooting: Compression Option in IIS
Users may experience slow mobile client responses especially noticeable when they are running with a slow network connection. The reason for the mobile client running slowly can be that the dynamic compression is not enabled on the IIS server.  
  
## Resolution  
 The IIS administrator must make sure that dynamic compression is enabled on the IIS. For more information, see [Enable HTTP Compression of Dynamic Content](http://go.microsoft.com/fwlink/?LinkId=392634)  
  
> [!NOTE]  
>  Dynamic compression is enabled by the ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/nav_web_server_md.md)]-->.  
  
## See Also  
 [Troubleshooting Using Microsoft Dynamics NAV](troubleshooting-using-microsoft-dynamics-nav.md)   
 [Troubleshooting the Microsoft Dynamics NAV Universal App](../Troubleshooting%20the%20Microsoft%20Dynamics%20NAV%20Universal%20App.md)