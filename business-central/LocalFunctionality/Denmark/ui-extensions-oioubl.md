---
title: OIOUBL Extension for Electronic Invoicing
description: The OIOUBL extension simplifies the process of sending sales documents electronically to customers in the Danish public sector using the OIOUBL format.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: OIOUBL, public sector, electronic invoicing, sales documents, Denmark
ms.search.form: 13645, 13646, 13647
ms.date: 04/24/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# The OIOUBL extension for electronic invoicing in Denmark

When you sell goods or services to customers in the Danish public sector, you must submit documents to the customer electronically in an XML file that is structured to meet the requirements of one or more Offentlig Information Online - Universal Business Language (OIOUBL) profiles.  

The OIOUBL extension in [!INCLUDE[prod_short](../../includes/prod_short.md)] makes it easy to generate these XML documents for posted sales and service invoices, credit memos, and issued reminders (which include finance charge memos).  

The current requirements for sending electronic invoices are based on UBL version 2.0 standard. Learn more in the [OIOUBL](https://aka.ms/OasisUblSite) website.

Learn more in the website for [Online OIOUBL Documentation](http://www.oioubl.info/classes/da/index.html) and the [Digitaliseringsstyrelsen](https://digst.dk/) website, which provide general information about OIOUBL.

## Getting started with the OIOUBL extension

By default, the OIOUBL extension is installed in [!INCLUDE[prod_short](../../includes/prod_short.md)]. However, there are a few things to do before you can use the extension:

- Set up payment methods, payment terms, and item charges.
- Set up customers for OIOUBL by specifying an account code, the OIOUBL profile to use to exchange documents, and the customer's Geographic Location Number (GLN).

Learn more in [Set Up the OIOUBL Extension](how-to-set-up-oioubl.md).  

## Related information

- [Denmark Local Functionality](denmark-local-functionality.md)  
- [Set Up the OIOUBL Extension](how-to-set-up-oioubl.md)  
- [Create Electronic Documents in an OIOUBL Format](how-to-create-electronic-documents-by-using-oioubl.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
