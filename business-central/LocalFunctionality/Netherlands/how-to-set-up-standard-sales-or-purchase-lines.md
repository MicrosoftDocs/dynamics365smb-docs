---
    title: How to Set Up Standard Sales or Purchase Lines
    description: In Business Central, you can specify how the standard sales or purchase codes will be entered when you are creating the specified sales or purchase documents.

    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Set Up Standard Sales or Purchase Lines
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can specify how the standard sales or purchase codes will be entered when you are creating the specified sales or purchase documents.  

The following procedure describes how to set up a standard sales line, but the same steps apply to setting up standard purchase lines in the **Purchases & Payables Setup** window.  

## To set up a standard sales line  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
2.  On the **Std. Customer Sales Codes** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Insert Std. Cust. Sales Lines**|Specify the method by which to insert the standard customer sales lines.<br /><br /> -   **Manual** - You must insert the standard sales lines that you set up for that customer. If you select this option, then you will not be able to select the **Quotes**, **Orders**, **Invoices**, or **Credit Memos** fields in the **Sales & Receivables Setup** window.<br />-   **Automatic** - Automatically insert standard sales lines on sales documents that you create for a customer.<br />-   **Always Ask** - Display a window with all the existing standard sales codes that you set up for the customer.|  
    |**Quotes**|Select to insert standard sales lines on sales quotes.|  
    |**Orders**|Select to insert standard sales lines on sales orders.|  
    |**Invoices**|Select to insert standard sales lines on sales invoices.|  
    |**Credit Memos**|Select to insert standard sales lines on sales credit memos.|  

3.  Choose the **OK** button.  

## See Also  
[Create Recurring Sales and Purchase Lines](../../sales-how-work-standard-lines.md)
