---
title: Set Up Stale Check
description: Set up cheque expiry periods and learn how stale-check actions differ between check ledger and bank account ledger entries in Business Central for India.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, stale check, stale check setup, manage stale cheques
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up stale check

Business Central has included Stale Check Feature as part of Indian Localization.

A check is considered stale after its validity period expires. Configure the period for each bank account according to the applicable bank requirements. A three-month period is an example, not a default or a statement of current legal requirements.

## Stale check setup

Following is the list of setups that are required to be configured.

- [General Ledger Setup](stale-check.md#set-up-general-ledger-setup)
- [Bank Account](stale-check.md#set-up-bank-account)

### Set up general ledger setup

Following needs to be configured in General Ledger Setup for stale check.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **General Ledger Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Activate Cheque No.**|If it's True, Document No won't be replaced by Cheque No while using Computer or Manual Cheque option. Cheque No & Cheque date flow in Bank ledger Entry in case of Bank Receipt, Bank Payment, and Contra Voucher. Cheque No. and Cheque Date also flow in Check Ledger Entry in case of Manual or Computer Cheque is used. If it's False, Document No. filed is replaced with check number.|

### Set up bank account

Following configuration is needed.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Bank Accounts**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Stale Cheque Stipulated Period**|Specifies the period for cheque stale date calculation, Cheque Stale Date = (Check Date + Stale Cheque Stipulated Period).|

## Manage a stale cheque from check ledger entries

Use **Stale Check** on **Check Ledger Entries** to financially void a posted check. The check must have **Entry Status** set to **Posted**, **Statement Status** set to **Open**, and a balancing account. The underlying transaction must balance.

1. Create a bank payment in **General Journal**, **Payment Journal**, or **Bank Payment Voucher**.
1. Enter the **Cheque No.** and **Cheque Date**, and post the payment.
1. To mark the check as stale go to the relevant **Bank Account**, choose the **Edit** action, and then choose the **Check Ledger Entries** action.
1. In the **Check Ledger Entries** window, choose the **Stale Check** action. 
1. On **Confirm Financial Stale**, review **Stale Date** and select **Type of Stale**. Choose **Unapply and Stale check** to unapply a customer or vendor payment, or **Stale check only** to leave the original application in place.
1. Confirm the action.

The action posts reversing entries and marks the check **Financially Voided**. It marks both the original check ledger entry and the related bank account ledger entry as stale. **Stale check only** doesn't mean that no financial entries are posted.

The expiry date is calculated from the check date and the bank account's **Stale Cheque Stipulated Period**. Review the resulting **Stale Cheque Expiry Date** before running the action.

## Mark a bank account ledger entry as stale

The **Stale Check** action on **Bank Account Ledger Entries** only marks the selected entry. It doesn't run the financial-voiding workflow or open **Confirm Financial Stale**.

1. Open the relevant **Bank Account Ledger Entries**.
1. Select the entry, choose **Stale Check**, and confirm.

This action sets **Stale Cheque** and **Cheque Stale Date** on the selected bank account ledger entry.

> [!NOTE]
> Make sure that your work date should be later than Stale cheque expiry date.

## Related information

[GST Overview](GST-001-Basic-Setup.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
