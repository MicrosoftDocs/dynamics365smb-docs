---
title: Tax Engine - Import/Export Configuration
description: Tax Engine - Import/Export Configuration
author: v-debapd

    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf
   
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Tax Engine - Import/Export Configuration


Json Exchange extension is used to import or export the configuration data of tax engine in json format.

There are two options available for importing and exporting tax configuration:

- **Import or Export from Tax Type**

This option is used when all configuration pertaining to a tax type is to be imported or exported. It contains entities, components, input parameter, rate setup and use cases.

- **Import or Export for a specific Use Case**

This option is used when configuration pertaining to one or more-use cases is to be imported or exported. It contains use case related information.

- **Importing Use Cases in a new company**

When a new company is created, use cases are required to be imported. Following are the steps to import the use cases in a new company.
1. Go to **Setting** -> **Assisted Setup** -> **Setup Tax Engine**, a **Tax Engine Setup** wizard will be opened.
2. Select **Append** and click on **Next**.
3. Click on **Finish**. System will import all the pre-configured use cases from the configuration file in the new company.


## Related information  
 [Tax Engine Configuration of Tax Type and Tax Rate](TaxEngine-003-Tax-Configuration.md)












































[!INCLUDE[footer-include](../../includes/footer-banner.md)]
