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
# How to: Set Up New Budgets
You can have multiple budgets for identical time periods by creating budgets with separate names. First, you set up the budget name and enter the budget figures. The budget name is then included on all the budget entries you create.  
  
 When you create a budget, you can define four dimensions for each budget. These budget-specific dimensions are called budget dimensions. You select the budget dimensions for each budget from among the dimensions you have already set up. Budget dimensions can be used to set filters on a budget and to add dimension information to budget entries. For more information, see Dimension.  
  
### To set up a new budget  
  
1.  In the **Search** box, enter **G\/L Budgets**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Manage** group, choose **Edit List** to open the **G\/L Budget Names** window.  
  
3.  In the **G\/L Budget Names** window, create a new line and fill in the relevant fields  
  
4.  On the **Home** tab, in the **Process** group, choose **Edit Budget** to open the **Budget** window.  
  
5.  Press Ctrl\+N to insert a new line, fill in the relevant fields and then choose the **OK** button to copy the new purchase budget name to the field.  
  
     Only entries that contain this budget name shown in the **Item Budget Name** field are now displayed. Because the budget name has just been created, there are no entries that match the filter. Therefore, the window is empty.  
  
6.  Select the appropriate time interval in the **View by** field on the **General** FastTab.  
  
7.  To enter an amount, choose the relevant cell in the matrix. The **G\/L Budget Entries** window opens.  
  
8.  Create a new line and fill in the **Amount** field. Close the **G\/L Budget Entries** window.  
  
9. Repeat steps until you have entered all of the budget amounts.  
  
> [!NOTE]  
>  On the **Filters** FastTab, there are between 4 to 8 filters, depending on how many budget dimensions you have set up under the budget name.  
  
## See Also  
 [How to: Import or Export a Budget](../how-to-import-or-export-a-budget.md)   
 [How to: View Budgets](../how-to-view-budgets.md)   
 Dimension   
 Copy G-L Budget