---
title: Tax Identification Types for Mexico
description: All customers and vendors must have a federal tax identification number. This article covers the tax identification types in the Mexican version.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: federal tax identification number, tax identification number
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Tax identification types for Mexico

All customers and vendors must have a federal tax identification number. The identification type used for a customer or vendor depends on whether the customer or vendor is classified as a company or as a person.  

## Available tax identification types

In Mexico, a legal entity, such as a company or a person, is assigned a tax identification number according to two types.  

### Registro Federal de Contribuyentes (RFC)  

This tax identification type can be applied to companies and to people. An RFC number for a company is 12 characters, while an RFC number for a person is 13 characters.  

### Clave Única de Registro de Población (CURP)

This tax identification type can only be applied to people. A CURP number is 18 characters.  

On the **Customer Card** or **Vendor Card**, set **Tax Identification Type** to **Legal Entity** for a company or **Natural Person** for a person. Then fill in **RFC No.** with 12 or 13 characters, respectively. If you enter a CURP number, the **CURP No.** field must contain 18 characters.

For your own company, use the **RFC Number** field on **Company Information**. This field also supports 12-character and 13-character RFC numbers.

## Related information

[Mexico Local Functionality](mexico-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
