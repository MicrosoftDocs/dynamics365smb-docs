---
title: Prepare for VAT Transactions Reports in the Italian Version [IT]
description: Learn how to prepare and submit periodic VAT Transactions reports to the Italian tax authorities, including setup steps and required information. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT transaction reports, periodic VAT transaction reports, VAT transaction amount, Italian version
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Prepare for VAT transactions reports in the Italian version

Before you use the VAT Transactions Report, set up the threshold amounts and the customer details that the report requires. Use the thresholds and reporting requirements that apply to the period you're reporting.

## Set up VAT transaction amounts  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Posting Setup**, and then choose the related link.  
1. Choose the **VAT Transaction Report Amount** action.  
1. Enter a **Starting Date**, **Threshold Amount Incl. VAT**, and **Threshold Amount Excl. VAT**. The starting date determines when the thresholds apply. The amount excluding VAT can't exceed the amount including VAT.
1. Return to **VAT Posting Setup**, and select **Include in VAT Transac. Rep.** for the combinations that must be included.

## Set up customer details

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Customers**, and then choose the related link.
1. Open the customer card.
1. Fill in the fields as described in the following table.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|  
    |**Individual Person**|Select if this customer is an individual person.|  
    |**Resident**|Specify whether the customer is resident in Italy.|  
    |**First Name**|Specifies the first name of the person.|  
    |**Last Name**|Specifies the last name of the person.|  
    |**Date of Birth**|Specifies the date of birth of the person.|  
    |**Place of Birth**|Specifies the place of birth of the person.|  

1. If the customer uses a tax representative, specify the representative as described in the next procedure.

    > [!NOTE]  
    > The following procedure uses a contact as the tax representative. Create the contact before you select it.

### Specify a tax representative for a nonresident customer

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Customers**, and then choose the related link.  
1. Open the customer card, and fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Tax Representative Type**|Specifies whether the representative is a customer or a contact. For this procedure, select **Contact**.|
    |**Tax Representative No.**|Specify the contact that is the tax representative for this customer.|  

Before you create the first VAT transaction report, prepare the existing data. Learn more in [Update VAT Transactions Data](how-to-update-vat-transactions-data.md). You can then create VAT transaction reports. Learn more in [Create Electronic VAT Transactions Reports](how-to-create-electronic-vat-transactions-reports.md).

## Related information

- [Update VAT Transactions Data](how-to-update-vat-transactions-data.md)   
- [Create Electronic VAT Transactions Reports](how-to-create-electronic-vat-transactions-reports.md)
- [Italian VAT](italian-vat.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
