---
    title: GST Settlement of Net Payment Liability
    description: GST Settlement of Net Payment Liability

    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 07/20/2020
    ms.author: v-debapd

---
# GST Settlement of Net Payment Liability

Settlement refers to discharge of tax liability to the government. Tax liability arises for scenarios mentioned below: 
- Outward Supplies (Sales, Transfers) 
- Inward Supplies that are subject to Reverse charge (Purchases, Inward Transfers)
- Credit Reversal Adjustments 
- Negative Credit from Purchase Transactions 
- Negative Credit for ISD Distributions 

This tax liability on both interstate transactions (IGST) and intrastate transactions (SGST/UTGST, CGST) is to be discharged on a monthly basis to the government. GST paid on purchase transactions can be taken as credit subject to certain conditions. Such credit can be offset against the tax payable on Sales. Hence, GST payable on sales transactions can be discharged by payment of cash or utilization of credit or both. Reverse charge Liability shall always be discharged in cash. Credit can be availed in the month of tax remittance to the government. Credit utilized can be credit pertaining to the same component or different components. 

- As per GST Law, credit of IGST, CGST and SGST/UTGST shall be claimed in the chronological order as given below: 

    |GST Component|GST Setoff Component|Priority|
    |----------------------------------|-----|---------------------------------------|
    |**IGST**|CGST|1|
    |**IGST**|SGST|2|
    |**CGST**|IGST|1|
    |**SGST**|IGST|1|  

The first priority for any component would be that component itself. This logic is inbuilt. The above table is setting priorities for other components.

## Sources of Settlement

1. Sales Liability : 

The net liability from below sources are shown in Payment Liability:
- Detailed GST Ledger entry: Liability from below transactions having 'Liabile to Pay' selected as true in Detail GST Ledger entry will be shown in liability for current period
  - Advance Receipt 
  - Refund
  - Reversal of Advance Receipt
  - Transactions posted through Sales or Service documents 
  - Warehouse Transfer Shipments
  - Service Transfer Shipments
  - Subcontracting Liability
- Detailed credit adjustment entry: Credit Reversals from Credit Adjustment Journal are shown in Liability
- Posted settlement entry: Any negative Liability from previous period settlement which were not adjusted are shown in Liability for Current period
- If net credit availed for this period is negative then it will be added in the current period Liability

2.	Reverse Charge Liability:
The net liability of the following transactions that are subject to reverse charge are shown in 'Payment Libaility- Rev. Chrg'.:
- Advance Payments
- Refund
- Reversal of Advance Receipt
- Transactions posted through Purchase Documents 

3.	Credit Availed : 
The net credit from below sources are shown in Credit Availed for Settlement.
- Detailed GST Ledger entry: Credit from transactions mentioned herebelow, having credit availed marked as true in 'Detail GST Ledger Entry' will be shown in liability for current period
  - Transactions posted through Purchase Documents 
  - Warehouse Transfer Receipts
  - Service Transfer Receipts
  - Subcontracting Receipts and Invoice
  - Transitional Provision Transactions
- Detailed Credit Adjustment entry: Credit re-availment entries from 'Credit Adjustments' are shown in 'Credit Availed'.
- Posted Settlement Entry: Any unutilized credit from previous period will get added in 'Credit Availed' for current period.
- Distributed Credit: Credit received after ISD distribution to the recipients will get added to 'Credit Availed'.

## Process of Settlement

1. Choose the ![img](image/search.jpg)icon, enter **GST Settlement**, and then choose the related link.
2. **GST Settlement Nos.** should not be blank on **General Ledger Setup**.
3. **GST Settlement** should not be blank on **Source Type Setup**.
4. Select relevant information in the following fields in **GST Settlement**

    |Field|Description|
    |----------------------------------|---------------------------------------|  
    |**GST Registration No.**|Specify the GST registration number for which settlement to be done.|
    |**Posting Date**|Specify the posting date of the settlement.|
    |**Account Type**|Select the account type as per the payment option.|
    |**Account No.**|Specify the relevant account number as per the selected account type.|
    |**Bank Reference No.**|Specify the bank reference number.|
    |**Bank Reference Date**|Specify the bank reference date.|

5. Once relevant values are selected in the request page click on **Apply Entries** on ribbon. 
6. System auto-populates the net Payment Liability and the Total Credit availed in settlement page for the given period.
7. Credit utilized shall be auto populated by the system based on the priorities set out in claim set-off table. However, the user can edit the same.
8. The auto population of credit utilization shall be based on the assumption that unless the credit is availed – both own credit (credit of the component itself) and cross credit (credit of other components) is utilized fully, cash payment for a particular component shall not arise.
9. Credit cannot be utilized for payment of interest, penalty, fees and others. They shall always be paid in cash.
10. Credit utilized and payment amount shall not exceed tax liability.
11. Total credit utilized for a particular component shall not exceed total credit availed of that components plus Surplus credit of other components prioritized in claim-set off table for such component.
12. Account No. and Account Type shall be the same for all tax components. However, Interest Account, Fees Account, Penalty Account and Others Account can be defined differently for different tax components.
13. Credit cannot be utilized for payment of reverse charge liability. The entire liability is to be discharged in cash. Once settlement is done for any payment or refund document, the same cannot be reversed in system.
14. Provision for dimensions are also available on settlement page.

Following are few examples of accounting entries.

- Example of accounting entry where Credit Availed is positive:

  |GST Component|Tax Liability|Credit Availed|Credit Utilized|Payment|
  |---------|---------|---------|---------|----|
  |**IGST**|20000|10000|15000|5000|
  |**CGST**|10000|15000|10000|0|
  |**SGST/UTGST**|15000|10000|10000|5000|

  - On posting accounting entry, will be as following:

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

  - On posting accounting entry, will be as following:

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
> In case of negative Credit, the same will be treated as our Liability and needs to be paid in the current period settlement.

- Example for Accounting Entries in case of Reverse Charge Liability:

  |GST Component|Reverse Charge Liability|Credit Availed|Credit Utilized|Payment|
  |---------|---------|---------|---------|----|
  |**IGST**|20000|0|0|20000|
  |**CGST**|10000|0|0|10000|
  |**SGST/UTGST**|15000|0|0|15000|

  - On posting accounting entry, will be as following:

    |GST Component|Tax Liability|
    |---------|---------|
    |**IGST Payable Account**|20000|
    |**CGST Payable Account**|10000|
    |**SGST/UTGST Payable Account**|15000|
    |**Bank Account**|-45000|




