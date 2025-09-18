---
title: Czech local functionality - Two steps fixed asset acquisition | Microsoft Docs
description: Learn how to acquire a fixed asset in Czech accounting using a two-step process involving acquisition and put-to-use actions.
author: v-pejano
ms-service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Fixed Asset, Localization, CZ
ms.date: 06/05/2025
ms.reviewer: v-soumramani
ms.author: v-pejano
---

# Two-step fixed asset acquisition

There are two steps to accomplish when acquiring a fixed asset in Czech accounting. When a company gets an invoice for a fixed asset acquisition, it must be posted. Since the initial use of the fixed asset, the used fixed asset is posted. Both the acquisition and put-to-use steps are required and connected with G/L entries. Fixed assets aren't depreciated until they're put to use.

For this process, use the **Custom 2** fixed asset posting type for the first step (acquisition) and **Acquisition** fixed asset posting type for the second step (put to use). Select the **Fixed Asset Acquisition as Custom2** check box on the **Fixed Asset Setup** page to start using this feature.

The value **Custom 2** is renamed in Czech language from "Vlastní 2" to "Pořízení" for correct FA purchase identification and better accountant understanding.

## Related information

- [Fixed Asset Localization for Czech (Extension)](ui-extensions-fixed-asset-localization-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  
