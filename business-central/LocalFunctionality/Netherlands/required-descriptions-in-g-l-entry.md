---
    title: Required Descriptions in G-L Entry
    description: When entering general journal lines on a form, the system fills in automatically the description field.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Required Descriptions in G-L Entry
When entering general journal lines on a form, the system fills in automatically the description field. This description will also be stored in the G/L entry after posting the journal. For a good audit trail, a more detailed description is desirable, when you post a journal line of type G/L Account.  

To force the user to enter a more detailed description, it is possible to choose if the system must fill in automatically the description of the G/L account or leave the field blank. If the **Omit Default Descr. in Jnl. Field** check box on the **G/L Account Card** page is checked, the system will not fill in the **Description** field for that G/L account when selected in a general journal line.  

When posting the journal lines, the system will check if all the **Description** fields are filled in. If there is a blank description, an error message will appear.  

> [!NOTE]  
>  Leaving the description field blank and check if all the description fields are filled in before posting, will only be done on the general journal pages in several application areas and on the local Cash Bank Giro pages.  

## See Also  
 [General Ledger](general-ledger.md)
