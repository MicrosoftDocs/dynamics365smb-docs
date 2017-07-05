---
    title: How to: Process Response Messages from Tax Authorities | Microsoft Docs
    description: When you submit a VAT or ICP declaration to the tax authorities electronically, they will process the declaration and send you a message in response.
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
# How to: Process Response Messages from Tax Authorities
When you submit a VAT or ICP declaration to the tax authorities electronically, they will process the declaration and send you a message in response.  
  
 You can import the response into [!INCLUDE[d365fin](../../includes/d365fin_md.md)] by using the **Receive Response Messages** batch job. The response message will contain the status of the declaration.  
  
### To import messages from the tax authorities' server  
  
1.  In the **Search** box, enter **Elec. Tax Decl. Response Msgs.**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Receive Response Messages**.  
  
3.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**CA Certificate Encryption Password**|The password that was used to encrypt the Certificate Authorities' certificates.|  
    |**User Certificate Password**|The password that is used to encrypt the user certificates.|  
  
4.  Choose the **OK** button.  
  
### To process the response messages from the tax authorities  
  
1.  In the **Search** box, enter **Elec. Tax Decl. Response Msgs.**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Process** group, choose **Process Response Messages**.  
  
3.  In the **Process Response Messages Batch Job** window, on the **Elec. Tax Decl. Response Msg**. FastTab, select the appropriate filters.  
  
4.  Choose the **OK** button.  
  
     The processed information about the response message is displayed in the **Elec. Tax Decl. Response Msgs.**. window.  
  
5.  To export a message or attachment, on the **Actions** tab, in the **Functions** group, choose **Export Response Message** or **Export Response Attachment**.  
  
## See Also  
 [Electronic VAT and ICP Declarations](electronic-vat-and-icp-declarations.md)   
 [How to: Set Up VAT Categories](how-to-set-up-vat-categories.md)   
 [How to: Create Electronic VAT and ICP Declarations](how-to-create-electronic-vat-and-icp-declarations.md)   
 Elec. Tax Declaration Header Table   
 Elec. Tax Decl. Response Msg. Table   
 Receive Response Messages Batch Job   
 Process Response Messages Batch Job