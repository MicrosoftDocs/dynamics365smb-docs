---
    title: How to Use Quick Filter on Pages | Microsoft Docs
    description: You can add filters to all pages, either by using the Quick Filter or the Advanced Filter. The Quick Filter is enabled by entering criteria in the **Type to filter** box at the top of a page. This filtering type is used for a fast entry of criteria. The advanced filtering option is available when you click the expand button next to the Quick Filter or when you press F3. All filters are cleared by pressing Ctrl+Shift+A.
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
# Use Quick Filter on Pages
You can add filters to all pages, either by using the Quick Filter or the Advanced Filter. The Quick Filter is enabled by entering criteria in the **Type to filter** box at the top of a page. This filtering type is used for a fast entry of criteria. The advanced filtering option is available when you click the expand button next to the Quick Filter or when you press F3. All filters are cleared by pressing Ctrl+Shift+A.  
  
> [!NOTE]  
>  In ADD INCLUDE<!--[!INCLUDE[nav_tablet](../../includes/nav_phone_md.md)]-->, you have a **Search** capability that works in the same way as Quick Filter.  
  
> [!IMPORTANT]  
>  Filtering using the Quick Filter works a bit differently than using the Advanced Filter. The Quick Filter provides an easy access to filter data by entering plain text, but does also provide a lot of search criteria options. Depending on whether you enter plain text or text including symbols, the Quick Filter behaves differently.  
>   
>  -   If you enter plain text in the search criteria, the search criteria is interpreted as a case insensitive search that contains certain text.  
> -   If you enter text including symbols in the search criteria, the search criteria is interpreted exactly as you entered it, and the search is case sensitive.  
  
 The following table illustrates some Quick Filter text search examples:  
  
|Search Criteria|Interpreted as…|Returns…|  
|---------------------|---------------------|--------------|  
|man|@*man*|All records that contain the text **man** and case insensitive.|  
|se|@*se*|All records that contain the text **se** and case insensitive.|  
|Man*|Starts with Man and case sensitive.|All records that start with the text **Man**|  
|'man'|An exact text and case sensitive.|All records that match **man** exactly|  
|@*man|Ends with and case insensitive.|All records that end with **man**|  
|@man*|Starts with and case insensitive.|All records that start with **man**|  
  
> [!NOTE]  
>  You cannot use a ***** when filtering on enumeration fields, such as the **Status** field on sales orders. To enter a filter for this type of field, you can enter the numeric value as a filtering parameter. For example, in the **Status** field on a sales order that has the values **Open**, **Released**, **Pending Approval**, and **Pending Prepayment**, use the values **0**, **1**, **2**, and **3** to filter for these options.  
  
 For more information about filter criteria, see [Enter Criteria in Filters](../../../archive/WorkingWithDynamics/enter-criteria-in-filters.md).  
  
### To use Quick Filter on pages  
  
1.  On any page, select the field to which you want to apply the filter, and then press F3.  
  
2.  In the **Type to filter** box, type a value to filter on.  
  
3.  Press Enter to view the filtered data.