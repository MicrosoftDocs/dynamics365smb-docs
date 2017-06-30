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
# How to: Delete Cost Budget Entries
You use the **Delete Cost Budget Entries** batch job to cancel cost budget entries from the cost budget register.  

 To prevent any gaps in the cost budget entries and cost register entries, you cannot delete a single entry or a batch of entries in the middle of the list of register entries.  

### To delete a cost budget entry  

1.  In the Search box, enter **Delete Cost Budget Entries**, and then choose the related link.  

2.  The **\($ B\_1139\_F\_1\_3 To Register No. $\)** field contains the last register entry number and cannot be changed.  

3.  You can use the **\($ B\_1139\_F\_1\_1 From Register No. $\)** field to select a register entry number from which the deletion should begin.  

4.  Choose the **OK** button to delete the selected cost budget entries.  

> [!NOTE]  
>  To avoid an accidental deletion of cost budget entries, you can close register entries by marking the lines as **Closed** in the **Closed** field in the **Cost Budget Registers** window.  

## See Also  
 Delete Cost Budget Entries   
 Closed   
 Cost Budget Registers
