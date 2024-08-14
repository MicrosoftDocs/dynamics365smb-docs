---
title: First steps 
description: Learn how to start with usage based billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# First steps

First, a **Usage Data Supplier** is set up and a matching import schema for related usage data is created via the **<a href="https://learn.microsoft.com/en-us/dynamics365/business-central/across-how-to-set-up-data-exchange-definitions" title="Data Exchange Definitions">Data Exchange Definitions</a>**. This will be linked to the **Usage Data Supplier**.

Afterwards, a new **Usage Data Import** is created for the supplier, in which the usage data (in the form of reconciliation files) is imported.

The imported data is processed. If an error occurs (e.g. because new usage data not previously known to the system is included in the import), the reasons for the non-processing can be corrected and the processing restarted.

The final step is to create the related Contract Invoices. This can be done as a batch processing.


## Graphic illustration
![](/img/ubb/ProcessOverview.png)