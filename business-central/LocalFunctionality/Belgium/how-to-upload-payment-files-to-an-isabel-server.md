---
    title: How to Upload Payment Files to an Isabel Server
    description: Payment files can be uploaded using the **IBS Logs** window. The **Upload Integration Mode** and **Download Integration Mode** fields in the **Electronic Banking Setup** window must be set to **Attended** to upload payment files.

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
# Upload Payment Files to an Isabel Server
> [!Note]
> [!INCLUDE[onprem_only](../../includes/onprem_only_md.md)]

Payment files can be uploaded using the **IBS Logs** window. The **Upload Integration Mode** and **Download Integration Mode** fields in the **Electronic Banking Setup** window must be set to **Attended** to upload payment files.  

> [!NOTE]  
>  Before you can upload payment files you must be logged on to the Isabel server.  

## To upload payment files in attended mode  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **IBS Logs**, and then choose the related link.  
2.  Choose the **Get Contract and User** action.  
3.  After verifying the payment files, a user ID and contract ID will be displayed in the **IBS User ID** and **IBS Contract ID** fields.  

    The **Upload Status** field will be set to **Ready for Upload**. If more than one contract exists on the Isabel server for the bank account, the **Upload Status** will be set to **Conflict Exists**. Select the correct contract.  

4.  Choose the **Perform Download** action. The payment files will be uploaded to the Isabel server and the **Process Status** field will be set to **Processed**.  
5.  Continue processing the payment files by signing and sending the files on the Isabel server.  

## See Also  
 [Archive IBS Log Entries](how-to-archive-ibs-log-entries.md)
