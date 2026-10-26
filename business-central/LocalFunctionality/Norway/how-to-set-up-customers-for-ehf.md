---
title: Set Up Norwegian Customers for EHF
description: Set up customer identifiers, account codes, and invoicing options for the legacy Norwegian EHF electronic document workflow in Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: EHF documents, create EHF documents, public sector customers, add EHF information, Norwegian version
ms.search.form: 21, 459
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up customers for EHF

> [!NOTE]
> This article describes the older EHF invoicing workflow. For new electronic invoicing setups, use the E-Documents framework instead. Learn more in [Set up e-documents](../../finance-how-setup-edocuments.md) and [Set up customers to receive e-documents](ehf-electronic-invoicing-in-norway.md#set-up-customers-to-receive-e-documents).

To create Elektronisk Handelsformat (EHF) documents for customers in the public sector, you must add EHF information to the relevant customers.  

This article only describes fields that apply to EHF. Learn more in [Register New Customers](../../sales-how-register-new-customers.md), which provides information about setting up customers in general.

## Set up a customer that uses Elektronisk Handelsformat  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Customers**, and then choose the related link.  
1. Open the customer that you want to enable for EHF.  
1. On the **Invoicing** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**GLN**|Required. Enter the Global Location Number (GLN) for the customer.|  
    |**Account Code**|Enter the account code for the customer.<br><br/> Customers in the public sector provide an account code when they place an order or requisition. Based on the value of this field, the account code is included in the EHF documents that you create in [!INCLUDE[prod_short](../../includes/prod_short.md)]. For more information, see Account Code.|  
    |**E-Invoice**|Select the checkbox to use electronic invoicing with this customer.|  
    |**Responsibility Center**|Make sure that the Responsibility Center that you have selected has a Country/Region Code specified.|  

These fields are specific to EHF. The values are used in all EHF documents that you create for this customer. Learn more in [EHF Electronic Invoicing in Norway](ehf-electronic-invoicing-in-norway.md).  

## Related information

- [Create Electronic Documents for EHF](how-to-create-electronic-documents-for-ehf.md)   
- [Set Up EHF](how-to-set-up-ehf.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
