---
    title: Recipient Reference Codes
    description: The recipient reference code determines the message that is sent to the recipient. The code is displayed on the remittance account and is used for vendors that are paid from this account.

    services: project-madeira 
    documentationcenter: ''
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
# Recipient Reference Codes
The recipient reference code determines the message that is sent to the recipient. The code is displayed on the remittance account and is used for vendors that are paid from this account. For each vendor, a special recipient reference code can be created if the general reference text is not used.  

The text in recipient reference fields can be formatted automatically with special codes. For example, if you enter **Payment of Invoice %2** in a recipient reference field, the information that will print is **Payment of Invoice 10000**.  

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

## See Also  
 [Set Up Vendors for Remittance](how-to-set-up-vendors-for-remittance.md)
