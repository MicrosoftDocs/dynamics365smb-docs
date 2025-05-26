---
title: VAT Reports [ES]
description: VAT is charged on transactions involving goods and services in Spain or goods imported into Spain. The following provides details about VAT functionality.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.date: 06/21/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# VAT Reports in the Spanish Version
VAT is charged on transactions that involve goods and services in Spain or goods imported into Spain. The following information provides more details about VAT functionality.  

## Equivalence Charge  
Equivalence Charge (EC) tax applies to activities that do not follow VAT rules. According to EC rules, companies must pay a surcharge to their vendors in addition to VAT. However, they can only charge VAT without the surcharge on sales invoices.  

### VAT with EC Percentage  
Preset general posting groups have an EC percentage in addition to their VAT percentage. Although the EC is tracked separately, both tax values are merged with VAT when it is possible. If the EC percentage is a separate field in the posting group, the EC is merged with the value in the **VAT %** column.  

For printing sales and purchase invoice books, the VAT percent and EC percentages are displayed in the **VAT Entry** table during posting.  

> [!NOTE]  
>  If the item has no taxable VAT, 0 is automatically displayed in the **VAT %** field in the VAT information pages.  

### Telematic VAT  
With telematic VAT you can design and generate monthly and yearly tax reports as electronic files or printed files. You can submit these reports to the tax authorities using a third-party program or an XML file from the tax authorities' website.  

### VAT Statement  
The VAT statement displays VAT amounts and base amounts in different columns.  

There are two report template types in the **VAT Statement Name** table:  

- **One-Column Report**  
- **Two-Columns Report**  

### VAT-VIES Declaration

You can report VAT on sales to other countries/regions in the European Union (EU). For more information, see [Report VAT to Tax Authorities](../../finance-how-report-vat.md).  

[!INCLUDE [finance-ecsaleslist](../../includes/finance-ecsaleslist.md)]

## Related information

[Spain Local Functionality](spain-local-functionality.md)  
[Report 340](report-340.md)  
[Report 347](report-347.md)  
[Report VAT to Tax Authorities](../../finance-how-report-vat.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
