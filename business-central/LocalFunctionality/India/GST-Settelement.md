---
title: GST Settlement of Net Payment Liability
description: GST Settlement of Net Payment Liability

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# GST Settlement of Net Payment Liability


## Settlement refers to discharge of tax liability to the government. Tax liability arises for scenarios mentioned below:
- Outward Supplies (Sales, Transfers)
- Inward Supplies that are subject to Reverse charge (Purchases, Inward Transfers)
- Credit Reversal Adjustments 
- Negative Credit from Purchase Transactions 
- Negative Credit for ISD Distributions 

This tax liability on both interstate transactions (IGST) and intrastate transactions (SGST/UTGST, CGST) is to be discharged on a monthly basis to the government. GST paid on purchase transactions can be taken as credit subject to certain conditions. Such credit can be offset against the tax payable on Sales. Hence, GST payable on sales transactions can be discharged by payment of cash or utilization of credit or both. Reverse charge Liability shall always be discharged in cash. Credit can be availed in the month of tax remittance to the government. Credit utilized can be credit pertaining to the same component or different components.

- As per GST Law, credit of IGST, CGST and SGST/UTGST shall be claimed in the chronological order as given below: 

    |GST Component|GST Setoff Component|Priority|
    |----------------------------------|-----|---------------------------------------|
    |**IGST**|IGST|1|
    |**IGST**|CGST|2|
    |**IGST**|SGST|3|
    |**CGST**|CGST|1|
    |**CGST**|IGST|2|
    |**SGST**|SGST|1| 
    |**SGST**|IGST|2|

## Setup return & reco. component for settlement

User needs to setup components for settlement. Select relevant information in the following fields in **Return & Reco Components** 

  |Field|Description|
  |---------|---------|
  |**Component ID**|Specifies the component name which will be required for GST settlement|
  |**Component Name**|Specifies the name of the component.|


## Sources of settlement

1. Sales liability : 

The net liability from below sources are shown in Payment Liability:
- Detailed GST Ledger entry: Liability from below transactions having 'Liabile to Pay' selected as true in Detail GST Ledger entry will be shown as liability for current period
  - Advance Receipt 
  - Refund
  - Reversal of Advance Receipt
  - Transactions posted through Sales or Service documents 
  - Warehouse Transfer Shipments
  - Service Transfer Shipments
  - Subcontracting Liability
- Detailed credit adjustment entry: Credit Reversals from Credit Adjustment Journal are shown as Liability
- Posted settlement entry: Any negative Liability from previous period settlement which was not adjusted is shown as Liability for Current period
- If net credit availed for this period is negative then it will be added in the current period liability

2.	Reverse charge liability:
The net liability of the following transactions that are subject to reverse charge is shown in 'Payment Liability- Rev. Chrg'.:
- Advance Payments
- Refund
- Reversal of Advance Receipt
- Transactions posted through Purchase Documents 

3.	Credit availed : 
The net credit from below sources is shown in Credit Availed for Settlement.
- Detailed GST Ledger entry: Credit from transactions mentioned below, having credit availed marked as true in 'Detail GST Ledger Entry' will be shown as liability for current period
  - Transactions posted through Purchase Documents 
  - Warehouse Transfer Receipts
  - Service Transfer Receipts
  - Subcontracting Receipts and Invoice
  - Transitional Provision Transactions
- Detailed Credit Adjustment entry: Credit re-availment entries from 'Credit Adjustments' are shown in 'Credit Availed'.
- Posted Settlement Entry: Any unutilized credit from previous period will get added in 'Credit Availed' for current period.
- Distributed Credit: Credit received after ISD distribution to the recipients will get added to 'Credit Availed'.

## Process of settlement

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **GST Settlement**, and then choose the related link.
2. **GST Settlement Nos.** should not be blank in **General Ledger Setup**.
3. **GST Settlement** should not be blank in **Source Type Setup**.
4. Select relevant information in the following fields in **GST Settlement**

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**GST Registration No.**|Specify the GST registration number for which settlement to be done.|
    |**Posting Date**|Specify the posting date of the settlement.|
    |**Account Type**|Select the account type as per the payment option, e.g G/L Account, Bank Account.|
    |**Account No.**|Specify the relevant account number as per the selected account type.|
    |**Bank Reference No.**|Specify the bank reference number.|
    |**Bank Reference Date**|Specify the bank reference date.|

5. Once relevant values are selected in the request page, click on **Apply Entries** on ribbon, **GST Settlement** page will open. Following field information will be displayed on the page.

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**GST Component Code**|Specifies the GST registration number for which settlement is to be done.|
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
    |**Total Credit AVailable**|Specifies the total credit available for the defined credit.|
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
    |**Account Type**|Specifies the account type of account defined for the payment, e.g. G/L, Bank.|
    |**Account No.**|Specifies the account number depending on the selected account type.|
    |**Total Payment Amount**|Specifies the total payment amount.|
    |**Bank Reference No.**|Specifies the bank reference number for the transaction.|
    |**Bank Reference Date**|Specifies the reference date for the transaction. |


1. System auto-populates the 'Net Payment Liability' and the 'Total Credit Availed' in settlement page for the given period.
1. 'Credit Utilized' shall be auto populated by the system based on the priorities set out in claim set-off table. However, they can be edited the same.
1. 'Credit Utilization' is auto populated when both ‘own credit’ (credit of the component itself) and cross credit (credit of other components) is utilized fully. It is  based on the assumption that unless the credit is availed cash payment for a particular component shall not arise.
1. Credit cannot be utilized for payment of interest, penalty, fees and others. They shall always be paid in cash.
1. Credit utilized and payment amount shall not exceed tax liability.
1. Total credit utilized for a particular component shall not exceed total credit availed for that component plus surplus credit of other components prioritized in claim-set off table for such component.
1. 'Account No'. and 'Account Type' shall be the same for all tax components. However, 'Interest Account', 'Fees Account', 'Penalty Account' and 'Others Account' can be defined differently for different tax components.
1. Credit cannot be utilized for payment of reverse charge liability. The entire liability is to be discharged in cash. Once settlement is done for any payment or refund document, the same cannot be reversed in system.
1. User can check out the component wise credit available, credit utilization and balance credit from **Action**-> **Details**.
1. Dimensions are also available on settlement page.

Following are few examples of accounting entries.

- Example of accounting entry where Credit Availed is positive:

  |GST Component|Tax Liability|Credit Availed|Credit Utilized|Payment|
  |---------|---------|---------|---------|----|
  |**IGST**|20000|10000|15000|5000|
  |**CGST**|10000|15000|10000|0|
  |**SGST/UTGST**|15000|10000|10000|5000|

  - On posting, accounting entries will be as following:

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

  - On posting, accounting entries will be as following:

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
> In case of negative credit, the same will be treated as liability and needs to be paid in the current period settlement.

- Example for accounting entries in case of Reverse Charge Liability:

  |GST Component|Reverse Charge Liability|Credit Availed|Credit Utilized|Payment|
  |---------|---------|---------|---------|----|
  |**IGST**|20000|0|0|20000|
  |**CGST**|10000|0|0|10000|
  |**SGST/UTGST**|15000|0|0|15000|

  - On posting, accounting entries will be as following:

    |GST Component|Tax Liability|
    |---------|---------|
    |**IGST Payable Account**|20000|
    |**CGST Payable Account**|10000|
    |**SGST/UTGST Payable Account**|15000|
    |**Bank Account**|-45000|


## Related information 
[GST E-Invoice](GST-E-Invoice.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
