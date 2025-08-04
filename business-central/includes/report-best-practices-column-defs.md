---
author: brentholtorf
ms.topic: include
ms.date: 04/05/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

Column definitions aren't versioned. When you change a column definition, the old version is replaced when your change saves to the database. The following list contains some best practices for working with column definitions.

- If you add a column definition, choose a good code and fill in the Description field with meaningful text while you still know what you use the column definition for. This information helps your coworkers (and your future self) work with financial reporting and perhaps changing the column definition.
- Use the **Where-Used** action to learn where a column definition is used before making any changes to it.
- Before you change a column definition, consider taking a copy of it as a backup, just in case your change doesn't work as expected. You can either just copy the definition (give it a good name), or export it. To learn more, go to [Import or export column definitions](#import-or-export-financial-report-column-definitions).
- If you need a fresh copy of a definition that [!INCLUDE [prod_short](prod_short.md)] provides, an easy way to get one is to create a new company that only contains setup data. Then, export the definition and import it in the company where the definition needs a refresh.