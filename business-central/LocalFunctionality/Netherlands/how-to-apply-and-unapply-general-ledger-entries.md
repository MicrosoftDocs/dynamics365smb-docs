---
    title: How to Apply and Unapply General Ledger Entries
    description: Applying temporary general ledger entries allows companies to work with temporary and transfer accounts in the general ledger. Temporary and transfer accounts are used to store temporary ledger entries that are waiting for further processing into the general ledger.
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
# Apply and Unapply General Ledger Entries
Applying temporary general ledger entries allows companies to work with temporary and transfer accounts in the general ledger. Temporary and transfer accounts are used to store temporary ledger entries that are waiting for further processing into the general ledger.  

You can use temporary accounts for:  

- Money transfers from one bank account to another.  
- Financial transaction transfers from one system to another in which part of the information temporarily resides on the original system.  
- Transactions for which you have issued a sales invoice to a customer but have not yet received the corresponding purchase invoice from the vendor.  

When the ledger entries have been processed, you can use the apply entries function to update the posted ledger entries and the posting account type.  

You can unapply the applied general ledger entries and then open the closed entries to make changes.  

## To apply general ledger entries  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Registers**, and then choose the related link.  
2.  Select a general ledger register, and then choose the **General Ledger** action.  
3.  On the **General Ledger Entries** page, choose the **Apply Entries** action.  

    All open ledger entries for the general ledger account are displayed on the **Apply General Ledger Entries** page.  

    > [!NOTE]  
    >  By default, the **Include Entries** field is set to **Open**. You can change the value of the **Include Entries** field to **All** or **Closed**. You can only apply general ledger entries that are **Open**.  

4.  Select the relevant general ledger entry, and then choose the **Set Applies-to ID** action.  

    The **Applies-to ID** field is updated with the user ID. The remaining amount is displayed in the **Balance** field on the **Apply General Ledger Entries** page.  
5.  Choose the **Post Application** action.  

    You can post the application even if the balance amount is equal to 0. When posted, the **Remaining Amount** field is affected as follows:  

    - If the **Balance** is equal to 0, then the **Remaining Amount** field on all ledger entries is set to 0.  

    - If the **Balance** is not equal to 0, then the amount in the **Balance** field is transferred to the **Remaining Amount** field for the general ledger entry that was selected when you posted the application.  

    - For all other general ledger entries, the **Remaining Amount** field is set to 0 and the **Open**, **Closed by Entry No.**, **Closed by Amount**, and **Closed at Date** fields are updated.  

    > [!NOTE]  
    >  When posted, the general ledger entries which update the **Applies-to ID** field are deleted.  

6.  Choose the **OK** button.  

## To view the applied general ledger entries  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Registers**, and then choose the related link.  
2.  Select a general ledger register, and then choose the **General Ledger** action.  
3.  Select the relevant general ledger entry, and then choose the **Applied Entries** action.  

    You can view all the applied general ledger entries.  

4.  Choose the **OK** button.  

## To unapply general ledger entries  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Registers**, and then choose the related link.  
2.  Select a general ledger register, and then choose the **General Ledger** action.  
3.  Select the general ledger entry that you want to unapply, and then choose the **Undo Application** action.  

    The applied general ledger entries are unapplied.  

    > [!NOTE]  
    >  If an entry is applied to more than one application entry, you must unapply the latest application entry first. By default, the latest entry is displayed.  

4.  Choose the **OK** button.  

## See Also  
[General Ledger](general-ledger.md)
