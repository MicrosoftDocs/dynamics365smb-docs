---
    title: How to Process Response Messages from Tax Authorities
    description: When you submit a VAT or ICP declaration to the tax authorities electronically, they will process the declaration and send you a message in response.
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
# Process Response Messages from Tax Authorities
When you submit a VAT or ICP declaration to the tax authorities electronically, they will process the declaration and send you a message in response.  

You can import the response into [!INCLUDE[d365fin](../../includes/d365fin_md.md)] by using the **Receive Response Messages** batch job. The response message will contain the status of the declaration.  

## To import messages from the tax authorities' server  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Elec. Tax Decl. Response Msgs.**, and then choose the related link.  
2.  Choose the **Receive Response Messages** action.  
3.  On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**CA Certificate Encryption Password**|The password that was used to encrypt the Certificate Authorities' certificates.|  
    |**User Certificate Password**|The password that is used to encrypt the user certificates.|  

4.  Choose the **OK** button.  

## To process the response messages from the tax authorities  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Elec. Tax Decl. Response Msgs.**, and then choose the related link.  
2.  Choose the **Process Response Messages** action.  
3.  In the **Process Response Messages Batch Job** window, on the **Elec. Tax Decl. Response Msg**. FastTab, select the appropriate filters.  
4.  Choose the **OK** button.  

    The processed information about the response message is displayed in the **Elec. Tax Decl. Response Msgs.**. window.  

5.  To export a message or attachment, choose the **Export Response Message** action or the **Export Response Attachment** action.  

## See Also  
 [Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)   
 [Set Up VAT Categories](how-to-set-up-vat-categories.md)   
 [Create Electronic VAT and ICP Declarations](how-to-create-electronic-vat-and-icp-declarations.md)
