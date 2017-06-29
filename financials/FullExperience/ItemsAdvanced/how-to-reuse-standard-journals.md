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
# How to: Reuse Standard Journals
When you need to fill a journal with lines that you have saved as a standard journal, you use a function to copy the standard journal lines into the journal.  
  
 Before you can use the **Get Standard Journals** function that is described in this procedure, you must create one or more standard journals. For more information, see [How to: Save Standard Journals](../Finance/how-to-save-standard-journals.md).  
  
> [!NOTE]  
>  The following procedure refers to the item journal, but the information also applies to the general journal.  
  
### To get a standard journal  
  
1.  In the **Search** box, enter **Item Journal**, and then choose the related link.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Get Standard Journals**.  
  
     The **Standard Item Journals** window opens showing codes and descriptions for all existing standard item journals.  
  
3.  To review a standard item journal before you select it for reuse, on the **Navigate** tab, in the **Standard** group, choose **Show Journal**.  
  
     Any changes you make in a standard item journal are implemented right away. They will be there next time you open or reuse the standard item journal in question. You should therefore be sure that the change is important enough to apply generally. Otherwise, make the specific change in the item journal after the standard item journal lines have been inserted. See step 4 below.  
  
4.  In the **Standard Item Journals** window, select the standard item journal you want to reuse, and choose the **OK** button to complete the **Get Standard Journals** function.  
  
     Now the item journal is filled with the lines you saved as the standard item journal. If journal lines already existed in the item journal, the inserted lines will be placed under the existing journal lines.  
  
     If you did not check the **Save Unit Amount** field when you used the **Save as Standard Item Journal** batch job, then the **Unit Amount** field on lines that are inserted from the standard journal is automatically filled with the item’s current value, copied from the **Unit Cost** field on the item card.  
  
    > [!NOTE]  
    >  If you selected the **Save Unit Amount** or **Save Quantity** fields, you should now make sure the inserted values are correct for this particular inventory adjustment before you post the item journal.  
  
5.  If the inserted item journal lines contain saved unit amounts that you do not want to post, you can quickly adjust it to the current value of the item:  
  
    1.  Select the item journal lines you want to adjust.  
  
    2.  On the **Navigate** tab, in the **Line** group, choose **Recalculate Unit Amount**. This will update the **Unit Amount** field with the current unit cost of the item.  
  
6.  Post the item journal.  
  
## See Also  
 [How to: Save Standard Journals](../Finance/how-to-save-standard-journals.md)   
 Save as Standard Item Journal   
 Item Journal