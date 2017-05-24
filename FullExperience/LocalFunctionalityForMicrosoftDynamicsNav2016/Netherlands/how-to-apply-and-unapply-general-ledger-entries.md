---
title: "How to: Apply and Unapply General Ledger Entries"
ms.custom: na
ms.date: "06-04-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "general ledger, applying entries"
  - "unapplying, general ledger entries"
  - "applying, general ledger entries"
ms.assetid: 41bd59e6-5f5b-473d-810e-6c071c8ae9b6
caps.latest.revision: 25
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
  - "nl-nl"
---
# How to: Apply and Unapply General Ledger Entries
Applying temporary general ledger entries allows companies to work with temporary and transfer accounts in the general ledger. Temporary and transfer accounts are used to store temporary ledger entries that are waiting for further processing into the general ledger.  
  
 You can use temporary accounts for:  
  
-   Money transfers from one bank account to another.  
  
-   Financial transaction transfers from one system to another in which part of the information temporarily resides on the original system.  
  
-   Transactions for which you have issued a sales invoice to a customer but have not yet received the corresponding purchase invoice from the vendor.  
  
 When the ledger entries have been processed, you can use the apply entries function to update the posted ledger entries and the posting account type.  
  
 You can unapply the applied general ledger entries and then open the closed entries to make changes.  
  
### To apply general ledger entries  
  
1.  In the **Search**  box, enter **\($ N\_116 G\/L Registers $\)**, and then choose the related link.  
  
2.  Select a general ledger register, and then, on the **Home** tab, in the **Process** group, choose **General Ledger**.  
  
3.  In the **\($ N\_20 General Ledger Entries $\)** window, on the **Home** tab, in the **Functions** group, choose **Apply Entries**.  
  
     All open ledger entries for the general ledger account are displayed in the **\($ N\_11309 Apply General Ledger Entries $\)** window.  
  
    > [!NOTE]  
    >  By default, the **Include Entries** field is set to **Open**. You can change the value of the **Include Entries** field to **All** or **Closed**. You can only apply general ledger entries that are **Open**.  
  
4.  Select the relevant general ledger entry, and then, on the **Navigate** tab, in the **Application** group, choose **Set Applies\-to ID**.  
  
     The **Applies\-to ID** field is updated with the user ID. The remaining amount is displayed in the **Balance** field in the **\($ N\_11309 Apply General Ledger Entries $\)** window.  
  
5.  On the **Navigate** tab, in the **Application** group, choose **Post Application**.  
  
     You can post the application even if the balance amount is equal to 0. When posted, the **Remaining Amount** field is affected as follows:  
  
    -   If the **Balance** is equal to 0, then the **Remaining Amount** field on all ledger entries is set to 0.  
  
    -   If the **Balance** is not equal to 0, then the amount in the **Balance** field is transferred to the **Remaining Amount** field for the general ledger entry that was selected when you posted the application.  
  
    -   For all other general ledger entries, the **Remaining Amount** field is set to 0 and the **Open**, **Closed by Entry No.**, **Closed by Amount**, and **Closed at Date** fields are updated.  
  
    > [!NOTE]  
    >  When posted, the general ledger entries which update the **Applies\-to ID** field are deleted.  
  
6.  Choose the **OK** button.  
  
### To view the applied general ledger entries  
  
1.  In the **Search**  box, enter **\($ N\_116 G\/L Registers $\)**, and then choose the related link.  
  
2.  Select a general ledger register, and then, on the **Home** tab, in the **Process** group, choose **General Ledger**.  
  
3.  Select the relevant general ledger entry, and then, on the **Navigate** tab, in the **Application** group, choose **Applied Entries**.  
  
     You can view all the applied general ledger entries.  
  
4.  Choose the **OK** button.  
  
### To unapply general ledger entries  
  
1.  In the **Search**  box, enter **\($ N\_116 G\/L Registers $\)**, and then choose the related link.  
  
2.  Select a general ledger register, and then, on the **Home** tab, in the **Process** group, choose **General Ledger**.  
  
3.  Select the general ledger entry that you want to unapply, and then, on the **Navigate** tab, in the **Application** group, choose **Undo Application**.  
  
     The applied general ledger entries are unapplied.  
  
    > [!NOTE]  
    >  If an entry is applied to more than one application entry, you must unapply the latest application entry first. By default, the latest entry is displayed.  
  
4.  Choose the **OK** button.  
  
## See Also  
 [\($ T\_15 G\/L Account $\)](assetId:///a65c2b09-9bb2-43db-8c53-c047bfc49777)   
 [\($ T\_17 G\/L Entry $\)](assetId:///2b5b8281-fbfa-4b7f-a154-a9ec61afadfe)   
 [\($ N\_20 General Ledger Entries $\)](assetId:///7634ea31-5577-42dc-9076-78cffea19ef4)