---
title: Set Up EHF in the Norwegian Version [NO]
description: Learn how to configure storage locations for EHF files when generating electronic documents such as invoices or credit memos.
author: brentholtorf
ms.topic: how-to
ms.devlang: al 
ms.search.keywords: EHF files, EHF file locations, EHF setup, sales and receivables, Norwegian version
ms.search.form: 459, 5919
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up EHF in the Norwegian version

> [!NOTE]
> This article describes the older EHF invoicing workflow. For new electronic invoicing setups, use the E-Documents framework instead. Learn more in [Set up e-documents](../../finance-how-setup-edocuments.md) and [Electronic invoicing in Norway](ehf-electronic-invoicing-in-norway.md#new-e-documents-framework).

You must define a location for storing Elektronisk Handelsformat (EHF) files when you create electronic documents such as invoices or credit memos. You must also define payment methods and set up relevant customers for EHF.  

## Set up EHF file locations for sales and receivables  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Sales & Receivables Setup**, and then choose the related link.  
1. On the **Sales & Receivables Setup** page, on the **E-Invoice** FastTab, in the **Output Paths** section, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Invoice Path**|The path and name of the folder where you want to store the EHF files for sales invoices.|  
    |**Cr. Memo Path**|The path and name of the folder where you want to store the EHF files for sales credit memos.|  
    |**E-Invoice Reminder Path**|The path and name of the folder where you want to store the EHF files for reminders.|  
    |**E-Invoice Fin. Charge Path**|The path and name of the folder where you want to store the EHF files for finance charge memos.|  

1. Choose the **OK** button.  

## Set up EHF file locations for service management  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Service Mgt. Setup**, and then choose the related link.  
1. On the **Service Mgt. Setup** page, on the **E-Invoice** FastTab, in the **Output Paths** section, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**E-Invoice Service Invoice Path**|The path and name of the folder where you want to store the EHF files for service invoices.|  
    |**E-Invoice Serv. Cr. Memo Path**|The path and name of the folder where you want to store the EHF files for service credit memos.|  

1. Choose the **OK** button.  

## Related information

- [Set Up Customers for EHF](how-to-set-up-customers-for-ehf.md)
- [EHF Electronic Invoicing in Norway](ehf-electronic-invoicing-in-norway.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
