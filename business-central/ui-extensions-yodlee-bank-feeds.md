---
title: Payment Reconciliation With the Envestnet Yodlee Bank Feeds Extension | Microsoft Docs
description: Describes the Envestnet Yodlee Bank Feeds extension, which links to bank accounts so you can and quickly reconcile payments.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: app, add-in, manifest, customize, stream, bank account link
ms.date: 04/01/2020
ms.author: sgroespe

---
# The Envestnet Yodlee Bank Feeds Extension
To quickly reconcile payments made to your bank accounts, the Envestnet Yodlee Bank Feeds service allows you to link your system bank account to your online bank account. This means that the latest bank statement is automatically or manually fed into your reconciliation journal, ensuring that you are always processing the latest payments with minimal risk of errors.

The Envestnet Yodlee Bank Feeds service is only supported in the United States and Canada.

> [!NOTE]
> The Envestnet Yodlee Bank Feeds service is only supported in the online version of Business Central. To use this functionality on-premises, you must obtain a cobrand account from Envestnet Yodlee.<br /><br />
> The Envestnet Yodlee Bank Feeds service is only supported in the United States and Canada.
> Only banks residing in these countries are supported, even though banks from other countries may appear in the Envestnet Yodlee Bank Feeds bank selection window in [!INCLUDE[d365fin](includes/d365fin_md.md)].

> [!IMPORTANT]
> Due to the new Payment Services Directive in Europe (PSD2), after September 14, 2019, you will no longer be able to automatically import bank statements from banks in the United Kingdom into [!INCLUDE[d365fin](includes/d365fin_md.md)]. We are looking into the possibility of offering this feature again in the future.

The Envestnet Yodlee Bank Feeds service provides the following benefits:

* Removes the need for manual entry.
* Improves efficiency and accuracy when doing payment reconciliation.
* Supports a large number of banks.
* Allows up-to-date information about bank transactions from within [!INCLUDE[d365fin](includes/d365fin_md.md)].
* Supports manual as well as automatic bank feeds.
* Enables outsourcing of payment reconciliation to an accountant by providing access to bank statements.

For more information, see [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).

## See Also
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions ](ui-extensions.md)    
[Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
