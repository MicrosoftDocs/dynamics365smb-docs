---
    title: How to: Print VAT Summary Information on Documents | Microsoft Docs
    description: If VAT is calculated, VAT summary information is typically printed on sales and purchase documents. However, in Iceland, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] does not print VAT summary information if only one VAT sales code is used in the document. You can modify this behavior by using the **Always Show VAT Summary** option.
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
# How to: Print VAT Summary Information on Documents
If VAT is calculated, VAT summary information is typically printed on sales and purchase documents. However, in Iceland, [!INCLUDE[d365fin](../../includes/d365fin_md.md)] does not print VAT summary information if only one VAT sales code is used in the document. You can modify this behavior by using the **Always Show VAT Summary** option.  
  
 The following procedure describes how to display VAT summary information on a sales invoice document, but the same steps also apply to sales order confirmations, sales quotes, sales credit memos, blanket sales orders, purchase orders, purchase invoices, and purchase credit memos.  
  
### To show VAT summary information  
  
1.  In the **Search** box, enter **Posted Sales Invoices**, and then choose the related link.  
  
2.  In the list, select the relevant document, and on the **Actions** tab, choose **Print**.  
  
3.  To display VAT information in the report, select the **Always Show VAT Summary** check box.  
  
## See Also  
 VAT Balancing Report   
 [VAT Reporting and Settlement](vat-reporting-and-settlement.md)   
 [VAT and VIES Report Setup](vat-and-vies-report-setup.md)