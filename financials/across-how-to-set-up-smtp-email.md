---
    title: How to Set Up SMTP Email | Microsoft Docs
    description: To send e-mails from ADD INCLUDE<!--[!INCLUDE[navnow](includes/navnow_md.md)]--> using an SMTP server, you must fill the **SMTP Mail Setup** window.
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
# How to: Set Up SMTP Email
To send e-mails from ADD INCLUDE<!--[!INCLUDE[navnow](includes/navnow_md.md)]--> using an SMTP server, you must fill the **SMTP Mail Setup** window.  
  
 E-mail sending is used for several features in ADD INCLUDE<!--[!INCLUDE[navnow](includes/workflow.md).  
  
 E-mails that are sent from ADD INCLUDE<!--[!INCLUDE[navnow](includes/how-to-manage-notification-templates.md).  
  
### To set up SMTP e-mail  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **SMTP Mail Setup**, and then choose the related link.  
  
2.  Fill the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**SMTP Server**|Specify the name of the SMTP server.|  
    |**SMTP Server Port**|Specify a port for the SMTP server. The default port is 25. **Note:**  When you set up the port, make sure that incoming and outgoing communications on the port is enabled for all clients and the Microsoft Dynamics NAV Server. Check your firewall settings.|  
    |**Authentication**|Specify the type of authentication that the SMTP server uses.<br /><br /> The default setting is **Anonymous**, which requires no user ID or password information. On an Azure deployment, use **Basic**.|  
    |**Secure Connection**|Specify if the SMTP server setup requires a encrypted channel that uses a cryptography or security protocol, such as secure socket layers (SSL).|  
  
3.  Choose the **OK** button.  
  
 For more information about SMTP e-mail systems, see [Configure SMTP E-mail (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=263830).  
  
## See Also  
 [How to: Manage Notification Templates](across-how-to-manage-notification-templates.md)   
 SMTP Mail Setup   
 [Workflow](across-workflow.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Configure SMTP E-mail (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=263830)