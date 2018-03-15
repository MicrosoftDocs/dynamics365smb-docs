---
    title: How to Set Up Simulation
    description: You can create and post simulation entries to the general ledger without affecting the real accounting.

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
# Set Up Simulation
You can create and post simulation entries to the general ledger without affecting the real accounting.  

Before you can start to use the simulation functionality, you must set up a source code and a number series, and you must add this information to a general journal template.  

## To set up simulation  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Source Codes**, and then choose the related link.  
2.  In the **Source Codes** window, create a new record and fill in the fields.  

    > [!IMPORTANT]  
    >  Select the **Simulation** field.  

3.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **No. Series**, and then choose the related link for the **Setup** area.  
4.  In the **No. Series** window, create a new record and fill in the fields. Drill down on the **Starting No.** field to set up additional information for the number series.  
5.  Select the **Default Nos.** field and the **Manual Nos.** field.  
6.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journal Templates**, and then choose the related link.  
7.  In the **General Journal Templates** window, create a new record and fill in the fields. In the **Type** field, select General, and specify your new number series and source code in the **No. Series** field and the **Source Code** field.  

Now you can create simulation entries using the general journal.  

## See Also  
 [Create Simulation Entries](how-to-create-simulation-entries.md)   
 [Delete Simulation Entries](how-to-delete-simulation-entries.md)   
 [Transfer Simulation Entries](how-to-transfer-simulation-entries.md)
