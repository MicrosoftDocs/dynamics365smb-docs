---
title: Banking Documents Localization for Czech (Extension) 
description: Learn about the features and functionality of the Banking Documents Localization extension for the Czech Republic in Business Central.
author: v-pejano
ms.topic: concept-article
ms.search.keywords: Czech, Finance, Banking, Localization
ms.date: 03/30/2026
ms.reviewer: v-soumramani
ms.author: v-jurxova
---

# Banking documents localization for Czech (extension)

Provides functionality for Banking Documents in [!INCLUDE[prod_short](../../includes/prod_short.md)] for the Czech Republic.

**Banking Documents** app allows you to create **Payment Orders** and **Bank Statements** documents in a form that respects local practices. You can use an unlimited number of bank accounts of various banking institutions and in different currencies. You can import and export bank files from/to the banking software.

This feature provides improved efficiency and prevents users from making mistakes when entering the customer and vendor bank account data by capturing the bank specific information and eliminating the need to re-enter it every time.

**The extension provides the following key features**:

- Create, issue, and export a payment order
- Create, import, and issue a bank statement
- Bank statement rollover into a payment journal
- Pairing entries in the payment journal and posting

**Transfer journal line description to bank statements**:

The **Keep Description** field has been added to the Bank Account Card page with the following attributes:

- The field is also available on the request page of the Create General Journal report.
- The default value on the report is inherited from the selected bank account.
- When you run the report, the value of Keep Description is transferred to the corresponding field on related payment journal lines.
- If you turn off the Keep Description field and change the account on a journal line, the description updates based on the validation of the new account.

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  
