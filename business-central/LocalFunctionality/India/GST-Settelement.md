---
title: GST Settlement of Net Payment Liability
description: Review GST settlement setup and steps for calculating net payment liability and recording settlement transactions in Business Central for India.
author: v-debapd   
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, net payment liability, settlement, settlement process
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# GST settlement of net payment liability

Settlement refers to discharge of tax liability to the government. Tax liability arises for scenarios mentioned below:

- Outward Supplies (Sales, Transfers)
- Inward Supplies that are subject to Reverse charge (Purchases, Inward Transfers)
- Credit Reversal Adjustments
- Negative Credit from Purchase Transactions
- Negative Credit for ISD Distributions

This tax liability on both interstate transactions (IGST) and intrastate transactions (SGST/UTGST, CGST) is to be discharged on a monthly basis to the government. GST paid on purchase transactions can be taken as credit subject to certain conditions. Such credit can be offset against the tax payable on Sales. Hence, GST payable on sales transactions can be discharged by payment of cash or utilization of credit or both. Reverse charge Liability shall always be discharged in cash. Credit can be availed in the month of tax remittance to the government. Credit utilized can be credit pertaining to the same component or different components.

- The following table shows the setoff priorities used in this article's example. Settlement calculates credit utilization from **GST Claim Setoff** setup.

  |GST Component|GST Setoff Component|Priority|
  |----------------------------------|-----|---------------------------------------|
  |**IGST**|IGST|1|
  |**IGST**|CGST|2|
  |**IGST**|SGST|3|
  |**CGST**|CGST|1|
  |**CGST**|IGST|2|
  |**SGST**|SGST|1|
  |**SGST**|IGST|2|

> [!NOTE]
> The statutory background and setoff example describe the original scenario. Confirm current settlement rules separately. The accounting examples below use illustrative amounts.

## Set up return and reconciliation components for settlement

User needs to set up components for settlement. Select relevant information in the following fields in **Return & Reco Components**

|Field|Description|
|---------|---------|
|**Component ID**|Specifies the component name, which is required for GST settlement|
|**Component Name**|Specifies the name of the component.|

## Sources of settlement

1. Sales liability

   The net liability from below sources are shown in Payment Liability:

   - Detailed GST Ledger entry: Liability from below transactions having 'Liabile to Pay' selected as true in Detail GST Ledger entry will be shown as liability for current period.
     - Advance Receipt
     - Refund
     - Reversal of Advance Receipt
     - Transactions posted through Sales or Service documents
     - Warehouse Transfer Shipments
     - Service Transfer Shipments
     - Subcontracting Liability
   - Detailed credit adjustment entry: Credit Reversals from Credit Adjustment Journal are shown as Liability
   - Posted settlement entry: Any negative Liability from previous period settlement, which wasn't adjusted is shown as Liability for Current period
   - If net credit availed for this period is negative, then it's added in the current period liability

1. Reverse charge liability

   The net liability of the following transactions that are subject to reverse charge is shown in 'Payment Liability- Rev. Chrg'.:
    - Advance Payments
    - Refund
    - Reversal of Advance Receipt
    - Transactions posted through Purchase Documents

1. Credit availed

   The net credit from below sources is shown in Credit Availed for Settlement.

   - Detailed GST Ledger entry: Credit from the transactions below, with **Credit Availed** selected, is included as credit for the current period.
     - Transactions posted through Purchase Documents
     - Warehouse Transfer Receipts
     - Service Transfer Receipts
     - Subcontracting Receipts and Invoice
     - Transitional Provision Transactions
   - Detailed Credit Adjustment entry: Credit re-availment entries from 'Credit Adjustments' are shown in 'Credit Availed'.
   - Posted Settlement Entry: Any unutilized credit from previous period gets added in 'Credit Availed' for current period.
   - Distributed Credit: Credit received after ISD distribution to the recipients get added to 'Credit Availed'.

## Process of settlement

1. [!INCLUDE [open-search](../../includes/open-search.md)] **GST Settlement**, and then choose the related link.
1. **GST Settlement Nos.** shouldn't be blank in **General Ledger Setup**.
1. **GST Settlement** shouldn't be blank in **Source Code Setup**.
1. Select relevant information in the following fields in **GST Settlement**

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**GST Registration No.**|Specify the GST registration number for which settlement to be done.|
    |**Posting Date**|Specify the posting date of the settlement.|
    |**Account Type**|Select the account type as per the payment option, e.g G/L Account, Bank Account.|
    |**Account No.**|Specify the relevant account number as per the selected account type.|
    |**Bank Reference No.**|Specify the bank reference number.|
    |**Bank Reference Date**|Specify the bank reference date.|

1. Choose **Apply Entries** to open **Pay GST**. Review the following fields.

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**GST Component Code**|Specifies the tax component, such as CGST, SGST, or IGST, for the settlement line.|
    |**Description**|Specifies the description.|
    |**Period End Date**|Specifies the end date of settlement period.|
    |**Payment Liability**|Specifies the payment liability of the defined component.|
    |**GST TCS Liability**|Specifies the GST TCS liability of the defined component.|
    |**Net Payment Liability**|Specifies the net payment liability of the defined component.|
    |**Unadjusted Liability**|Specifies the unadjusted liability of the defined component.|
    |**Credit Availed**|Specifies the credit availed value for the defined component.|
    |**Distributed Credit**|Specifies the distributed credit value for the defined component.|
    |**GST TDS Credit Available**|Specifies the GST TDS credit available for the defined component.|
    |**GST TDS Credit Utilized**|Specifies the GST TDS credit utilized for the defined component.|
    |**GST TCS Credit Available**|Specifies the GST TCS credit available for the defined component.|
    |**GST TCS Credit Utilized**|Specifies the GST TCS credit utilized for the defined component.|
    |**Total Credit Available**|Specifies the total credit available for the defined credit.|
    |**Unadjusted Credit**|Specifies the unadjusted credit for the defined component.|
    |**Credit Utilized**|Specifies the credit utilized for the defined component.|
    |**Payment Amount**|Specifies the payment amount for the defined component.|
    |**Payment Liability - Rev. Chrg.**|Specifies the payment liability for reverse charge for the defined component.|
    |**Payment Amount - Rev. Chrg.**|Specifies the payment amount for reverse charge for the defined component. |
    |**Interest**|Specifies the interest amount.|
    |**Interest Account No.**|Specifies the interest account number.|
    |**Penalty**|Specifies the penalty amount.|
    |**Penalty Account No.**|Specifies the penalty account number.|
    |**Fees**|Specifies the fees.|
    |**Fees Account No.**|Specifies the fees account number.|
    |**Others**|Specifies the amount for any other charges.|
    |**Others Account No.**|Specifies the account number for other charges.|
    |**Account Type**|Specifies the account type of account defined for the payment, for example, G/L, Bank.|
    |**Account No.**|Specifies the account number depending on the selected account type.|
    |**Total Payment Amount**|Specifies the total payment amount.|
    |**Bank Reference No.**|Specifies the bank reference number for the transaction.|
    |**Bank Reference Date**|Specifies the reference date for the transaction. |

## Review settlement amounts before posting

The settlement request requires a GST registration number that isn't an input service distributor. The date filter includes entries through the settlement period end date.

- **Net Payment Liability** and available credit are calculated for the period. **Credit Utilized** is calculated from the priorities in **GST Claim Setoff**, including the component's own credit and eligible surplus credit from other components. You can edit the utilization before posting.
- Credit can't be used for interest, penalties, fees, or other charges. These amounts require payment accounts. Specify the corresponding expense accounts when entering these charges.
- Credit utilization must not exceed net payment liability or available credit. Review the resulting **Payment Amount** after changing utilization.
- Use the same **Account Type**, **Account No.**, **Bank Reference No.**, and **Bank Reference Date** across all component lines. The interest, fee, penalty, and other expense accounts can differ by component.
- Reverse charge liability requires a separate **Payment Amount - Rev. Chrg.** equal to the positive reverse charge liability. Input credit isn't used to discharge this amount.

## Post the settlement

1. Choose **Details** to check the credit available, utilization, and remaining credit by component.
1. Review the settlement dimensions and payment accounts.
1. Choose **Post**.

Once a payment or refund document is settled, its transaction reversal is blocked. Review the settlement before posting.

Following are few examples of accounting entries.

- Example of accounting entry where Credit Availed is positive:

  |GST Component|Tax Liability|Credit Availed|Credit Utilized|Payment|
  |---------|---------|---------|---------|----|
  |**IGST**|20000|10000|15000|5000|
  |**CGST**|10000|15000|10000|0|
  |**SGST/UTGST**|15000|10000|10000|5000|

  - On posting, accounting entries are as following:

    |GST Component|Tax Liability|
    |---------|---------|
    |**IGST Payable Account**|20000|
    |**CGST Payable Account**|10000|
    |**SGST/UTGST Payable Account**|15000|
    |**Bank Account**|-10000| 
    |**IGST Receivable Account**|-10000|
    |**CGST Receivable Account**|-15000|
    |**SGST/UTGST Receivable Account**|-10000|

- Example for Accounting Entry when Credit Availed is Negative:

  |GST Component|Tax Liability|Credit Availed|Credit Utilized|Payment|
  |---------|---------|---------|---------|----|
  |**IGST**|20000|-10000|5000|25000|
  |**CGST**|10000|15000|10000|0|
  |**SGST/UTGST**|15000|10000|10000|5000|

  - On posting, accounting entries are as following:

    |GST Component|Tax Liability|
    |---------|---------|
    |**IGST Payable Account**|30000|
    |**CGST Payable Account**|10000|
    |**SGST/UTGST Payable Account**|15000|
    |**IGST Receivable Account**|10000|
    |**Bank Account**|-30000| 
    |**IGST Payable Account**|-10000|
    |**CGST Receivable Account**|-15000|
    |**SGST/UTGST Receivable Account**|-10000|

> [!NOTE]
> In case of negative credit, the same is treated as liability and needs to be paid in the current period settlement.

- Example for accounting entries in case of Reverse Charge Liability:

  |GST Component|Reverse Charge Liability|Credit Availed|Credit Utilized|Payment|
  |---------|---------|---------|---------|----|
  |**IGST**|20000|0|0|20000|
  |**CGST**|10000|0|0|10000|
  |**SGST/UTGST**|15000|0|0|15000|

  - On posting, accounting entries are as following:

    |GST Component|Tax Liability|
    |---------|---------|
    |**IGST Payable Account**|20000|
    |**CGST Payable Account**|10000|
    |**SGST/UTGST Payable Account**|15000|
    |**Bank Account**|-45000|

## Related information

[GST E-Invoice](GST-E-Invoice.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
