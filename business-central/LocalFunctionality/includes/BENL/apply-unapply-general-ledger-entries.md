---
author: brentholtorf
ms.topic: include
ms.date: 03/17/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

> [!NOTE]
> Businesses in all countries/regions can benefit from the ability to review general ledger entries before posting them. In a future release, we'll deprecate the country/region specific feature and replace it with one that's available in all country/region versions. After the feature is deprecated, you can use it to access previous reviews, but not to do new reviews. We'll archive your data according to local requirements. Learn more in [Deprecated Features in the Base App](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1), which provides information about deprecation. Learn more in [Review Amounts in General Ledger Accounts](../../../finance-review-accounts.md), which provides information about the replacement feature.

By applying temporary general ledger entries, companies can work with temporary and transfer accounts in the general ledger. Temporary and transfer accounts are used to store temporary ledger entries that are waiting for further processing into the general ledger.  

You can use temporary accounts for:  

- Money transfers from one bank account to another.  
- Financial transaction transfers from one system to another in which part of the information temporarily resides on the original system.  
- Transactions for which you issued a sales invoice to a customer but haven't yet received the corresponding purchase invoice from the vendor.  

When the ledger entries are processed, you can use the **Apply Entries** function to update the posted ledger entries and the posting account type.  

You can unapply the applied general ledger entries and then open the closed entries to make changes.  

## Apply general ledger entries  

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Registers**, and then choose the related link.  
1. Select a general ledger register, and then choose the **General Ledger** action.  
1. On the **General Ledger Entries** page, choose the **Apply Entries** action.  

   All open ledger entries for the general ledger account are displayed on the **Apply General Ledger Entries** page.  

    > [!NOTE]  
    > By default, the **Include Entries** field is set to **Open**. You can change the value of the **Include Entries** field to **All** or **Closed**. You can only apply general ledger entries that are **Open**.  

1. Select the relevant general ledger entry, and then choose the **Set Applies-to ID** action.  

    The **Applies-to ID** field is updated with the user ID. The remaining amount is displayed in the **Balance** field on the **Apply General Ledger Entries** page.  

    > [!IMPORTANT]  
    > You can apply multiple entries only if all entries that are being applied can be fully closed.  

1. Choose the **Post Application** action.  

    You can post the application even if the balance amount is equal to 0. When posted, the **Remaining Amount** field is affected as follows:  

    - If the **Balance** is equal to 0, then the **Remaining Amount** field on all ledger entries is set to 0.  
    - If the **Balance** isn't equal to 0, then the amount in the **Balance** field is transferred to the **Remaining Amount** field for the general ledger entry that was selected when you posted the application.  
    - For all other general ledger entries, the **Remaining Amount** field is set to 0 and the **Open**, **Closed by Entry No.**, **Closed by Amount**, and **Closed at Date** fields are updated.  

    > [!NOTE]  
    > When posted, the general ledger entries which update the **Applies-to ID** field are deleted.  

1. Choose the **OK** button.  

## View the applied general ledger entries  

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Registers**, and then choose the related link.  
1. Select a general ledger register, and then choose the **General Ledger** action.  
1. Select the relevant general ledger entry, and then choose the **Applied Entries** action.  

   You can view all the applied general ledger entries.  

1. Choose the **OK** button.  

## Unapply general ledger entries  

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Registers**, and then choose the related link.  
1. Select a general ledger register, and then choose the **General Ledger** action.  
1. Select the general ledger entry that you want to unapply, and then choose the **Undo Application** action.  

   The applied general ledger entries are unapplied.  

    > [!NOTE]  
    > If an entry is applied to more than one application entry, you must unapply the latest application entry first. By default, the latest entry is displayed.  

1. Choose the **OK** button.  
