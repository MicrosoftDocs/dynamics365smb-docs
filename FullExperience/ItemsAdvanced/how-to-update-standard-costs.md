---
title: "How to: Update Standard Costs"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "standard costs, updating"
  - "costs, updating standard"
ms.assetid: e552d7c8-667e-42aa-a61e-c936953c829a
caps.latest.revision: 4
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Update Standard Costs
You must periodically update the standard costs of components and roll the new costs up to the parent item. The process typically consists of the following four steps:  
  
1.  Update costs at the component and capacity levels. For more information, see [\($ B\_5851 Suggest Item Standard Cost $\)](../Topic/\($%20B_5851%20Suggest%20Item%20Standard%20Cost%20$\).md).  
  
2.  Consolidate and roll up the component and capacity costs to calculate the total manufacturing or assembly cost of the items. For more information, see [\($ B\_5854 Roll Up Standard Cost $\)](../Topic/\($%20B_5854%20Roll%20Up%20Standard%20Cost%20$\).md).  
  
3.  Implement the standard costs that are entered when you run the previous batch jobs. The standard costs do not take effect until they are implemented. For more information, see [\($ B\_5855 Implement Standard Cost Changes $\)](../Topic/\($%20B_5855%20Implement%20Standard%20Cost%20Changes%20$\).md).  
  
4.  Implement the changes to update the **Unit Cost** field on the item card and perform inventory revaluation. For more information, see [\($ N\_5803 Revaluation Journal $\)](../Topic/\($%20N_5803%20Revaluation%20Journal%20$\).md).  
  
 For more information, see [About Calculating Standard Cost](../Finance/about-calculating-standard-cost.md).  
  
 After you understand the process, you can use the following summary of steps.  
  
> [!NOTE]  
>  To preview changes that the following processes make to your data, it is recommended that you perform the steps in the [!INCLUDE[demolong](../ApplicationDesign/includes/demolong_md.md)] before working in the live company.  
  
### To update standard costs  
  
1.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ B\_795 Adjust Cost\-Item Entries $\)](DynamicsNAV:////runreport?report=795)** batch job.  
  
2.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ B\_1002 Post Inventory Cost to G\/L $\)](DynamicsNAV:////runreport?report=1002)** batch job.  
  
3.  Open the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ N\_5841 Standard Cost Worksheet $\)](DynamicsNAV:////runpage?Page=5841)** and use one or more of the following functions:  
  
    1.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ B\_5851 Suggest Item Standard Cost $\)](DynamicsNAV:////runreport?report=5851)** batch job.  
  
    2.  Review the results and make changes as necessary.  
  
    3.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ B\_5852 Suggest Capacity Standard Cost $\)](DynamicsNAV:////runreport?report=5852)** batch job.  
  
    4.  Review the results and make changes as necessary.  
  
4.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ B\_5854 Roll up Standard Cost $\)](DynamicsNAV:////runreport?report=5854)** batch job.  
  
5.  Review the results and make changes as necessary.  
  
6.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ B\_5855 Implement Standard Cost Changes $\)](DynamicsNAV:////runreport?report=5855)** batch job.  
  
7.  Review and post the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**[\($ N\_5803 Revaluation Journal $\)](DynamicsNAV:////runpage?Page=5803)**, which has been populated with entries from previous steps in this process.  
  
## See Also  
 [\($ N\_5841 Standard Cost Worksheet $\)](../Finance/-$-n_5841-standard-cost-worksheet-$-.md)   
 [About Calculating Standard Cost](../Finance/about-calculating-standard-cost.md)   
 [Manage Inventory Costs](../Finance/manage-inventory-costs.md)   
 [\($ T\_27\_22 Unit Cost $\)](../Finance/-$-t_27_22-unit-cost-$-.md)   
 [Design Details: Costing Methods](../ApplicationDesign/design-details-costing-methods.md)   
 [How to: Fill In Revaluation Journals Manually](../DesignAndEngineering/how-to-fill-in-revaluation-journals-manually.md)   
 [How to: Fill In the Revaluation Journal with the Batch Job](../DesignAndEngineering/how-to-fill-in-the-revaluation-journal-with-the-batch-job.md)