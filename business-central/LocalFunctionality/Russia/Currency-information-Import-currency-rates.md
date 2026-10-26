---
title: Currency information in Russia
description: Russian localization provides features for importing currency rates in Business Central.
author: DianaMalina
ms.topic: article
ms.search.keywords: currency information, currency rates, import currency rates, import currencies, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Currency information and import currency rates

Local currency information for printing forms is specified in **General Ledger Setup**.

Used fields on the **General tab**:

- LCY Code
- Local currency description

## Import currencies

Go to **Company information**. Fill fields:

| Field | Description |
|--|--|
| **Import Curr. Exch. Rates** | Specifies if it's possible to run the Import Currency Exch. Rate batch job. |
| **Import Conflict Resolution** | Specifies what happens if a user runs the Import Currency Exch. rate batch job and there are conflicting exchange rates.|

Go to **Currency**. Оn the **General tab** fill fields for each currency:

| Field | Description |
|--|--|
| **Import** | Specifies if the currency has an imported exchange rate. |
| **Ru Bank Code** | Specifies the Russian bank code associated with the currency. |
| **Ru Bank Digital Code** | Specifies the Russian bank digital code associated with the currency. |

### Import currency rates

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Import Currency Exch. Rate**, and then choose the related link.
1. Enter the **Start Date** and **End Date** of the period for which you want to import exchange rates. Both dates are required. The end date can't be earlier than the start date.
1. Choose **OK**.

The batch job imports rates for all companies that have **Import Curr. Exch. Rates** selected. Within each company, it processes currencies that have **Import** selected and requires a **RU Bank Code**. The **Import Conflict Resolution** setting controls whether existing rates are replaced.

## Related information

- [Adjust Exchange Rates](Adjust-Exchange-Rates.md)  
- [Russia Local Functionality](russia-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
