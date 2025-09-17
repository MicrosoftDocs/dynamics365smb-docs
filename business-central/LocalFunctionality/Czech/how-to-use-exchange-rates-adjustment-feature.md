---
title: Czech local functionality - Exchange rates adjustment feature 
description: Companies in the Czech Republic request some improvements in the Exchange Rates Adjustment feature in the Czech version of Business Central.
author: v-pejano
ms-service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 06/04/2025
ms.reviewer: v-soumramani
ms.author: v-pejano
---

# Exchange rates adjustment feature (recalculation of receivables and payables)

Most companies in the Czech Republic request the following improvements to be implemented in Exchange Rates Adjustment:

- Ability to run Exchange Rates Adjustment for Customers, Vendors, and Bank Accounts separately
- Ability to have Exchange Rates Adjustment batch post adjustments in detail and summarized per currency
- Ability to run Exchange Rates Adjustment just as simulation (without posting) in Test Mode

On standard report Adjust Exchange Rates is now possible to:

- Set Bank Account, Customer, Vendor filter for adjustment
- Choose adjustment for Customer or Vendor or Bank Account
- Choose the test mode
- Choose to summarize entries
- Choose the method for dimensions transfer

The Adjust Exchange Rate report feature also modifies the calculation principle for implemented gains and losses based on the Income Tax Act. This feature calculates the implemented gain or loss against the recently adjusted amount.

This feature in the standard version of Microsoft [!INCLUDE[d365fin](../../includes/d365fin_long_md.md)] reverses the unrealized gain or loss first, and calculates the realized gain or loss afterwards. The calculation is made against the amount in the original exchange rate during the application of the payment and the invoice.

The new calculation principle handles deviations from the currently adjusted exchange rate.
The Adjust Exchange Rates batch job was extended to include the Czech Advance Payments module.

## Related information

- [Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
