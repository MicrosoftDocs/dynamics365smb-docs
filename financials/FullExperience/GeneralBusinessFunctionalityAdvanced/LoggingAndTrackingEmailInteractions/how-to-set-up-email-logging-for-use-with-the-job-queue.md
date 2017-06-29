---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Set Up Email Logging for use with the Job Queue
You can run regular background processing such as email logging using a job queue. In the following procedure, you configure the ADD INCLUDE<!--[!INCLUDE[nav_server](../../includes/nav_server_md.md)]-->. When you do this, you can decide whether it makes sense in your installation to set up a unique server instance to manage your email logging. Any instance that you set up must have access to the Exchange Server and run as a user account with that access.  
  
> [!NOTE]  
>  When you are using public folders in a multiple Exchange Server environment, you may encounter delays in seeing a mail message synchronize among the servers. For example, a mail message on one server can take several minutes to be synchronized with another server on the same domain. This can manifest itself when you are using email logging with job queues.  
  
 To use email logging, you must be connected to Microsoft Exchange Server and have an email account.  
  
> [!NOTE]  
>  The email account that is used to configure email logging in ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> must have certain permissions with regard to the public folders.  
>   
>  -   When you configure email logging setup in the **Marketing Setup** window, the user name that is used for the validation of setup must have **Read** access to the public folders.  
> -   When email logging is running on the ADD INCLUDE<!--[!INCLUDE[nav_server](../../includes/nav_server_md.md)]-->, the user account credentials that are used on the server instance must have full **Read**, **Write**, and **Delete items** permission levels set on the public folders.  
>   
>  For more information, see [Managing Public Folder Permissions](http://go.microsoft.com/fwlink/?LinkId=246183).  
  
### To set up Microsoft Dynamics NAV Server  
  
1.  Open ADD INCLUDE<!--[!INCLUDE[nav_admin](../../includes/Microsoft%20Dynamics%20NAV%20Server%20Administration%20Tool.md).  
  
2.  Create a new server instance that uses a user account for the service account. The user account must have an account on an Exchange Server. For more information, see [How to: Create a Microsoft Dynamics NAV Server Instance](../FullExperience/How%20to:%20Create%20a%20Microsoft%20Dynamics%20NAV%20Server%20Instance.md).  
  
    > [!NOTE]  
    >  The user must have sufficient ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/demolong_md.md)]-->.  
  
3.  Choose **Edit**. On the **NAS Services** FastTab, in the **Startup Codeunit** field, enter the following parameter: *450*. In the **Company** field, enter the name of the company.  
  
4.  Choose **Save**, and then choose **OK**.  
  
5.  Start the server instance.  
  
6.  If there are errors in starting the queue, you can check the event viewer log. In **Control Panel**, open **Administrative Tools**, and then choose **Event Viewer**.  
  
7.  Select **Windows Logs**, and then choose **Application** to open the Services snap-in.  
  
 Review the error message and make modifications as needed. After you have verified that the server instance is running correctly, you can stop it from running. Then, set up a job queue to run on the server instance.  
  
## See Also  
 [How to: Set Up Job Queues](../FullExperience/how-to-set-up-job-queues.md)