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
# How to: Generate Electronic Invoices
In ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, after you post a sales invoice you must generate an electronic invoice that will be sent to the customer. You can also export the electronic invoice as an XML file, which you can save to a specified location.  
  
 The following procedure describes how to generate electronic invoices for sales invoices, but the same steps also apply to service invoices and credit memos.  
  
### To generate electronic invoices for sales invoices  
  
1.  In the **Search** box, enter **Posted Sales Invoice**, and then choose the related link.  
  
2.  Select the posted invoice.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Send Electronic Document**. An email will be sent to the customer with the electronic invoice attached as an XML file. If you selected the **Send PDF Report** field in the **General Ledger Setup** window, a PDF will be included with the XML file.  
  
4.  Optionally, on the **Actions** tab, in the **Functions** group, choose **Export E\-Document as XML**. Select the location where you want to save the electronic invoice as an XML file.  
  
     To verify the electronic invoice activity, in the **Posted Sales Invoice** window, on the **Invoicing** FastTab, the **Electronic Document Sent** and **No. of E\-Document Submissions** fields will be updated.  
  
> [!NOTE]  
>  ADD INCLUDE<!--[!INCLUDE[bp_refimplementation](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/includes/bp_refimplementation_md.md)]-->  
  
## See Also  
 [How to: Set Up Electronic Invoicing](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Mexico/how-to-set-up-electronic-invoicing.md)   
 [Electronic Invoicing](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Mexico/electronic-invoicing.md)   
 Posted Sales Invoice   
 General Ledger Setup