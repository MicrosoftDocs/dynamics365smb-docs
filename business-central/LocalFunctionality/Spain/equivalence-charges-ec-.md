---
title: Equivalence Charges (EC) [ES]
description: An Equivalence Charge (EC) is a tax that is used in retail sales and in activities that don't follow VAT rules. 
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.date: 11/14/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Equivalence Charges (EC) in the Spanish version
An Equivalence Charge (EC) is a tax that is used in retail sales and in activities that don't follow VAT rules. Under EC rules, companies must pay a surcharge to their vendors when purchasing goods, in addition to the usual VAT. However, when selling goods, only VAT can be charged. Some general posting groups must have an EC percentage in addition to the VAT percentage. This information is tracked separately, but in order to minimize changes, both taxes are combined.  

The **EC %** field is a separate field in the **Purchase Line**, **Sales Line**, **Sales Line Archive** and **Purchase Line Archive** tables. However, in sales and purchase lines, both taxes are combined and the value is displayed in the **VAT %** field. The **VAT + EC %** field is used when these values are combined. At the time of posting, the VAT percentage and the EC percentage are inserted in the **VAT Entry** table. This makes it possible to print the **Sales Invoice Book** report and the **Purchases Invoice Book** report.  

## Related information  
[Spain Local Functionality](spain-local-functionality.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
