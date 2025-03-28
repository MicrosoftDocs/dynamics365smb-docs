---
title: How to Set Up Customers for OIOUBL | Microsoft Docs
description: To generate Offentlig Information Online UBL (OIOUBL) documents for public sector customers, it's necessary to include OIOUBL information for the relevant customers.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: OIOUBL, Denmark, public sector customers
ms.date: 03/04/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up customers for OIOUBL

To create Offentlig Information Online UBL (OIOUBL) documents for customers in the public sector, you must add OIOUBL information for the relevant customers.  

This article only describes fields that apply to OIOUBL. Learn more in [Register New Customers](../../sales-how-register-new-customers.md).  

### Process to set up customers

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
1. Open the customer that you want to enable for OIOUBL.  
1. On the **Invoicing** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**GLN**|Enter the customer's Global Location Number, which uniquely identifies the billing address. A GLN has a fixed length of 13 digits. It includes an assigned company prefix, a location reference, and a check digit.|  
    |**Account Code**|Enter the account code for the customer.<br><br/> Customers in the public sector provide an account code when they place an order or requisition. Based on the value of this field, the account code is included in the OIOUBL documents that you create in [!INCLUDE[prod_short](../../includes/prod_short.md)]. In accordance with **Lov om Offentlige Betalinger** and related statutes, the customer is entitled to withhold payment until they receive an invoice with the relevant account code.|  
    |**OIOUBL Profile Code**|Specifies the profile that this customer requires for electronic documents if this is different from the default profile that you specified on the **Sales & Receivables Setup** page.|  
    |**OIOUBL Profile Code Required**|Specifies if this customer requires a profile code for electronic documents. **Tip:**  If the **OIOUBL Profile Code Required** field is selected, you can't post a sales document for this customer unless you specified a profile.|  

 These fields are specific to OIOUBL. The values are used in all OIOUBL documents that you create for this customer. Learn more in [OIOUBL Electronic Invoicing Overview](oioubl-electronic-invoicing-overview.md).  

## Related information

- [Denmark Local Functionality](denmark-local-functionality.md)  
- [Register New Customers](../../sales-how-register-new-customers.md)
- [Set Up OIOUBL](how-to-set-up-oioubl.md)
- [Create Electronic Documents by Using OIOUBL](how-to-create-electronic-documents-by-using-oioubl.md)
- [OIOUBL Electronic Invoicing Overview](oioubl-electronic-invoicing-overview.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
