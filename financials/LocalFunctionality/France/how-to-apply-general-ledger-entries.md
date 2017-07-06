---
    title: How to: Apply General Ledger Entries | Microsoft Docs
    description: You apply general ledger entries to justify ledger balances on asset and liability accounts. For example, you can apply transactions on the bill of exchange accounts to get a clear picture of which bills make up the balance of the account.
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
# How to: Apply General Ledger Entries
You apply general ledger entries to justify ledger balances on asset and liability accounts. For example, you can apply transactions on the bill of exchange accounts to get a clear picture of which bills make up the balance of the account.  
  
### To apply general ledger entries  
  
1.  In the **Search** box, enter **Chart of Accounts**, and then choose the related link.  
  
2.  In the **Chart of Accounts** window, select the account that you want to apply entries for, and then on the **Navigate** tab, in the **Account** group, choose **Apply Entries**.  
  
3.  In the **Apply G/L Entries** window, select the ledger entries that you want to apply.  
  
4.  On the **Navigate** tab, in the **Process** group, choose **Set Applies-to ID** to populate the Applies-to ID field with the user ID of the current user.  
  
5.  On the **Navigate** tab, in the **Process** group, choose **Post Application**.  
  
     This effectuates the application by setting the Letter and Letter Date fields.  
  
> [!NOTE]  
>  Applied entries will be identified by the same three-letter combination and the same date. Balanced entries will be assigned only uppercase letters, and unbalanced entries will be assigned only lowercase letters.  
  
## See Also  
 [How to: Unapply General Ledger Entries](how-to-unapply-general-ledger-entries.md)