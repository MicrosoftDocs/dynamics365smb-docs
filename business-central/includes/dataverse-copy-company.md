---
author: brentholtorf
ms.topic: include
ms.date: 03/08/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

> [!NOTE]
> When you copy a company in an environment where Dataverse or Sales integration is enabled, [!INCLUDE [prod_short](prod_short.md)] clears the following settings while copying to the target company:
>
> * Dataverse and Dynamics Connection Settings to ensure that integration correctly re-initiates in the target company.
> * Integration records to ensure that the target company doesn't point to records that are coupled in the source company.
> * Integration synchronization jobs to stop synchronization background jobs.
> * Synchronization errors, if they exist, because they point to errors in the source company and would just be considered noise in the target company.
