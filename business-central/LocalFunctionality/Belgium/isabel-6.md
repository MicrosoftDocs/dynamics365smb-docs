---
    title: Isabel 6
    description: The Isabel organization has developed a Client Isabel Synchronizer (CIS) platform that allows [!INCLUDE[d365fin](../../includes/d365fin_md.md)] to securely integrate with Isabel. CIS handles document exchange to and from the Isabel server.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Isabel 6
The Isabel organization has developed a Client Isabel Synchronizer (CIS) platform that allows [!INCLUDE[d365fin](../../includes/d365fin_md.md)] to securely integrate with Isabel. CIS handles document exchange to and from the Isabel server.  

To upload or download the bank files, you will have to set up your environment to work with Isabel. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] communicates to the CIS.dll through a COM wrapper.  

To set up your system to work with Isabel, complete the following:  

- Install the Isabel security components. For more information, see the download area on the [Isabel website](http://go.microsoft.com/fwlink/?LinkId=210323).  

- Install the COM wrapper that is manufactured by the Isabel organization. This wrapper is included with the Isabel GO 6.20 package.  

- Register the COM wrapper on your computer. At the command prompt, locate the CIS.dll and then execute the **regsvr32 CISComWrapper.dll** command.  

## See Also  
 [Isabel website](http://go.microsoft.com/fwlink/?LinkId=210323)   
 [Belgian Electronic Banking](belgian-electronic-banking.md)   
 [Set Up Electronic Banking](how-to-set-up-electronic-banking.md)
