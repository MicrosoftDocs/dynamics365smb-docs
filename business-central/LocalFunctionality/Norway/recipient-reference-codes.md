---
title: Recipient reference codes [NO]
description: Learn about the message sent to the recipient and shown on the remittance account, based on the recipient reference code.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: remittance account, recipient reference, Norwegian version, recipient reference code
ms.date: 05/16/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Recipient reference codes in the Norwegian version

The recipient reference code determines the message that is sent to the recipient. The code is displayed on the remittance account and is used for vendors that are paid from this account. For each vendor, a special recipient reference code can be created if the general reference text isn't used.  

The text in recipient reference fields can be formatted automatically with special codes. For example, if you enter **Payment of Invoice %2** in a recipient reference field, the information that prints is **Payment of Invoice 10000**.  

The recipient reference codes are described in the following table.  

|**Code**|Description|  
|--------------|---------------------------------------|  
|**%1**|The document type. Either invoice or credit memo.|  
|**%2**|The vendor's invoice number.|  
|**%3**|The **Our Account No.** field from the **Vendor Card** page. This is usually the customer number that is used by the vendor.|  
|**%4**|The invoice or credit memo number.|  
|**%5**|The description from the vendor ledger entry.|  
|**%6**|The original amount from the vendor ledger entries. The amount is shown as positive.|  
|**%7**|The remaining amount from the vendor ledger entries. The amount is shown as positive.|  
|**%8**|The local currency amount from the vendor ledger entry. The amount is shown as positive.|  
|**%9**|The currency code from the vendor ledger entry.|  
|**%10**|The due date from the vendor ledger entry.|  
|**%11**|The Kunde ID number from the vendor ledger entry.|  

## Related information

[Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
