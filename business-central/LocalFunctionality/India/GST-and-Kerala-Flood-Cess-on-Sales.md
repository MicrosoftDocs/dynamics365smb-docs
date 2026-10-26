---
title: GST and Kerala Flood Cess on Sales Transaction
description: Review the historical Kerala Flood Cess sales example and its GST accounting context in Business Central for India, without treating old rates as current.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, Kerala flood cess, create sales invoice
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# GST and Kerala Flood Cess on sales transaction

> [!IMPORTANT]
> Because Kerala Flood CESS (KFC) is no longer applicable, the content in this article is no longer needed and will be removed in the coming months.

The following historical example describes Kerala Flood Cess on intrastate supplies to an unregistered customer, or B2C supplies. The cess was shown separately on the invoice. The example doesn't describe a current tax requirement.

## Create a sales invoice

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Sales Invoices**, and then choose the related link.
1. Select **Customer** on **Sales Invoice** header, GST customer type should be **Unregistered**.
1. Select **Item Code** for goods or **G/L Account** for service sales on **Sales Invoice** line. GST Group Code, HSN/SAC Code shouldn't be blank on **Item** or **G/L Account**.

For example, there's a sales invoice for INR 10,000 and 18% GST (that is, 9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction) and 1% Kerala Flood Cess has to be charged on the invoice amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**KFC**|100|

- On posting the sales invoice for Intra-State or Intra-Union Territory sale of goods to unregistered customer, GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|11900|
    |**SGST/UTGST Payable Account**|-900|
    |**CGST Payable Account**|-900|
    |**Kerala Flood Cess**|-100|
    |**Sales Account**|-10000|

> [!TIP]
> System automatically updates 'Nature of Supply' B2C for Unregistered Customer.

## Related information

[Exempted Sales](GST-Exempted-Sales.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
