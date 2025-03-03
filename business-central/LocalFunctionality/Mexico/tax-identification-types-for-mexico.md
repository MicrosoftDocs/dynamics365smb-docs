---
title: Tax Identification Types for Mexico
description: All customers and vendors must have a federal tax identification number. This article covers the tax identification types in the Mexican version.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: federal tax identification number, tax identification number
ms.date: 02/26/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Tax identification types for Mexico

All customers and vendors must have a federal tax identification number. The identification type used for a customer or vendor depends on whether the customer or vendor is classified as a company or as a person.  

## Available tax identification types

In Mexico, a legal entity, such as a company or a person, is assigned a tax identification number according to two types.  

### Registro Federal de Contribuyentes (RFC)  

This tax identification type can be applied to companies and to people. An RFC number for a company is 12 characters, while an RFC number for a person is 13 characters.  

### Cédula de identification fiscal con clave única de registro de población (CURP)

This tax identification type can only be applied to people. A CURP number is 18 characters.  

When you create a new customer or vendor in [!INCLUDE[prod_short](../../includes/prod_short.md)], you specify whether the customer or vendor is a company or a person, and then you specify the tax identification type. The tax identification type and the tax identification number are included in any reports that reference tax information about a customer or vendor.  

## Related information

[Mexico Local Functionality](mexico-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
