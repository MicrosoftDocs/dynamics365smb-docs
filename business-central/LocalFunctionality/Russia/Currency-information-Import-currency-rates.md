---
title: Currency information in Russia
description: Russian enhancements include currency information for importing currency rates.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Currency information, Import currency rates

Local currency information for printing forms is specified in **General Ledger Setup**.

Used fields on the **General tab**:

- LCY Code
- Local currency description

### Import currencies

Go to **Company information**. Fill fields:

| Field                          | Description                                                  |
| ------------------------------ | ------------------------------------------------------------ |
| **Import Curr. Exch. Rates**   | Specifies if it is possible to run the Import Currency Exch. Rate batch job. |
| **Import Conflict Resolution** | Specifies what will happen if a user runs the Import Currency Exch. rate batch job and there are conflicting exchange rates. |

Go to **Currency**. Оn the **General tab** fill fields for each currency:

| Field                    | Description                                                  |
| ------------------------ | ------------------------------------------------------------ |
| **Import**               | Specifies if the currency has an imported exchange rate.     |
| **Ru Bank Code**         | Specifies the Russian bank code associated with the currency. |
| **Ru Bank Digital Code** | Specifies the Russian bank digital code associated with the currency. |

##### Import currency rates:

1. Go to Departments -> Financial management -> Periodic activities -> Currency -> Import currency rates.

2. Enter the start and end dates of the period for which you want to adjust the exchange rates.

## See Also

[Adjust Exchange Rates](Adjust-Exchange-Rates.md)  
[Russia Local Functionality](russia-local-functionality.md)  
