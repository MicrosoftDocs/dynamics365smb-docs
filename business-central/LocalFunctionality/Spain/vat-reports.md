---
title: VAT Reports [ES]
description: Provides detailed information about VAT functionality for transactions involving goods and services in Spain, including imports.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: VAT functionality, VAT reports, equivalence charge, EC percentage, telematic VAT, VAT-VIES declaration, VAT statement, Spanish version
ms.date: 05/29/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# VAT reports in the Spanish version

VAT is charged on transactions that involve goods and services in Spain or goods imported into Spain. The following information provides more details about VAT functionality.  

## Equivalence charge

Equivalence Charge (EC) tax applies to activities that don't follow VAT rules. According to EC rules, companies must pay a surcharge to their vendors in addition to VAT. However, they can only charge VAT without the surcharge on sales invoices.  

### VAT with EC percentage

Preset general posting groups have an EC percentage in addition to their VAT percentage. Although the EC is tracked separately, both tax values are merged with VAT when it's possible. If the EC percentage is a separate field in the posting group, the EC is merged with the value in the **VAT %** column.  

For printing sales and purchase invoice books, the VAT percent and EC percentages are displayed in the **VAT Entry** table during posting.  

> [!NOTE]  
> If the item has no taxable VAT, 0 is automatically displayed in the **VAT %** field in the VAT information pages.  

### Telematic VAT

With telematic VAT, you can design and generate monthly and yearly tax reports as electronic files or printed files. You can submit these reports to the tax authorities using a third-party program or an XML file from the tax authorities' website.  

### VAT statement

The VAT statement displays VAT amounts and base amounts in different columns.  

There are two report template types in the **VAT Statement Name** table:  

- **One-Column Report**  
- **Two-Columns Report**  

### VAT-VIES declaration

You can report VAT on sales to other countries/regions in the European Union (EU). Learn more in [Report VAT to Tax Authorities](../../finance-how-report-vat.md).  

[!INCLUDE [finance-ecsaleslist](../../includes/finance-ecsaleslist.md)]

## Related information

- [Spain Local Functionality](spain-local-functionality.md)  
- [Report 340](report-340.md)  
- [Report 347](report-347.md)  
- [Report VAT to Tax Authorities](../../finance-how-report-vat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
