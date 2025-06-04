---
title: Functional Currency – Czechia
description: This document explains the concept of functional currency and its application in Business Central.
author: v-pejano
ms.author: v-pejano
ms.reviewer: solsen
ms.search.keywords: CZ, Czech, Currency, Finance, Accounting, Functional Currency, Exchange Rates
ms.topic: article
ms.date: 08/28/2024
ms.search.form: 118
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Functional Currency – Czechia

The new amendment to Act No. 563/1991 Coll., on Accounting, effective from 1 January 2024, introduces the concept of functional currency as the currency of accounting. Functional currency means the currency of the primary economic environment in which the entity operates and may be other than the Czech currency. The functional currency of an entity shall be determined on the basis of the criteria for determining the functional currency under IFRS as governed by European Union law.  

If the company decides to implement accounting in a foreign currency, then for other records and reports that must be in Czech currency, it uses the Additional Reporting Currencies functionality for reporting. However, this only deals with the creation of material items and VAT items, but not with subsequent reporting. All VAT reporting must be done in Czech currency (CZK), so the reporting functionalities have been adapted as follows:

- Preview of the VAT statement
- VAT control report
- VAT control report statistics
- VIES Declaration
- Export of the VAT statement
- Export of VAT control report
- Export of the VIES Declaration
- Printing the VAT statement (Report 11769)
- Printing of the Recording Obligation (Basis for VAT) and List of Tax Documents (Report 11756)
- Test report of the VAT Control Report (Report 31103)
- Test report of the VIES Declaration (Report 31064)

New VAT rate to additional reporting currency (Document Currency/Additional Reporting Currency) fields have been added to the purchase and sales documents to allow the currency rate to be adjusted if necessary. Similar functionality has been added on purchase and sales advances. The printing of document reports has also been modified.

## Related information

[Core localization pack for Czech](ui-extensions-core-localization-pack-cz.md)  
[Czech local functionality](czech-local-functionality.md)  
[Finance](../../finance.md)  

## [!INCLUDE[prod_short](../../includes/free_trial_md.md)]  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
