---
title: The Troubleshooting FA Ledger Entries Extension
description: Use the FA Ledger Entries extension to round fixed-asset ledger amounts to whole numbers for easier reconciliation and reporting.
documentationcenter: ''
author: brentholtorf
ms.topic: troubleshooting-general
ms.devlang: al
ms.search.keywords: machinery, buildings, troubleshooting fixed assets
ms.date: 08/07/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Troubleshooting FA Ledger Entries extension

Use the Troubleshooting FA Ledger Entries extension to round depreciation and acquisition amounts in fixed asset ledger entries to whole numbers. For example, to round an amount of 30,000.44 to 30,000. Typical causes of rounding issues are data migration, suddenly starting to post amounts to the general ledger, or customizations you've made to your [!INCLUDE[prod_short](includes/prod_short.md)].

The Troubleshooting FA Ledger Entries extension is preinstalled and ready to go. If you remove the extension, but want to install it again, you can find it on AppSource.

## Troubleshooting fixed asset ledger entries

When you open the **Fixed Asset Card** page for the first time, the **FA Ledger Entries Scan** job queue entry is scheduled to monitor amounts every Sunday. If it finds amounts that you might want to round, a notification will display the next time you open the Fixed Asset Card page. The notification provides a **See more** option that opens the **FA Ledger Entries with Rounding Issues** page, which lists the entries with amounts that you might want to round. To round the amounts, choose the entries, and then choose the **Accept Selection** action. You can use the **Find entries with issues** action to update the list with new issues that occurred after the job queue entry ran on the previous Sunday.

## Related information

- [Fixed Assets](fa-manage.md)  
- [Managing Fixed Assets](fa-manage.md)  
- [Maintain Fixed Assets](fa-how-maintain.md)  
- [Customizing Business Central Online Using Extensions](ui-extensions.md)  
- [Finance](finance.md)  
- [Getting Ready for Doing Business](ui-get-ready-business.md)  
- [Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
