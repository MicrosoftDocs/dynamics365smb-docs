---
    title: FlowFilters | Microsoft Docs
    description: ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> contains fields called FlowFields. These are fields whose contents are constantly changing. The value of the contents of a FlowField is calculated each time you open the window containing the field. FlowFilters are used to determine how information is included when the contents of FlowFields are calculated.
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
# FlowFilters
ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> contains fields called FlowFields. These are fields whose contents are constantly changing. The value of the contents of a FlowField is calculated each time you open the window containing the field. FlowFilters are used to determine how information is included when the contents of FlowFields are calculated.  
  
 FlowFields are used to display amounts and quantities that must always be up-to-date. The calculation can be based on information in tables other than the one that contains the field.  
  
 When viewing a list, you can specify a FlowFilter basically the same way you specify other filters. Click the page title menu and then select **Limit totals**. On the filter pane, you can specify what FlowFilters should be used.  
  
> [!NOTE]  
>  You cannot specify FlowFilters on the ADD INCLUDE<!--[!INCLUDE[nav_web](../../includes/nav_web_md.md)]--> you can use Filter on column.  
  
 An example of a FlowField is the **Balance** field, which is in the **G/L Account** table. You can see the **Balance** field on the **G/L Account** card, but the information on which the balance is based is taken from the **Entry** table, which contains posted general ledger entries. Similarly, the contents of the **Balance** field for a customer is based on information in the **Customer Ledger Entry** table, and so on.  
  
 The only information that you can change in the **G/L Account**, **Customer**, **Vendor** and **Item** tables is basic information such as addresses and codes. Financial information in these tables is displayed in FlowFields, but cannot be changed directly. This information is calculated from information in ledger entry tables. You can change information in the ledger entry tables by posting entries.  
  
 The FlowFilter function allows you to temporarily limit which entries in the other tables should be included in the calculation. You do this by defining a FlowFilter in the window in which the result of the calculation will be displayed (for example, the result of the calculation for the **Balance** field will appear on the **Customer** card). The filter will be used in the ledger entry table (in this case the **Customer Ledger Entry** table), when the ledger entries are calculated.  
  
## See Also  
 [Set Filters](../FullExperience/how-to-set-filters.md)   
 [Enter Criteria in Filters](../FullExperience/enter-criteria-in-filters.md)