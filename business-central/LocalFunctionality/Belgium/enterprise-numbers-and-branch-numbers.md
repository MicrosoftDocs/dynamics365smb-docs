---
title: Enterprise Numbers and Branch Numbers [BE]
description: Companies receive a unique enterprise number and branch numbers by the Belgian Crossroad Bank of Enterprises.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: enterprise number, crossroads bank, VAT registration number, branch numbers, Belgian version
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

# Enterprise numbers and branch numbers in the Belgian version

Companies receive a unique enterprise number and one or more branch numbers from the Belgian [Crossroads Bank for Enterprises](https://economie.fgov.be/en/themes/enterprises/crossroads-bank-enterprises). These numbers are used in all correspondence to simplify communication with the Belgian administrative and legal authorities.  

## Enterprise numbers

The enterprise number replaces the existing VAT number. For existing companies with a VAT registration number, the enterprise number is set as the VAT registration number preceded by a leading zero. New companies receive a new enterprise number.  

An enterprise number consists of 10 digits. [!INCLUDE[prod_short](../../includes/prod_short.md)] validates the **Enterprise No.** field on the **Company Information** page using a modulo-97 check: the last two digits of the number must equal 97 minus the remainder of the first eight digits divided by 97. If the number doesn't pass this check, you get an error and can't save the field.  

The enterprise number is printed on the following documents:  

- Outgoing sales and purchase documents  
- Financial statements  
- Reminders and finance charge memos  
- Intrastat forms and files  

The enterprise number is set up in the following locations:  

- Company Information table  
- Contact card  
- Customer table  
- Vendor table  

## Branch numbers

A branch number is given to a company to identify an address where at least one of the company’s activities is exercised, for example, a workshop, office, warehouse, agency, or subsidiary. Unlike the enterprise number, there's no legal requirement to print the branch number.  

All branches of a company receive a unique number that is different from the enterprise number. The branch number is transferable to another company, such as after a merger or takeover. [!INCLUDE[prod_short](../../includes/prod_short.md)] validates the **Branch No.** field using the same modulo-97 check as the enterprise number.  

The branch number is set up in the following locations:  

- Company Information table  
- Location table  

## Related information

- [Belgium Local Functionality](belgium-local-functionality.md)
- [Crossroads Bank for Enterprises](https://economie.fgov.be/en/themes/enterprises/crossroads-bank-enterprises)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
