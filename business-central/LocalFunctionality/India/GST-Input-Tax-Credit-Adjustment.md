---
title: GST Input Tax Credit Adjustments
description: Learn how to manage and adjust GST input tax credit in Business Central for India, including credit reversals, reavailment, and reverse charge transactions.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, input tax credit adjustments, credit adjustment journal, reverse charge transactions
ms.date: 23/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# GST input tax credit adjustments

This article explains the requirement and process of GST credit adjustment.

- [Credit Adjustment Journal](GST-Input-Tax-Credit-Adjustment.md#credit-adjustment-journal)
- [Credit Adjustment for Reverse Charge Transactions](GST-Input-Tax-Credit-Adjustment.md#gst-credit-adjustment-for-reverse-charge-transactions)
- [Credit Adjustment Entry Process](GST-Input-Tax-Credit-Adjustment.md#gst-credit-adjustment-entry-process)

## Credit adjustment journal

Credit adjustment journal is designed to handle certain credit adjustments arising as an outcome of reconciliation.

- Purpose of Credit Adjustments

    |Nature of Adjustment|Purpose of Adjustment|
    |----------------------------------|---------------------------------------|
    |**Credit Reversal**|To reverse the availed credit for posted transactions. Detailed GST Ledger entries and Detailed Cr. Adjustment entries are updated with Credit Adjustment type as ‘Credit Reversal’. Detailed Cr. Adjustment Entries are created with ‘Credit Availed’ as FALSE and ‘Liable to Pay’ as TRUE.|  
    |**Credit Re-availment**|To reavail the reversed credit for posted transactions. Detailed GST Ledger entries and Detailed Cr. Adjustment entries are updated with Credit Adjustment type as ‘Credit Re-Availment’. Detailed Cr. Adjustment Entries are created with ‘Credit Availed’ as TRUE and ‘Liable to Pay’ as FALSE.|  
    |**Permanent reversal**|To reverse a transaction permanently. Detailed GST Ledger entries and Detailed Cr. Adjustment entries are updated with Credit Adjustment type as ‘Permanent Reversal’. Detailed Cr. Adjustment Entries are created with ‘Credit Availed’ as FALSE and ‘Liable to Pay’ as FALSE.|

- Need for Adjustment

    |Nature of Adjustment|Need for Adjustment|
    |----------------------------------|---------------------------------------|
    |**Credit Reversal**|If provisional credit is availed and credit remains unmatched, then after a prescribed period, the credit gets autoreversed in Credit ledger of GSTN Portal. To reverse such credit availment in the books of account and posted to respective GST mismatch account.|  
    |**Credit Re-availment**|If credit is reversed due to the reason that vendor payment isn't made within 180 days or for any other reason. Subsequently, if the vendor payment is made, then the reversed credit can be reavailed. Hence, to reavail the credit and post it to respective GST Receivable account.|  
    |**Permanent reversal**|If it's certain that the vendor will never upload the invoice information in GSTN portal, then the credit posted to respective GST Mismatch Account and post the same into respective GST expense account.|

- Accounting Entries

   |Nature of Adjustment|Document Type|Debit|Credit|
   |---------|---------|---------|---------|
   |**Credit Reversal**|Invoice|GST Credit Mismatch Account|GST Payable Account|
   |**Credit Reversal**|Credit Memo|GST Payable Account|GST Credit Mismatch Account|
   |**Credit Re-Availment**|Invoice|Receivable Account|GST Mismatch Account|
   |**Credit Re-Availment**|Credit Memo|GST Mismatch Account|Receivable Account|
   |**Permanent Reversal**|Invoice|GST Expense Account|GST Mismatch Account|
   |**Permanent Reversal**|Credit Memo|GST Mismatch Account|GST Expense Account|

> [!NOTE]
> GST Credit Adjustment Journal can be posted by selecting 'Nature of adjustment type' as 'Credit Re-Availment' and 'Permanent Reversal' after posting GST Adjustment Journal for type 'Credit Reversal'. If the GST Credit Adjustment Journal is posted with 'Nature of Adjustment' as ‘Permanent Reversal’ then system won't consider these entries again for posting via adjustment type as ‘Credit Reversal’ or ‘Credit Re-Availment’.

## GST credit adjustment for reverse charge transactions

Credit Adjustment Journal functionality is also available for adjusting reverse charge transactions where GST Group Type is 'Service'. This functionality is designed to handle certain adjustments arising on selecting GST Credit Type incorrectly at the time of transaction.

- Purpose of Credit Adjustments for Reverse charge transactions

    |Nature of Adjustment|Purpose of Adjustment|
    |----------------------------------|---------------------------------------|
    |**Credit Reversal**|To reverse the availed credit for posted transactions. Detailed GST Ledger entries and Detailed Cr. Adjustment entries are updated with Credit Adjustment Type as ‘Credit Reversal’. Detailed Cr. Adjustment Entries are created with ‘Credit Availed’ as FALSE and ‘Liable to Pay’ as TRUE.|
    |**Credit Re-Availment**|To reavail the reversed credit for posted transactions. Detailed GST Ledger Entries and Detailed Cr. Adjustment entries are updated with Credit Adjustment Type as ‘Credit Re-Availment’. Detailed Cr. Adjustment Entries are created with ‘Credit Availed’ as TRUE and ‘Liable to Pay’ as FALSE.|
    |**Credit Availment**|To avail credit, which isn't availed in posted transactions. Detailed GST Ledger Entries and Detailed Cr. Adjustment entries are updated with Credit Adjustment Type as ‘Credit Re-Availment’. Detailed Cr. Adjustment Entries are created with ‘Credit Availed’ as TRUE and ‘Liable to Pay’ as FALSE.|
    |**Reversal of Availment**|To reverse the availed credit in above scenario. Detailed GST Ledger Entries and Detailed Cr. Adjustment entries are updated with Credit Adjustment Type as ‘Permanent Reversal’. Detailed Cr. Adjustment Entries are created with ‘Credit Availed’ as FALSE and ‘Liable to Pay’ as FALSE.|

- Need for Adjustment

    |Nature of Adjustment|Need for Adjustment|
    |----------------------------------|---------------------------------------|
    |**Credit Reversal**|If GST Credit is selected as Availment in transactions and later on realized that it has been incorrectly selected, then this adjustment allows to reverse credit and post it to respective GST Payable Account.| 
    |**Credit Re-Availment**|If GST Credit is selected as Non-Availment in transactions and later realized that it has been incorrectly selected, then this adjustment allows to Avail Credit and post it to respective GST Receivables Account.|
    |**Reversal of Availment**|Reversal of Availment will be used to reverse the entries posted for Credit Availment. System will Re-Avail Credit and post it to respective GST Receivable Account.|

- Accounting Entries

  |Nature of Adjustment|Document Type|Line Type|Debit|Credit|
  |---------|---------|---------|---------|-----|
  |**Credit Reversal**|Invoice|G/L Account|G/L Account selected in transaction|GST Payable Account|
  |**Credit Reversal**|Invoice|Item|Respective Purchase Account|GST Payable Account|
  |**Credit Reversal**|Invoice|FA|FA Acquisition Account|GST Payable Account|
  |**Credit Re-Availment**|Invoice|G/L Account|Receivable Account| G/L Account selected in transaction|
  |**Credit Re-Availment**|Invoice|Item|Receivable Account|Respective Purchase Account|
  |**Credit Re-Availment**|Invoice|FA|Receivable Account|FA Acquisition Account|
  |**Credit Availment**|Invoice|G/L Account|Receivable Account| G/L Account selected in transaction|
  |**Credit Availment**|Invoice|Item|Receivable Account|Respective Purchase Account|
  |**Credit Availment**|Invoice|FA|Receivable Account|FA Acquisition Account|
  |**Reversal of Availment**|Invoice|G/L Account|G/L Account selected in transaction|GST Payable Account|
  |**Reversal of Availment**|Invoice|Item|Respective Purchase Account|GST Payable Account|
  |**Reversal of Availment**|Invoice|FA|FA Acquisition Account|GST Payable Account|

> [!NOTE]
>
> - GST Credit Adjustment Journal can be posted as Credit Re-Availment after posting GST Adjustment Journal for Type Credit Reversal.
> - GST Credit Adjustment Journal can be posted as Reversal of Availment after posting GST Adjustment Journal for Type Credit Availment.
> - Permanent Reversal isn't applicable for reverse charge transactions.
> - The Credit Adjustment for reverse charge transactions can be executed only for GST Group Type as 'Service'. The GST credit and liability for reverse charge transactions, where GST Group Type is 'Service' is realized only on application of payment. System filters application entries in GST Credit Adjustment Journal for reverse charge scenarios.

## GST credit adjustment entry process

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **GST Credit Adjustment**, and then choose the related link.
1. **GST Credit Adj. Jnl Nos.** shouldn't be blank on **General Ledger Setup**.
1. **GST Credit Adjustment Journal** shouldn't be blank on **Source Type Setup**.
1. Select relevant information for following fields in **GST Credit Adjustment Journal**

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**GST Registration No.**|Specify the GST registration number for which adjustment is to be done.|
    |**Period Month**|Specify the relevant month of adjustment.|
    |**Period Year**|Specify the relevant year of adjustment.|
    |**Posting Date**|Specify the posting date of the adjustment entry.|
    |**Vendor No.**|Specify the relevant vendor for which adjustment is to be done.|
    |**Document No.**|Specify the document number for which adjustment is to be done.|
    |**External Document No.**|Specify the vendor invoice reference number for which adjustment is to be done.|
    |**Nature of Adjustment**|Specify the relevant nature of adjustment.|
    |**Input Service Distribution**|Specifies whether the GST registration number is assigned for input service distribution.|
    |**Reverse Charge**|Specifies whether the adjustment will be done for Reverse Charge entry or not.|
    |**Adjustment %**|Select applicable % (1% to 100%). Based on the applicable %, system creates lines and % value can be modified. Partial amount can be posted in Credit Adjustment.|

1. Once relevant values are selected on the request page, select on **Apply Entries**.
1. Check the documents and values and select on **Action** > **Posting** > **Dimensions** or **Line Dimension**, fill the relevant dimensions and post the entry.

## Related information

[GST Settlement](GST-Settelement.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
