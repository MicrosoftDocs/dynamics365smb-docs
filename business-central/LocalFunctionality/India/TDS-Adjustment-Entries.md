---
    title: TDS Adjustments
    description: TDS Adjustments

    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 16/07/2020
    ms.author: v-debapd

---
# TDS Adjustments

TDS adjustment can be required, for any corrections in the TDS amount, TDS rate or TDS base amount already deducted but not paid to government authorities. The revised TDS amount will be updated in the relevant GL Accounts for TDS Payable and Vendor Account. Existing TDS entry will be updated with revised TDS percentages, TDS amount and TDS base amount.

## TDS Adjustment Process

1. Choose the ![img](image/search.jpg)icon, enter **TDS Adjustment Journal**, and then choose the related link.
2. Select the relevant transaction number in **Transaction No.** field from the drop down, and the selected line will be populated with the posted record. Following information can be changed in the adjustment journal as per the requirement:
  
    |Field Name|Use|
    |----------------------------------|---------------------------------------|  
    |**TDS % Applied**|Fill the revised TDS %.|  
    |**TDS Base Applied**|Fill the revised TDS base amount.|

3. On posting of the adjustment journal G/L Entry, TDS Entry, Vendor Ledger Entry and Detailed Vendor Ledger Entry will be updated with the adjusted amount and revised information.
























