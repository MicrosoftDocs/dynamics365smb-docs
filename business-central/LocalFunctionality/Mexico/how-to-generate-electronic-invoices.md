---
    title: How to Generate Electronic Invoices
    description: In Business Central, after you post a sales invoice you must generate an electronic invoice that will be sent to the customer. You can also export the electronic invoice as an XML file, which you can save to a specified location.

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
# Generate Electronic Invoices
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], after you post a sales invoice you must generate an electronic invoice that will be sent to the customer. You can also export the electronic invoice as an XML file, which you can save to a specified location.  

The following procedure describes how to generate electronic invoices for sales invoices, but the same steps also apply to service invoices and credit memos.  

## To generate electronic invoices for sales invoices  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Sales Invoice**, and then choose the related link.  
2.  Select the posted invoice.  
3.  Choose the **Send Electronic Document** action. An email will be sent to the customer with the electronic invoice attached as an XML file. If you selected the **Send PDF Report** field on the **General Ledger Setup** page, a PDF will be included with the XML file.  
4.  Optionally, choose the **Export E-Document as XML** action. Select the location where you want to save the electronic invoice as an XML file.  

    To verify the electronic invoice activity, on the **Posted Sales Invoice** page, on the **Invoicing** FastTab, the **Electronic Document Sent** and **No. of E-Document Submissions** fields will be updated.  

> [!NOTE]  
>  ADD INCLUDE<!--[!INCLUDE[bp_refimplementation](../../includes/bp_refimplementation_md.md)]-->  

## See Also  
 [Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md)   
  [Electronic Invoicing](electronic-invoicing.md)  
  [Mexico Local Functionality](mexico-local-functionality.md)
