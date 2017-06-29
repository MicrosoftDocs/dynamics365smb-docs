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
# How to: Set Up Codes for Import VAT
You use the import VAT feature when you need to post a document where the entire amount must be treated as VAT. This is necessary if you receive a VAT invoice from the tax authorities for imported goods.  
  
### To set up codes for import VAT  
  
1.  In the **Search** box, enter **VAT Product Posting Groups**, and then choose the related link.  
  
2.  In the **VAT Product Posting Groups** window, set up a new VAT posting group for import VAT.  
  
3.  In the **Search** box, enter **VAT Posting Setup**, and then choose the related link.  
  
4.  In the **VAT Posting Setup** window, set up a new line. You may use any of your existing VAT business posting groups in combination with the new VAT product posting group for import VAT.  
  
5.  To view the options, choose the **VAT Calculation Type** field and then select the option **Full VAT**.  
  
6.  In the **Purchase VAT Account** field, enter the general ledger account that must be used for posting import VAT. You do not have to enter any other general ledger accounts on the line.  
  
## See Also  
 [How to: Post Import VAT](../Finance/how-to-post-import-vat.md)   
 [How to: Create a VAT Combination Setup](../Finance/how-to-create-a-vat-combination-setup.md)