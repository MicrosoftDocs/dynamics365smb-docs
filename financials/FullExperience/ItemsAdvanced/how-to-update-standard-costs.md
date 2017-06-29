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
# How to: Update Standard Costs
You must periodically update the standard costs of components and roll the new costs up to the parent item. The process typically consists of the following four steps:  
  
1.  Update costs at the component and capacity levels. For more information, see Suggest Item Standard Cost.  
  
2.  Consolidate and roll up the component and capacity costs to calculate the total manufacturing or assembly cost of the items. For more information, see Roll Up Standard Cost.  
  
3.  Implement the standard costs that are entered when you run the previous batch jobs. The standard costs do not take effect until they are implemented. For more information, see Implement Standard Cost Changes.  
  
4.  Implement the changes to update the **Unit Cost** field on the item card and perform inventory revaluation. For more information, see Revaluation Journal.  
  
 For more information, see [About Calculating Standard Cost](../Finance/about-calculating-standard-cost.md).  
  
 After you understand the process, you can use the following summary of steps.  
  
> [!NOTE]  
>  To preview changes that the following processes make to your data, it is recommended that you perform the steps in the ADD INCLUDE<!--[!INCLUDE[demolong](../ApplicationDesign/includes/demolong_md.md)]--> before working in the live company.  
  
### To update standard costs  
  
1.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**Adjust Cost-Item Entries** batch job.  
  
2.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**Post Inventory Cost to G\/L** batch job.  
  
3.  Open the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**Standard Cost Worksheet** and use one or more of the following functions:  
  
    1.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**Suggest Item Standard Cost** batch job.  
  
    2.  Review the results and make changes as necessary.  
  
    3.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**Suggest Capacity Standard Cost** batch job.  
  
    4.  Review the results and make changes as necessary.  
  
4.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**Roll up Standard Cost** batch job.  
  
5.  Review the results and make changes as necessary.  
  
6.  Run the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**Implement Standard Cost Changes** batch job.  
  
7.  Review and post the ![Shortcut icon](../BusinessFunctionality/OnlineMaps/media/shortcutcoldicon.gif "shortcutColdIcon")**Revaluation Journal**, which has been populated with entries from previous steps in this process.  
  
## See Also  
 Standard Cost Worksheet   
 [About Calculating Standard Cost](../Finance/about-calculating-standard-cost.md)   
 [Manage Inventory Costs](../Finance/manage-inventory-costs.md)   
 Unit Cost   
 [Design Details: Costing Methods](../ApplicationDesign/design-details-costing-methods.md)   
 [How to: Fill In Revaluation Journals Manually](../DesignAndEngineering/how-to-fill-in-revaluation-journals-manually.md)   
 [How to: Fill In the Revaluation Journal with the Batch Job](../DesignAndEngineering/how-to-fill-in-the-revaluation-journal-with-the-batch-job.md)