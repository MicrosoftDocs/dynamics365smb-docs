---
    title: How to: Create a Record from a  Configuration Template | Microsoft Docs
    description: You can use the structure of data that is contained in the data templates to convert your information into records in the database, one-by-one. To do so, you use the **Create Instance** function. This is a miniature version of the data migration process and can be useful for prototyping or treating smaller data creation tasks.
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
# How to: Create a Record from a  Configuration Template
You can use the structure of data that is contained in the data templates to convert your information into records in the database, one-by-one. To do so, you use the **Create Instance** function. This is a miniature version of the data migration process and can be useful for prototyping or treating smaller data creation tasks.  
  
 The following steps illustrate how to create an item card from an item data template. You can create a record from any data template using the same procedure.  
  
### To create a record from a configuration template  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Configuration Templates**, and then choose the related link.  
  
2.  In the **Setup Master Templates** window, select the item template that you have created and choose **Edit**. For more information on how to create a template, see [How to: Create a Configuration Template](../how-to-create-a-configuration-template.md).  
  
3.  On the **Actions** tab, choose **Create Instance**. An item card is created.  
  
4.  Choose the **OK** button.  
  
5.  To review the new item card, Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.  
  
6.  Open the new item card.  
  
7.  Expand various FastTabs, and verify that the information was created correctly on them.  
  
 After you have created and verified the structure of the configuration templates, you can continue with the actual migration of your customer’s data into the new [!INCLUDE[d365fin](../../includes/d365fin_md.md)] database.  
  
## See Also  
 [How to: Use a Configuration Template on a Record](../how-to-use-a-configuration-template-on-a-record.md)