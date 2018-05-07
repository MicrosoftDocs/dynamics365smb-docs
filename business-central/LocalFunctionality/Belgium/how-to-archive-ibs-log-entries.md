---
    title: How to Archive IBS Log Entries
    description: IBS log lines that have a process status of **Processed** can be archived. IBS logs contain information about electronic banking files that are created during Isabel electronic bank transfers.

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
# Archive IBS Log Entries
> [!Note]
> [!INCLUDE[onprem_only](../../includes/onprem_only_md.md)]

IBS log lines that have a process status of **Processed** can be archived. IBS logs contain information about electronic banking files that are created during Isabel electronic bank transfers.  

Isabel is a third-party software program that is frequently used in Belgium to manage and transfer electronic banking files. Isabel currently supports bank transactions, such as SEPA credit transfers, automated bank orders, and CODA files.  

## To archive an IBS log entry  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **IBS Logs**, and then choose the related link.  
2.  Select the line that you want to archive, and then choose the **Archive** action.  
3.  A message appears asking if you want to archive the IBS log records.  
4.  Choose the **Yes** button.  

    > [!NOTE]  
    >  The **Process Status** field for the line will now be **Archived**. You can delete a record with a status of **Archived**.  

## See Also  
[Belgium Local Functionality](belgium-local-functionality.md)
