---
title: Service Transfer
description: Service Transfer
author: v-debapd  
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, service transfer
ms.date: 06/24/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Service transfer

Service transfers between locations, branches, or divisions having different registration numbers are taxable under GST. In such a case, if services transferred within the state from one location to another, then CGST and SGST/UTGST is levied, otherwise, where the registration number is same, there shall be no levy. Service transferred from one state to another state, then IGST is levied.

## Create a service transfer order

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Service Transfer Order**, and then choose the related link. 
1. Select **Transfer-from Code** and **Transfer-to Code** on **Service Transfer Order** header. State Code and GST registration number shouldn't be blank on **Location** card.
1. Select **Ship Control Account** and **Receive Control Account** on **Service Transfer Order** header.
1. Select G/L Account for **Transfer From G/L Account No.** on **Shipment Line** and **Transfer To G/L Account No.** on **Receipt Line**. GST Group Code, HSN/SAC Code shouldn't be blank on **G/L Account** card.

For example, service for INR 10000 is being transferred on which 18% GST (9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction), has to be charged.

- GST Calculation on Service Transfer Order appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10000|  
    |**IGST**|1800|
    |**CGST**|900|
    |**SGST**|900|

- On posting of shipment in case of Intra-State or Intra-Union Territory service transfer, GL Entries is as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Inter-location Control Account**|11800|
    |**CGST Payable Account**|-900|
    |**SGST/UTGST Payable Account**|-900|
    |**Services Account**|-10000|

- On posting of receipt in case of Intra-State or Intra-Union Territory service transfer, GL Entries is as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|10000|  
    |**SGST/UTGST Receivable Account**|900|  
    |**CGST Receivable Account**|900|
    |**Inter-location Control Account**|-11800|

- On posting of shipment in case of Interstate service transfer, GL Entries is as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Inter-location Control Account**|11800|
    |**IGST Payable Account**|-1800|
    |**Services Account**|-10000|

- On posting of receipt in case of Interstate service transfer, GL Entries is as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|10000|
    |**IGST Receivable Account**|1800|
    |**Inter-location Control Account**|-11800|

## Related information

[GST Stock Transfer](GST-Stock-Transfer.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
