---
title: Setting up and how to stale check
description: Describes the setup steps and process for handling stale checks in Business Central for India.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, stale check, stale check setup, manage stale cheques
ms.date: 06/26/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up stale check

Business Central has included Stale Check Feature as part of Indian Localization.

A check is considered to be stale after it has expired. Each bank has a specific period during which checks are considered to be valid. This period usually lasts three months. If a check isn't presented for payment within the specified period, it's considered to be stale.

## Stale check setup

Following is the list of setups that are required to be configured.

- [General Ledger Setup](stale-check.md#set-up-general-ledger-setup)
- [Bank Account](stale-check.md#set-up-bank-account)

### Set up general ledger setup

Following needs to be configured in General Ledger Setup for stale check.

1. Choose the ![Search for Page or Report](image/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Activate Cheque No.**|If it's True, Document No won't be replaced by Cheque No while using Computer or Manual Cheque option. Cheque No & Cheque date flow in Bank ledger Entry in case of Bank Receipt, Bank Payment, and Contra Voucher. Cheque No. and Cheque Date also flow in Check Ledger Entry in case of Manual or Computer Cheque is used. If it's False, Document No. filed is replaced with check number.|

### Set up bank account

Following configuration is needed.

1. Choose the ![Search for Page or Report](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Account**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Stale Cheque Stipulated Period**|Specifies the period for cheque stale date calculation, Cheque Stale Date = (Check Date + Stale Cheque Stipulated Period).|

## How to manage stale cheque

Following is the process of managing stale cheque.

1. Create and post bank payment from **General Journal**, **Payment Journal**, or **Bank Payment Voucher**.
1. **Cheque No.** and **Cheque Date** should have a value in the payment journal.
1. System calculates the **Stale Cheque Expiry Date** and populate the same in **Bank Ledger Entry** and **Check Ledger Entry**.
1. To mark the check as stale go to the relevant **Bank Account**, choose the **Edit** action, and then choose the **Check Ledger Entries** action.
1. In the **Check Ledger Entries** window, choose the **Stale Check** action. 
1. Select the **Stale Check Only** check box.
1. Choose the **OK** button.
1. Cheque can also be staled from **Bank Ledger Entry**. In the **Bank Ledger Entries** window, choose the **Stale Check** action.
1. Select the **Stale Check Only** check box.
1. Choose the **OK** button.

> [!NOTE]
> Make sure that your work date should be later than Stale cheque expiry date.

## Related information

[GST Overview](GST-001-Basic-Setup.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
