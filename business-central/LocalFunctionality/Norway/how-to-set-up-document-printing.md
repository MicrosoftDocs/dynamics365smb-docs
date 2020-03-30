---
    title: How to Set Up Document Printing
    description: In Business Central, you can print the sales reports that use the required giro specifications by using different paper types and paper trays.

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
# Set Up Document Printing
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can print the sales reports that use the required giro specifications by using different paper types and paper trays.  

When you use tray numbers and paper sources for Norwegian sales documents, you must consider how the printer and printer driver interpret this information. You may have to specify other tray numbers for your specific printer.  

> [!NOTE]  
>  KID information will also print where the giro information is printed.  

The following documents require a printed giro:  

- Invoices  
- Credit memos  
- Finance charge memos  
- Reminders  

The Norwegian version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)] contains the following sets of sales documents.  

|**Set**|Description|  
|-------------|---------------------------------------|  
|1|The standard [!INCLUDE[d365fin](../../includes/d365fin_md.md)] documents. No giro information is printed.|  
|2|The giro is printed on every page. The last page prints the giro total.|  

## To set up paper trays  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Printer Selections**, and then choose the related link.  
2.  Select the report.  
3.  Choose the **Sales Document Paper Tray Setup** action.  
4.  Select a paper source from the **First Page - Paper Source** field.  
5.  The **First Page – Tray Number** field will automatically display the selected paper source. You can also manually enter a tray number.  

    > [!IMPORTANT]  
    >  Not all printers will have the same paper source names. You can specify a number in the **Tray Number** field. The number may correspond to a paper source. To find the number that a specific printer is using, see the technical documentation for the printer.  

    The **Other Pages** and **Giro Page** fields are set up the same way.  

6.  Choose the **OK** button.  

## See Also  
  [Norwegian Giro and OCR-B Font](norwegian-giro-and-ocr-b-font.md)   
 [Set Up KID Numbers on Sales Documents](how-to-set-up-kid-numbers-on-sales-documents.md)
