---
    title: Troubleshooting: Record Locked by Another User | Microsoft Docs
    description: If you have ended ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]-->, you may experience the following error message: “Record locked by another user”. This is caused by a lock on data in a job that is still running on the server.
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
# Troubleshooting: Record Locked by Another User
If you have ended ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]-->, you may experience the following error message: “Record locked by another user”. This is caused by a lock on data in a job that is still running on the server.  
  
 To release this lock, you must either shut down the SQL server manually, or restart the Microsoft Dynamics NAV Server session using the Microsoft Dynamics NAV Server Administration tool.