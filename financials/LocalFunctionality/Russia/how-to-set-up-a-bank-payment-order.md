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
# How to: Set Up a Bank Payment Order
Bank payment orders must be used if a bank payment is for the official state budget. To use a bank payment order, a general journal template must be created as described in the following procedure.  
  
### To set up a bank payment order  
  
1.  In the **Search** box, enter **General Journal Templates**, and then choose the related link.  
  
2.  Create a general journal batch for every bank operation.  
  
3.  In the **Bal. Account Type** field, select the bank account type.  
  
4.  In the **Bal. Account No.** field, enter the bank account.  
  
5.  In the **Search** box, enter **Source Codes**, and then choose the related link.  
  
6.  Create a source code record.  
  
7.  In the **Search** box, enter **Source Code Setup**, and then choose the related link.  
  
8.  On the **General** tab, in the **Bank Payments** field, select the source code that you entered in the **Source Codes** window.  
  
## See Also  
 [How to: Set Up Bank Interface Files](assetId:///e960b140-df19-4ff4-bcfa-5a034ceb4b53)   
 [Bank Management](../bank-management.md)   
 KBK