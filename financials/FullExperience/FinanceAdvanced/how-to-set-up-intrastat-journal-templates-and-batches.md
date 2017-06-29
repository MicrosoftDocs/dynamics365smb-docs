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
# How to: Set Up Intrastat Journal Templates and Batches
Before you can use the **Intrastat Journal**, you must decide which Intrastat journal templates and batches you will use. You do this in the **Intrastat Journal Templates** and **Intrastat Jnl. Batches** windows.  
  
 Because Intrastat is reported monthly, you must create 12 Intrastat journals based on the same template. You set up the names of these 12 journals in the **Intrastat Jnl. Batches** window.  
  
### To set up Intrastat templates  
  
1.  In the **Search** box, enter **Intrastat Journal Templates**, and then choose the related link.  
  
2.  In the **Intrastat Journal Templates** window, create several templates if you need several different forms.  
  
3.  Assign a **Name** and **Description** to each template.  
  
### To set up Intrastat batches  
  
1.  Select the template for which you want to create batches. On the **Navigate**, in the **Template** group, choose **Batches**.  
  
2.  Enter a **Name** and **Description** for each batch.  
  
    > [!NOTE]  
    >  We recommended that you set up a unique **Intrastat Journal Batch** for each month.  
  
3.  On each batch line, set up the relevant information in the following fields.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Statistics Period**|Enter the statistics period as a four\-digit number, where the first two digits represent the year and the next two digits represent the month. For example, enter **1206** for June 2012.|  
    |**Currency Identifier**|Enter a code that identifies the currency of the Intrastat report. For example, you can enter **EUR** for euro and **USD** for US dollars.|  
    |**Amounts in Add. Currency**|Select this field if you want the Intrastat report to display in the additional reporting currency.|  
    |**Reported**|This field is automatically filled when you run the **Intrastat \- Make Disk Tax Auth** batch job. If you want to run the batch job again, clear this field.|  
  
> [!NOTE]  
>  **Intrastat Journal Batches** are not similar in structure to other journal batches.  
  
## See Also  
 [How to: Fill In Intrastat Journals](../Finance/how-to-fill-in-intrastat-journals.md)   
 [How to: Reorganize Intrastat Journals](../Finance/how-to-reorganize-intrastat-journals.md)   
 Intrastat Journal Templates   
 Intrastat Jnl. Batches   
 Amounts in Add. Currency   
 Intrastat \- Make Disk Tax Auth