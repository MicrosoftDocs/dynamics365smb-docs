---
title: Docket Reports [NL]
description: The Dutch telebanking app lets you combine ledger entries for a customer or vendor into a single payment or collection order to the bank.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: Dutch telebanking, combine ledger entries, single payment, collection order, docket report, same transaction mode, Dutch version, Netherlands
ms.date: 03/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Docket reports in the Dutch version

The Dutch telebanking application allows you to combine ledger entries for the same customer or vendor, having the same transaction mode, into one payment or collection order to the bank. As such one total amount is paid to or collected from the vendor or customer involved. Possibly this combined payment could lack all detail information about the individual payments or collections. Telebanking offers you the possibility to inform your vendor or customer in detail by generating a docket report that describes the individual payments that constitute the total amount paid or collected.  

When generating payment proposals using the **Get Proposal Entries** batch job the system selects the **Docket** checkbox on the proposal in case that:  

- The resulting combined payment includes too many invoice numbers to list them in the available four description fields of the new proposal line: **Description 1** field, **Description 2** field, **Description 3** field, and **Description 4** field.  
- The payment isn't based upon an invoice.  

## Related information

[Telebanking](telebanking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
