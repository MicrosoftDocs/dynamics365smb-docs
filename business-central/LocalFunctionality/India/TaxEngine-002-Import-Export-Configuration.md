---
title: Tax Engine - Import/Export Configuration
description: Tax Engine - Import/Export Configuration
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, tax engine, tax engine configuration, json exchange
ms.date: 06/26/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Tax engine - Import/Export configuration

Json Exchange extension is used to import or export the configuration data of tax engine in json format.

There are two options available for importing and exporting tax configuration:

- **Import or Export from Tax Type**

This option is used when all configuration pertaining to a tax type is to be imported or exported. It contains entities, components, input parameter, rate setup, and use cases.

- **Import or Export for a specific Use Case**

This option is used when configuration pertaining to one or more-use cases is to be imported or exported. It contains use case related information.

- **Importing Use Cases in a new company**

When a new company is created, use cases are required to be imported. Following are the steps to import the use cases in a new company.

1. Go to **Setting** > **Assisted Setup** > **Setup Tax Engine**, a **Tax Engine Setup** wizard opens.
1. Select **Append** and select **Next**.
1. Select **Finish**. System imports all the preconfigured use cases from the configuration file in the new company.

## Related information

[Tax Engine Configuration of Tax Type and Tax Rate](TaxEngine-003-Tax-Configuration.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
